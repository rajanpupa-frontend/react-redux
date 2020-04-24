# Learn Redux

`npm install redux react-redux --save`

- Normally data is passed as params from parent to child in react
- This creates a problem if the data needs to be shared among various components
- One way is to put the data at the very top and pass to child after child

- Store is a totally different way of handling data
- store keeps a very big state (data) of the whole application
- any component can interact with the state for data

```javascript
// can put this script in index.js and see the log
import {createStore} from 'redux';
// STORE -> globalized state
// ACTION Increment
const increment = ()=> {
    return {
        type: 'INCREMENT'
    }
}
const decrement = ()=> {
    return {
        type: 'DECREMENT'
    }
}
// REDUCER - how action transcribe state to next state
const counter = (state = 0, action ) => {
    switch(action.type){
        case "INCREMENT":
            return state + 1;
        case "DECREMENT":
            return state - 1;
    }
}
let store = createStore(counter);
// DISPLAY in the console
store.subscribe(()=> console.log(store.getState()));
// DISPATCH - Send action to the reducer
store.dispatch(increment());
store.dispatch(decrement());
```

### References
[youtube](https://www.youtube.com/watch?v=CVpUuw9XSjY)