# ES6 Object & Array Destructuring
Created with [CodeSandbox](https://codesandbox.io/)  
Notes from: React module  
[The Complete 2021 Web Development Bootcamp](https://www.udemy.com/course/the-complete-web-development-bootcamp/)  
Instructor: Dr. Angela Yu

## Description
It renders information about two cars:
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
 
### Destructuring

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
We will recieve the value *"meow"* as if it where ```console.log(animals[0].sound)```
But "sound" is not a good variable name in our case...

### Naming Variables: Differences destructuring Arrays and Objects 

When we are destructuring an Array, we could have called each of these destructured variables any name.       
When we are destructuring an Object, these names have to match with the property names of that object (**key**: value).      
If there is no match we will receive the output **undefined**.

If we wanted to actually give these variables a different name,    
we can add a colon followed by our choosen variable name.           
eg: destructuring the properties of our ```cat``` and ```dog``` Objects
```javascript
const { name: catName, sound: catSound } = cat;
const { name: dogName, sound: dogSound } = dog;
```
And now the properties are very clear and easy to retrieve
```javascript
console.log(catSound);
```
We will recieve the value *"meow"*.

This is really useful especially when we are getting hold of data from public APIs      
where you didn't get the chance to name the properties inside those JSONs.

### Providing a Default Values

If we want to give a custom default value to *undefined* fields:      
```javascript
const { catColor = "Blue" } = cat;
```
This basically says: "If name is *undefined*, then use this value instead".         
This is also really helpful because sometimes, when you're getting data from the Internet,      
and any undefined fields might may cause our app or website to just crash.
However this won't work if the value is already defined:
eg: ```const { catSound = "Purr"} = cat;``` won't work, the value is already *"meow"*

### Nested Objects

We can find Objects nested inside our Objects.     
And we can deconstructure its properties too.       
eg: practice.js - the top speed of the Honda Civic.       
```javascript
const cars = [
  {
    model: "Honda Civic",
    //The top colour refers to the first item in the array below:
    //i.e. hondaTopColour = "black"
    coloursByPopularity: ["black", "silver"],
    speedStats: {
      topSpeed: 140,
      zeroToSixty: 8.5
    }
  },
  {
    model: "Tesla Model 3",
    coloursByPopularity: ["red", "white"],
    speedStats: {
      topSpeed: 150,
      zeroToSixty: 3.2
    }
  }
];
```
eg: top speed of the Honda Civic Deconstructured
```javascript
const [honda, tesla] = cars;
const {
  speedStats: { topSpeed: hondaTopSpeed }
} = honda;
```
First, we destructure the Elements inside the Array ```cars``` (in practice.js): ```const [honda, tesla] = cars;```       
Using square braces ```[]``` because it's an Array.        
Then, we destructure the Nested Object:         
We start out with a const and our object: ```const {} = honda```    
Using curly braces ```{}``` because it's an Object.        
We deconstructure the property, as always: ```const {speedStats} = honda``` ...      
And we add a colon ```:``` but instead of giving it an alternative name,      
we open up a set of curly braces ```{}```because it's an Object: ```const {speedStats:{} = honda```       
and we pull out the values inside: ```const {speedStats:{topspeed} = honda```       
Finally, we rename *topSpeed* to "hondaTopSpeed" so the name is clearer       
```const {speedStats:{topSpeed: hondaTopSpeed} = honda;```



---
## What I have learned with this project:
* Destructuring:
  * Destructuring an Array
  * Destructuring an Object
  * Destructuring Nested Objects
* How to name Variables when destructuring
* Provide Default Values 

