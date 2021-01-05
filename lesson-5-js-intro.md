# What is JavaScript?

![Slide of death star frame, death star lights on, kyber ray](https://i.imgur.com/ZPGqhnk.png)

When we talked about the three pillars of the web, we talked about HTML, CSS, and JavaScript. HTML gives our web pages __structure__, CSS gives our web pages __style__, and Javascript give our webpages __functionality__. With all three of these tools in your arsenal, there is no limit to what you can build on the web.

JavaScript is what you'll hear referred to as a _programming language_. HTML and CSS are also languages, but they are for _markup_ and _style_ respectively. 

_JavaScript is a completely different programming language from _Java_. This is good to keep in mind as you're googling JS issues while developing._ 

_JS connects to our webpage similar to how a CSS file would, by connecting to the __HTML__._

---

# Do websites need JavaScript?

Every time you fill out a form, search for something, login, load an account, or really do anything other than just look at _static_ content on the web, you are leveraging the power of JavaScript. A website without JavaScript would never change. It's contents would be set in stone, simply displaying information with nothing the user could do to interact with it.

![Buzz Lightyears arm with the control panel sticker, next to it a Pip-Boy from fallout with lots of knobs and live data displayed.](https://i.imgur.com/ea23Ilk.png)

When we talk about _static_ vs _dynamic_ websites, you can think of them like cars. Imagine having a badass Delorian with leather seats and intricate details, but no engine. You can sit in it and enjoy it for a while, but that's gonna get old quick. Now let's say that Delorian has an engine _and_ a flux capacitor. RAD. __That's__ the kind of difference JS can bring by allowing us to build dynamic sites.

---

# Am I cut out to be a programmer?

![goofy 80's style guy at a computer with the title "Hackerman" underneath him](https://i.ytimg.com/vi/KEkrWRHCDQU/maxresdefault.jpg)

People often assume that because they aren't "good" at math, or don't consider themselves to be left-brained, they could never become programmers or engineers. __This is one of the biggest misconceptions about programming__. 

Can those things _help_? Sure! Are they _fundamental_? Absolutely not. 

Becoming a programmer is about learning a new way of thinking. It's about approaching problems differently, and being able to break them down. It's __not__ about memorizing syntax and being a human calculator. You will naturally start remembering things more and more as time passes and you spend time using these tools and working in the JavaScript programming language. But what is most valuable is developing the skill set of _thinking like a developer_. 

### TL;DR - You _are_ without a doubt cut out to be a programmer. Your own journey will be unique, but the web is for you. Everything you bring to the table is valuable.

![goofy picture of people encouraging each other](https://i.ytimg.com/vi/FrXG7ejTmD4/maxresdefault.jpg)

The web is a blank canvas. Any idea you've ever had for a game, an art project, an app, _literally anything_, JavaScript is the superpower that will enable you to make these things a reality.

> _I didn't have an easy time learning and starting out as a developer. If you're still feeling unsure that you can do this, [here's a look into the rocky beginning of my career, and all the fears and doubts that I experienced](https://dev.to/mikel_brierly/a-brutally-honest-look-back-at-the-beginning-of-my-career-hmf)._

---

# Getting Started

![Parody of "Hello World" code, or unsplash code](https://images.unsplash.com/photo-1516331590554-978b8de25f18?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1352&q=80)

#### _Head over to [this repo to get set up](https://github.com/developer-delta/javascript-first-steps) with a template for writing our JavaScript_

Once you have followed the steps to get that repository set up, you should be able to run the command `open index.html` to open your newly created HTML file in the browser. You should now see a completely blank web page opened up your browser. _(Make sure google chrome is set as your default browser)_

> If you _don't_ see that, check to make sure you are in the correct directory to be opening your HTML file.

* Ok let's go back to the terminal and type `code .` in the `javascript-first-steps` directory to open this folder in VSCode.
  * _If you get errors saying the `code .` command does not exist, go into VSCode itself and type `CMD + P`, then type `> install code` and click on the first result. Now retry that last command._
* Next we'll open our `app.js` file.
* In our fresh new JavaScript file, let's write a simple line of code:

```javascript
alert('This is JavaScript in action hot damn!')
```

* `CMD + S` to save, and go back to your browser and refresh the page. Eh? See anything happen? You have just started leveraging the power of JS!

![Emperor Palpatine talking about power](https://i.kym-cdn.com/entries/icons/original/000/032/676/Unlimited_Power_Banner.jpg)

* Now on another line, let's write another command:

```javascript
console.log('Here is a secret message...');
```

* `CMD + S` to save, then refresh again, and this time right click anywhere on the white browser page and select `inspect`. (Close the alert first)

* In the new window that opens, select the tab labelled `console`.
  ![Screen Shot of the console tab of ](https://i.imgur.com/ifuqrsJ.png)
* You should now see the message that we put inside of the last line of code!
* Ok now for our last little example, create a new `console.log` or `alert` on another line in our `app.js` file.
* Inside of the parentheses, put in any simple math equation you like. Let's say `2344453 / 534` for example. (`/` is for divide. `*` is for multiply)
  * Make sure to remove the quotes `''` from inside the parentheses first.
* Save and reload the webpage, and see what output you get.
* __Ok! Now that we've gotten our feet a little wet, let's take a deeper look into what is going on with this sorcery.__

### Where and how

_How does the browser know where our JavaScript is? And How does it know what to do with it?_

* Browser __requests__ the html file after we give it an __address__ to look for it at (URL).
* The HTML then tells browser where any other necessary files are located. We have already seen how CSS is included with the `style` tag. _JavaScript is very similar._ The HTML knows where the javascript is with a `script` tag.

```HTML
<script src="app.js"></script>
```

* The `src` attribute must be correctly pointing to the location of your JavaScript file in relation to the HTML looking for it. _(Remember you may need to use `../../` to go back a certain number of directories.)_
* The `script` tag lives at the end of your `head` element.
```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <meta charset="utf-8">
    <title>My first JS</title>
    <script src="app.js"></script>
  </head>
  <body>
  </body>
</html>
```

So that's __where__ our javascript comes from, but how does it... _do stuff_?

![Rob Stark yelling "HOW??"](http://blog.charitydynamics.com/wp-content/uploads/2015/07/GOT-how_GIF.gif)

You will hear the terms "running" and "executing" often in relation to `JS`. Basically what these mean is the point in time that the browser has access to your `JS` file, and begins "reading" it and taking action on it.

For now it's ok to think of your browser "reading" your `JS` similar to the way you read a book. From top to bottom, left to right. __One line at a time__. 

Go ahead and paste this into your `JS` file as an example to see how your browser runs code. We'll use the `console.log` statement since we already know a little bit of what to expect from it.

```javascript
console.log('first');
console.log('second');
console.log('third');
console.log('fourth');
console.log('fifth');
console.log('sixth');
```

The output of that is predictably in order. The reason being is that the browser reads each line, and __takes an action__ as soon as it can.

> `semicolons` are used in JS kind of like periods in a regular sentence. They indicate the _end_ of a `statement`. Some statements span multiple lines, and the semicolon would go at the very end of it. Your code will work without semicolons for now, but keep them in the back of your mind for the future!

### Types

Ok so we've seen a tiny bit of JavaScript in action, but there's still a lot we don't know about the code we just ran. One of the most important and basic components of that code is values and their `types`. 

A `type` is the name we use for the different flavors of information passed around in our programs. Here we'll look at three of them for starters. There are more, but we'll get to them later. We'll be learning about:

`strings`
`numbers`
`booleans`

##### Strings

![Patrick star from spongebob reading JS syntax](https://www.freecodecamp.org/news/content/images/2019/07/panel-3-1.png)

If we look at our repetitive `console.log` statements above, we see that they are all identical up to the open parentheses, and then we have text wrapped in quotes that displays different information.

"Text wrapped in quotes" is a `type` in JavaScript called a `string`.

Here are some strings:
`'z'`
`'An exceptionally long sentence with a lot of words and spaces and stuff in it'`
`"Hey look double quotes!"`
`"tkwoeirgjfowiejfadsg"`

That's _four_ strings. Everything within the quotes makes up the content of those `strings`.

Here are some _INVALID_ strings:
`"oh man this never ends who knows where it'll go` (No closing quote)
`"Single and double quotes are not friends'` (Quotes must be the same type for each string)

> When you hear about "empty strings" they are just quotes with nothing inside, like this: `""`. That is valid, it's just empty. It is still of the type `string`.

##### Numbers

![Some number meme](https://pbs.twimg.com/media/ECI3anoUwAAtsjR.jpg)

Numbers are pretty straightforward! Here are some:

```javascript
1
24
42
3323984
0
```
Enlightening huh? The main thing to note is that they are not wrapped in quotes. If you were to wrap a number in quotes, what do you think happens to it's `type`?

`"1138"`

_that_ is a string. Even though it contains number characters, it's wrapped in quotes, therefore making it a string.

Keeping a value as a `number` allows you to use it like a number, doing arithmetic operations on it or using it as a counter.

```javascript
10 + 5 // returns 15

"10 + 5" // returns "10 + 5"

```

_You can also do division `/`, multiplication `*`, subtraction `-`, and many other operations that we'll look at in the future._

Go open your browser and if your Developer Tools aren't open still, right click, select `inspect`, then navigate to `Console`. Type in some numbers and try out adding or subtracting and then hit `enter` to see what you get! Also try this using quotes to create strings. The "Dev Tools" let you write simple JavaScript statements in the 'console' to test out!

![using the console to add 10 and 15](https://i.imgur.com/ohZkBHN.png)

##### Booleans

![Harvey dent from batman with half his face burnt off](https://www.gogocosplay.com/wp-content/uploads/2019/02/harvey-dent-two-face-e1548992628907.jpg)

_Boolawhat?_

A Boolean is a `type` in JavaScript that is basically just a coin. It can only be `true` or `false`. Often it is used like a switch or toggle to help us undo or redo operations based on the state of things. 

Sometimes we'll want to _check_ whether or not something exists or is equal to another value, and we can do that with the `strict equality` operator _(we'll talk about that operator in a second)._

```javascript
"I exist" === "I exist"; // returns true

"Zero" === 0 // returns false

2 === 1 // returns false
```

When we use JavaScript to check if something will return a true/false value as a `boolean`, that is literally called checking for `truthy` and `falsy` values.

---

### Variables

So far we have seen how we can use the browsers console to output values from our `app.js` JS code, and we have used it to play around in as a sandbox for arithmetic and simple operations. But what if you wanted to create a value, and then __save__ it somehow for a later use?

That's where `variables` come in. They allow us to give a name to a value.

Here's what that looks like:

```javascript
let harry = "Daniel Radcliffe";
```

The _value_ of `harry` is now the `string` "Daniel Radcliffe". We could even use `console.log(harry)` to see that `string` printed out to the console!

Let's break down the anatomy of that line there by creating another similar one:

> _Go ahead and add these variables to the bottom of your `app.js` file._

```javascript
let hermione = "Emma Watson";
```

`let` is a __keyword__ in JS that means "Hey I'm about to create a variable, listen up". It is a `declaration`.

It allows us to `declare` our variable (hermione) and _assign_ it (=) a `value` ("Emma Watson").

It's very important to note here that the equal sign `=` in JS does not mean "is the same as". The single equal sign is used for `assignment`. To make the value of one thing the _same_ value as another. 

So if we have `declared` the `variable` hermione and assigned it the `value` "Emma Watson", what would we get if we used `console.log()` to print it out to our browser console? Let's give it a shot in our `app.js` file.

```javascript
console.log(hermione)
```

> _Note that `hermione` is not in quotes because it is not a string, but a variable._

What we just did there was a `variable declaration` AND a `variable assignment` in the same line. Booyah.

```javascript
let hermione; // variable assignment
hermione = "Emma Watson"; // variable declaration

// the most common syntax for variable declaration and assignment together.
let ron = "Rupert Grint";
```

##### Constants

When we are creating `variables`, often you may want to change their values as you progress through your program. `let` allows us to do this. Take this code for example:

```javascript
let darkLord = "Tom Riddle";
console.log(darkLord);

darkLord = "Voldemort";
console.log(darkLord);
```

Go ahead and put that in your `app.js` file and see what you get as the output. Hmm... So even though we logged out the same `variable`, it's value was different. The reason is because we `reassigned` the `variable` to "Voldemort" after logging it the first time. `let` allows us to do this, it __lets__ us do this reassignment. 

__BUT__ what if you wanted to create a variable that should be set in stone. A variable that _didn't_ let you reassign it. A _constant_.

A _constant_ is a variable that once it's value has been set, it can never be changed. The keyword to use them is `const`. Let's see an example:

```javascript
const MAX_VOLUME = 93;
```

> All caps for `const` declarations isn't something you _have_ to do, but it is encouraged so that later on in the program if people use the `MAX_VOLUME` variable, they'll know it's a `const` just by the fact that it's all caps. When developers are in agreement about doing something like this to make the codebase better, it is called a __best practice__.

It is __best practice__ to capitalize your `const` variables.

Let's try something out to help us really grasp the difference between `let` and `const`. Copy and paste the "Tom Riddle" code block above to the bottom of `app.js`, but change the variable declaration to `const` instead of `let`:

```javascript
const darkLord = "Tom Riddle";
console.log(darkLord);

darkLord = "Voldemort";
console.log(darkLord);
```

An `error`! A-ha! So JS will _throw_ an error if we try to do something like that that breaks the rules JS has set in place for us. Useful!

Remember that errors exist to benefit the developer. They should be embraced and appreciated, rather than treated like an indication of failure. Errors are like clues to how you can fix your problems! They're awesome!

For a _user_ errors are often the end of the line, but for a _developer_, they're just the beginning.

---

### The Console

![pic of a fallout terminal](https://www.ordinaryreviews.com/wp-content/uploads/2018/08/fallout-4-hacking.jpg)

##### Logging

What is this `console.log` we keep using?

The `console` (as we have seen) lives in your browser. In Google Chrome you can open it up and have a tray that gives you access to it.

`console.log` is a way for our JS code to communicate things about our code to us _through_ the browser console. It's like we have an informant spy inside the code giving us information we need.

Let's look at the syntax of `console.log()`.

`console` is a keyword given to us by the browser that JS has `reserved`. 

> _`reserved` just means that you can't use that word as a variable name in your own code. Like if you were choosing a username for a website, and yours was already taken, you'd have to choose another. Same idea._

It is `reserved` so that _we_ can use it in our code. There are a couple different ways we can use `console`:

```javascript
console.log("I give you information and can print variables, etc.");
console.warn("I give warnings for things like updates needed or minor mistakes")
console.error("I'm not messing around and I'll throw a real gnarly big red message when something is broken!");
```

For now don't worry too much about the dot `.` between `console` and `log`. We'll learn about `methods` in the future. 

For now you'll just be using `console.log`, but it's good to see how other "levels" can be used. 

The last important part of the syntax is the parentheses `()`. Whatever you want to log, put it in between those parentheses. _Keep the `type` the same as it in your code._

```javascript
var VOL = 11;

console.log(VOL); // prints 11
console.log("VOL"); // prints "VOL" as a string
```

##### Debugging

![prince robot IV](https://static.tvtropes.org/pmwiki/pub/images/prince_robot_iv_5259.jpg)

So you might be wondering why we even need something to tell us what's happening in our code if we can just open up VSCode and look directly at it, right?

That is true! But unless you _literally_ have a computer for a head, it's unlikely you'll be able to solve problems of any complexity by just reading code. Let's look at an example:

```javascript
let number = Math.random(); // creates random decimal number.
```

Any idea what that will do? Or how it may format the number it spits out? Maybe you are using that value later on in your code and it's not what you expected, so you need to see it at a certain point in time to be able to fix it. 

__This is called `debugging`. And one of the tools of `debugging` is the `console.log`.__

```javascript
let number = Math.random(); // creates random decimal number.

console.log(number); // 0.12365481788905841
```

Oh Interesting! So that doesn't even give us a round number. Just a decimal... hmmm. 

Why don't _you_ do some googling to see how that could `log` out a round number between 1 and 10 and add that to your code.

__You just did some `debugging`!! 🎉🎉🎉__

And you used `console.log` as a tool to figure it out. Generally speaking, you don't want to leave console logs in your code. They are mostly for debugging, and you take them out when you are done writing your program.

---

### Equal is not equal

![wat gif](https://media4.giphy.com/media/3WmWdBzqveXaE/200.gif)

Earlier when we talked about variable `assignment` and `declaration` we used the syntax of a single equal sign to do the `assignment`. That may have felt a little weird, and _traditionally_ that is not what the equal sign means, but in JS it has a new meaning.

> In spoken languages, there are words called "false friends" that have different meanings in each language. For example in Danish "fart" means _speed_. So a speed bump is actually called a "fartbump".

But there is a way in JS to check if something's `value` is __equal__ to the `value` of something else by using _three_ equal signs.

This is called the `strict equality` operator. 

```
===
```

Here's some examples:

```javascript
"a" === "a"; // returns true

2 + 2 === 4; // returns true
2 + 2 === 5; // returns false

let name = "Mario"; // assigns the value "Mario" to the variable "name"
name === "Mario"; // returns true
```

If you can understand the difference between these two:

```javascript
let name = "Mario";
name === "Mario";
```

Then you got it!

---

### Concatenation

![jellicle cats](https://media4.giphy.com/media/h2CbcQnvZhCi9A1Nyh/200.gif)

There's one last thing about `strings` we should cover in this intro lesson. One of the most useful ways to manipulate `strings` is by using `concatenation`. 

`concatenation` is just a fancy word for "joining things together". 

You'll see pretty quickly how awesome this is when you use it with variables. Let's look at an example:

```javascript
let name = "Luigi";

console.log("Hiya may-a name-a is-a " + name);
```

Add that to your code and run it real quick. Pretty sweet huh? The magic of `concatenation` happens with the plus `+` operator. When you use it on strings, you are `concatenating`.

`"Add me " + "to this" + " and add me " + " to that."`
prints
`"Add me to this and add me to that."`

Try and use `alert()` and a `variable` in your javascript to create something unique that will pop up on your page!

---

### Functions

So far we have looked at features of JavaScript that allow us to create and store values, change variables, and print to the console. But everything we've written so far is very _static_ and doesn't seem to offer much value. This is where functions come in. 

_Functions are where all the pieces come together and give JavaScript it's power. Let's take a look:_

```javascript
(x) => {
  return x + 10
}
```
So there's a function! That function has no name though, and functions are usually more useful when they have names, so let's `assign` that function to a `variable`.

```javascript
const addTen = (x) => {
  return x + 10;
}
```

What we did right there is known as a `function declaration`. Let's break it down a bit.

`const addTen = ` This part here should look somewhat familiar. We know that `const` is a variable. So we are `declaring` the variable `addTen` and _assigning_ it to a function.

Alright, now the good stuff. First up, in our function we have a pair of parentheses, inside of there is `x`. `x` is known as a parameter, and it could be anything! We've just named it `x` in this example. 

Parameters are like _placeholders_ in our functions, they don't have any `value` in and of themselves, but we'll give them value in just a sec.

Next we see `=> {  }`. This is the syntax of the second part of our function. The curly braces are often on a different line just to be able to hold code legibly inside, but the meaning is the same even if they are on the same line.

So in it's absolute simplest syntax, this makes up a function:

```javascript
() => {

}
```

Now that function is useless, but it contains all of the syntax that makes a `function` valid! 

Now let's go back to our `addTen` example. 

```javascript
const addTen = (x) => {
  return x + 10;
}
```

All of the __logic__ of a function happens inside of the curly braces `{}`. You can think of the parentheses `()` as a kindof "hopper" in a machine that takes in ingredients, and the curly braces `{}` are where the machines actual gears and springs and power is. 

So how about the last part we haven't talked about yet, the `return` statement?

The `return` statement is a _keyword_ that indicates what should be "spit out" from the function. It `returns` a value _from_ the function. Our function here only has one line between the curly braces, but it could have many! And if it did, we would put the return statement toward the end when we finally had the value we wanted to "spit out". 

_Without a `return` statement, your function will do nothing._

Ok great, but what about that `x`? The `parameter` of our function? It has no `value`, and doesn't seem to be doing anything...

```javascript
const addTen = (x) => {
  return x + 10;
}
```

The `x` parameter is where things get exciting. `x` could be anything! Anything we want to "pass" to our machine. Let's say we wanted it to be the `number` 5. 

The way to "give" a function a _real_ `value` is to `call` it. `calling` a function (sometimes called `executing`) is like flipping the switch to turn on your machine with ingredients ready to go. Let's `execute` our function and pass it the `number` `5`.

```javascript
addTen(5);
```

Now what this will do is `execute` our function, and _pass_ it the `number` 5. You can imagine now that everywhere we had the `parameter` `x`, that `x` is now a `5` because we gave it a value.

Now what will happen is our function will `return` the value `15` because we are adding `5 + 10`.

Let's make one quick addition to the function so we can see some output in the console. Copy and paste these `function declaration` and the `function execution` lines into the bottom of your `app.js` file.

```javascript
const addTen = (x) => {
  console.log(x + 10);
  return x + 10;
}

addTen(5);
```

All that we added there was a `console.log` into the function so we can see the value that will be returned from the function. 

`returned` values are not logged to the console, but they are available to our javascript if we wanted to keep using them. So for now we just want to see what will be the output of our new function. In this case it's `15`!

Go ahead and make some changes to our function and run them to see what kind of different outputs you can get. Try to use `variables` and different `types` if possible to really change it up!

### DOM preview

We have just covered a _ton_ of JavaScript!! But you may have noticed that we didn't actually make any _visual_ changes appear on our webpage. This is because we haven't been interacting with something called the `DOM`. The `DOM` is what allows us to visualize things on our webpage, and manipulate them with JavaScript. It's a bit much to go over today, so we'll save it for next time, but don't worry, we'll be able to see our hard work in action in no time!

---

### Homework

![You've taken your first step into a larger world](https://64.media.tumblr.com/0983e12a79750034d4481363c27fd602/tumblr_o4i92cpye51twcj5xo2_500.gif)

Repetition is your best friend while learning JS! Let's go over these concepts and practice writing more of the JavaScript we just covered.

* [Head over to the `javascript-first-steps` repo for the homework](https://github.com/developer-delta/javascript-first-steps)!