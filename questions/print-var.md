# Cannot print a variable's detailed information

# 1 - Problem Context and Statement
When I was using `console.log()` method to check the value of a state variable `data`. I used `console.log('data:',data)`
and the result is `[object, Object]`, instead of the detailed information inside the variable.

# 2 - Answer
When you use `console.log('data: ' + data)` in JavaScript, it actually converts data to a string and then concatenates it 
with the string 'data:', resulting in the output `data: [object Object]` where `[object Object]` is the **_default toString 
output_** for an object. This is because when an object is converted to
a string, it usually results in `[object Object]`, as that's the default behavior of the `toString()` method for most 
objects.

Using `console.log(data)` directly avoids this issue. It logs the object `data` itself, rather than converting it to a 
string. 
This way, you get to see the detailed information about the object, including its properties and values.