## React Resources
### Getting Started with React
- [Getting Started with React](https://www.taniarascia.com/getting-started-with-react/)
  - [GitHub](https://github.com/taniarascia/react-tutorial/tree/master/src)
  - [Create React App](https://www.taniarascia.com/getting-started-with-react/#create-react-app)
    - create-react-app
      - `npx create-react-app react-tutorial`
    - start
      - `cd react-tutorial`
      - `yarn start`
      - `localhost:3000`
    - files
      - `/public`
        - includes `index.html`
      - `/src`
        - React code
    - `/src/App.js`
  - [React Developer Tools](https://www.taniarascia.com/getting-started-with-react/#react-developer-tools)
    - [React DevTools for Chrome](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi)
  - [JSX: JavaScript + XML](https://www.taniarascia.com/getting-started-with-react/#jsx-javascript--xml)
    - JSX:
      - `className` instead of `class`
      - properties and methods are camelCase (e.g., `onclick` -> `onClick`)
      - self-closing tags must end in a slash (e.g., `<img />`)
  - [Components](https://www.taniarascia.com/getting-started-with-react/#components)
    - [Class Components](https://www.taniarascia.com/getting-started-with-react/#class-components)
      - extend `Component`
      - must include `render()`
      - `return` can only return one parent element
    - [Simple Component](https://www.taniarascia.com/getting-started-with-react/#simple-components)
      - functions (such as with ES6 arrow syntax)
      - no use of `class` keyword
      - no `render()`
  - [Props](https://www.taniarascia.com/getting-started-with-react/#props)
    - `virtual DOM`
    - data passed to a component via `props` is read-only
  - [State](https://www.taniarascia.com/getting-started-with-react/#state)
    - to modify array within state, `this.setState()` must be used (rather than setting `this.state.property`)
    - `.filter()` creates a new array (rather than modifying the array passed in)
  - [Submitting Form Data](https://www.taniarascia.com/getting-started-with-react/#submitting-form-data)
  - [Pulling in API Data](https://www.taniarascia.com/getting-started-with-react/#pulling-in-api-data)
    - `componentDidMount()`
      - React lifecycle method for when a component has been inserted into the DOM
  - [Building and Deploying a React App](https://www.taniarascia.com/getting-started-with-react/#building-and-deploying-a-react-app)
    - `yarn build`
  - [GitHub Pages](https://ehelander.github.io/react/react-tutorial)

### Using React with Nx
- [Using React with Nx](https://nx.dev/guides/react)
  - [Creating a New Nx Workspace](https://nx.dev/guides/react#creating-a-new-nx-workspace)
    - Create a new `nrwl` workspace
      - `npx create-nx-workspace happynrwl --preset=empty`
    - Create a new `happynrwl` workspace with a React application
      - `npx create-nx-workspace happynrwl --preset=react`
  - [Generating a React Application](https://nx.dev/guides/react#generating-a-react-application)
    - Generate a new `frontend` application
      - `ng g app frontend --framework=react`
    - Serve app
      - `ng serve frontend`
    - Build app
      - `ng build frontend`
    - Lint app
      - `ng lint frontend`
    - Test the app using Jest
      - `ng test frontend`
    - Test the app using Cypress
      - `ng e2e frontend-e2e`
  - [Generating a React Library](https://nx.dev/guides/react#generating-a-react-library)
    - Generate a new `home` library
      - `ng g lib home --framework=react`
    - Test lib
      - `ng test home`
    - Lint lib
      - `ng lint home`
  - [Using Library in Application](https://nx.dev/guides/react#using-library-in-application)
    - Can import library into an application
      - `import { Home } from '@myworkspace/home';`
  - [Sharing Code](https://nx.dev/guides/react#sharing-code)
  - [Understanding Your Nx Workspace](https://nx.dev/guides/react#understanding-your-nx-workspace)
    - See current dependency diagram of the workspace
      - `yarn dep-graph`
    - Print the apps affected by a PR
      - `yarn affected:apps --base=master`
    - Rerun build for all projects affected by a PR
      - `yarn affected:build --base=master`
    - Rerun unit tests for all projects affected by a PR
      - `yarn affected:test --base=master`
    - Rerun e2e tests for all projects affected by a PR
      - `yarn affected:e2e --base=master`
    - Rerun any target (here, `lint`) for all projects affected by a PR
      - `yarn affected: --target=lint --base=master`

### Main Concepts
- [Hello World](https://reactjs.org/docs/hello-world.html)
- [Introducting JSX](https://reactjs.org/docs/introducing-jsx.html)
- [Rendering Components](https://reactjs.org/docs/rendering-elements.html)
  - Applications built with just React usually have a single root DOM node. If you are integrating React into an existing app, you may have as many isolated root DOM nodes as you like.
  - [Updating the Rendered Element](https://reactjs.org/docs/rendering-elements.html#updating-the-rendered-element)
    - React elements are immutable. Once you create an element, you can’t change its children or attributes. An element is like a single frame in a movie: it represents the UI at a certain point in time.
  - [React Only Updates What's Necessary](https://reactjs.org/docs/rendering-elements.html#react-only-updates-whats-necessary)
    - React DOM compares the element and its children to the previous one, and only applies the DOM updates necessary to bring the DOM to the desired state.
    - In our experience, thinking about how the UI should look at any given moment rather than how to change it over time eliminates a whole class of bugs.
- [Components and Props](https://reactjs.org/docs/components-and-props.html)
  - Conceptually, components are like JavaScript functions. They accept arbitrary inputs (called “props”) and return React elements describing what should appear on the screen.
  - [Function and Class Components](https://reactjs.org/docs/components-and-props.html#function-and-class-components)
    - This function is a valid React component because it accepts a single “props” (which stands for properties) object argument with data and returns a React element. We call such components “function components” because they are literally JavaScript functions.
  - [Rendering a Component](https://reactjs.org/docs/components-and-props.html#rendering-a-component)
    - When React sees an element representing a user-defined component, it passes JSX attributes to this component as a single object. We call this object “props”.
    - Note: Always start component names with a capital letter.
      - React treats components starting with lowercase letters as DOM tags. For example, `<div />` represents an HTML div tag, but `<Welcome />` represents a component and requires Welcome to be in scope.
  - [Composing Components](https://reactjs.org/docs/components-and-props.html#composing-components)
  - [Extracting Components](https://reactjs.org/docs/components-and-props.html#extracting-components)
    - We recommend naming props from the component’s own point of view rather than the context in which it is being used.
    - A good rule of thumb is that if a part of your UI is used several times (Button, Panel, Avatar), or is complex enough on its own (App, FeedStory, Comment), it is a good candidate to be a reusable component.
  - [Props are Read-Only](https://reactjs.org/docs/components-and-props.html#props-are-read-only)
    - Whether you declare a component as a function or a class, it must never modify its own props.
    - **All React components must act like pure functions with respect to their props.**
- [State and Lifecycle](https://reactjs.org/docs/state-and-lifecycle.html)
  - State is similar to props, but it is private and fully controlled by the component.
  - [Converting a Function to a Class](https://reactjs.org/docs/state-and-lifecycle.html#converting-a-function-to-a-class)
    - You can convert a function component like `Clock` to a class in five steps:
      1. Create an ES6 class, with the same name, that extends `React.Component`.
      2. Add a single empty method to it called `render()`.
      3. Move the body of the function into the `render()` method.
      4. Replace props with this.props in the `render()` body.
      5. Delete the remaining empty function declaration.
    - The `render` method will be called each time an update happens, but as long as we render `<Clock />` into the same DOM node, only a single instance of the `Clock` class will be used. This lets us use additional features such as local state and lifecycle methods.
  - [Adding Local State to a Class](https://reactjs.org/docs/state-and-lifecycle.html#adding-local-state-to-a-class)
    - We will move the `date` from `props` to `state` in three steps:
      1. Replace `this.props.date` with `this.state.date` in the `render()` method
      2. Add a class constructor that assigns the initial `this.state`
          - Note how we pass `props` to the base constructor
          - Class components should always call the base constructor with `props`.
      3. Remove the `date` prop from the `<Clock />` element
  - [Adding Lifecycle Methods to a Class](https://reactjs.org/docs/state-and-lifecycle.html#adding-lifecycle-methods-to-a-class)
    - In applications with many components, it’s very important to free up resources taken by the components when they are destroyed.
    - `componentDidMount()`
    - `componentWillUnmount()`
    - `setState()`
  - [Using State Correctly](https://reactjs.org/docs/state-and-lifecycle.html#using-state-correctly)
    - There are three things you should know about `setState()`.
    - [Do Not Modify State Directly](https://reactjs.org/docs/state-and-lifecycle.html#do-not-modify-state-directly)
      - The only place where you can assign this.state is the constructor.
    - [State Updates May Be Asynchronous](https://reactjs.org/docs/state-and-lifecycle.html#state-updates-may-be-asynchronous)
      - React may batch multiple setState() calls into a single update for performance.
      - Because this.props and this.state may be updated asynchronously, you should not rely on their values for calculating the next state.
        - To fix it, use a second form of setState() that accepts a function rather than an object. That function will receive the previous state as the first argument, and the props at the time the update is applied as the second argument.
    - [State Updates are Merged](https://reactjs.org/docs/state-and-lifecycle.html#state-updates-are-merged)
      - When you call `setState()`, React merges the object you provide into the current state.
- [The Data Flows Down](https://reactjs.org/docs/state-and-lifecycle.html#the-data-flows-down)
  - Neither parent nor child components can know if a certain component is stateful or stateless, and they shouldn’t care whether it is defined as a function or a class.
  - 



