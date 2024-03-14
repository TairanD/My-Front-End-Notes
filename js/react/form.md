<body style="font-family: serif"></body>

# Form in React

## 1 - General Idea
- Create your form 
- Track input values and store them in somewhere inside the component
- Process those data later

## 2 - Detailed Idea
1. Create form.
2. Add useStates.
3. Associate variables to `value`.
4. Enable Changes.

## 3 - Detailed Steps
1. Using `<form><form/>`, `<label><label/>`, and `<input/>`, etc. to create a form
2. Using useState to create trackable variables. Since useStates are independent with each other,
we can create useStates for every input/textarea to track them.
3. Setting up the `value` property of each input/textarea to the corresponding variable.
4. However, at this point you will find out you cannot change the value inside the input area. That's because
you have not done anything to update the value. 
   1. Therefore, you need to add onChange property to your input.
   2. Then, passing the event object as a parameter, and using the set function to set the current variable as the 
   current input. The value will consequently change as it has been associated to the variable.

## 4 - Code Example
```jsx
import React, {useState, useEffect} from 'react';

const Form = () => {

    const [title, setTitle] = useState();
    const [contents, setContents] = useState();
    const [identity, setIdentity] = useState();

    return (
        <div className=''>
            <h2>Simple Example</h2>
            <form>
                <label>Title:</label>
                <input type='text' required value={title} onChange={e => setTitle(e.target.value)}/>

                <label>Contents:</label>
                <textarea required value={contents} onChange={e => setContents(e.target.value)}/>

                <label>Identity:</label>
                <select required value={identity} onChange={e => setIdentity(e.target.value)}>
                    <option value="user">user</option>
                    <option value="administer">administer</option>
                </select>
                <button>Submit</button>
            </form>
            <p>title:{title}, contents:{contents}, identity:{identity}</p>
        </div>
    )
}

export default Form;
```

## 5 - Improved Technique


## 6 - How to submit data to the back end?
Check it out in the following link:
- [fetch](./react/fetch.md)