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