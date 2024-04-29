# React_Brief_Introduction

Let's learn some basics of React, which is currently at version 18 as of my last update. React is a popular JavaScript library for building user interfaces, particularly for web applications. It allows developers to create reusable UI components.

## 1. Setting Up Your Environment

To work with React, you'll first need Node.js installed on your machine. Once you have Node.js, you can create a new React project using Create React App, a tool that sets up a new project with sensible defaults.

```
npx create-react-app my-react-app
cd my-react-app
npm start
```

## 2. Creating a Simple Component

React components can be created as functions. Here’s a simple component that displays a message:

```jsx
import React from 'react';

function Welcome() {
  return <h1>Hello, React!</h1>;
}

export default Welcome;
```

## 3. Using JSX

JSX is a syntax extension for JavaScript that looks similar to XML or HTML. It is used with React to describe what the UI should look like. Here's how you might use JSX to combine data and HTML structure:

```jsx
import React from 'react';

function UserGreeting(props) {
  return <h1>Welcome back, {props.name}!</h1>;
}

export default UserGreeting;
```

## 4. State and State Hook

State in React allows you to keep track of changes in data over time. Here's how to use the useState hook in a functional component:

```jsx
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}

export default Counter;
```

## 5. Effects and Effect Hook

The useEffect hook lets you perform side effects in function components. Here’s an example of using useEffect to update the document title:

```jsx
import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  // Similar to componentDidMount and componentDidUpdate:
  useEffect(() => {
    // Update the document title using the browser API
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}

export default Example;
```

## 6. Handling Events

React elements handle events similarly to handling events on DOM elements. Here's an example:

```jsx
import React from 'react';

function MyButton() {
  function handleClick() {
    alert('Button was clicked!');
  }

  return <button onClick={handleClick}>Click me!</button>;
}

export default MyButton;
```

## 7. Component Lifecycle

In class components, React lifecycle methods allow you to run code at specific points in a component's life, such as when it is created, updated, or destroyed. With hooks in functional components, these lifecycle behaviors are handled more abstractly but achieve similar results.

Mounting, Updating, and Unmounting: Lifecycle methods like componentDidMount, componentDidUpdate, and componentWillUnmount in class components or effects in hooks (useEffect) allow components to react to changes

## 8. Context API

React's Context API allows you to share values (like user authentication status or theme settings) across all levels of the application without passing props down manually through every level of the component tree

```jsx
import React, { useContext, createContext, useState } from 'react';

const ThemeContext = createContext();

function App() {
  const [theme, setTheme] = useState('dark');

  return (
    <ThemeContext.Provider value={{ theme, setTheme }}>
      <Toolbar />
    </ThemeContext.Provider>
  );
}

function Toolbar() {
  return (
    <div>
      <ThemedButton />
    </div>
  );
}

function ThemedButton() {
  const { theme, setTheme } = useContext(ThemeContext);

  return <button onClick={() => setTheme(theme === 'dark' ? 'light' : 'dark')}>
    Change to {theme === 'dark' ? 'light' : 'dark'} theme
  </button>;
}

export default App;
```

## 9. Hooks

Hooks are a feature introduced in React 16.8 that allow you to use state and other React features without writing a class. 

They make function components as powerful as class components:

**useState**: Lets you add state to function components

**useEffect**: Lets you perform side effects in function components

**useContext**: Lets you subscribe to React context without introducing nesting

**useReducer**: An alternative to useState that is preferable for managing complex state logic

**useMemo and useCallback**: Optimize performance by memoizing expensive functions

## 10. Fragments

React Fragments let you group a list of children without adding extra nodes to the DOM

```jsx
import React from 'react';

function Table() {
  return (
    <table>
      <tbody>
        <tr>
          <Columns />
        </tr>
      </tbody>
    </table>
  );
}

function Columns() {
  return (
    <>
      <td>Hello</td>
      <td>World</td>
    </>
  );
}

export default Table;
```

## 11. Higher Order Components (HOCs)

A higher-order component (HOC) is an advanced technique in React for reusing component logic

HOCs are not part of the React API, per se, but are a pattern that emerges from React’s compositional nature.

```jsx
import React from 'react';

function withLogging(WrappedComponent) {
  return class extends React.Component {
    componentDidMount() {
      console.log('Component did mount');
    }

    render() {
      return <WrappedComponent {...this.props} />;
    }
  };
}

// Use HOC
const MyComponentWithLogging = withLogging(MyComponent);
```

## 12. Portals

Portals provide a first-class way to render children into a DOM node that exists outside the DOM hierarchy of the parent component.

```jsx
import React from 'react';
import ReactDOM from 'react-dom';

function Modal({ children }) {
  return ReactDOM.createPortal(
    children,
    document.getElementById('modal-root')
  );
}

function App() {
  return (
    <div onClick={() => console.log('Clicked inside')}>
      <Modal>
        <div onClick={(e) => e.stopPropagation()}>
          Click me, I'm inside the modal!
        </div>
      </Modal>
    </div>
  );
}
```

These features are just the tip of the iceberg in React's capabilities. They can be combined in many ways to build complex, high-performing applications that scale well with your development needs.
