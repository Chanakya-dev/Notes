# 3: Understanding Lifecycle Methods

To demonstrate the mounting and unmounting phases in your `App.js`, we'll introduce a new component called `LifecycleDemo`. This component will use the `useEffect` hook to log messages when it mounts and unmounts. We'll then incorporate this component into your existing `App.js` so you can see the effects in action.

### Create the `LifecycleDemo` Component

```jsx
import React, { useEffect } from "react";

function LifecycleDemo() {
  useEffect(() => {
    console.log("LifecycleDemo has mounted"); // Runs after the component mounts

    return () => {
      console.log("LifecycleDemo is unmounting"); // Runs when the component unmounts
    };
  }, []); // The empty array ensures these logs only occur at mounting and unmounting

  return <p>Lifecycle demonstration in progress...</p>;
}

export default LifecycleDemo;
```

### Incorporate `LifecycleDemo` into `App.js`

```jsx
import React, { useState } from "react";
import logo from "./logo.svg";
import "./App.css";
import Greeting from "./Greeting";
import PersonalizedGreeting from "./PersonalizedGreeting";
import CoffeeCounter from "./CoffeeCounter";
import LifecycleDemo from "./LifecycleDemo"; // Make sure to import the new component

function App() {
  const [showLifecycleDemo, setShowLifecycleDemo] = useState(true); // State to control the visibility of LifecycleDemo

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
        <CoffeeCounter />
        {showLifecycleDemo && <LifecycleDemo />}{" "}
        {/* Conditional rendering of LifecycleDemo */}
        <button onClick={() => setShowLifecycleDemo(!showLifecycleDemo)}>
          {showLifecycleDemo ? "Hide Lifecycle Demo" : "Show Lifecycle Demo"}
        </button>
      </header>
    </div>
  );
}

export default App;
```

### Enhanced `LifecycleDemo` Component

```jsx
import React, { useEffect, useState } from "react";

function LifecycleDemo() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    console.log("LifecycleDemo has mounted"); // Building the toy

    return () => {
      console.log("LifecycleDemo is unmounting"); // Putting the toy away
    };
  }, []); // This only happens once when the toy is built and when it's put away

  useEffect(() => {
    console.log(`Count has been updated to ${count}`); // Playing with the toy
  }, [count]); // This happens every time the counter changes

  return (
    <div>
      <p>Lifecycle demonstration in progress...</p>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment Count</button>
    </div>
  );
}

export default LifecycleDemo;
```

### Explanation

- Do a `console.log` and print `showLifecycleDemo`.
- **Assignment**: Students should try to explain this concept.

### How it works:

- When you click the button "Show Lifecycle Demo", `LifecycleDemo` is mounted, and you should see "LifecycleDemo has mounted" in the console.
- If you click "Hide Lifecycle Demo", `LifecycleDemo` will unmount, and "LifecycleDemo is unmounting" will be logged in the console.

This setup not only demonstrates mounting and unmounting but also gives you a practical example of how to manipulate component visibility based on user interaction, which is a common pattern in many React applications.

# 3 Router

**Title: The Mystical Routes of React Router**

In the enchanted kingdom of React, there exists a powerful sorcery known as React Router. It allows wizards to navigate seamlessly between different parts of their magical web applications. In this chapter, we'll explore the basics of routing and learn how to create mystical routes that transport users to different components.

### Example 3.1: Creating Mystical Routes

```jsx
import React from "react";
import { BrowserRouter as Router, Routes, Route, Link } from "react-router-dom";
import Home from "./components/Home";
import About from "./components/About";
import Contact from "./components/Contact";

function App() {
  return (
    <Router>
      <div>
        <nav>
          <ul>
            <li>
              <Link to="/">Home</Link>
            </li>
            <li>
              <Link to="/about">About</Link>
            </li>
            <li>
              <Link to="/contact">Contact</Link>
            </li>
          </ul>
        </nav>

        <Routes>
          {" "}
          {/* Wrap all Route components within a Routes component */}
          <Route path="/" element={<Home />} />{" "}
          {/* Use element prop instead of component */}
          <Route path="/about" element={<About />} />
          <Route path="/contact" element={<Contact />} />
        </Routes>
      </div>
    </Router>
  );
}

export default App;
```

In this example, we've used React Router to create a mystical navigation system for our application. Let's break down the enchantment:

1. We import the necessary components from the `react-router-dom` library: `BrowserRouter`, `Route`, and `Link`.
2. We wrap our entire application with the `BrowserRouter` component, which provides the routing functionality.
3. Inside the `Router`, we define a navigation menu using the `Link` component. Each `Link` has a `to` prop that specifies the path to navigate to when clicked.
4. We define our routes using the `Route` component. Each `Route` has a `path` prop that matches the URL path and an `element` prop that specifies which component to render when the path matches.

Now, let's create the magical components that our routes will transport us to:

```jsx
// Home.js
import React from 'react';

function Home() {
  return <h1>Welcome to the Enchanted Homepage!</h1>;
}

export default Home;

// About.js
import React from 'react';

function About() {
  return <h1>Discover the Secrets of Our Mystical Kingdom!</h1>;
}

export default About;

// Contact.js
import React from 'react';

function Contact() {
  return <h1>Send a Magical Message to Our Wise Wizards!</h1>;
}

export default Contact;
```

In these component files, we've defined the `Home`, `About`, and `Contact` components that our routes will render when the corresponding paths are matched.

When a user clicks on a `Link`, React Router will magically transport them to the matching route and render the associated component. It's like casting a spell to navigate through the mystical realms of our application!

### Conclusion

React Router is a powerful tool that allows us to create enchanting routes and navigate seamlessly between different parts of our React application. By defining routes and linking them to components, we can create a magical user experience that feels like traversing through a mystical kingdom.

Remember, the key to mastering React Router is understanding the basic concepts of routing and practicing the art of creating mystical routes. Keep exploring the depths of React Router, and may your routes be filled with wonder and enchantment!

Happy coding, and may your React adventures be filled with magical navigation!
