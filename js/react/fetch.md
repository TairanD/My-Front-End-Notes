<body style="font-family: serif"></body>

# React Fetch

## 1 - Using fetch to fetch data

## 2 - Using fetch to submit data
In the [form.md](./react/form.md) section I have introduced how to create a form with trackable and changeable 
input elements. Now, we need to figure out how to submit form data to the back-end/url. 

When the user presses the button inside a form, it fires a submit event on that form. What we will do is to **listen**
to this submit event and react to it. (An alternative approach is to attach an onclick on the button, but we do not discuss
it here.) 
```jsx
import React, {useState, useEffect} from 'react';

const Form = () => {

    const [title, setTitle] = useState();
    const [contents, setContents] = useState();
    const [identity, setIdentity] = useState();

    const handleSubmit = (e) => {
      e.preventDefault();
      
      const blog = {title, contents, identity}
    }
    
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

