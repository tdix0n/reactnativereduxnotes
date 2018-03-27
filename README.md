# reactnativereduxnotes
React Native Redux Notes

##Tasks
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
