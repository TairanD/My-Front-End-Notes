# Event Object

## Definition
An object containing information about the event which is just happened.

## Scenario
1. An event occurs (click, submit, change, etc.)
2. -> the browser encapsulate information of this event to a generated object
   - the event objects contains various properties and methods
     - the type of event
     - the target element
     - mouse coordinates
     - keyboard keys pressed
     - ......
3. -> the browser pass this event object to the _event handler function_ (I think we can assume event handler functions 
as one type of recall functions) associated with the event
6. -> the event handler function is executed with the information provided by the event object.