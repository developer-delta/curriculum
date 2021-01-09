> OVERVIEW:
> * Lecture -  about and recap (10 mins)
> * Lecture and working session - Coffee Machine (50 mins)
> * Homework - Card generator. Questions, convo, going over concepts (30+ mins)

# JavaScript conditionals and the DOM

![Choose your own adventure book. Maybe from black mirror]()

As we have been learning Javascript, you may have noticed that the only way to see what we've been making changes to is by open the `console`. That's cool and all, but what if we wanted to make changes to what the user _actually sees_ on the page? Like updating a number or validating a form input? The DOM makes all that possible.

In addition to dabbling with the DOM, we'll also learn one more piece of JavaScript logic called conditionals, or "if" statements. These are tools in our JS toolbelt that allow us to write code that can _make decisions_.

**Using these two new superpowers, we will work together to create an interactive greeting-card generator**

![pic of fun greeting card generator]()

> _This project will also allow us to recap on semantic `HTML tags`, `CSS properties`, `CSS rules`, `variables`, `functions`, `git`, and GitHub._

---

# Recap

### Variables

* Variables are containers for values we want to store. Let's say we have some nice Sumatra coffee beans that we want to put into a container to use later.

  ```javascript
  // variable declaration and assignment
  const fancyBeans = "sumatra";
  ```

  ![pic of container of beans with lid]()

  that container is _only_ for sumatra beans. If we wanted one where we could change what type of beans go in, we'd use a `let`.

  ```javascript
  // variable declaration
  let anyBean;
  // variable assignment
  anyBean = "Dunkin";
  ```

  ![pic of container of beans without lid]()
  
  And later if we wanted to put better beans in there, we could!

  ```javascript
  // variable reassignment
  anyBean = "Sumatra";
  ```

  ![pic of wonderful beans!]()

### Functions

Functions are the foundation of our JavaScript code. They are machines that we use to complete tasks, manipulate things, or handle repetition.

![pic of awesome waiting room machine]()

Let's build a coffee machine for our new coffee beans. _And not just_ a Mr. Coffee, let's make one of those awesome waiting-room monoliths with all kinds of business.

```javascript
// declare function named "megaCoffeeMachine"
const megaCoffeeMachine = () => {

}

console.log(megaCoffeeMachine()); 
```

![img of coffee machine just a box with a hopper not much going on]()

Now that function isn't really going to do anything, but it's a start. Let's put in our coffee beans at least!

```javascript
// "beans" is a parameter
const megaCoffeeMachine = (beans) => {

}

// "fancyBeans" is an argument
console.log(megaCoffeeMachine(fancyBeans));
```

![img of pouring beans in top]()

Now we have a machine that takes in some beans, but they seem to disappear inside. Our `console.log` statement doesn't give us anything...

What we're missing is the `return` statement. By using the return statement, that little slidey plastic door on the front of the coffee machine should open up and give us something back!

```javascript
const megaCoffeeMachine = (beans) => {
  return beans;
}

console.log(megaCoffeeMachine(fancyBeans)); // logs "sumatra"
```

![drawing of beans coming out door]()

Alright, now we got something back, although our machine doesn't _do_ anything with the beans, we still have built a machine and are ready to add features to it!

Let's give back a simple string explaining what kind of coffee they're getting. Looks like a simple cup of black coffee.

```javascript
const megaCoffeeMachine = (beans) => {
  const yourDrink = "Here's a tasty cup of " + beans + " coffee. Enjoy!";
  return yourDrink;
}

console.log(megaCoffeeMachine(fancyBeans)); // logs "here's a tasty cup of sumatra coffee. Enjoy!"
```

![fun pic of a black cup of coffee coming out of machine]()

But what of those folks who like cream in their coffee? Let's add some functionality to accommodate them.

```javascript
const megaCoffeeMachine = (beans) => {
  const yourDrink = "Here's a tasty cup of " + beans + " coffee with cream!";
  return yourDrink;
}

console.log(megaCoffeeMachine(fancyBeans)); // logs "here's a tasty cup of sumatra coffee with cream!"
```

So we have cream in our coffee now, but now we can't give out just black coffee. I _suppose_ we could build a whole 'nother coffee machine for black coffee, but that seems overkill, there's gotta be a better way.

---

# Conditionals

_In come `conditionals` to save the day for our coffee machine!_

`conditionals` allow your code to make decisions based on inputs. They use the statements `if` and `else` to make this happen. Let's take a look -

```javascript

let dude = "Dingus";

if(dude === "Dingus") {
  console.log("This guy is a total dingus.");
} else {
  console.log("Oh man yeah he's not a dingus at all.");
}
```

The `condition` in an `if` `else` statement lives between the parentheses `()`. Everything in those parentheses **has** to evaluate to `true` to be run. So this for example will do absolutely nothing -

```javascript
if(false) {
  console.log("I will never ever happen");
}
```

And this will print "But I'll ALWAYS happen!" every time -

```javascript
if(false) {
  console.log("I will never ever happen");
} else {
  console.log("But I'll ALWAYS happen!");
}
```

If else statements are one of the more "readable" pieces of JS that naturally just make sense and _do what they look like they're doing_.

**_But back to our coffee machine!!_**

Let's use a `conditional` to solve our cream problem!

```javascript
const megaCoffeeMachine = (beans, cream) => {
  
  let yourDrink;

  if(cream) {

    yourDrink = "Here's a tasty cup of " + beans + " coffee with cream!";

  } else {

    yourDrink = "Here's a tasty cup of " + beans + " coffee, black as night!";

  }

  return yourDrink;
}

console.log(megaCoffeeMachine(fancyBeans, true)); 
console.log(megaCoffeeMachine(fancyBeans));
```

Here's that same code with some added notes -

```javascript
const megaCoffeeMachine = (beans, cream) => {
  
  // declare yourDrink (like an empty cup waiting for coffee)
  let yourDrink;

  // use a conditional that checks if the cream parameter is true
  if(cream) {
    // if cream is true, then reassign the yourDrink variable to a sentence about cream
    yourDrink = "Here's a tasty cup of " + beans + " coffee with cream!";

  // if cream is NOT true (or doesn't exist), then reassign yourDrink variable to a sentence without cream
  } else {
    yourDrink = "Here's a tasty cup of " + beans + " coffee, black as night!";
  }
  return yourDrink;
}

console.log(megaCoffeeMachine(fancyBeans, true)); // logs "here's a tasty cup of sumatra coffee with cream!"
console.log(megaCoffeeMachine(fancyBeans)); // logs "here's a tasty cup of sumatra coffee, black as night!"
```

![Two cups of coffee!!]()

**Booyah functionality!!**

> Try and add a conditional to check if a user wants decaf or regular!

We can use another feature of `conditionals` called `else if` if we want to have multiple options. What if somebody wants a dairy alternative creamer?

```javascript
const megaCoffeeMachine = (beans, cream) => {
  
  let yourDrink;

  if(cream) {

    yourDrink = "Here's a tasty cup of " + beans + " coffee with cream!";

  } else if(cream === "VEGAN") {

    yourDrink = "We get it you're vegan... " + beans + " coffee, vegan AF!";

  } else {

    yourDrink = "Here's a tasty cup of " + beans + " coffee, black as night!";

  }

  return yourDrink;
}

console.log(megaCoffeeMachine(fancyBeans, true)); 
console.log(megaCoffeeMachine(fancyBeans));
console.log(megaCoffeeMachine(fancyBeans, "VEGAN"));
```

Now we have multiple options for our users for cream as well. But we probably want our function to see the light of day! To get it out on the page where it can be seen, and used, and loved!

---

# The Document Object Model

![A fancy picture frame and painting of coffee or something]()

The `DOM` is the Document Object Model.

For now the important part to remember is `document`. The `DOM` is basically everything you see on your screen.

It is essentially the HTML `document` being rendered as your browser sees it. But it's special power is that we can access this document with JavaScript because of the `DOM`.

Let's say we wanted our coffee shop patrons to be able to access our coffee machine from the browser, and actually interact with it. Let's check out a possible example.

In the `body` of our `HTML` file -
```html
<select id="coffeeTypes"> 
  <option value="">Black coffee</option>
  <option value="cream">Coffee with cream</option>
  <option value="VEGAN">Coffee with soy creamer</option>
</select>

<p></p>
```

And in our JS file -

