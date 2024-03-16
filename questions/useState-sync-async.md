# useState - Synchronous or Asynchronous

## 1 - Problem Context
When I was trying to use setData method provided by the useState hook to set fetched data from an url to variable data.
I wrote following code:
```javascript
const [data, setData] = useState(null)

useEffect(()=> {
    fetch('/find_question')
        .then(response => response.json())
        .then(response => {
            console.log(response)
            setData(response)
            console.log(data)
        })
}, [])
```

## 2 - Problem Statement
Yet, in the console, data was printed as `null`, indicating that it was not assigned to the response correctly.
Why is that?

## 3 - Answer
In React, _**state updates**_ via useState are asynchronous. This means that when you call setData to update the state, React 
doesn't immediately apply the update. Instead, it schedules the state update to occur after the current render cycle has 
completed (after rendering the current webpage page). This behavior ensures better performance by batching state updates.

In my code, when I call `console.log(data)` immediately after `setData(response)`, the data variable hasn't been updated
yet because the state update is asynchronous. Therefore, you'll see the old value of data logged to the console.

## 4 - Further Explore
When I was accidentally add async keyword ahead of the recall function. Following error popped out:
```javascript
// Effect callbacks are synchronous to prevent race conditions. Put the async function inside:  
useEffect(() => {   
    async function fetchData() {     // You can await here     
        const response = await MyAPI.getData(someId);     
        // ...
    }   
    fetchData();
}, [someId]); // Or [] if effect doesn't need props or state
```
The execution of the effect callbacks defined by useEffect must be synchronous. This means that when you define an effect with 
useEffect, the callback function you provide will execute synchronously after React has performed the necessary updates 
to the DOM. However, within the callback function of useEffect, you can perform asynchronous operations, such as fetching data from 
an API using fetch or making asynchronous function calls. When you do this, you typically use async/await syntax or return 
a Promise to handle the asynchronous behavior.

In conclusion, It's important to note that even though the useEffect callback is synchronous, you can still perform asynchronous
operations within it. The synchronous nature of the callback ensures that the effect is executed at the appropriate time
in the React component lifecycle, while still allowing for asynchronous behavior inside the callback.
