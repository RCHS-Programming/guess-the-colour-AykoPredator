## Change a button's colour
At the moment, all the buttons on the web page are red. The whole game is based on having different coloured buttons, so you need a way to change a button's colour! 

Colours in computer programs are made up of three different values: R, G, and B, for red, green, and blue. Each value is between 0 and 255, and together, these three values define the 16777216 colours that a computer can display.

For example:
- Red is (255, 0, 0)
- Green is (0, 255, 0)
- Blue is (0, 0, 255)
- Purple, which is a mix of red and blue, is (255, 0, 255)
- White is all three colour values at full brightness (255, 255, 255)
- Black is all three values at zero brightness (0, 0, 0)

So to change a button's colour, you tell the button to use three values between 0 and 255 as its background colour.

Because you need to do this a few times in the code for your game, you are going to write a **function** so that your JavaScript program can do most of the work for you.

--- collapse ---
---
title: What is a function?
---
Code is often made up of functions, which are sets of instructions joined together with a name. Why are functions useful? Think about all the steps involved in making a cup of tea: 

  1. Get kettle
  2. Put water in kettle
  3. Boil water
  4. Get teapot
  5. Put teabag in teapot
  6. Put water in teapot
  7. Wait
  8. Get cup
  9. Pour tea into cup
  
That's a lot of steps! It would be boring to have to tell someone to do each of them every time you wanted them to make a cup of tea. It's much easier to teach someone how to make a cup of tea once and then just ask them to 'make tea' the next time. 

With coding it is similar: you create functions to do complex things with simple commands.

--- /collapse ---

--- task ---
Your function needs to:

 - Take a button
 - Take three values, for red, green, and blue
 - Use those values to make a colour
 - Assign that colour as the background colour of the button

Add this code to your `script.js` file to create this function using the name `setButtonColour`.
```JavaScript
function setButtonColour(button, red, green, blue){
    button.setAttribute('style',
                        'background-color: rgb('+ red +','+ green +','+ blue +');'
                       );
}
```

To change the colour, the code changes the **CSS style rule** for the button.

--- /task ---

To use your function, you need to point it to a button.

All the `button` tags in the HTML file have the `class` of `colourButton`. This `class` lets you select all the buttons as a group and then pick one for testing your function.

--- task ---
At the top of your `script.js` file, add this line of code to store all the buttons in a variable called `buttons`:

```JavaScript
var buttons = document.getElementsByClassName('colourButton');
```
--- /task ---

`buttons` isn't a regular variable like `heading`, it is an **array**. An array is a list of things. The `buttons` array contains anything with the `class` name `colourButton`.

You can read what's at any position of an array using the position number surrounded by square brackets `[]`. Since JavaScript starts counting from zero, you get the first item in the array like this:

```JavaScript
buttons[0]
```

--- task ---
Below where you created your `buttons` array, add this line of code, which takes the first button in the array and changes the button colour to blue using your `setButtonColour` function:

```JavaScript
setButtonColour(buttons[0], 0, 0, 255);
```
--- /task ---

Now watch your button change colour! Since you're working offline, you need to reload the page in your browser to see the change.

![The first button has changed from red to blue. The other five buttons remain red.](images/1blue.png)
