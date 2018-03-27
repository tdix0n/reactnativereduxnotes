# React Native Redux Notes

## Tasks
- Create Store
This should be called once. Probably put this in the App root
```
const store = createStore(reducer);
```
- Create Actions
Actions should 
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
- Wrap App in `<Provider> </Provider>` tags and pass the Store to it as a Prop
```
const App = () => (
  <Provider store={store}>
    <Counter/>
  </Provider>
);
```
- Create Reducers to take the current State and Actions, and return a new state
Reducers should be switch statements, applying
Reducers should always fallback to returning the original state (in case there is no change)
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
- Define a default state above the reducer
```
const initialState = {
  count: 0
};
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
