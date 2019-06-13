## About ReactJS
**Key concepts:**
* Components : *functional component and class component*
* JSX : *mix of html & JavaScript in curly braces*
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

## Class Component
* a class that extends Component and has a render function
* ES6 class syntax
* property is accessed with: `this.props`

```jsx
import React, { Component } from 'react';

class MyComponent extends Component {
  // ... ... ..
  
  render() {
    return (
      <h1> Hello { this.props.name }! Today is: { new Date() } </h1>
    );
  }
}

export default MyComponent;
```

Using component
```jsx
<div id="container">
</div>

ReactDOM.render(<MyComponent name="Hassan" />, document.getElementById('content'));
```


## Functional Component
* a function which accepts props and returns a React element
* easier to read and test (plain JavaScript functions)
* performance (faster than class component)
* has to return JSX (a single tag/container)
* the whole fucntion acts like return() function of class component

```jsx
import React from 'react';

const myComponent(props) {
  return (
    <h1> 
      Hello { props.name }!
    </h1>
  )
}

// ES6 arrow function
const myComponent = (props) => {
  let greeting = `Hello { props.name }!`; // interplated string
  return (
    <h1> { greeting } </h1>
  )
}

// ES6 destructing
const myComponent = ({name}) => {
  return (
    <h1> Hello { name }! </h1>
  )
}

export default myComponent;
```
