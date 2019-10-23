## Running react app
* react uses JSX (JS + HTML)
* JSX needs to be transpiled
* babel tranpiles JSX
* react app need to be transpiled before running
* It slowly compiles JSX with Babel in the browser and uses a large development build of React.

## Traspiling on the fly 
We can use babel to transpile react app without using react CLI
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Reactaz</title>
    <script src="https://unpkg.com/react@16/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/babel-standalone@6.26.0/babel.js"></script>
  </head>
  <body>
  
    <div id="root"></div>

    <script type="text/babel">
	
		class MyComponent extends React.Component {
		  // ... ... ..
		  render() {
			return (
			  <h1> Hello {this.props.name}! </h1>
			);
		  }
		}

		let containerDiv = document.getElementById('root');
		ReactDOM.render(<MyComponent name="Hassan" />, containerDiv);
		
    </script>
  </body>
</html>
```
