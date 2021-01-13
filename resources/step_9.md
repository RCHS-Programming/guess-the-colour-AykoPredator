## Challenge: fill the web page with the winning colour

Your game works now, so here's a challenge for you: using your new coding knowledge, can you fill the web page with the winning colour when the player clicks the correct button? 

You need to know two other things to meet this challenge:
1. The whole of the web page is contained in the `body` tag of the HTML file
1. Just like you can select page elements by `id` and by `class`, you can select elements by `tagName`. And just like when you select by `class`, selecting by `tagName` can mean you select more than one element, so you'll get an array back (although in the case of the `body` tag, there will only ever be one element with that `tagName`).

Now try to use `document.getElementsByTagName()` to change the background of the page to the winning colour when the player clicks the correct button!

--- hints ---
--- hint ---
Remember that you already have a function for setting button colours? You can use the same function to change the background colour of the page `body`.
--- /hint ---
--- hint ---
Update the background colour at the same time the message to the player gets updated.
--- /hint ---
--- /hints ---