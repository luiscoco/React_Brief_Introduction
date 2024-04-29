# React_Brief_Introduction

Let's learn some basics of React, which is currently at version 18 as of my last update. React is a popular JavaScript library for building user interfaces, particularly for web applications. It allows developers to create reusable UI components.

## 1. Setting Up Your Environment

To work with React, you'll first need **Node.js** installed on your machine

Once you have Node.js, you can create a new React project using Create React App, a tool that sets up a new project with sensible defaults

```
npx create-react-app my-app
cd my-react-app
npm start
```

**To create a new React project** using Visual Studio Code (**VSCode**), you can follow these steps:

**Install Node.js and npm**: Make sure you have Node.js and npm installed on your computer. You can download and install them from nodejs.org

**Install Visual Studio Code**: If you don't have VSCode installed, download and install it from code.visualstudio.com

**Open Visual Studio Code**: Launch VSCode

**Open a Terminal in VSCode**: You can open a terminal by selecting Terminal > New Terminal from the top menu in VSCode. This opens an integrated terminal inside VSCode

**Create a new React project using Create React App**: In the terminal, run the following command to create a new React project. Replace my-app with your desired project name:

```
npx create-react-app my-app
```

This command uses npx (which comes with npm) to run the create-react-app command line utility that sets up a new React project

Navigate into your project directory: Change your current directory to the new project directory that was created:

```
cd my-app
```

Start the development server: Run the following command to start the development server:

```
npm start
```

This will compile your React application and open it in your default web browser. The development server will watch for any files you edit and automatically reload the page to reflect changes

Code your application: Your new React project is set up and running. You can now open the project folder in VSCode and start modifying the source code. Use the Explorer in VSCode to open files and make changes

These steps will get your new React project up and running in VSCode

This is the files and folders new project structure

![image](https://github.com/luiscoco/React_Brief_Introduction/assets/32194879/8e81b8b7-b226-4c5e-95d1-f7dfe23d2496)

Let's explain the workflow for a new application.

**index.html** -> **index.js** -> **App.js**

**index.html**

![image](https://github.com/luiscoco/React_Brief_Introduction/assets/32194879/1a857063-09f6-4ce8-9dca-50a45e64d0b0)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <meta name="theme-color" content="#000000" />
    <meta
      name="description"
      content="Web site created using create-react-app"
    />
    <link rel="apple-touch-icon" href="%PUBLIC_URL%/logo192.png" />
    <link rel="manifest" href="%PUBLIC_URL%/manifest.json" />
    <title>React App</title>
  </head>
  <body>
    <noscript>You need to enable JavaScript to run this app.</noscript>
    <div id="root"></div>
  </body>
</html>
```

**index.js**

```javascript
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

// If you want to start measuring performance in your app, pass a function
// to log results (for example: reportWebVitals(console.log))
// or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
reportWebVitals();
```

**App.js**

```javascript
import logo from './logo.svg';
import './App.css';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

export default App;
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
