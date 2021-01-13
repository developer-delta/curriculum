> * Lecture -  about and recap (10 mins)
> * Lecture and working session - Coffee Machine (50 mins)
> * Homework - Card generator. Questions, convo, going over concepts (30+ mins)

* We should do our lesson on the DOM, THEN -
* Go through the flow of a git push, pull, PR together for a refresher,
* Then Assign tasks to different people to actually BUILD the "horses mouth" Greeting Card generator TOGETHER in a real open-source world.
* Maybe we all pair program on the BASE HTMl document during a class together.
* focus on the DOM and Conditionals.
* Whip out A11y shit as we go
* 


> _This project will also allow us to recap on semantic `HTML tags`, `CSS properties`, `CSS rules`, `variables`, `functions`, `git`, and GitHub._

# The Document Object Model

![A fancy picture frame and painting of coffee or something]()

**Using these two new superpowers, we will work together to create an interactive greeting-card generator**

![pic of fun greeting card generator]()

As we have been learning Javascript, you may have noticed that the only way to see what we've been making changes to is by open the `console`. That's cool and all, but what if we wanted to make changes to what the user _actually sees_ on the page? Like updating a number or validating a form input? The DOM makes all that possible.

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
  * if inside, card opens goes inside\
  * Use query parameters to send it to people??

---

NOTES

* Editing and expanding on the SAME function (Coffee) is helpful I think. Making it grow and encompass more things is really helpful  

* console.log the whole function, not just console.log inside the function.

* Coffee metaphor
  * Function is like coffee machine
  * Takes parameters - Beans, grounds, 
  * function with multiple parameters - Automated waiting room coffee machine
  * return is like the little door sliding open