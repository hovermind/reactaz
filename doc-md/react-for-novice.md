## About react
* A React codebase is made up of components.
* These components are written using JSX.
* Data flows from parent to children, except when it comes to state, which originates inside a component.
* Components possess a small set of lifecycle and utility methods.
* Components can also be written as pure functions.
* You should keep data logic and UI logic in separate components.
* Higher-order components are a common pattern for giving a component access to new tools.

```jsx
class MyComponent extends React.Component {

  // ... ... ...

  render() {
    return <p> Hello World! <p>;
  }
  
}
```

Mix of js and markup: `{ ... }`
```jsx
class MyComponent extends React.Component {

  // ... ... ...

  render() {
    return <p> Today is: { new Date() } </p>;
  }
  
}
```
