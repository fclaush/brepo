---
title: FizzBuzz - A JavaScript program
layout: page
summary: "Many programmers..."
---

> Credits to Angela Yu, The App Brewery [Udemy Course, Web Development](https://www.udemy.com/course/the-complete-web-development-bootcamp/)


## Story about FizzBuzz

Now one of the most common questions that you're going to encounter on any programming interview is something called FizzBuzz, and it's a really simple problem and this is usually how they would define it.

So you have to write a program that prints the numbers from 1 to 100. But for multiples of three print "Fizz" instead of the number and for the multiples of five print "Buzz".

For numbers which are multiples of both three and five, for example fifteen, then print "FizzBuzz" instead of the number.

So it's pretty simple, but it's a really easy way of seeing how you solve problems and demonstrating a candidate's programming skills.

And just the other day I came across a article on Coding Horror, which is one of my favorite blogs, about why can't programmers program.

And the interesting thing that they talk about is what seems to be common knowledge amongst programming recruiters, and the fact of the matter is that out of 200 applicants there's probably only one person who can actually code.

And this is a really strange phenomenon. Part of the reason is down to the fact that completing computer science degrees doesn't necessarily enable people to code, and a lot of people will graduate from a computer science degree and they might know how, say, compilers work or, you know, some aspects of computer history, but they might not actually know exactly how to write good code.

One of the most interesting statistics I came across is that in the UK some of the most in-demand jobs involve programming and software development, and yet the university degree that has the highest unemployment rate happens to be computer science, which is really really strange.

So I'm going to use this classic interview question and I'm going to make it even more difficult because we're going to use it to learn all about arrays but on a slightly deeper level.

So let's try and be better than 199 of programming interviewees, and let's look at this FizzBuzz problem and use it to learn more about arrays.

[Read more about FizzBuzz here:](https://blog.codinghorror.com/fizzbuzz-the-programmers-stairway-to-heaven/)



## Code

```
var output = [];
var count = 1;


function fizzBuzz() {

if (count % 3 === 0 && count % 5 === 0) {
    output.push("FizzBuzz");
}

else if (count % 3 === 0) {
    output.push("Fizz");
}
else if (count % 5 === 0) {
    output.push("Buzz");
}
else {
    output.push(count);
}

count++;
//comment in JS

     console.log(output);
}
```


## While Loop

```
var output = [];
var count = 1;


function fizzBuzz() {

    while (count <= 100) {

if (count % 3 === 0 && count % 5 === 0) {
    output.push("FizzBuzz");
}

else if (count % 3 === 0) {
    output.push("Fizz");
}
else if (count % 5 === 0) {
    output.push("Buzz");
}
else {
    output.push(count);
}

count++;
//comment in JS

}

     console.log(output);
}
```

## For

```
For (var i=1;i<2;i++) {
  console.log (i);
}
```

```
var output = [];
var count = 1;


function fizzBuzz() {

    for (var count = 1; count <= 100; count++) {

if (count % 3 === 0 && count % 5 === 0) {
    output.push("FizzBuzz");
}

else if (count % 3 === 0) {
    output.push("Fizz");
}
else if (count % 5 === 0) {
    output.push("Buzz");
}
else {
    output.push(count);
}


//comment in JS

}

     console.log(output);
}
```
