# React-Redux
In this [note](../redux.md), I've introduced Redux. So, how does Redux work with React?

## 1 - What's react-redux
React-Redux is the official library for integrating Redux with React applications. It provides a set of APIs and components
that make it easier and more efficient to use Redux with React. 

With react-redux, we programmers do not need to consider the three major functions of store, dispatch, subscribe, & getState,
because the library do them for us. Also, react-redux offers two features to make the whole process more easily.

## 2 - Provider
Provider is a component provided by react-redux, which is the top-level container for the entire application. It passes the 
Redux store as a prop to all components in the application, allowing any component in the component tree to access the 
state in the Redux store. This means we can trigger `reducer` to change `state` in any component using `dispatch(action)`, and
listen to these changes using `subscribe`, and acquire values after changes using `getState`.

Yet, the above procedure is not a good practice since it will mess up with the data flow. Additionally, overcoupling will
impact on the re-usability of components, making the maintenance more difficult.

## 3 - connect
`connect` is a function requiring four parameters:
1. `mapStateToProps(state, [ownProps])`: the function will return a new object as a part of props passing to ui components.
We can customize the object according to demands of the component. The changes of `ownProps` will also trigger `mapStateToProps`.
For example, 
    ```javascript
    function mapStateToProps(state){
        return { todos: state.todos };
    }
    ```
2. `mapDispatchToProps(dispatch, [ownProps])`: the 


## 4 - React -> Redux -> React
### 4.1
Provider component accepts the store of redux as props, then passes it through context.








