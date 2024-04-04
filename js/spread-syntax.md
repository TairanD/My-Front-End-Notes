# Spread Syntax


The spread syntax for arrays is a feature in JavaScript used to expand or spread the elements of an iterable object, 
such as an array. It utilizes three dots (`...`) to spread or expand an iterable object. The spread syntax for arrays
can be used in various scenarios, including creating new arrays, merging arrays, and copying arrays. Let's delve 
into the usage of the spread syntax for arrays:

## 1 - Merging Arrays
The spread syntax for arrays can also merge multiple arrays into a single array. Here's an example:
```javascript
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];
const array3 = [7, 8, 9];
const mergedArray = [...array1, ...array2, ...array3];
console.log(mergedArray); // Output: [1, 2, 3, 4, 5, 6, 7, 8, 9]
```
In this example, elements from `array1`, `array2`, and `array3` are merged into `mergedArray`.

## 2 - Copying Arrays
The spread syntax for arrays can be utilized to create a copy of an array. Here's an example:
```javascript
const originalArray = [1, 2, 3];
const copiedArray = [...originalArray];
console.log(copiedArray); // Output: [1, 2, 3]
```
In this example, the spread syntax is used to copy all elements from `originalArray` into `copiedArray`.