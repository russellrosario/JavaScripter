# Array Methods

* [Create an array](#user-content-create-an-array)
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
* [Augment items within an array](#user-content-augment-items-within-an-array)
* [Return true if every item meets a condition](#user-content-return-true-if-every-item-meets-a-condition)
* [Return true if at least one item matches a condition](#user-content-return-true-if-at-least-one-item-matches-a-condition)
* [Execute a function once per array item](#user-content-execute-a-function-once-per-array-item)
* [Filter an array](#user-content-filter-an-array)
* [Detect an array](#user-content-detect-an-array)
* [Simple FIFO queue](#user-content-simple-fifo-queue)
* [Find index of an item](#user-content-find-index-of-an-item)
* [Randomise an array](#user-content-randomise-an-array)
* [Chaining Methods](#chaining-methods)

## Create an array

```javascript
var meals = ['breakfast', 'lunch', 'dinner'] ;
```

## Empty an array

Keeping references intact.

```javascript
var meals = ['breakfast', 'lunch', 'dinner'];
meals.splice(0, meals.length);
```

or

```javascript
var meals = ['breakfast', 'lunch', 'dinner'];
meals.length = 0
```

## Clone an array

```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

var copy = meals.slice();
// ['breakfast', 'lunch', 'dinner']
```

## Get last item

```javascript

var meals = ['breakfast', 'lunch', 'dinner'];

meals[meals.length - 1];
// 'dinner'
```

Or

```javascript
var meals = ['breakfast', 'lunch', 'dinner'];
meals.slice(-1)[0];
// 'dinner'
```

## Remove first item

```javascript

var meals = ['breakfast', 'lunch', 'dinner'];

meals.shift();
// 'breakfast'

meals;
// ['lunch', 'dinner']
```

## Remove last item

```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

meals.pop();
// 'dinner'

meals;
// ['breakfast', 'lunch'];
```

## Add new item(s) to beginning

```javascript
var meals = ['lunch', 'dinner'];

meals.unshift('breakfast');
// 3 - the array length

meals;
// ['breakfast', 'lunch', 'dinner']
```

## Add new item(s) to end

```javascript

var meals = ['breakfast', 'lunch', 'dinner'];

meals.push('supper');
// 2

meals;
// ['breakfast', 'lunch', 'dinner', 'supper'];
```

## Overwrite item at a specific index

```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

meals[1] = 'brunch';
// ['breakfast', 'brunch', 'dinner'];
```

Or
```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

meals.splice(1, 1, 'brunch');
```

## Add new item(s) at a specific index

```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

meals.splice(1, 0, 'brunch', 'more brunch');
// ['breakfast', 'brunch', 'more brunch', 'lunch', 'dinner']
```

## Remove single item at a specific index

```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

meals.splice(1, 1);
// ['lunch']

meals;
// ['breakfast', 'dinner']
```

## Remove several items

```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

meals.splice(1, 2);
// ['lunch', 'dinner']

meals;
// ['breakfast']
```

## Reverse an array

```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

meals.reverse();
// ['dinner', 'lunch', 'breakfast'];
```

## Delimit an array

```javascript

var meals = ['breakfast', 'lunch', 'dinner'];

meals.join(' AND ');
// 'breakfast AND lunch AND dinner'
```

## Sort in alphabetical order

```javascript

var meals = ['dinner', 'supper', 'breakfast', 'lunch'];

meals.sort();
// ['breakfast', 'dinner', 'lunch', 'supper']
```

## Sort in numerical order

```javascript
var numbers = [1438,2605,794,3947,6241,11745,2585];

numbers.sort(function(a, b) {
    return a - b;
});
// [794,1438,2585,2605,3947,6241,11745]
```

## Join two arrays together

```javascript
var dayTimeMeals = ['breakfast', 'lunch'];
var nightTimeMeals = ['merienda', 'dinner'];

var allTheMeals = dayTimeMeals.concat(nightTimeMeals);
// ['breakfast', 'lunch', 'merienda', 'dinner']
```

## Copy specific item(s)

```javascript
var meals = ['breakfast', 'lunch', 'dinner', 'supper'];

nightTimeMeals = meals.slice(2,4);
// ['dinner', 'supper']
```

## Augment items within an array

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
// true

meals.every(function(item){ return item.length > 6 });
// false
```

## Return true if at least one item matches a condition

```javascript
var meals = ['breakfast', 'lunch', 'dinner', 'supper'];

meals.some(function(item){ return item === 'lunch';});
// true

meals.some(function(item){ return item === 'burgers!!';});
//false
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
// ['lunch', 'dinner', 'supper'];
```
## Detect an array

```javascript
var meals = ['breakfast', 'lunch', 'dinner'];

Array.isArray(meals)
// true
```

## Simple FIFO queue

```javascript
var meals = ['breakfast', 'elevenses', 'brunch'];

meals.shift();
meals.push('lunch');

// ['elevenses', 'brunch', 'lunch']

meals.shift()
meals.push('afternoon tea');

// ['brunch', 'lunch', 'afternoon tea']
// ... and so on ...
```

## Find index of an item

```javascript
var meals = ['breakfast', 'elevenses', 'brunch'];
meals.indexOf('brunch');
// 2
```

## Randomise an array

```javascript
function randomiseArray(arr) {
    var buffer = [], start;

    for(var i = arr.length; i >= arr.length && i > 0;i--) {
        start = Math.floor(Math.random() * arr.length);
        buffer.push(arr.splice(start, 1)[0])
    };

    return buffer;
}

randomiseArray([0,1,2,3,4]);
// [2,1,0,3,4]

randomiseArray([0,1,2,3,4]);
// [3,2,1,4,0]

randomiseArray([0,1,2,3,4]);
// [1,2,4,0,3]
```

# Chaining methods

```javascript
var meals = [
  {type: 'breakfast', name: 'Full English', calories: 1500},
  {type: 'breakfast', name: 'Colacao', calories: 260},
  {type: 'breakfast', name: 'Croissant and jam', calories: 520},
  {type: 'breakfast', name: 'Granola with Greek yoghurt and blueberries', calories: 680},
  {type: 'brinner', name: 'Shepherds Pie with strawberry yoghurt', calories: 915},
  {type: 'brinner', name: 'Milky Porridge with beef and green beans', calories: 875},
  {type: 'dinner', name: 'Phad Thai', calories: 750},
  {type: 'dinner', name: 'Chicken Katsu curry and rice', calories: 830},
];

function getMealsByMaxCalories(meals, maxCalories, dailyAllowance) {
  return meals
    .filter(function(meal) {
        return meal.calories <= maxCalories;
    })
    .map(function(meal) {
        return {
            name: meal.name,
            calories: meal.calories,
            percentageOfDailyAllowance: meal.calories / dailyAllowance * 100
        }
    });
}

getMealsByMaxCalories(meals, 850, 2000);

/*
[
  {
    "name": "Colacao",
    "calories": 260,
    "percentageOfDailyAllowance": 13
  },
  {
    "name": "Croissant and jam",
    "calories": 520,
    "percentageOfDailyAllowance": 26
  },
  {
    "name": "Granola with Greek yoghurt and blueberries",
    "calories": 680,
    "percentageOfDailyAllowance": 34
  },
  {
    "name": "Phad Thai",
    "calories": 750,
    "percentageOfDailyAllowance": 37.5
  }
]
*/
```