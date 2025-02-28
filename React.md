# React Learnings

## Creating a React App
To create a new React app, use the following command:

```sh
npx create-react-app my-app
```

Alternatively, using npm or yarn:

```sh
npm init react-app my-app
# or
yarn create react-app my-app
```

After installation, navigate to your project directory and start the development server:

```sh
cd my-app
npm start
```

## Creating a React App with Vite
Vite is a fast build tool for modern web applications. To create a new React app using Vite, run the following commands:

```sh
npm create vite@latest my-app --template react
# or
yarn create vite@latest my-app --template react
```

After installation, navigate to your project directory, install dependencies, and start the development server:

```sh
cd my-app
npm install
npm run dev
```

## Significance of `useState` and `useEffect` in React

### `useState`
The `useState` hook allows functional components to manage state. Example:

```jsx
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

### `useEffect`
The `useEffect` hook handles side effects like fetching data, subscriptions, or manual DOM manipulations. Example:

```jsx
import React, { useState, useEffect } from 'react';

function Timer() {
  const [time, setTime] = useState(0);

  useEffect(() => {
    const interval = setInterval(() => {
      setTime((prevTime) => prevTime + 1);
    }, 1000);

    return () => clearInterval(interval); // Cleanup on unmount
  }, []);

  return <p>Time: {time}s</p>;
}
```

## Concept of Components in React
Components are reusable building blocks of a React application. They can be functional or class-based.

### Functional Component Example:
```jsx
function Greeting({ name }) {
  return <h1>Hello, {name}!</h1>;
}
```

### Class Component Example:
```jsx
import React, { Component } from 'react';

class Greeting extends Component {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}
```

React encourages breaking UI into smaller, reusable components to improve maintainability and scalability.

## Idea of Parent Component in `main.jsx`
In React, the `main.jsx` file typically renders the root component (parent component) that contains child components.

### Example of `main.jsx`:
```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

Here, `App` is the parent component, which may contain multiple child components inside it. This structure helps organize the React application efficiently.
