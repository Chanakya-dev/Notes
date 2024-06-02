````markdown
# Getting Started with React.js

React.js is a powerful library for building user interfaces. In this tutorial, we will explore the core concepts of React and learn how to create interactive web applications. Before we start, set up your React project by running `npx create-react-app react-app` in your terminal, and then navigate into your new project with `cd react-app`.

## Chapter 1: Understanding Components

In React, everything revolves around the concept of components. Components are like the building blocks that come together to form the entire application.

### Example 1.1: Creating a Simple Component

```jsx
import React from "react";

function Greeting() {
  return (
    <div>
      <h1>Welcome to our Coffee Shop!</h1>
      <p>Enjoy the best coffee in town!</p>
    </div>
  );
}

export default Greeting;
```
````

### Edit `App.js`

```jsx
import logo from "./logo.svg";
import "./App.css";
import Greeting from "./Greeting";

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>

        <Greeting />
      </header>
    </div>
  );
}

export default App;
```

In this example, we've created a functional component named `Greeting`. It returns JSX, a syntax that allows us to write HTML-like code within JavaScript. The component renders a title and a paragraph.

## Chapter 2: Using JSX

In React, we use JSX to describe the structure and appearance of our components. JSX blends HTML and JavaScript together.

### Example 2.1: Creating a Component with Props

```jsx
import React from "react";

function PersonalizedGreeting(props) {
  return <h1>Hello, {props.name}! Welcome to our Coffee Shop!</h1>;
}

export default PersonalizedGreeting;
```

In this example, we've created a `PersonalizedGreeting` component that accepts a `name` prop. The JSX inside the component dynamically displays the `name` using curly braces `{}`.

## Chapter 3: Working with Props

Props allow us to pass data from a parent component to its children. They enable us to create reusable and customizable components.

### Example 3.1: Passing Props

```jsx
import logo from "./logo.svg";
import "./App.css";
import Greeting from "./Greeting";
import PersonalizedGreeting from "./PersonalizedGreeting";

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>

        <Greeting />
        <PersonalizedGreeting name="Alice" />
        <PersonalizedGreeting name="Bob" />
      </header>
    </div>
  );
}

export default App;
```

In this example, we've rendered the `PersonalizedGreeting` component twice, passing different `name` props to each instance. The `PersonalizedGreeting` component receives the `name` prop and displays it in the JSX.

## Chapter 4: Managing State

State holds the data of a component and allows components to manage and update their own data.

### Example 4.1: Using State

```jsx
import React, { useState } from "react";

function CoffeeCounter() {
  const [cups, setCups] = useState(0);

  function handleClick() {
    setCups(cups + 1);
  }

  return (
    <div>
      <p>Cups of coffee served: {cups}</p>
      <button onClick={handleClick}>Serve another cup</button>
    </div>
  );
}

export default CoffeeCounter;
```

### Import this in `App.js`

In this example, we've used the `useState` hook to add state to our component. The `cups` state variable holds the number of cups of coffee served, and the `setCups` function updates the state when the button is clicked.

## Conclusion

React.js is a powerful library that allows us to create interactive user interfaces. By mastering the core concepts of components, JSX, props, and state, you'll be able to build web applications that captivate users.

Remember, practice is key to becoming proficient in React. Keep exploring, and happy coding!

```

```
