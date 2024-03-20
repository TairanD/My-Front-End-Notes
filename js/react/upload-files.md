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