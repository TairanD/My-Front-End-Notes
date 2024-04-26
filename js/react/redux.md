# Redux

## 1 - Why Redux?
In react, the data flow is usually top-to-bottom, which means the data/information is transported from the parent components
to the child components. Yet, if we want to transport data from bottom to top, it will be more complicated. 
For example, we can use recall functions to let the children pass specific logics and information to their parents, or we 
can use getChildContext to pass information. However, the syntax will be quite redundant and complex. 

Redux provide a centralized state management. By wrapping an additional component to the top-level component, it can function 
as a platform to preserve data and transport information.

## 2 - How does Redux work with React?
`react-redux` provides two things to achieve the collaboration between Redux and React: `connect` and `Provider`.
- `connect` associates components with Redux
- `Provider` passes `store` to components.

## 3 - Redux
Redux is mainly consisted of three parts: store, reducer, & action.

### 3.1 - store
`store` is an object, which has four major methods:
#### 3.1.1 - dispatch
`dispatch` is used to dispatch actions.

#### 3.1.2 - subscribe
`subscribe` is responsible to listen to the changes of states - this function will register one listener to listen any
change when `store.dispatch` is executed.

#### 3.1.3 - getState
Acquiring the state in the `store` - when we trigger reducer with action to change state, we need to get data from the new
state.

#### 3.1.4 - replaceReducer
Replacing the current reducer, change the logics of changing state.

### 3.2 - actions
`action` is an object, in which `type` attribute is required, along with some information. `action` can be created by `actionCreator`.
`store.dispatch` is used to send `action`.

### 3.3 - reducers
`reducer` is a function. It requires two parameters: a `state` and an `action`. Based on the `type` of `action`, `reducer` will
return a new `state`. There are many types of `reducer` according to different business logics. `combineReducers` combines
them together.
- `combineReducers`: also a reducer. It accepts a list of states and one action, then send states to their corresponding
reducer. All reducers will receive the same action, by the type of which they will return new state if the type of action is
existed, return default if not. In the end, these states will be combined again, and the `combineReducer` returns 
a new list of states.

#### *Note: state in Redux is not relevant to state in React.

### 3.4 - Example (Without React)
```javascript
// import Redux
import { createStore } from "redux";

// initialize state
const initialState = [];

// define a customized reducer
const myReducer = function (state = initialState, action) {
    switch (action.type) {
        case "addBook":
            console.log(action)
            return [...state, action.bookName]
        default:
            return [...state]
    }
}

// create a store
const store = createStore(myReducer);

// get elements
const root = document.getElementById("root");
const addBook = document.getElementById("addBook");
const addBookInput = document.getElementById("addBookInput");
const addBookBtn = document.getElementById("addBookBtn");

// add listener
addBookBtn.addEventListener("click", () => {
    const bookName = addBookInput.value;
    if (bookName){
        addBookInput.value = "";
    }
    
    // define a customized action
    const myAction = {
        type: "addBook",
        bookName: bookName
    }
    
    // send the action using 
    store.dispatch(myAction);
});

// listen the changes of state using store,subscribe
const mySubscribe = store.subscribe(()=>{
    console.log(store.getState());
});
```

## 3.5 - Redux Procedure
component -> store.dispatch(action)
-> reducer
-> store.subscribe
-> store.getState
-> component















