# Array and Object methods

* [Empty an array](#user-content-empty-an-array)
* [Clone an array](#user-content-clone-an-array)
* [Get last item](#user-content-get-last-item)
* [Get consecutive item(s)](#user-content-get-last-item)
* [Remove first item](#user-content-remove-first-item)
* [Remove last item](#user-content-remove-last-item)
* [Remove single item at a specific index](#user-content-remove-single-item-at-a-specific-index)
* [Remove several items](#user-content-remove-several-items)
* [Add new item(s) to beginning](#user-content-add-new-items-to-beginning)
* [Add new item(s) to end](#user-content-add-new-items-to-end)
* [Add new item(s) at a specific index](#user-content-add-new-items-at-a-specific-index)
* [Overwrite item at a specific index](#user-content-overwrite-item-at-a-specific-index)
* [Reverse an array](#user-content-reverse-an-array)
* [Sort in numerical order](#user-content-sort-in-numerical-order)
* [Sort in alphabetical order](#user-content-sort-in-alphabetical-order)
* [Shuffle array](#user-content-randomise-an-array)
* [Join array items into a string](#user-content-delimit-an-array)
* [Split string into an array](#user-content-delimit-an-array)
* [Join two arrays together](#user-content-join-two-arrays-together)
* [Find array intersection](#user-content-join-two-arrays-together)
* [Remove duplicates from array](#user-content-join-two-arrays-together)
* [Map items to a new array](#user-content-map-items-to-a-new-array)
* [Filter an array](#user-content-filter-an-array)
* [Reduce an array](#user-content-reduce-an-array)
* [Execute a function once per array item](#user-content-execute-a-function-once-per-array-item)
* [Every item meets a condition](#user-content-return-true-if-every-item-meets-a-condition)
* [One item meets a condition](#user-content-return-true-if-at-least-one-item-matches-a-condition)
* [Find index of an item](#user-content-find-index-of-an-item)
* [Detect an array](#user-content-detect-an-array)
* [Spread array rest parameters](#user-content-reduce-an-array)
* [Clone an object(s) (shallow)](#user-content-reduce-an-array)
* [Loop over object's key value pairs](#user-content-reduce-an-array)
* [Fix object states](#user-content-reduce-an-array)


## Empty an array
```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

array.splice(0, meals.length);
// OR
array.length = 0
```

## Clone an array
```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

var copy = meals.slice()
// OR
var copy = [...meals]
```

## Get last item
```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

meals[meals.length - 1];
// OR
meals.slice(-1)[0];
```
## Get consecutive items
```javascript
var meals = ['breakfast', 'brunch', 'lunch', 'dinner'];

meals.slice(2,4);
```
nightTimeMeals =

## Remove first item
```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

meals.shift();
```

## Remove last item
```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

meals.pop();
```

## Add new item(s) to beginning
```javascript
var meals = ['lunch', 'dinner'];

meals.unshift('breakfast');
```

## Add new item(s) to end
```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

meals.push('supper');
```

## Overwrite item at a specific index
```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

meals[1] = 'brunch';
// OR
meals.splice(1, 1, 'brunch');
```

## Add new item(s) at a specific index
```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

meals.splice(1, 0, 'brunch', 'more brunch');
```

## Remove single item at a specific index
```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

meals.splice(1, 1);
```

## Remove several items
```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

meals.splice(1, 2);
```

## Reverse an array
```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

meals.reverse();
```

## Join array items into a string
```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

meals.join(' AND ');
```

## Split string into an array
```javascript
var string = "breakfast AND lunch AND dinner"

var meals = string.split(' AND ');
```

## Sort in alphabetical order
```javascript
var meals = ['dinner', 'supper', 'breakfast', 'lunch'];

meals.sort();
```

## Sort in numerical order
```javascript
var numbers = [1438,2605,794,3947,6241,11745,2585];

numbers.sort(function(a, b) {
    return a - b;
});
```

## Join two arrays together
```javascript
var dayTimeMeals = ['breakfast', 'lunch'];
var nightTimeMeals = ['merienda', 'dinner'];

var allTheMeals = dayTimeMeals.concat(nightTimeMeals);
// OR
var allTheMeals = [...dayTimeMeals, ...nightTimeMeals]
```

## Find array intersection
```javascript
var animals = ['fish', 'bird', 'gorilla', 'dog']
var mammals = ['horse','gorilla','human','dog']

animals.filter(function(n) {
    return mammals.indexOf(n) !== -1;
});
```

## Remove duplicates from array
```javascript
var numbers = [1, 1, 1, 5, 6, 4]

numbers = [...new Set(numbers)]
```

## Map items to a new array
```javascript
var meals = ['breakfast', 'lunch', 'dinner'];
var type = ['king', 'prince', 'pauper'];

meals.map(function(item, i) {
  return item + ' like a ' + type[i];
});
// ["breakfast like a king", "lunch like a prince", "dinner like a pauper"]
```

## Return true if every item meets a condition
```javascript
var meals = ['breakfast', 'lunch', 'dinner', 'supper'];

meals.every(function(item){ return item.length > 0 });
```

## Return true if at least one item matches a condition
```javascript
var meals = ['breakfast', 'lunch', 'dinner', 'supper'];

meals.some(function(item){ return item === 'lunch';});
// OR
meals.includes('lunch')
```

## Execute a function once per array item
```javascript
var meals = ['breakfast', 'lunch', 'dinner', 'supper'];

meals.forEach(function(currentValue, index, arr){  console.log(index, currentValue, arr)})
// OR
for (item in meals) { console.log(meals[item])}
```

## Filter an array
```javascript
var meals = ['breakfast', 'lunch', 'dinner', 'supper'];

meals.filter(function(item) {
  return item !== 'breakfast';
});
```
## Detect an array
```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

Array.isArray(meals)
```

## Find index of an item
```javascript
var meals = ['breakfast', 'elevenses', 'brunch'];
meals.indexOf('brunch');
```

## Shuffle array
```javascript
function randomiseArray(arr) {
    var buffer = [], start;

    for(var i = arr.length; i >= arr.length && i > 0;i--) {
        start = Math.floor(Math.random() * arr.length);
        buffer.push(arr.splice(start, 1)[0])
    };

    return buffer;
}
```
## Reduce an array
```javascript
var numbers = [30, 41, 466, 44];

var sum = numbers.reduce((total, amount) => total + amount);
```

## Spread array into function parameters
```javascript
let numbers = [9, 4, 7, 1];

Math.min(...numbers); // 1
```

## Clone a object(s) (shallow)
```javascript
const obja = {a: 1, b: 2};
const objb = {a: 3, d: 4};
const copy = {
    ...obja,
    ...objb
  }
```

## Loop over object's key value pairs
```javascript
var myObject = {a: 1, b: 2, c: 3};
for (var prop in myObject) {
  console.log(prop + myObject[prop])
}
```

## Modify object states
```javascript
Object.freeze(object) // prevent mutation and deletion
Object.seal(object) // allow mutation, but no additions or deletions to state
```







