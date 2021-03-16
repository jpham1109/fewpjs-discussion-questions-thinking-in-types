# Discussion Questions: Thinking in Types

## Objectives

- Recall the datatypes in JavaScript
- Identify the types of different data
- Identify the types of input and output of functions and operators

## JS Data Types Review Questions

1. What are the basic data types in JavaScript? Fill in the table of types below with descriptions of the types and the operators that work on them.

2. `Object` is the basic data type that we use to build other, more specialized 'types' of data. Name some of the ways that `Object` is used in JavaScript (e.g. what other types are really `Object` underneath).

## Exercise - Thinking in Types

When writing a function, it's often helpful to start by considering the inputs and the output. In particular, knowing the data type of the inputs and the data type of the outputs lets you know what kinds of operations are allowed on those arguments. They also hint at what the 'right' operations to do are.

For the following functions, fill in the table with the types of the inputs and the types of the outputs.

| Function                                         | types of inputs                  | type of output                |
| ------------------------------------------------ | -------------------------------- | ----------------------------- |
| `function addFive(number) { return number + 5}`  |       all datatypes              |    integer, except for string |
| `function sum(a, b) { return a + b }`            |               ""                 |              ""               |
| `function concat(a, b) { return "Yes!" + a + b + "!" }` |      all data types       |         all string            |
| `document.querySelector`                         |tag name of element of document   |  that element, all of it      |
| `function sayHi(a) { return "Hi, " + a.b + "!" }`|             all data types       |           undefined           |
| `function compare(a) { return a.length > 5 }`    | everything except null, undefined|            boolean            |


### "Shapes" of `Object`s

Many functions operate on `Object` types that need to have particular keys. In such cases, it's useful to name the 'shapes' of `Object` that functions expect in order to help you think about the functionality. You might say that a 'Person' is an `Object` that has keys 'name' and 'age'. You might write:

```js
// Person: {
//  name: string,
//  age: number,
// }
```

to represent the 'shape' of a Person.

When you have functions like the following, you can use the shorthand to write the type of the input and output.

```js
function getName(person) {
  return person.name;
}

function getAge(person) {
  return person.age;
}

function makePerson(name, age) {
  return {
    name: name,
    age: age
  };
}

function birthday(person) {
  person.age += 1;
  return person;
}

function getDistance(pointA, pointB) {
  return Math.sqrt((pointA.x - pointB.x) ** 2 + (pointA.y - pointB.y) ** 2);
}
```

Fill in the table using the 'shape' shorthand

| Function      | types of inputs                  | type of output           |
| ------------- | -------------------------------- | ------------------------ |
| `getName`     |    Person: { name: string }      |        string            |
| `getAge`      |                                  |                          |
| `makePerson`  |                                  |                          |
| `birthday`    |                                  |                          |
| `getDistance` |                                  |                          |


### Functions that take in functions as arguments

Some functions take in functions as arguments ('callback functions'). If those functions will be called with particular types of arguments, it's helpful to specify the type of function that will be passed in.

> Note: you may see the word `void` or `undefined` meaning 'this function does not return anything'

Fill in the rest of the table.

| Function                       | types of inputs                  | type of output                | callback function  type of inputs |
| ------------------------------ | -------------------------------- | ----------------------------- | ------------------------------------------------------- |
| `Array.prototype.forEach`      |      callback function           |    undefined                  |  currentValue: number, index: number, arr: array  |                                                    |
| `Array.prototype.map`          |                                  |                               |           |                                 
| `Array.prototype.find`         |                                  |                               |          |                                   
| `Array.prototype.filter`       |                                  |                               |           |                                 
| `Array.prototype.reduce`       |                                  |                               |          |                                   
| `window.setTimeout`            |                                  |                               |           |                                 

