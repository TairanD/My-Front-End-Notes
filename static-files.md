# Static Files

## Definition
Static content is any content that can be delivered to an end user without having to be generated, modified, or processed.
The server delivers the same file to each user, making static content one of the simplest and most efficient content types to transmit over the Internet.

## Confusion: Why static files can achieve dynamic effects
Static files are typically files such as HTML, CSS, Js files, images, etc. We always hear that Js files can achieve dynamic effects like
according to user's inputs and operations to update pages dynamically. 

- How can this be called 'static'?

Let's revise the definition, where we can find **_static files are actually static to the server side, instead of to UI effects.
Depending on the JavaScript's ability to execute on the client-side_**. Once a React application is loaded into the user's browser, 
it can interact with the user and dynamically update the page based on user input and actions. This is because React manages 
the rendering and updating of the page using concepts like the virtual DOM and state management, allowing the page to change 
dynamically without needing to request new HTML pages from the server every time.

From this perspective, we can clearly understand why files like js are defined as 'static files'.