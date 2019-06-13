## About ReactJS
Key concepts:
* Components : *functional component and class component*
* JSX : *html markup + JavaScript*
* Props & State : *State changes (i.e. user input), Props don't (i.e. attribute)*
* The Component API
* Higher-order (container) component : *contains data logic. whole purpose is to get data and contain sub-components*
* Presentational component : *contains UI logic. whole purpose is to show data (dumb)*

**Things to know:**
* A React codebase is made up of components
* These components are written using JSX
* Data flows from parent to children, except when it comes to state, which originates inside a component
* Components possess a small set of lifecycle and utility methods
* Components can also be written as pure functions
* You should keep data logic and UI logic in separate components
* Higher-order components are a common pattern for giving a component access to new tools

Courtesy: [Master these five concepts, then master React](https://www.freecodecamp.org/news/the-5-things-you-need-to-know-to-understand-react-a1dbd5d114a3/)

## Class component
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

## Functional component
```jsx
const myComponent = (props) => {
  return <p>Hello {props.name}! Today is {new Date()}.</p>
}
```
