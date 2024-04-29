# React_Brief_Introduction

https://react.dev/learn

https://react.dev/reference/react

Let's learn some basics of React, which is currently at **version 18** as of my last update

React is a popular **JavaScript library** for building user interfaces, particularly for web applications

It allows developers to **create reusable UI components**

## 1. How to Set Up your environment and how to create a new React project with VSCode

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

![image](https://github.com/luiscoco/React_Brief_Introduction/assets/32194879/aeacb8a6-3d9d-451d-bbe3-cf725132e04f)

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

![image](https://github.com/luiscoco/React_Brief_Introduction/assets/32194879/eadc0e71-db8c-4a14-907f-24d0bbfa6a6c)

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

To create a new React component in your existing React application using Visual Studio Code (VSCode), follow these steps. I'll provide both the process for creating a class component and a functional component as examples.

### 2.1. Creating a Functional Component

Open Your Project in VSCode: Open the folder containing your React project in VSCode

Create a New File for Your Component:

Navigate to the appropriate directory within your project where you want to add the new component (commonly it would be inside a components folder if you have one)

Right-click on the folder in which you want to create the new component, select New File

Name the file with a capital letter (as per React convention), for example, **MyFunctionalComponent.js**

Write the Functional Component Code:

Open the new file you just created

Enter the following template for a basic functional component:

```javascript
import React from 'react';

function MyFunctionalComponent() {
  return (
    <div>
      Hello, this is my new component!
    </div>
  );
}

export default MyFunctionalComponent;
```

### 2.2. Creating a Class Component

Open Your Project in VSCode: Just like with the functional component, start by opening your React project in VSCode

Create a New File for Your Component:

Navigate to where you want this new class component within your project's structure

Right-click on the folder, select New File, and name it, e.g., **MyClassComponent.js**

Write the Class Component Code:

Open the newly created file.

Enter the following template for a basic class component:

```javascript
import React, { Component } from 'react';

class MyClassComponent extends Component {
  render() {
    return (
      <div>
        Hello, this is my class component!
      </div>
    );
  }
}

export default MyClassComponent;
```

### 2.3. Using Your New Component

After creating your new component, you can use it in your application by importing it into another component file. Here’s how you can do it:

Open the Component File where you want to use your newly created component (e.g., App.js)

**Import the Component at the top of the file**:

```javascript
import MyFunctionalComponent from './path/to/MyFunctionalComponent';
// or if it's a class component
import MyClassComponent from './path/to/MyClassComponent';
```

**Use the Component in your JSX**:

```javascript
function App() {
  return (
    <div>
      <MyFunctionalComponent />
      <MyClassComponent />
    </div>
  );
}
```

Save the file and if your development server is running, it should automatically reload and display your new components

These steps will help you efficiently create and integrate new React components into your application using VSCode

### 2.4. Differences between Functional and Class components

In React, you can define components either as **functional components** or **class components**, and the choice between them influences not only the **syntax** but also some of the **capabilities** and **behavior** of the components

Here are the main differences:

#### 2.4.1. Syntax and Definition

**Functional Components**: These are simpler and defined as JavaScript functions

They directly **return JSX**, which describes the UI

Since React 16.8, functional components can **use hooks** to manage **state** and **lifecycle events**, which were previously only available in class components:

```javascript
function MyComponent() {
  return <div>Hello, World!</div>;
}
```

**Class Components**: These are defined as **ES6 classes**

They extend **React.Component** and require at least the **render()** method, which returns JSX

They have more boilerplate compared to functional components but provide more explicit handling of lifecycle methods and state:

```javascript
class MyComponent extends React.Component {
  render() {
    return <div>Hello, World!</div>;
  }
}
```

#### 2.4.2. State and Lifecycle

**Functional Components (with Hooks)**: They use hooks like **useState** and **useEffect** to handle state and lifecycle events

This makes the component concise and easier to understand at a glance, particularly when the component grows in complexity

**Class Components**: They manage state using **this.state** and **this.setState**, and handle lifecycle processes in methods like **componentDidMount**, **componentDidUpdate**, and **componentWillUnmount**

#### 2.4.3. this Keyword

**Functional Components**: There is no this keyword in functional components

All functions and values are accessed directly

**Class Components**: You often need to bind event handlers to this or use arrow functions to ensure that this refers to the component instance

#### 2.4.4. Use Cases

**Functional Components**: Recommended for most components, especially after **hooks** were introduced, as they provide a more modern and straightforward way to write components with fewer lines of code and better performance optimizations

**Class Components**: Useful in more complex scenarios that may require more nuanced control over performance optimizations through **shouldComponentUpdate** or when the component needs to manage internal state in a more traditional way

#### 2.4.5. Optimization

**Functional Components**: Often lead to smaller bundle sizes and better performance due to simplifications in how React handles them

**Class Components**: Can sometimes lead to larger bundles and slower performance because they involve more complexity and overhead in their creation and destruction processes

#### 2.4.6. Conclusion

While both functional and class components are still supported in React, the introduction of hooks has largely swung the community and official recommendations towards **functional components**

They offer a cleaner and more efficient way to write components, manage state, and handle side effects

However, class components remain in use, particularly in older codebases or in complex scenarios where their explicit nature around lifecycle handling might be preferred

## 3. Using JSX

JSX is a syntax extension for JavaScript that looks similar to XML or HTML

It is used with React to describe what the UI should look like

Here's how you might use JSX to combine data and HTML structure:

```jsx
import React from 'react';

function UserGreeting(props) {
  return <h1>Welcome back, {props.name}!</h1>;
}

export default UserGreeting;
```

## 4. State and State Hook

State in React allows you to keep track of changes in data over time. Here's how to use the useState hook in a functional component:

### 4.1. Functional component

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

### 4.2. Class component

Here's how you would implement the same functionality using state in a class component in React

This example will demonstrate how to use the state within a class component to create a simple counter similar to your functional component example

```javascript
import React, { Component } from 'react';

class Counter extends Component {
  constructor(props) {
    super(props);
    // Initializing the state
    this.state = {
      count: 0
    };
  }

  // Method to increment the counter
  incrementCount = () => {
    this.setState({ count: this.state.count + 1 });
  };

  render() {
    return (
      <div>
        <p>You clicked {this.state.count} times</p>
        <button onClick={this.incrementCount}>
          Click me
        </button>
      </div>
    );
  }
}

export default Counter;
```

**Key Points**:

**Initialization**: The state is initialized in the constructor of the class component using this.state. Here, count is set to 0

**State Update**: The incrementCount method updates the state using this.setState(), which triggers a re-render of the component with the new state value

**Rendering**: In the render method, the current count is accessed using this.state.count and displayed. The button uses the incrementCount method to update the state every time it's clicked

This example demonstrates the traditional way of managing state in class components, contrasting with the use of the useState hook in functional components, which provides a more straightforward and cleaner API for handling state in newer React applications

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

In class components, React lifecycle methods allow you to run code at specific points in a component's life, such as when it is created, updated, or destroyed

With hooks in functional components, these lifecycle behaviors are handled more abstractly but achieve similar results

**Mounting, Updating, and Unmounting**: Lifecycle methods like componentDidMount, componentDidUpdate, and componentWillUnmount in class components or effects in hooks (useEffect) allow components to react to changes

Below are examples of how lifecycle events are managed in both class components and functional components using hooks in React

These examples will focus on the three main phases of a component's lifecycle: **Mounting, Updating, and Unmounting**

### 7.1. Class Component Lifecycle Methods

Here is an example of a class component that utilizes lifecycle methods:

```javascript
import React, { Component } from 'react';

class LifecycleExample extends Component {
  constructor(props) {
    super(props);
    this.state = { counter: 0 };
    console.log('Constructor: Component is initialized, not yet mounted.');
  }

  componentDidMount() {
    console.log('componentDidMount: Component has mounted');
    // Typically used for API calls to fetch initial data
  }

  componentDidUpdate(prevProps, prevState) {
    console.log('componentDidUpdate: Component has updated');
    if (prevState.counter !== this.state.counter) {
      console.log(`Counter changed from ${prevState.counter} to ${this.state.counter}`);
    }
  }

  componentWillUnmount() {
    console.log('componentWillUnmount: Component is about to be unmounted');
    // Cleanup actions, like clearing timers or canceling network requests
  }

  incrementCounter = () => {
    this.setState({ counter: this.state.counter + 1 });
  };

  render() {
    return (
      <div>
        <h1>Counter: {this.state.counter}</h1>
        <button onClick={this.incrementCounter}>Increment Counter</button>
      </div>
    );
  }
}

export default LifecycleExample;
```

### 7.2. Functional Component with Hooks

Equivalent functionality using hooks in a functional component:

```javascript
import React, { useState, useEffect } from 'react';

function LifecycleExample() {
  const [counter, setCounter] = useState(0);

  useEffect(() => {
    console.log('useEffect: Running after mount (componentDidMount equivalent)');
    return () => {
      console.log('useEffect Cleanup: Running before unmount (componentWillUnmount equivalent)');
    };
  }, []); // Empty dependency array makes this effect run only on mount and unmount

  useEffect(() => {
    console.log('useEffect: Running after counter updates (componentDidUpdate equivalent)');
  }, [counter]); // This effect runs on every update of counter

  const incrementCounter = () => {
    setCounter(counter + 1);
  };

  return (
    <div>
      <h1>Counter: {counter}</h1>
      <button onClick={incrementCounter}>Increment Counter</button>
    </div>
  );
}

export default LifecycleExample;
```

### 7.3. Explanation

**Mounting**: In class components, componentDidMount is used to run code after the component is inserted into the DOM. In functional components, useEffect with an empty dependency array ([]) mimics this behavior

**Updating**: In class components, componentDidUpdate allows you to execute code when the component updates due to changes in state or props. In functional components, useEffect with specific dependencies (like [counter]) serves the same purpose

**Unmounting**: In class components, componentWillUnmount is used for cleanup just before the component is removed from the DOM. The cleanup function returned by useEffect in functional components achieves similar results

These examples show how lifecycle behaviors can be implemented in both class and functional components, offering flexibility depending on the chosen approach in React development.

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
