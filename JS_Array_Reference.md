# JavaScript Array Reference Sheet

In this blog, I would like to discuss the different methods that JavaScript offers for arrays. This could work as a refresher or a concise guide if you are learning the language

## Array Methods

** Table of Contents **

- [Basic Array Methods](#section-1)
- [Array Search Methods](#section-2)
- [Array Sort Methods](#section-3)
- [Array Iteration Methods](#section-4)
- [Conclusion](#conclusion)

  <a id="section-1"></a>

### Section 1: Basic Array Methods

#### 1. Array .length

returns length of the array

```javascript
let nums = [1, 2, 3, 4];
print(nums.length);

// Output: 4
```

#### 2. Array .toString()

Converts array to comma separated string

```javascript
let cities = ["Mumbai", "Paris", "London"];
console.log(cities.toString());

// Output: Mumbai, Paris, London
```

#### 3. Array .at()

Returns the value of the element of the given index

```javascript
let languages = ["English", "French", "Hindi"];

console.log(languages.at(2));

// Output Hindi
```

#### 4. Array.join()

Joins the array elements into a string

```javascript
let heroes = ["Batman", "Superman", "Spiderman"];

hero_text = heroes.join(",");

console.log(hero_text);

// Output 'Batman, Superman, Spiderman'
```

#### 5. Array .pop()

Removes the last element from the array.

```javascript
let arr = [1, 2, 3, 4];
let arr2 = arr.pop();
console.log(arr2);

// output [1, 2, 3]
```

#### 6. Array .push()

Adds an element at the end of the array.

```javascript
let fruits = ["apple", "fig", "guava"];
fruits.push("mango");
console.log(fruits);

// Output ['apple', 'fig', 'guava', 'mango']
```

#### 7. Array .shift()

Removes the first element of the array.

```javascript
let arr = ["a", "b", "c", "d", "e"];
let arr2 = arr.shift();
console.log(arr2);

// Output ['b', 'c', 'd', 'e']
```

#### 8. Array .unshift()

Adds a new element at the start of the array.

```javascript
let people = ["Jack", "Mary", "Bob"];
people.unshift("Tom");
console.log(people);

// Output ['Tom', 'Jack', 'Mary', 'bob']
```

#### 9. Array delete()

Used to remove an element from the array.

WARNING!!! - should be avoided as it leaves a hole in the array. Alternate methods should be used such as pop(), shift(), etc...

```javascript
let arr = [1, 2, 3, 4];
delete arr[0];
console.log(arr);

// Output [2, 3, 4]
```

#### 10. Array concat()

Creates a new array by merging arrays.

```javascript
const arr1 = [1, 2, 3, 4];
const arr2 = [5, 6, 7, 8];

const numbers = arr1.concat(arr2);
console.log(numbers);

// Output [1, 2, 3, 4, 5, 6, 7, 8]

const cart1 = ['eggs', 'bread', 'jam'];
const cart2 = ['cereals', 'cookies', 'cake'];
const cart3 = ['milk', 'honey', 'cheese']

const shoppingBag = car1.concat(cart2, card3);
console.log(shoppingBag):

// Output: ['eggs', 'bread', 'jam', 'cereals', 'cookies', 'cake', 'milk', 'honey', 'cheese']
```

#### 11. Array copyWithin()

To copy array element/s from one position to another within the same array.

```javascript
/*
Syntax:
<array>.copyWithin(location, <index-from>, <index-upto>)
*/

// ** Copy all elements to index 2 **
const letters = ["a", "b", "c", "d", "e"];
letters.copyWithin(2, 0);
console.log(letters);

// Output ['a', 'b', 'a', 'b', 'c']

// ** Copy elements from index 0 to index 2, to(index position) 2

const arr = ["hi", "oh", "ah", "no", "ya"];
arr.copyWithin(2, 0, 2);
console.log(arr);

// Output [ 'hi', 'oh', 'hi', 'oh', 'ya' ]
```

Note:

> > > - copyWithin() overwrites existing value.
> > > - copyWithin() does'nt add elements to an array.
> > > - copyWithin() doe not change change the length of the array.

#### 12. Array .flat()

Used to flatten a multi-dimensional array.

```javascript
const arr = [
  [1, 2],
  [3, 4],
  [5, 6],
];
const result = arr.flat();
console.log(result);

// Output [1, 2, 3, 4, 5, 6]
```

#### 13. Array flatMap()

Maps all elements in the array and then flattens the array.

```javascript
const nums = [1, 2, 3, 4, 5];
const numsMapped = nums.flatMap((x) => [x, x * 10]);
console.log(numsMapped);

// Output [1, 10, 2, 20, 3, 30, 4, 40, 5, 50]
```

#### 14. Array.splice()

Used to add new items to an array.

```javascript
// Syntax:
<array>.splice(<index>,<no_of_items_to_remove>, <item_to_add>, <item_to_add2>)

const boys = ['Tom', 'Derek', 'Harry', 'Eric', 'Dennis'];

boys.splice(2, 2, 'Mohan', 'Paresh');
console.log(boys)

// 1. first parameter (2) is the index where the new item/s will be inserted.
// 2. second parameter (2) is the number of items to be removed.
// 3. next are the items to be inserted


/*
Output:
['Tom', 'Derek', 'Mohan', 'Paresh', 'Dennis'];
*/
```

The splice method can also be used to return the items removed or to simply remove the items

```javascript
const fruits = ["Apple", "Cherry", "Guava", "Mango", "Plum"];
const deleted_fruits = fruits.splice(2, 2);
console.log(deleted_fruits);

// Output ['Guava', 'Mango']
```

#### 15. Array.toSpliced( )

This method was introduced in ES2023. This method returns a new spliced array instead of altering the original array.

```javascript
const pets = ["Dog", "Cat", "Parrot", "Hamster", "Rabbit"];
// Removes 1 element from index 0
const new_pets = pets.toSpliced(0, 1);
console.log(new_pets)[
  // Output
  // 'Dog has been removed'
  ("Cat", "Parrot", "Hamster", "Rabbit")
];
```

#### 16. Array.slice()

Used to slice a piece of the array. This method returns a new array and does not alter the original array.

```javascript
const cars = ["Bugatti", "Lamborghini", "Ferrari", "Lotus"];
// Returns a new array starting form the element at index 1
const sliced_cars = cars.slice(1);
console.log(sliced_cars);

// Output
["Lamborghini", "Ferrari", "Lotus"]``;
```

You can also set a range of items to be sliced by entering a second parameter.

```javascript
const cars = ["Bugatti", "Lamborghini", "Ferrari", "Lotus"];
// Returns a slice array from index 1 upto index 3
const sliced_cars = cars.slice(1, 3);
console.log(sliced_cars);

// Output ['Lamborghini', 'Ferrari']
```

<a id="section-2"></a>

### Section 2: Array Search Methods

#### 1. Array indexOf()

This method return the index of the searched value in an array.

```javascript
Syntax:
array.indexof(<item_to_be_searched>,<from_position>)

- first parameter is the value you are searching for in the array.

- The second parameter is optional. It is used to specify the starting position of the search
```

If the searched value is not present the method return ' -1 '.

If the item occurs more than once in the array, then the index of the first occurrence will be returned.

```javascript
const arr = ["Japan", "China", "Russia", "Ghana"];
console.log(arr.indexOf("China"));

// Output 1
```

#### 2. Array lastIndexOf()

This method returns the index of the last occurrence of the specified search item.

```javascript
const flowers = ["Rose", "Daisy", "Lilly", "Tulip", "Daisy"];
console.log(lastIndexOf("Daisy"));

// Output 4
```

#### 3. Array includes()

This method searches for an element in an array and returns 'true' if it is present or 'false' if otherwise.

```javascript
const arr = ["bread", "jam", "butter"];
console.log(arr.includes("jam"));

// Output true

console.log(arr.includes("cheese"));

// Output false
```

#### 4. Array find()

This method returns the first array element that meets the test criteria.

```javascript
const nums = [1, 2, 3, 5, 5];
console.log(nums.find((item) => item % 2 === 0));

// Output 2
```

#### 5. Array findIndex()

This method iterates through each element of the array and returns the index of the element that passes the test function.

The function takes 3 parameters:

- value : The value of the element
- index : The index of the element
- array : The array itself (useful when you want to access the other elements of the array)

If none of the array elements pass the test function, it returns '-1'.

```javascript
const arr = [2, 4, 6, 7, 8, 9];

const first_odd_num = arr.findIndex(testFunction);

function testFunction(value, index, array) {
  return value % 2 !== 0;
}

console.log(first_odd_num);

// Output 3
```

#### 6. Array findLast()

This method iterates through each element of the array from the end and returns the value of the first element that passes the test function.

If none of the elements pass the test then this method returns 'undefined'.

```javascript
const numbers = [10, 59, 35, 65, 22];
console.log(numbers.findLast((value) => value > 50));

// Output 65
```

#### 7. Array findLastIndex()

This method iterates through each element of the array from the end and returns the index of the first element that matches the test function.

If none of the elements pass the test, then it returns '-1'

```javascript
const numbers = [1, 11, 2, 22, 3, 33];

console.log(numbers.findLastIndex((x) => x < 20));

// Output 4
```

<a id="section-3"></a>

### Section 3: Array Sort Methods

##### 1. Array sort()

This method sorts and array alphabetically.

```javascript
const arr = ["a", "e", "d", "b", "c"];
arr.sort();

console.log(arr);

// Output [ 'a', 'b', 'c', 'd', 'e' ]
```

##### 2. Array reverse()

This method reverses the elements in an array.

<mark>Note:</mark> This method alters the original array.

```javascript
const arr = ["a", "b", "c", "d", "e"];
arr.reverse();
console.log(arr);

// Output [ 'e', 'd', 'c', 'b', 'a' ]
```

##### 3. Array reverse sort

To reverse sort an array you can use both sort() and reverse() methods.

<mark>Note:</mark> This method alters the original array.

```javascript
let arr = ["a", "c", "d", "e", "b"];
arr.sort();
arr.reverse();

console.log(arr);

// Output [ 'e', 'd', 'c', 'b', 'a' ]
```

##### 4. Array toSorted()

This method returns a new sorted array. It does not alter the original array.

```javascript
arr = ["a", "d", "c", "e", "b"];
sorted_arr = toSorted(arr);
console.log(sorted_arr);

// Output [ 'a', 'b','c', 'd', 'e' ]
```

##### 5. Array toReversed()

This method returns a new reversed array. It does not alter the original array.

```javascript
arr = ["a", "b", "c", "d", "e"];
reversed_arr = toReversed(arr);
console.log(reversed_arr);

// Output ['e', 'd', 'c', 'b', 'a' ]
```

##### 6. Numeric Sort

The sort() method above cannot be used for sorting numbers. This is because the sort() method by default sorts values as strings. So, if we sort numbers as string then we will get wrong outputs.

```javascript
const nums = [1, 7, 9, 3, 8, 2, 4, 6, 5, 100];
nums.sort();
console.log(nums);

/*** Gives Incorrect results ***/

// Output [ 1, 100, 2, 3, 4, 5, 6, 7, 8, 9]
```

To overcome this problem, we need to use a comparison function.

```javascript
const nums = [1, 7, 9, 3, 8, 2, 4, 6, 5, 100];
nums.sort(function (a, b) {
  return a - b;
});
console.log(nums);

// Output
// [ 1, 2, 3, 4, 5, 6, 7, 8, 9, 100 ]
```

The compare function can also be used to sort the numbers in descending order.

```javascript
const nums = [1, 7, 9, 3, 8, 2, 4, 6, 5, 100];
nums.sort(function (a, b) {
  return b - a;
});
console.log(nums);

// Output
// [ 100, 9, 8, 7, 6, 5, 4, 3, 2, 1 ]
```

How does the compare function work?
The compare function iterates through the array elements and compares then 2 at a time <mark> (a, b)</mark>

- if the result is negative, the function will sort 'a' as a lower value than 'b'.
- if the result is positive, the function will sort 'a' as a higher value than 'b'.
- if the result is zero, then there is no change to the sort order.

##### 7. Array Random Sort

One of the popular methods to sort an array is the Fisher Yates method.

`Note: The array will shuffle each time you run the below code`

```javascript
const nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

for (let i = nums.length - 1; i > 0; i--) {
  let j = Math.floor(Math.random() * i + 1);
  let k = nums[i];
  nums[i] = nums[j];
  nums[j] = k;
}
console.log(nums);

// Output
// [ 1, 2, 3, 10, 6, 7, 5, 9,  8, 4 ]
```

##### 8. Array Minimum and Maximum values

The sort method can be used to find the minimum and maximum values in an array.

- the first element will be the minimum value for an array sorted in ascending order.

- the last element will be the maximum value for an array sorted in descending order.

```javascript
const nums = [111, 12, 63, 34, 15, 96, 27, 80, 19, 10];
nums.sort((a, b) => a - b);
const minimum = nums[0];
console.log("Minimum: ", minimum);
const maximum = nums[nums.length - 1];
console.log("Maximum: ", maximum);

// Output
/*
Minimum: 10
Maximum: 111
*/
```

##### 9. Array Math.min() and Math.max()

The method <code>Math.min.apply</code> and <code>Maht.max.apply</code> can be used to get the lowest or highest value from an array instead of sorting the whole array.

```javascript
const nums = [111, 12, 63, 34, 15, 96, 27, 80, 19, 10];

function myMin(arr) {
  return Math.min.apply(null, arr);
}

function myMax(arr) {
  return Math.max.apply(null, arr);
}

minimum = myMin(nums);
maximum = myMax(nums);
console.log("Minimum: ", minimum);
console.log("Maximum: ", maximum);

/*
Output:
Minimum:  10
Maximum:  111
*/
```

##### 10. Sorting Array of Objects

Object array too can be sorted using the `Array.sort()` method. You will need to use the compare function as well.

```javascript
const students = [
  { name: "John", age: 13 },
  { name: "Max", age: 18 },
  { name: "Jane", age: 15 },
  { name: "Chris", age: 11 },
];

// Sort Age in ascending order
const asc_sorted = students.sort((a, b) => a.age - b.age);

// Sort Age in descending order
const desc_sorted = students.sort((a, b) => b.age - a.age);

console.log("Ascending: ", asc_sorted);
console.log("Descending: ", desc_sorted);

/*
Output:

Ascending:  [
{ name: 'Max', age: 18 },
{ name: 'Jane', age: 15 },
{ name: 'John', age: 13 },
{ name: 'Chris', age: 11 }
]


Descending:  [
{ name: 'Max', age: 18 },
{ name: 'Jane', age: 15 },
{ name: 'John', age: 13 },
{ name: 'Chris', age: 11 }
]
*/
```

<a id="section-4"></a>

### Section 4: Array Iteration Methods

##### 1. Array forEach()

This method runs a callback function once on each of the array element.

The call back function can take three arguments:

- value - value of the item on which the function is acting.
- index - index reference of the array.
- array - the array itself

```JavaScript
const arr = [1, 2, 3, 4]
arr.forEach(makeDouble)

function makeDouble(value, index, array){
  console.log(value * 2);
}
/*
Output:
2
4
6
8
*/
```

##### 2. Array map()

This method creates a new array by running a callback function on each array element. If the array element is empty, then the function will not run on that particular array element. This method does not alter the original array.

The callback function takes three arguments:

- value - The value of the element.
- index - The index of the element.
- array - The array itself.

If the callback function only uses the value argument, then the index and array arguments are omitted.

```javascript
const nums = [1, 2, 3, 4, 5];
const thrice_nums = nums.map((value) => value * 3);
console.log(thrice_nums);

/*
Output:

[ 3, 6, 9, 12, 15 ]
*/
```

##### 3. Array flatMap()

This method returns a new array formed by running a call back function on each of the array elements and then flattening the array by one level.

```javascript
const arr = [1, 2, 3, 4, 5, 6];
// if element is even return [2, 2]
const arr2 = arr.flatMap((num) => (num % 2 === 0 ? [2, 2] : num));
console.log(arr2);

/*

Step 1: Even numbers are replaced with array [2,2]

Step 2: The [2,2] array is flattened and thus '2,2' is returned below. 

Output:

[1, 2, 2, 3, 2, 2, 5, 2, 2 ]

*/
```

##### 4. Array filter()

This method returns a new array by running a test on each element of the array provided by a callback function. Only the elements that pass the callback function test are returned.

```javascript
// Below code returns a new array with only the even numbers from the original array.

const arr = [1, 2, 3, 4, 5, 6];
const arr2 = arr.filter((item) => item % 2 === 0);
console.log(arr2);

/*
Output:
[ 2, 4, 6 ]
*/
```

##### 5. Array reduce()

This method executes a reducer function on each of the array elements and return a single value.

This method adds the value of the current element to the previous element. When the function runs the first time, there is no initial value of previous element unless it is supplied. Otherwise the value of the first array element is taken as the initial value and iteration starts from the index[1] instead of index[0].

`This method works from left to right in the array.`

The callback function takes four arguments:

- initial value = The initial value or previously returned value.
- value - Item value.
- index - Item index.
- array - the array itself.

```javascript
// Without Initial Value;
const arr = [1, 2, 3, 4, 5, 6];
// First element is taken as the initial value - in this case 1
// Iteration starts from second element by adding it's value to 1
// 1+2 = 3, 3+3 = 6, 6+4 = 10, 10+5 = 15, 15+5 = 21

const sum1 = arr.reduce((total, value) => total + value);

// With Initial Value;
const initialValue = 10;
// The initial value is provided  i.e 10
// Iteration starts from first element by adding it's value to 10
// 10+1 = 11, 11+2 = 13, 13+3 = 16, 16+4 = 20, 20+5 = 25, 25+6 = 31
const sum2 = arr.reduce(
  (total, value, initialValue) => total + value,
  initialValue
);

console.log("Sum1: ", sum1);
console.log("Sum2: ", sum2);

/* 
Output:

Sum1:  21
Sum2:  31
*/
```

##### 6. Array reduceRight()

This method runs a reducer function on each array element and reduces it to a single value.
This method runs from right-to-left. This method does not reduce the original array.

This method adds the value of the current element to the previous element. When the function runs the first time, there is no initial value of previous element unless it is supplied. Otherwise the value of the last array element is taken as the initial value and iteration starts from the array.length-2 instead of array.length -1.

`This method runs from right to left`

The call back (reducer) function takes four arguments:

- Initial Value: The provided initial value or the values of the last element of the array.
- value - The item value.
- index = The index of the item in the array.
- array - The array itself.

```javascript
// This code returns the sum of all the array elements.

// Without Initial Value;
const arr = [1, 2, 3, 4, 5, 6];
// First element is taken as the initial value - in this case 6
// Iteration starts from second to last element  - in this case 5
// 6+5 = 11, 11+4 = 15, 15+3 = 18, 18+2 = 20, 20+1 = 21

const sum1 = arr.reduceRight((total, value) => total + value);

// With Initial Value;
const initialValue = 10;
// First element is the provided initialValue i.e 10
// Iteration starts from last element i.e 6
// 10+6 = 16, 16+5 = 21, 21+4 = 25, 25+3 = 28, 28+2 = 30, 30+1 = 31
const sum2 = arr.reduceRight(
  (total, value, initialValue) => total + value,
  initialValue
);

console.log("Sum1: ", sum1);
console.log("Sum2: ", sum2);
```

##### 7. Array every()

This method runs a callback function test on every element of the array to check if it passes the test. It returns `true` if all the elements pass the test, else it returns `false`.

The callback function takes three arguments:

- value - The value of the element.
- index - The index of the element in the array.
- array = The array itself.

```javascript
const arr = [12, 33, 15, 55];
console.log(arr.every((element) => element % 5 === 0));

// Output: false
```

##### 8. Array some()

This method runs a callback function test on every element in the array and checks if some of the elements pass the test.

The callback function takes three arguments:

- value - The value of the element.
- index - The index of the element in the array.
- array - The array itself.

```javascript
const arr = [5, 10, 15, 20, 25, 30];
console.log(arr.some((element) => element > 20));

// Output: true
```

##### 9. Array.from()

This method returns an array from another iterable objects such as text, arrays, etc..

```JavaScript
const text = 'google'
console.log(Array.from(text))

// Output: [ 'g', 'o', 'o', 'g', 'l', 'e' ]

console.log(Array.from([1, 2, 3], (x) => x + x))
// the callback function passed at the end takes each element of the array and adds it to itself and then passes it into the new array.

// Output: [ 2, 4, 6 ]
```

##### 10. Array.keys()

This method returns a new iterator object that contains the keys for each index of the array.

```javascript
const friends = ["Harry", "Steve", "Larry", "Matt"];
const iterator = friends.keys();

for (let key of iterator) {
  console.log(key);
}
/*
Output:
  0
  1
  2
  3
*/
```

##### 11. Array.entries()

This method returns a new iterator object which contains the key-value pairs for each index of the array.

```javascript
const friends = ["Harry", "Steve", "Larry", "Matt"];
const iterator = friends.entries();

console.log(iterator.next().value);
console.log(iterator.next().value);
console.log(iterator.next().value);

/*
Output:

[ 0, 'Harry' ]
[ 1, 'Steve' ]
[ 2, 'Larry' ]
*/
```

##### 12. Array.with()

This method creates a copy of the array with modified value without altering the original array.

```javascript
const weekdays = ["Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"];

const newWeekdays = weekdays.with(1, "Monday");

console.log(newWeekdays);

/* 
Output:

[ 'Sun', 'Monday', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat' ]
*/
```

##### 13. Array Spread(...)

The spread method allows an array to be expanded into more objects zero or more arguments(for functions) or elements (for array literals) are expected.

```javascript
// For Functions
const sum = (x, y, z) => x + y + z;

const nums = [1, 2, 3];

result = sum(...nums);

console.log(result);

// Output: 6

// For array literals

const arr1 = ["a", "b", "c"];

const arr2 = ["d", "e", "f"];

const combine = [...arr1, ...arr2];

console.log(combine);

/*
Output:

[ 'a', 'b', 'c', 'd', 'e', 'f' ]
*/
```

<a id="conclusion"></a>

## Conclusion

I hope this will help you to get to know about the different array functions and would be helpful in someway in your coding journey. All the best, keep coding, keep creating...
