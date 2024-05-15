# Re-Render

### React ReRender
When a component's states or properties change, React will automatically update the component.

### Procedure
1. The **state** and **props** of a component are used in React to describe the component's state and properties. 
When there's a change in the component's state or props, React **triggers** a re-render of the component.
2. Whenever there's a change in the component's state or props, React re-executes the component's **render function**.
The render function is typically the render() method in a component. It returns a React element tree that describes the component's UI structure.
3. After re-executing the render function, React generates a new [Virtual DOM](./virtual-dom.md) tree. React compare the differences between the new and old virtual DOM trees.
4. Based on the comparison of virtual DOMs, React calculates the parts of the actual DOM that need to be updated and applies those changes, updating the page.
In this way, React can minimize DOM updates by only updating the parts that have changed, thus improving performance.
5. During the re-rendering process, React calls the component's lifecycle methods, allowing the component to perform actions at different stages.
6. If a parent component re-renders, its **child components** will also re-render.
React ensures that when a parent component re-renders, its child components update to **reflect the latest state and props**.

