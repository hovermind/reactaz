## About ReactJS
#### Key concepts:
* **Components** : *functional component & class component. higher-order component (container, data logic) & presentational component (UI logic)*
* **JSX** : *mix of html markup and JavaScript in curly braces*
* **Props & State** : *state changes (i.e. user input), props don't (i.e. attribute)*
* **The Component API**

#### Things to know:
* A React codebase is made up of components and these components are written using JSX
* Data flows from parent to children, except when it comes to state, which originates inside a component
* Components possess a small set of lifecycle and utility methods
* You should keep data logic and UI logic in separate components
* Higher-order components are a common pattern for giving a component access to new tools

Courtesy: [Master these five concepts, then master React](https://www.freecodecamp.org/news/the-5-things-you-need-to-know-to-understand-react-a1dbd5d114a3/)

## Class Component
* a class that extends `React.Component` and has a render function
* ES6 class syntax
* property is accessed with: `this.props`
* destructing props: `const {foo} = this.props;`

```jsx
import React from 'react';

class MyComponent extends React.Component {
  // ... ... ..
  // ES6 destructing : const {name} = this.props;
  render() {
    return (
      <h1> Hello {this.props.name}! </h1>  // <h1> Hello {name}! </h1>
    );
  }
}

export default MyComponent;
```

Using class component
```jsx
<div id="container">
</div>

ReactDOM.render(<MyComponent name="Hassan" />, document.getElementById('content'));
```

Using class component in other component: 
```jsx
import React, { Component } from 'react';
import MyComponent from './MyComponent';

class MyOtherComponent extends Component {

  render() {
    return (
      <div>
        <div>This is my other component.</div>
        <MyComponent name="ハッサン" />
      </div>
    );
  }
}

export default MyOtherComponent;
```

## State of Class Component
* set: `this.setState({stateName : stateVal})` or `this.setState(updater [, callback])`
* get: `this.state`

**Passing object:** performs a shallow merge of the state change into the new state
```jsx
this.setState({foo: 2});
```

**Passing updater and callback function:** 
```jsx
// updater function signature: (prevState, props) => stateChange
// componentDidUpdate lifecycle callback should be used instead of optional callback of setState (most cases)

this.setState((prevState, props) => {
  return {counter: prevState.counter + props.step};
});
```
**Note:** *Due to the async nature of `setState()`, it is not advisable to use `this.state` to get the previous state within `setState()`, use `prevState` to get previous state*

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
