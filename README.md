# reactnativereduxnotes
React Native Redux Notes

## Tasks
- Create Store
- Create Actions
- Create a mapStateToProps function

```
function mapStateToProps(state) {
  return {
    count: state.count
  };
}
```

- Export the component wrapped in mapStateToProps

```
export default connect(mapStateToProps)(Counter);
```
- Wrap App in `<Provider> </Provider>` tags
- Create Reducers to respond to Actions
```
function reducer(state = initialState, action) {
  switch(action.type) {
    case 'INCREMENT':
      return {
        count: state.count + 1
      };
    case 'DECREMENT':
      return {
        count: state.count - 1
      };
    default:
      return state;
  }
}
```

- Ensure components receiving data from the Store use Props
e.g. 
```
  render() {
    return (
      <div>
        <h2>Counter</h2>
        <div>
          <button onClick={this.decrement}>-</button>
          <span>{this.props.count}</span>
          <button onClick={this.increment}>+</button>
        </div>
      </div>
    )
  }
}
```
