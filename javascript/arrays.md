# Array Methods

* [Empty an array](#user-content-empty-an-array)
* [Clone an array](#user-content-clone-an-array)
* [Get last item](#user-content-get-last-item)
* [Remove first item](#user-content-remove-first-item)
* [Remove last item](#user-content-remove-last-item)
* [Add new item(s) to beginning](#user-content-add-new-items-to-beginning)
* [Add new item(s) to end](#user-content-add-new-items-to-end)
* [Overwrite item at a specific index](#user-content-overwrite-item-at-a-specific-index)
* [Add new item(s) at a specific index](#user-content-add-new-items-at-a-specific-index)
* [Remove single item at a specific index](#user-content-remove-single-item-at-a-specific-index)
* [Remove several items](#user-content-remove-several-items)
* [Reverse an array](#user-content-reverse-an-array)
* [Delimit an array](#user-content-delimit-an-array)
* [Sort in numerical order](#user-content-sort-in-numerical-order)
* [Sort in alphabetical order](#user-content-sort-in-alphabetical-order)
* [Join two arrays together](#user-content-join-two-arrays-together)
* [Copy specific item(s)](#user-content-copy-specific-items)
* [Map items to a new array](#user-content-augment-items-within-an-array)
* [Return true if every item meets a condition](#user-content-return-true-if-every-item-meets-a-condition)
* [Return true if at least one item matches a condition](#user-content-return-true-if-at-least-one-item-matches-a-condition)
* [Execute a function once per array item](#user-content-execute-a-function-once-per-array-item)
* [Filter an array](#user-content-filter-an-array)
* [Detect an array](#user-content-detect-an-array)
* [Simple FIFO queue](#user-content-simple-fifo-queue)
* [Find index of an item](#user-content-find-index-of-an-item)
* [Shuffle array](#user-content-randomise-an-array)

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

var copy = meals.slice();
```

## Get last item
```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

meals[meals.length - 1];
// OR
meals.slice(-1)[0];
```

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

## Delimit an array
```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

meals.join(' AND ');
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
```

## Copy specific item(s)
```javascript
var meals = ['breakfast', 'lunch', 'dinner', 'supper'];

nightTimeMeals = meals.slice(2,4);
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
```

## Execute a function once per array item
```javascript
var meals = ['breakfast', 'lunch', 'dinner', 'supper'];

meals.forEach(function(currentValue, index, arr){
  console.log(index, currentValue, arr);
});
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