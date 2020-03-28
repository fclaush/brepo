---
title: JavaScript - Fibonacci
layout: page
summary:
---

## Fibonacci

> Credits to Angela Yu, The App Brewery [Udemy Course, Web Development](https://www.udemy.com/course/the-complete-web-development-bootcamp/)

So let's create some sort of variable code output and we can set that to an empty array with nothing

inside.

Now the next step is we have to check whether if n is equal to 1 and if so we're going to give the output

as 0.

So to do that we'll use an if statement to check if this n that's being passed in is equal to 1.

And if so then we're going to say that output is going to be equal to just zero.

So this is the first item in the sequence and then we can go ahead and return the output.

Now the next step in our flowchart is will if it wasn't equal to 1 then is it equal to 2.

And if so then the output should be zero comma 1.

So we can represent this logic by using an elusive remember that else if only gets checked if the first

one was false.

So now we can say well if it's not equal to 1 Well is it equal to 2.

So if it is then we're going to set the output to equal zero comma one stored inside an array and again

it will be returned at the end.

Now finally if it's not one and it's not too well then we have to sum the last two values in the output

so we can catch that final condition using an L statement and inside here we're going to set the output

to equal to zero comma 1 to begin because this is the start of our sequence and then we're going to

sum the last two values and we can do that by reaching into the outputs and getting hold of the first

value.

So output at position 0 which is this one and then we add that to the output at position 1.

So now we're basically adding this first item to the second item and this should equal 1 and that should

be somehow added to the end of this existing array.

And if you remember from previous lessons on arrays we can do that by saying output dot push and we

can wrap this calculation inside of parentheses and we will end up adding this solution to the existing

array.

And at this point the output should now look like zero comma one comma 1 and it will get returned.

Now we have to check whether if N equals the number of items in the output.

So we could do this using another if statement and we could say F and triple equals output length.

Then we can go ahead and return the output but otherwise we have to continue to add the last two items

together.

So how could we change our code here so that instead of manually saying it's the item from the output

array at position 0 this one plus the item at position 1 This one.

How can we say instead that we want to get the last item plus the second from last item.

Well we could use the length.

So in this case output length is going to be equal to 2.

So if we wanted this to be one then we could say output dot length minus one and then we have our second

from the end which is going to be output length minus two.

So this still works exactly the same.

But now this line of code can work no matter the size of our array because even if it was this long

output length at this point is going to be equal to four so four minus one is going to be three.

So this becomes three and if we look at the item at position three in our Rea it's zero one two three.

So it's this last item and minus two makes it 2 and 0 1 2 becomes the second from last item.

So we're adding one plus two here.

So this line of code now makes it dynamic and we could now use it inside our L statement.

But notice how these two lines of code are now repeating.

And also when we get to the end of the L statement we have no way of going back to the beginning to

check if the n is equal to output length again like what is required here given how much this looks

like a circle.

It should remind you that we need to use a loop.

So instead of writing all of this we could just simply create a loop and the type of loop that I'm going

to create in this case is a for loop.

So I'm gonna say let's create a variable inside the for loop that set equal to so the existing number

of items in our output and then we're going to use a semicolon and say that while i is less than n the

total number of items we need in our output continue to increase.

I buy one and every single time what you want to do is to do this to get the last item from the outputs

to get the second from the last item from the outputs.

Add them together and then push it onto our array and finally return the output.

So now let's take off over Nazi generator and then paste it into our wrap lit playground.

And now let's go ahead and try to run our code by calling the Fibonacci generator and let's just start

off with something quite simple.

Let's start with an equals 1.

Now if I hit run in the output I get zero.

If I change this to 2 in the output I get 0 1 and if I change this to 5 in the output I get a 5 item

sequence in an array.

So now that we've confirmed that our code works let's go ahead and click check solution to see if we

got it right.

Brilliant.

So now we've passed this challenge.

How did you get on with this challenge.

Did you struggle with maybe using some of the array methods or did you remember to use a loop so that

it goes around and around and does the same action repeatedly.

Now remember that there's many many ways of solving this challenge.

You could have used a while loop you could have done something fancy instead of using many ifs and else

is there's a lot of ways.

But as long as your output satisfies the criteria that we set out in the challenge then it doesn't matter

which way you chose.

In fact at this stage as long as your solution makes sense to you then that will be the perfect solution.

```
function fibonacciGenerator (n) {

var output = [];
if (n === 1) {
  output = [0];
}
else if (n === 2) {
  output = [0, 1];
}
else {
  output = [0, 1];

  for (var i = 2; i < n; i++) {
    output.push(output[output.length - 2] + output[output.length - 1]);
  }
}

return output;
}

output = fibonacciGenerator(100);
console.log(output)
´´´
