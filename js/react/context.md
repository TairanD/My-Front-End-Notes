# Context in React

## 1 - Why Context?
Context in React is useful when you have data that needs to be accessed by many components at different levels of **nesting**,
**without having to pass props down manually at every level**. It helps in avoiding prop drilling, where you pass props through intermediary components that don't need the data just to reach deeply nested components that do.
## 2 - What is Context?
Context in React provides a way to share values like themes, preferred languages, or any other data that needs to be 
accessed by **many components at different nesting levels**. It consists of a Context object created using 
`React.createContext()`, which contains a `Provider` and a `Consumer`. The `Provider` component is used to wrap the part of 
the component tree where you want to make the context available, while the `Consumer` component is used to access 
the value of the context within a component.
## 3 - How to use it?
To use Context in React:

1. Create Context: Create a Context object using `React.createContext()`.
2. Provide Context: Wrap the part of the component tree where you want to make the context available with the `Provider`
component. Pass the data you want to share as a value `prop` to the `Provider`.
3. Consume Context: Use the `Consumer` component to access the context value within a component. Alternatively, use 
the `useContext` hook in functional components to access the context value.
4. Access Context Value: Consumers can access the context value by wrapping the part of the component tree they need it
in with the `Consumer` component or using the `useContext` hook.

Context allows you to manage global state or shared data in your React application in a more efficient and organized way, making your code cleaner and more maintainable.






