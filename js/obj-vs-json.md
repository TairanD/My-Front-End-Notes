# Object vs JSON (Js)

## Object

### Definition
In JavaScript, an object is a composite data type defined using curly braces `{}` and contains zero or more key-value
pairs.

```javascript
let me = {
    name: 'John',
    age: 22,
    isStudent: true
};
```

### Key-Value Pairs
Each key-value pair in an object consists of a key, which is a **string or symbol**, and its corresponding
value, which can be of **any data type**, including numbers, strings, booleans, functions, or even other objects.

## JSON 

### Definition
Data Exchange Format: JSON is a lightweight data exchange format used for passing and storing data between different programs.
```json
{
    "name": "John",
    "age": 25,
    "isStudent": false
}
```
### Strict Syntax 
JSON has strict syntax rules: data must exist in key-value pairs, and keys and string values must be enclosed in double quotes. Arrays and objects are the two compound data types in JSON.
Strings in JSON must use double quotes, whereas in JavaScript objects, keys do NOT necessarily require 
double quotes.