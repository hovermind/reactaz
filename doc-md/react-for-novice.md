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
  render() {
    return (
      <h1> Hello {this.props.name}! </h1>
    );
  }
}

export default MyComponent;
```

**Using class component**
```jsx
import ReactDOM from 'react-dom';
import MyComponent from './MyComponent';

<div id="container">
</div>

let containerDiv = document.getElementById('content');
ReactDOM.render(<MyComponent name="Hassan" />, containerDiv);
```

**Using class component in other component** 
```jsx
import React from 'react';
import MyComponent from './MyComponent';

class MyOtherComponent extends React.Component {
  // ... ... ...
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
* normally `setState()` will be called from event handler function or lifecycle callbacks

**Set state - passing object:** performs a shallow merge of the state change into the new state
```jsx
this.setState({foo: 2});
```

**Set state - passing updater and callback function:**
Updater function signature: `(prevState, props) => stateChange`
```jsx
// inside event handler or lifecycle callback
this.setState((prevState, props) => {
  return {counter: prevState.counter + props.step};
});
```
**Note:** 
* due to the async nature of `setState()`, it is not advisable to use `this.state` to get the previous state within `setState()`, use `prevState` to get previous state
* `componentDidUpdate()` lifecycle callback should be used instead of optional callback of `setState()` (in most cases)

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
