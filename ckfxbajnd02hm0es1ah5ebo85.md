## Way to convert Javascript Object to an Array

It was a bit lengthy to convert `Object` to an `Array` in Javascript <br>
so we had to do something like this 😐
```
var animals = {
  cat: 1,
  dog: 2,
};

var keys = [];

for (var animal in animals) {
  if (animals.hasOwnProperty(animal)) {
    keys.push(animal);
  }
}

keys; // ["cat", "dog"]
``` 

### ES6 😎

Later `ES6` Introduced and we got easiest way  

Now, there is a built-in method that quickly turns all the keys of object into an array:

#### 1. Object.keys 🤩

```
var animals = {
  cat: 1,
  dog: 2,
};

const keys = Object.keys(animals);
 keys; // ["cat", "dog"]
``` 

#### 2. Object.values 🤟

Using `Object.values` we can extract the values into an array with one method. 

```
 var animals = {
  cat: 1,
  dog: 2,
};

const values = Object.values(animals);
values; 
 // [1,2]

``` 

#### 3. Object.entries 😍
using `Object.entries` now we will get both (keys and values) now 🥳

```
var animals = {
  cat: 1,
  dog: 2,
};

const entries = Object.entries(animals);
 entries; //  [['cat':1],['dog':2]]
``` 

