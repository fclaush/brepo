---
layout: page
title: Java Script - Code Learn
summary: "Shows the code snippets used while learning JavaScript"
---

## WEB DEVELOPMENT COURSE

### Array

~~~
var guestlist = ["Frank", "Nico", "Mama"];

console.log(guestlist);
~~~

![JS Guestlist](images/)
This lists the array items and the number of array items.

~~~
var guestlist = ["Frank", "Nico", "Mama"];

console.log(guestlist.length);
~~~

This results in number of items in array.


## Prompt for checking an array
~~~
var guestList = ["Frank", "Nico", "Mama"];

var guestName = prompt ("What is your name?")

if (guestList.includes(guestName)) {
    alert("Welcome!");
} else {
    alert("Sorry maybe next time");
}
~~~
