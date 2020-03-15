---
title: JavaScript - DrumKit
layout: page
summary: "Building a Drumkit on a website"
---

## DrumKit - Adding Event Listener To A Button

> Credits to Angela Yu, The App Brewery [Udemy Course, Web Development](https://www.udemy.com/course/the-complete-web-development-bootcamp/)



Set up the Project with the files index.html, the index.js, and the styles.css open side by side

inside Atom,

link up the index.js with our index.html and test it using an alert.

In index.html:

```
<script src="index.js" charset="utf-8"></script>
```

In index.js:

```
alert("Hello!");
```


So as we did before we always put our scripts right at the end just before the body closing tag.

And we use the script with a source. So the source is of course index.js, and hit save, and then let's

just give it a test as always with a simple alert just to make sure that everything is linked up properly

and it's working.

And so now inside our index.html we've got a link to our stylesheet,

we’ve got a script that points to our index.js, and we're ready to begin.

Now, at the moment, even though I have all of these buttons on my web site, nothing actually happens when

I press on them,

right?

Absolutely nothing happens.

Now in order to start registering the button clicks, I need to add what we call an event listener to

it,

so the buttons will let me know when a user clicks on it.

Now inside our index.js, let's first create a function that does something when the button gets

clicked.

So let's call this function handleClick, and it's going to take no inputs, but it will carry out an alert

that says “I got clicked!”. And we basically want our button to trigger this function when it receives a click.

So in order to do that we first have to select our button inside the HTML and add an event listener that

listens

for when it gets clicked, and when it does, to call this function called handleClick.

```
function handleClick () {
  alert("Hello!");  
}
```


So first of course we'll need to tap into the document and then we'll querySelector for our button.

Now I'm only targeting the first button here just so that we can see what's going on before we start trying to do this to all the buttons.

```
document.querySelector ("button")
```

All right. So now that I've selected my first button, the next step is to add an event listener, and the

method for it is pretty much what it sounds like. It’s addEventListener.

```
document.querySelector("button").addEventListener
```

Now if we take a look inside the documentation, as you always should when you’re using a new method or a new property, then you can see that the method addEventListener sets up a function to be called whenever the specified event is delivered to the target.

[MDN](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)

So the target in our case is the object that we're calling the method addEventListener on, which in

our case is simply just going to be the first button on our web page, and then we're calling the method

addEventListener. And this event listener usually has two parameters.

The first one is the type which is a case sensitive string representing the event type to listen to.

> ###### Syntax
target.addEventListener(type, listener [, options]);
target.addEventListener(type, listener [, useCapture]);
target.addEventListener(type, listener [, useCapture, wantsUntrusted  ]); // Gecko/Mozilla only


And if you click on this link you can see all of the different event types that you can listen to.

[Event Listener](https://developer.mozilla.org/en-US/docs/Web/Events)


But in our case we're just looking for something really really simple which is simply the click event

which means that the mouse clicked on the button. So let's go ahead and add that click event. And remember we have to add it as a string. So that's the first parameter done.

```
document.querySelector("button").addEventListener("Click", )
```

Now what about the second parameter?

Well, the second parameter is a listener,

and this usually is a Javascript function that's going to be called when that click event gets detected.

So, in our case, we're going to call our function handleClick.

```
document.querySelector("button").addEventListener("Click", handleClick )
```


So what this line of code does is it finds the first button in our document, which is the w drum button,

and then it adds a event listener to that button so that it listens for clicks that happen on that button.

![Index.html - First Button](/images/js_drum_kit_1st_btn.png)

And when it does it runs the code inside the function handleClick, and that should send us an alert

saying "I got clicked!".

So let's try it out. Let's refresh our web site, and if you remember I only added that event listener to

the first button.

```
document.querySelector("button").addEventListener("click", handleClick);

function handleClick () {
  alert("I got Clicked!");
}
```


So if we click any of these other buttons still nothing will happen.

But when I click on the first button, then you can see that we've got the message "I got clicked!".

So that means that this button is listening for every time that the user clicks on it and we're able

to get it to call a method every single time

it does get clicked.


Now the keen eyed amongst you might have noticed that the way that we're calling our function is a little

bit different from usual, namely we normally call or function with a set of parentheses,

but in this case we're not using it.

```
document.querySelector("button").addEventListener("click", handleClick());

function handleClick () {
  alert("I got Clicked!");
}
```


Now why is that?

Well let's see what happens when we do add the parentheses.

So let's save and let's refresh our web site.

Now you'll notice that immediately this alert gets called, and this is the problem.

What happens is that our code will run and run and run until it hits the script tag and then it'll go

and find the index.js file that we specified in the script tag and it'll run this line of code.

Now if we add the parentheses here, then this is a straight up method call, and it will call that

method straight away when it's adding the event listener.

Now that's not what we want to happen.

We don't want this function to trigger as soon as the event listener is added,

right?

No, we want it to trigger when the click happens.

So in that case instead of calling our function as we would with the parentheses we're passing in the

name of the function as an input.

So that means that we're waiting for this click event to happen before we call the handleClick function.

And this is a bit of a logical jump that you'll have to make in order to understand a lot of things

in Javascript.

It's the idea of passing a function as an input so that it can be called at a later time.

Now there's other ways that you'll see this part written out in the wild.

The most common way is, instead of adding a function name here that calls the function later on,

most people will write this code as simply an anonymous function.

```
document.querySelector("button").addEventListener("click", function () {
  alert("I got Clicked!");
});
```


So anonymous functions look pretty much exactly the same as a normal function but they're just anonymous.

They don't have a name.

So this is what it would look like.

And we can replace this part of the code with our anonymous function.

So now you'll see it does exactly the same thing, namely when I click on the button, it goes and carries

out the content of that anonymous function.

And inside the parentheses of this anonymous function are all the instructions that you want to happen

when that button detects the click.

#### 5 Buttons

Loops are a great way of preventing ourselves from doing really tedious

work, because you might realize that you can say something like querySelectorAll for button, and then

you can say, for the first button add event listener,
```
document.querySelector("button")[0].addEventListener("click", function () {
  alert("I got Clicked!");
});
```

then for the second button add event listener,
```
document.querySelector("button")[1].addEventListener("click", function () {
  alert("I got Clicked!");
});
```
and so on.

And there's seven buttons, so that's a lot of lines of code, which we are not interested in doing, right?

So instead what we can do is we can create a for loop. And remember, for the for loop,

we start out with creating a variable i that's equal to zero,

and then we specify the upper bound of i,

so namely when should our loop stop.

And in this case we want our loop to loop through seven times because we have seven buttons. And we can get

that number 7 by simply saying document.querySelectorAll, and we're going to select all of the items

that have the tag 'button'.

```
for (var i = 0;   i< document.querySelectorAll("button"))

document.querySelector("button")[].addEventListener("click", function () {
  alert("I got Clicked!");
});
```

Now this is a little bit dangerous because say if later on we decide to add another button say in our

footer, like a button that points towards our Twitter or our Facebook or whatever it may be,

then this loop is also going to loop through all of those buttons,

adding an event listener.

So we should really be a little bit more specific with our selector. And if we take a look here, all

of our buttons have a class of drum applied to it.

```
for (var i = 0; i< document.querySelectorAll(".drum"))

document.querySelector("button")[].addEventListener("click", function () {
  alert("I got Clicked!");
});
```

So instead of just targeting button elements we can be more specific and more safe by saying target

all of the elements that have a selector of .drum.

And remember the dot specifies that this is going to be a class that we're targeting.

So now we're looking through our document querying for all of the elements that have a class of drum,

and then we're going to call .length on it in order to see how many elements we've got that have

a class of drum.

```
for (var i = 0; i< document.querySelectorAll(".drum").length)
```

And that number will help us determine when we should stop looping, because we essentially

just want to loop through all of our buttons and add event listeners.

So what better way of stopping our loop than figuring out how many buttons we have that has the class

drum on it?

Now you can also separate this line out if you wish,

and if it makes it clearer to you, by creating a new variable

saying numberOfDrumButtons,

```
var numberOfDrumButtons = document.querySelectorAll(".drum").length
```

and you can set it equal to this, and then you can use that inside the

for loop, by saying start i from zero and end

when i is no longer less than the number of drum buttons.

```
for (var i = 0; i<numberOfDrumButtons; )
```


And finally we're going to increment i by one each time.

So now inside our for loop we're going to use this part of our code,

right?

So we're going to paste that into here, and maybe give it a little bit of space from everything else so

you can see more clearly what's going on.

And in this case we're looking through our document, we're querying for all of the selectors that have

the class drum, and then we're selecting each individual element from this array to add an event listener.

So we want to start off with zero.

And then the next time the loop runs it will be 1, and then it'll be 2.

And this is where we put our i.

So when this loop starts off, i is going to be equal to zero.

So this is going to be equal to zero,

so we get our first drum element. And then the next time that this loop runs i gets incremented by 1,

so this i is now equal to 1,

and we get the next element, and so on and so forth.

So now if we hit save and we refresh our web site, then you can see that no matter which button we click

on, we're always going to get the alert "I got clicked!". So that event listener has been added to all of

our buttons by using a for loop.

Now if you find it easier in this case you can also use a while loop,

so while i is less than the number of drum buttons, or whichever way you found to be most effective.

Now what I didn't want you to do was to write out this code seven times changing the i from 0 through

to 7.

So if you had any problems with this challenge then I strongly urge you to take a look back at the lessons

in the Javascript module,

where we went over this concept of loops, and maybe repeat some of the exercises and challenges so that you're

fully comfortable with this before we carry on.

But once you're ready we're going to get started playing some sounds.
