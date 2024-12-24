# JavaScript-Callbacks
A callback function is a function passed into another function as an argument, It means the outer function uses the callback function to do something when it's needed or to finish its task.

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

## Array Callback

**Array Method foreach**
