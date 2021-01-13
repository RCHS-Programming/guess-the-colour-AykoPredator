## Random colours

Now you can select a button and change its colour to whatever you want! But to make your game work, you need random colours. That's easy, because JavaScript can pick random numbers for you, and you can make sure they're between `0` and `255`.

The best way to do this in your program is to write another function that creates a random colour value (a number between `0` and `255`) and **returns** it. When a function returns a value, you can store the value for later or use it immediately.

--- task ---
Use the following code to create a function called `makeColourValue` that uses JavaScript's built-in `Math.random` and `Math.round` functions to generate a random number between `0` and `255`, and that then returns this value.

```JavaScript
function makeColourValue(){
    return Math.round(Math.random()*255);
}
```
--- /task ---

--- collapse ---
---
title: JavaScript and random numbers
---
JavaScript has a built-in function called `Math.random` that produces a random decimal number between `0` and `1`. By multiplying this number, you can get a random number between `0` and any other number. For example, to get a number between `0` and `100`, you multiply the result of `Math.random` by `100`, like this:

```JavaScript
myRandomNumber = Math.random()*100;
```

This works because the smallest random number `Math.random` can create is `0`, and `0 * 100=0`. The largest random number is `1`, and `1 * 100 = 100`. And with any random number in between, you get a number in between `0` and `100`. For example, `0.25 * 100 = 25`.

`Math.random` produces a **decimal** number, for example `0.245834`. For your game, you only want whole numbers (integers), because only those work as colour values. So you need to round the result of `Math.random`. Luckily, JavaScript has a built-in function called `Math.round` to help you round decimal number. So to get a whole number between `0` and `100`, you would write:

```JavaScript
myRandomNumber = Math.round(Math.random()*100);
```
--- /collapse ---

Now it's time to use this new function.

--- task ---
Create three variables, named `red`, `green`, and `blue`, with random colours picked by your `makeColourValue` function. Then update the code that sets the button colour so that it uses these three variables to set the button's colour.

```JavaScript
var red = makeColourValue();
var green = makeColourValue();
var blue = makeColourValue();

setButtonColour(buttons[0], red, green, blue);
```
--- /task ---
Now reload the web page a few times and see the button change colour every time! Since you're working offline, reload the page by refreshing your browser.
