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

## Array Method foreach
The `forEach()` method executes a provided function once for each element in an array. It’s useful for iterating over array elements without the need for managing indices manually.

`Key points about forEach():`
***Does not return anything:*** It returns undefined, meaning it does not produce a result like other array methods (e.g., map()).


***Does not execute for empty elements:*** If the array has holes (empty slots), the function will not be called for them.


***Callback function:*** The method accepts a callback function as its parameter, which is called for each element in the array.

```js
const numbers = [1, 2, 3, 4];
numbers.forEach(function(number, index) {
    console.log('Index:', index, 'Value:', number);
});
```

## Array Method Map
The `~map()` method creates a new array populated with the results of calling a provided function on every element in the calling array. It does not change the original array.

`Key points about map():`
1. ***Returns a new array:*** It returns a new array with the results of applying the callback function to each element.
2. ***Does not modify the original array:*** The original array remains unchanged.
3. ***Does not change the length of the array:*** The new array will have the same length as the original array, even if the callback function returns undefined or some value for every element.
4. ***Accepts a callback function:*** The callback function is called for each element, and the element is transformed based on the logic in the function.

`Syntax:`
```js
let newArray = array.map(function(currentValue, index, array) {
    // Code to return a new value for each element
});
```

```js
currentValue: The current element being processed in the array.
index (optional): The index of the current element.
array (optional): The array that map() was called upon.
```

```js
const numbers = [1, 2, 3, 4];
const doubled = numbers.map(function(number) {
    return number * 2;
});
console.log(doubled); // Output: [2, 4, 6, 8]
```


## Array Method Filter
The `filter()` method creates a new array with all elements that pass the test implemented by the provided function. It is useful when you want to exclude certain elements based on a condition.


Key points about `filter():`

1.  ***Returns a new array:*** Like map(), filter() returns a new array.
2.  ***Does not modify the original array:*** The original array remains unchanged.
3.  ***Can result in a smaller array:*** Unlike map(), which creates an array of the same size, filter() can result in a smaller array, depending on how many elements pass the condition.
4.  ***Accepts a callback function:*** The callback function is called for each element, and it returns true or false to decide whether the element should be included in the new array.


```js
const numbers = [1, 2, 3, 4, 5, 6];
const evenNumbers = numbers.filter(function(number) {
    return number % 2 === 0; // Only even numbers
});
console.log(evenNumbers); // Output: [2, 4, 6]
```

##  Array Method Filter 
The `find()` method in JavaScript returns the first element that satisfies the condition, not an array. It accepts three parameters: the current element, its index, and the entire array. Once it finds an element that meets the condition, it breaks out of the loop and returns that element. If no element satisfies the condition, it returns undefined.

Key points `find():`
1. ***find() does not return a new array;*** it returns the first matching element (or undefined if no element matches).
2. Once the condition is met for an element, it breaks and returns that element.


```js
const array1 = [5, 12, 8, 130, 44];

const found = array1.find((element) => element > 10);

console.log(found);
// Expected output: 12
```


##  Array Method toSorted
The `toSorted()` method is used to sort elements of an array (such as numbers or strings) without mutating the original array. Instead, it returns a new sorted array. This is particularly useful when you want to maintain the original order of the array.

Key Points `toSorted():`
 - Does Not Mutate Original Array: Unlike sort(), which sorts the array in place, toSorted() returns a new sorted array.
 - Works with Numbers and Strings: It can sort both strings and numbers. However, when sorting numbers, we typically use the formula a - b for numeric comparison to ensure the correct order.
 - String Sorting: When sorting strings, it uses the default lexicographical order (alphabetical order). It’s not ideal for numeric strings (e.g., "12", "2") because they are sorted lexicographically by default.
 - For Numbers: When dealing with numbers, we can specify a sorting function, like a - b, where:
     - a - b is used to sort numbers in ascending order.
     - If a - b is negative, it means a should come before b (swap).
     - If a - b is positive, it means a should come after b.

```js
const months = ["Mar", "Jan", "Feb", "Dec"];
const sortedMonths = months.toSorted();
console.log(sortedMonths); // ['Dec', 'Feb', 'Jan', 'Mar']
console.log(months); // ['Mar', 'Jan', 'Feb', 'Dec']

const values = [1, 10, 21, 2];
const sortedValues = values.toSorted((a, b) => a - b);
console.log(sortedValues); // [1, 2, 10, 21]
console.log(values); // [1, 10, 21, 2]
```
