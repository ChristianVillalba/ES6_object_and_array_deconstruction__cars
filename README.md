# ES6 Object & Array Destructuring
Created with [CodeSandbox](https://codesandbox.io/)  
Notes from: React module  
[The Complete 2021 Web Development Bootcamp](https://www.udemy.com/course/the-complete-web-development-bootcamp/)  
Instructor: Dr. Angela Yu

## Description
It renders without styles information about two cars:
* Brand and model
* Top Speed (km/h)
* Colour

This project may produce Errors in the console (DevTools).
The Errors are related to the structure of the HTML Elements.      

The goal of this lesson was to make it clear in how destructuring works in JavaScript ES6 and get some practice using the syntax.

---
## Notes
[Documentation: Destructuring assignment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)  

The stats that we render come from our practice.js file where there's a constant called cars.      
This is a relatively complex structure:      
It's an array with two objects inside the object.       
There's nested objects inside each object and there's also other nested arrays.      
 
### Destructuring Objects 

#### Destructuring an Array

eg: data.js     
```javascript
const animals = [
  { name: "cat", sound: "meow" },
  { name: "dog", sound: "woof" }
];
```
In order to destructure an Array, We need to create a new constant.      
I'm destructuring an array so the variable names go inside an Array Literal (square brackets```[]```)     
```javascript
const [cat, dog] = animals;
```
Our code has reached inside this array of animals pulled out the first item and assigned it a name of ```cat```,         
pulled out a second item and assigned it a name of ```dog```.         
It's exactly the same that:
```javascript
var cat = animals[0];
var dog = animals[1];
```
But obviously in a much more concise kind of syntax.
When destructuring anything into separate variable names,     
we need to use **unique names** for the **variables** inside our file.

If I decide to log the value of cat,      
```javascript
console.log(cat);
```
We can see it is just a single Object with two Properties: ```name``` and ```sound```.

#### Destructuring an Object

In order to destructure an Object, We need to create a new constant.      
I'm destructuring an Object so the variable names go inside an Object Literal (curly braces instead```{}```)       
Inside these curly braces we can pull out any of the properties that we want from the object.     
eg: the two properties of the ```cat``` Object
```javascript
const {name, sound} = cat;
```
These deconstructions are the equivalent to ```cat.name``` and ```cat.sound```     
If I decide to log the value of sound,      
```javascript
console.log(sound);
```
We will recieve the value *"meow"* 




When we are destructuring an array we could have basically called each of these destructured variables any name.       
When we are destructuring an object, these names have to match with the property names of that object (**key**: value).
If there is no match we will rec


---
## What I have learned with this project:
