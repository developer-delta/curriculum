<!-- > * Lecture -  about and recap (10 mins)
> * Lecture and working session -  (50 mins)
* I think we should do the ring light Zoom thing first. Def have opportunities to manipulate the DOM AND build something fuckin cool together.
  * Should I just design it and then put together stories??
  * Like not even start it until we're all working together??
  * Use Codepen together to prototype stuff?

* We should do our lesson on the DOM, THEN -
* Go through the flow of a git push, pull, PR together for a refresher,
  * build the light ring thing 
* Maybe we all pair program on the BASE HTMl document during a class together.
* focus on the DOM.
* Whip out A11y shit as we go
* Maybe do a "save preset"? That saves to localStorage?
 -->

# The Document Object Model

![restaurant buffet late at night](https://images.unsplash.com/photo-1573550854847-3d78b3c72c2f?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80)

As we have been learning Javascript, you may have noticed that the only way to visualize what we've been making changes to is by opening the `console`. That's cool and all, but what if we wanted to make changes to what the user _actually sees_ on the screen? Like updating a number, color, or form input? The `DOM` makes all that possible.

The `DOM` is the **Document Object Model**. _It's basically everything you see on your screen._

Remember how our `HTML` files and `CSS` files are sometimes referred to as "documents"? That's where the `document` in `document object model` comes from.

It is essentially a **map** of our `HTML` that our JS can navigate.

For example if you wanted to use JavaScript to change a button from green to red when clicked, the `DOM` is how our JS would be able to find and manipulate that button.

**Let's check out an example before your eyes completely glaze over and roll back into your skull.**

```html
<h1>Tasty Buffet</h1>
<input class="buffet" type="text" placeholder="Find some grub">
<button class="add">Add to Plate</button>
<div class="plate"></div>
<button class="eat">Chow Down</button>
<p class="stomach"></p>
```
![website with a header titled "Tasty Buffet", followed by a text input, button saying "Add to Plate", a large circle, and then a final button labeled "Chow Down"](https://i.imgur.com/llhqgLe.png)

> _If you would like to follow along, [open up the Codepen template](https://codepen.io/mikelbrierly/pen/gOwQQox?editors=1011) for this lesson_
> * _Click on "console" at the bottom left of the Codepen screen_
> ![Screen Shot of the codepen console](https://i.imgur.com/66LqyvS.png)
> * _Click "Change View" > "Editor Layout" > ![icon of left aligned editor windows in CodePen](https://i.imgur.com/f2L6mOd.png)_
> * _Codepen is a web playground where you can try out ideas and run small pieces of CSS, HTML, and JS!_

Our HTML snippet creates a heading, two buttons, a div container styled (kinda) like a plate, and an empty "stomach" paragraph tag.

If you try and put text in to the input and click either of the buttons, nothing happens. Let's write some JS that will interact with the `DOM`.

In the console, run this line of JavaScript:

```javascript
document.querySelector('.buffet');
```

You should get this output :

```JavaScript
"<input class='buffet' type='text' placeholder='Find some grub'>"
```

Well I'll be darned that looks familiar! Let's break down what's going on here.

* `document.` **is a gift from the browser** that let's us access our `HTML` with JavaScript to modify it or get information from it. 
* `querySelector` is a _method_ that allows us to access `HTML` elements. In this case, our input with the class `buffet`.
  * `querySelector` is a great method to learn because it is so flexible. The string inside the `()` works exactly like CSS selectors do!
* I know _method_ is a new term, but for now, all you need to know is that they are **functions we can use that are provided by the browser**.

`document` gives us a TON of different methods we can use to manipulate the page.

![a list of hundreds of methods from document.](https://i.imgur.com/aodMomJ.gif)

_Instead of memorizing all of them, we'll just look at a couple common ones here, and you'll learn more as you google things you want to accomplish, and then discover new methods you can use to get there!_

In our JS, let's assign our querySelector to a variable so we can easily reference that `DOM` element whenever we like

```javascript
const userInput = document.querySelector('.buffet');
```

Go ahead and add in an `addFood` function that we will be using in a second. 

```javascript
const userInput = document.querySelector('.buffet');

const addFood = () => {
  console.log(userInput);
}
```

Next we'll use another type of `DOM method` called an "event listener". You tell them to pay attention ("listen") to a certain HTML element, and then they will execute any function you like when it sees a change.


```javascript
const userInput = document.querySelector('.buffet');

const addFood = () => {
  // log out any value from the text input
  console.log(userInput.value);
}

// the "change" we are listening for here is when any key on the keyboard is used
userInput.addEventListener('keyup', addFood());
```

Now when any key is pressed, we call `addFood`, and whatever value was typed in gets logged out to the console!

![Andy from parks and rec looking at the camera with joy](https://thumbs.gfycat.com/MildBeneficialAtlanticridleyturtle-small.gif)

Now we're allowing our _user_ to actually leverage our JavaScript in a powerful way!

We can use the `DOM` not just to _get_ information, but also to send it _back_ to our `HTML`. Remember the "plate" div `<p></p>` tag we added to our `HTML`? Let's put some stuff in it!

```javascript
const userInput = document.querySelector('.buffet');
const plate = document.querySelector('.plate');

const addFood = () => {
  plate.append(userInput.value);
}

userInput.addEventListener('keyup', addFood);
```

First we added a new variable that lets us target our "plate" div on the `DOM`. Then instead of using `console.log`, we used the method `append` to stick the `userInput` into `.plate`.

> _Where did `.append` come from? I **just** learned about that method. I was going to use a different approach, but stumbled across `.append` and it seems more modern and flexible, so I used it! This is part of learning the DOM. Google what you want to accomplish, and carefully read the results. You'll learn a ton!_

![typing in pizza and burger to the text input, and seeing "Pizza burger" printed out into the plate multiple times](https://i.imgur.com/GxXhnRF.gif)

Nice! But also not nice... 

Let's change it so that we only add food to our plate when the "Add to Plate" `button` is pressed!

```javascript
const userInput = document.querySelector('.buffet');
const plate = document.querySelector('.plate');
const addButton = document.querySelector('.add');

const addFood = () => {
  plate.append(userInput.value);
}

addButton.addEventListener('click', addFood);
```

Notice that we changed our "event listener" to be triggered by our `button` instead of our `input`? The sky is the limit!

![clicking "Add to Plate" now adds the users input onto the plate instead of typing](https://i.imgur.com/9DnJ81y.gif)

Let's make one more adjustment. Instead of just appending _text_ into our `.plate` div, let's append a _paragraph_ element that contains text.

```javascript
const userInput = document.querySelector('.buffet');
const plate = document.querySelector('.plate');
const addButton = document.querySelector('.add');

const addFood = () => {
  const p = document.createElement('p');
  p.innerHTML = userInput.value; //innerHTML injects userInput.value into our new p tag
  plate.append(p);
}

addButton.addEventListener('click', addFood);
```
![typing in food names now adds them in paragraph tags nicely spaced](https://i.imgur.com/oyJ2HiF.gif)

Now we have some real functionality in our Buffet app! And I'm hungry.

# Homework

[![Ryan Gosling refusing to eat his cereal](https://i.pinimg.com/originals/7b/e5/9b/7be59b5ed20819f9569eebb442b4c3e7.gif)](https://www.youtube.com/watch?v=ohJtvuCAsp4)

Your homework for this lesson is to make the **Tasty Buffet** way better! 

> _When you're done with your homework, save your work in CodePen, and send the link in Slack!_

### Buffet Remodel

* Add CSS styling to give your buffet some heart and soul! _Feel free to make any changes you like, just don't remove any of the DOM interaction_

### The "Chow Down" feature

* Write a second function that the "Chow Down" button will use, and update the "stomach" paragraph accordingly.
  * If the user added less than 3 items to their plates, `<p class="stomach"></p>` should have content added that says something about still being hungry.
  * If the user added 4 or 5 items, then the "stomach" paragraph tag should display something about being satisfied
  * If the user added more than 5 items, then the p tag should read something about being full.

### Michelin Stars (Stretch goals)

* Think about making your buffet accessible. Add `aria` attributes to your code. (look into `aria-live` regions in particular)
* When a user clicks "Add to Plate", clear the text input.
* If a user types in "Pizza", add 🍕 to the plate instead of the text itself.
* Animate the food appearing on the plate with transitions or keyframes
  
