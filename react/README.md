[Back](../README.md)

# React Questions


## What is React app structure

```
node_modules - js components
public - static content with index.html having '<div id="root"></div>'
src
 - components
   - App.js with "<BrowserRouter>"
 - index.js having
        ReactDOM.render(
            <BrowserRouter>
            <App />
            </BrowserRouter>,
            document.getElementById('root'));
```

## How to build React component

```javascript
class AsyncSelect extends React.Component {

    constructor(props) {
        super(props);
        ...
    }

    componentDidMount() {
        ...
    }
    
    render() {
        return (
            <div id={this.dropdownContainerId} className="control select is-primary dropdown">
            ...
            </div>
        );
    }
}

export default AsyncSelect;
```

## Other resources

 - [node-template-pg](https://gitlab.com/shianra/node-template-pg)
 - [react-template-ui](https://gitlab.com/shianra/react-template-ui)
