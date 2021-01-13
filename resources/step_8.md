## Reset the game

At the moment, you have to reload your web page every time you want to reset the game. There is a **Reset game** button on the web page, but clicking the button doesn't have any effect.

To make the button work, you are going to connect an event listener to it and wrap your game code up in a function for that listener to call.

--- task ---
The game code needed to reset the game is the code that sets the `answerButton` variable, and the `for` loop. Take those piece of your code and put them in a function called `startGame`.

```JavaScript
function startGame() {

  var answerButton = Math.round(Math.random() * (buttons.length - 1));

  for (var i = 0; i < buttons.length; i++) {

    var red = makeColourValue();
    var green = makeColourValue();
    var blue = makeColourValue();

    setButtonColour(buttons[i], red, green, blue);

    if (i === answerButton) {
      heading.innerHTML = `(${red}, ${green}, ${blue})`;
    }

    buttons[i].addEventListener('click', function(){
        if (this === buttons[answerButton]) {
            answerMessage.innerHTML = "Correct!";
        } else {
            answerMessage.innerHTML = "Wrong answer! Guess again!";
        }
    });

  }

}
```
--- /task ---

If you reload the web page now, nothing seems to be working! That's because, just like all the other functions in your program, you need to **call** `startGame`, otherwise your game doesn't start.

--- task ---
Add a line __at the very end__ of your program to call the `startGame` function.

```JavaScript
startGame();
```
--- /task ---

The `startGame` function also needs to clear the `answerMessage` element of the web page, so that there is no message when a new round of the game begins.

--- task ---
To clear the element, add the following line **at the very beginning** of the `startGame` function.

```JavaScript
answerMessage.innerHTML = "";
```

--- /task ---

Clicking the **Reset game** button still doesn't do anything. That's because the button needs an event listener which calls `startGame`. You already know how to add event listeners to make buttons respond to clicks, so if you want to, you can try to do that by yourself, before looking at the instructions!

--- task ---
Making the **Reset game** button work involves two steps:
 - Select the button using its `id`, which is `resetButton`
 - Add a listener to the button to call the `startGame` function when the button is clicked

Add this line to the end of your program to do that:
```JavaScript
document.getElementById('resetButton').addEventListener('click', startGame);
```

Do you see that the listener gets added directly to the button here, without the button first being stored in a variable? 

I decided to code it this way because the game code doesn't need the **Reset game** button in any other place, so I can save the memory necessary to store the variable.

The other method of first storing the button in a variable and then adding a listener works just fine too.

--- /task ---

Now try out your game! When you get the right answer, click the **Reset game** button and check everything works like it should.