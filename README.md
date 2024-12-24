# JavaScript-Callbacks

<img src="https://i.ytimg.com/vi/qtfi4-8dj9c/hq720.jpg?sqp=-oaymwE7CK4FEIIDSFryq4qpAy0IARUAAAAAGAElAADIQj0AgKJD8AEB-AHUBoAC4AOKAgwIABABGH8gFihMMA8=&rs=AOn4CLAOqIxFXGgEDc4p3INMKY8AbGoJbA">


A callback function is a function passed into another function as an argument, It means the outer function uses the callback function to do something when it's needed or to finish its task.

<img src="https://i0.wp.com/jscurious.com/wp-content/uploads/2020/12/callback_functions_javascript_jscurious.jpg?fit=1182%2C645&ssl=1">


```Example:``` Calling Your Friend
You tell your friend to call you when they’re done with their homework.


Your friend is the outer function, and your phone number is the callback function.

```js
function doneHomework() {
  console.log("I finished my homework!");
}

function friend(callback) {
  console.log("I'm doing my homework...");
  callback(); // Call the callback function when homework is done
}

// Pass the 'doneHomework' function as the callback
friend(doneHomework);
```

```What Happens:```
The outer function (friend) is working on homework.

Once it's done, it calls back the doneHomework function.

# Array Callback

**Array Method foreach**
The `forEach()` method executes a provided function once for each element in an array. It’s useful for iterating over array elements without the need for managing indices manually.

`Key points about forEach():`
Does not return anything: It returns undefined, meaning it does not produce a result like other array methods (e.g., map()).


Does not execute for empty elements: If the array has holes (empty slots), the function will not be called for them.


Callback function: The method accepts a callback function as its parameter, which is called for each element in the array.
