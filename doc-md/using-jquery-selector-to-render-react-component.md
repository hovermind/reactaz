## Using jquery selector
* react render funtion takes dom object to which react component should be rendered.
* jQuery selector reaturns array
* use `$('#id')[0]` to get object (instead of array)

```html
<div id="root">
</div>

<script type="text/javascript">
  class MyComponent extends React.Component {
    // ... ... ..
    render() {
      return (
      <h1> Hello {this.props.name}!</h1>
      );
    }
  }

  ReactDOM.render(<MyComponent name="Hassan" />, $('#root')[0]);
</script>
```