```javascript
const dropDownMenu = document.querySelector('select');

dropDownMenu.addEventListener('change', megaCoffeeMachine(fancyBeans));

const megaCoffeeMachine = (beans) => {

  const creamChoice = dropDownMenu.value; 
  
  let yourDrink;

  if(creamChoice) {

    yourDrink = "Here's a tasty cup of " + beans + " coffee with cream!";

  } else if(creamChoice === "VEGAN") {

    yourDrink = "We get it you're vegan... " + beans + " coffee, vegan AF!";

  } else {

    yourDrink = "Here's a tasty cup of " + beans + " coffee, black as night!";

  }

  return yourDrink;
}
```

Our HTML snippet there simply creates a common drop-down select menu. We give `string` values to all of the `options` in our dropdown. (these will be used in our JS)

Next in our JS we add `DOM` interaction.

```javascript
const dropDownMenu = document.querySelector('select');
```

`document.` is the really important part there. That is a **gift from our browser to our JavaScript** that let's us access our `HTML` to modify it or get information from it. In this case we are using `querySelector` to access our drop down menu items.

> _There are a multitude of "methods" that `document.` can be used with, and googling the action you want to take will usually get you to the right one! In this case we are just using `querySelector` and `addEventListener`_

Then we use something called an "event listener" that also does what it sounds like it does. You tell it to pay attention to a certain HTML element, and then it will execute any function you like when it sees a change. 

```javascript
dropDownMenu.addEventListener('change', megaCoffeeMachine(fancyBeans));
```

When any change happens to the dropdown menu, we want to trigger our `megaCoffeeMachine` function with the `fancyBeans` as an argument.

Now we're allowing our _user_ to actually leverage our JavaScript in a powerful way! But the last missing piece is to display the **output** of our function to the page. 

We can use the `DOM` not just to get information, but also to send it _back_ to our `HTML`. Remember that tiny empty `<p></p>` tag we added at the end of our `HTML`? Let's put something in it!

```javascript
const paragraph = document.querySelector('p');
```

This allows us to target our paragraph element to be used later on.

And in our conditional instead of `return`ing the `yourDrink` variable, we'll just shove that string into our paragraph element using `textContent` (another gift from the `DOM` gods).

```javascript
paragraph.textContent = yourDrink;
```

And here is what the whole JS file would look like with everything we've written so far -

```javascript
let anyBean;
anyBean = "Dunkin";

anyBean = "Sumatra";

const fancyBeans = "sumatra";

const dropDownMenu = document.querySelector('select');
const paragraph = document.querySelector('p');

dropDownMenu.addEventListener('change', megaCoffeeMachine(fancyBeans));

const megaCoffeeMachine = (beans) => {

  const creamChoice = dropDownMenu.value; 
  
  let yourDrink;

  if(creamChoice) {

    yourDrink = "Here's a tasty cup of " + beans + " coffee with cream!";

  } else if(creamChoice === "VEGAN") {

    yourDrink = "We get it you're vegan... " + beans + " coffee, vegan AF!";

  } else {

    yourDrink = "Here's a tasty cup of " + beans + " coffee, black as night!";

  }

  paragraph.textContent = yourDrink;
}
```

![Awesome total package coffee machine!!!]()

---

HOMEWORK

* Thank you card generator
  * cp entire "card" directory and rename it for PR
  * This will be a follow along learning project. After class ask everyone to make changes to theirs and submit a Pull Request. Maybe have PR's in during class but encourage everyone to make changes after as well.
  * Code along together. Speaking what needs to be written, then writing it. Starting with pseudo code.
  * if front, card stays closed goes on front
  * if inside, card opens goes inside

---

NOTES

20 MINS of lecture, 40 mins of working session, 30+ mins of conversation/recap

* In lecture let's have a simple text input and an alert message popping up if the name is something or another. GOOGLE away

* Editing and expanding on the SAME function (Coffee) is helpful I think. Making it grow and encompass more things is really helpful  

* console.log the whole function, not just console.log inside the function.

* Coffee metaphor
  * Function is like coffee machine
  * Takes parameters - Beans, grounds, 
  * function with multiple parameters - Automated waiting room coffee machine
  * return is like the little door sliding open





<!-- * Good truck metaphor [from Kevin Kononenko](https://blog.codeanalogies.com/2017/12/20/a-visual-guide-to-understanding-the-sign-in-javascript/) -->