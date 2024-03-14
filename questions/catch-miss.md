# Error does not be caught

# Problem Context
When I was trying to request data from an url.

### Problem Statement
I created the following function to submit form data to an url. While since I misspelled the link, 
the browser warned me with 404 state code. I found my mistake and fixed it.

However, when I used following code to debug, instead printing error in the console, false was printed. I wondered why is that?
```js
const handleSubmit = (e) => {
  e.preventDefault();

  const blog = {title, contents, identity}
    fetch('/all_questions', {
        method: 'POST',
        headers: { "Content-Type" : "application/json"},
        body: JSON.stringify(blog)
    }).then((response)=>{
        console.log(response.ok)
    }).catch(error => {
        console.error('Error:', error);
    });
}
```

### Answer
When dealing with errors like network request status code errors, they typically don't trigger the catch statement in JavaScript. The catch statement is usually used to catch exceptions that occur during the execution of code, such as syntax errors or logical errors.

Status code errors returned from network requests (such as 404, 500, etc.) are results of the request, not exceptions in the JavaScript code. Therefore, they won't be caught by the catch statement. You need to handle them in the then method, for example, by checking the status code of the response and handling it accordingly.

If you do need to handle exceptions that might occur during the network request process (such as network connection failures or cross-origin issues), you can use the catch method after the fetch method to catch those exceptions. However, for status code errors returned from requests, it's still best to handle them in the then method.

