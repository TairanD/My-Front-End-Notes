# Upload Files

## axios


## e.target.files
- e represents an [event objects](../event-object.md).
- e.target represents the element that triggered the event. For example, if a user clicks a button, e.target would refer to that button element.
- e.target.files: This is typically used in conjunction with file input elements (`<input type="file">`). When a user selects one or more files using such an input element, the files property of the input element contains a FileList object representing the selected files.
## FormData
Instead of writing an HTML form with the form tag in the action and submit that to the server, we would like to use js object.

FormData is sort of the replication of what a form does. It can be regarded as an array of arrays. Each array inside the array
represents an element that will be sent to the server. These inside arrays have 2 things: a name and a value. 

#### Usage
```javascript
let fd = new FormData()
fd.append('name', 'hello')
fd.append('id', 123)
fd.append('birth date', Date.now())

fd.append()
```

## Procedure
1. Create state variable `file` and `setFile` function using useState
2. Create a `handleChange` function
   1. Using e.target.files to access to selected files by user
   2. Set retrieved files to variable `file`
3. Associate the `handleChange` function to the `input` element
4. Store `file` into a FormData object
5. Create a `handleUpload` function
   1. Using fetch/axios to post files
6. Associate the `handleUpload` function to the `button` element