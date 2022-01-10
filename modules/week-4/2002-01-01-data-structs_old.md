---
title: Data Structures
module: 4
jotted: true
---

# Basic JS Data Structures

So far, you have learned about basic data types, including;

- Numbers
- Strings
- Booleans
- null
- undefined

You have also learned how to store a single piece of data with a binding or variable. However, there are many instances where it is necessary for you to reference and manage multiple pieces of data from a single binding. This could be for simplicity in your code, or because a collection of data is related and should be kept together.

> In computer science, a data structure is a particular way of organizing data in a computer so that it can be used efficiently. [From Wikipedia](https://en.wikipedia.org/wiki/Data_structure)

There are many different types of data structures. If you plan to work extensively with code after school (i.e. a developer job), you should take care to learn some of these. There are many resources for learning these, as a preview, you can check out;

- [Carnes, Beau. "10 Common Data Structures Explained with Videos + Exercises." freeCodeCamp. July 5th, 2017. Web.](https://medium.freecodecamp.org/10-common-data-structures-explained-with-videos-exercises-aaff6c06fb2b)

For this week, you are going to learn three simple, and highly common data structures that are used in JS.

- Arrays
- Objects
- and JSON (JavaScript Object Notation)

## Arrays

> An array is a data structure that contains a group of elements. Typically these elements are all of the same data type, such as an Number or string. Arrays are commonly used in computer programs to organize data so that a related set of values can be easily sorted or searched. [From Tech Terms](https://techterms.com/definition/array)

An array is a collection of data in "indexed" locations.

<div id="jotted-demo-1" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-1"), {
    files: [
        {
            type: "js",
            hide: false,
            content: `
// An array with 4 items
let myArray = [ "item1", "item2", "item3", "item4" ];

// retrieve the item at index 0
console.log( myArray[0] );
// -> returns "item1"

// retrieve the item at the end
console.log( myArray[myArray.length - 1] );
// -> returns "item4"

// add a new item
myArray.push( "new item" );
// retrieve the new item
console.log( myArray[myArray.length - 1] );
// -> returns "new item"
            `
        }
    ],
    showBlank: false,
    showResult: false,
    plugins: [
        { name: 'ace', options: { "maxLines": 50 } },
        { name: 'console', options: { autoClear: true } },
    ]
});
</script>


## JS Objects

> In JavaScript, objects can be seen as a collection of properties. With the object literal syntax, a limited set of properties are initialized; then properties can be added and removed. Property values can be values of any type, including other objects, which enables building complex data structures. Properties are identified using key values. A key value is either a String or a Symbol value.

In JS, the _object_ data structure can be used to create sets of different types of data. Each piece of data is stored within the _object_ using a unique _key value_ (aka. _identifier_).


<div id="jotted-demo-2" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-2"), {
    files: [
        {
            type: "js",
            hide: false,
            content: `
let myObject = {
    key1: 2,
    key2: "ha"
};

console.log(myObject.key1);
// -> 2

console.log( myObject["key2"] );
// -> "ha"

// add a new key:value pair
myObject.newKey = "Something New";

console.log( myObject["newKey"] );
// -> "Something New"
            `
        }
    ],
    showBlank: false,
    showResult: false,
    plugins: [
        { name: 'ace', options: { "maxLines": 50 } },
        { name: 'console', options: { autoClear: true } },
    ]
});
</script>

#### JSON

_JSON (**J**ava**S**cript **O**bject **N**otation)_ is a multi-language format for sharing collections of data. However, it is based on the JS Object, therefore, you will not have to really learn too much new. Instead, you need to make sure you learn about JS Objects, how to create them, manipulate them, and read them.


## Reading

To get started, please read the following, which cover the usage and definition of functions in great detail;

- Haverbeke, Marijn. **Eloquent JavaScript: A Modern Introduction to Programming.** 3rd Edition. N.p., 2018. Web.
    - [_Chapter 4; Data Structures: Objects and Arrays_](http://eloquentjavascript.net/3rd_edition/04_data.html)
- **JavaScript Guide.** MDN web docs. 2018. Web.
    - [_Indexed Collections_](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    - [_Working with objects_](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects)
    - [_Keyed Collections_](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Keyed_collections)

## Videos

#### Videos on the basic of _Arrays!

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/QEZXbRiaY1I" frameborder="0" allowfullscreen></iframe></div>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/MeZVVxLn26E" frameborder="0" allowfullscreen></iframe></div>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/EeZBKv34mm4" frameborder="0" allowfullscreen></iframe></div>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/Urwzk6ILvPQ" frameborder="0" allowfullscreen></iframe></div>


#### Videos about _Objects_

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/Gp5nnerXETg" frameborder="0" allowfullscreen></iframe></div>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/r6SnMjsLrBk" frameborder="0" allowfullscreen></iframe></div>

<div class="embed-responsive embed-responsive-16by9"><iframe class="embed-responsive-item" src="https://www.youtube.com/embed/B-k76DMOj2k" frameborder="0" allowfullscreen></iframe></div>

## Interactive JS Console

While you work on this chapter, you should use the following interactive JS console to test.

<div id="jotted-demo-0" class="jotted-theme-stacked"></div>

<script>
    new Jotted(document.querySelector("#jotted-demo-0"), {
    files: [
        {
            type: "js",
            hide: false,
            content: "// Your test code here!\n\n\n"
        }
    ],
    showBlank: false,
    showResult: false,
    plugins: [
        { name: 'ace', options: { "maxLines": 50 } },
        { name: 'console', options: { autoClear: false } },
    ]
});
</script>
