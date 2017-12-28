# React

* JSX
* What React is ?
* `props` and `state`
* include non react components ( jquery )
* Rendering `render()`
* Lifecycle
  * `constructor()`, `componentWillMount()`, `componentDidMount()`
  * `componentWillReceiveProps()`, `shouldComponentUpdate()`, `componentWillUpdate()`, `componentDidUpdate()`, `componentWillUnmount()`
  * `setState()`, `forceUpdate()`
* Function vs Class
* `key` ( unique, index, noKeys, staticLists )
* Immutable
* `setState(updater[, callback])`,
* `children` ( `this.props.children` )
* Flow
* `Refs` ( ` <input type="text" ref={(input) => { this.textInput = input; }} />` -> `this.textInput.focus();` )


```js
this.setState((prevState, props) => {
  return {counter: prevState.counter + props.step};
});
```

* defaultProps
* PropTypes

```
import PropTypes from 'prop-types';

class Greeting extends React.Component {

  static propTypes = {
    loading: PropTypes.bool.isRequired,
  };

  render() {
    return (
      <h1>Hello, {this.props.name}</h1>
    );
  }
}

Greeting.propTypes = {
  name: PropTypes.string
};

Greeting.defaultProps = {
  name: 'Stranger'
};
````

## FORMS

```
class NameForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {value: ''};

    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }

  handleChange(event) {
    this.setState({value: event.target.value});
  }

  handleSubmit(event) {
    alert('A name was submitted: ' + this.state.value);
    event.preventDefault();
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Name:
          <input type="text" value={this.state.value} onChange={this.handleChange} />
        </label>
        <input type="submit" value="Submit" />
      </form>
    );
  }
}
```


* what do you use for forms ?



## HTTP(s)

* methods ( `GET`, `POST`, `PUT`, `PATCH`, 'DELETE' )
* status codes
* file upload
* progress


## Redux

* Actions ( const ADD_TODO = 'ADD_TODO' )
* Action Creators
```
function addTodo(text) {
  return {
    type: ADD_TODO,
    text
  }
}
```
* Reducers
```
function todoApp(state = initialState, action) {
  switch (action.type) {
    case SET_VISIBILITY_FILTER:
      return Object.assign({}, state, {
        visibilityFilter: action.filter
      })
    default:
      return state
  }
}
```
* Store ( `dispatch`, `subscribe`, `unsubscribe` )
* Asynchronous

###  Thunk vs Saga

