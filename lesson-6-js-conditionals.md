# JavaScript conditionals

![Choose your own adventure book. Maybe from black mirror](https://miro.medium.com/max/3066/1*o6N2_Yvw9nsWAmi8qK_4pQ.jpeg)

As we have been learning Javascript, our code has been very "static" so far. Everything that happens has been laid out in stone by us when we wrote the code. But letting our code make it's own decisions based on a set of parameters is where the real power of programming will start to shine. And we get to implement that sci-fi majesty with a simple piece of JS syntax called `conditionals`.

# JS Recap

## Variables

Variables are containers for values we want to store. Let's say we have some nice Sumatra coffee beans that we want to put into a container to use later.

```javascript
// variable declaration and assignment
const fancyBeans = "sumatra";
```

that container is _only_ for sumatra beans. If we wanted one where we could change what type of beans go in, we'd use a `let`.

```javascript
// variable declaration
let anyBean;
// variable assignment
anyBean = "Dunkin";
```

And later if we wanted to put better beans in there, we could!

```javascript
// variable reassignment
anyBean = "Sumatra";
```

## Functions

Functions are the foundation of our JavaScript code. They are machines that we use to complete tasks, manipulate things, or handle repetition.

Let's build a coffee machine for our new coffee beans. _And not just_ a Mr. Coffee, let's make one of those awesome waiting-room monoliths with all kinds of business.

  ![awesome waiting room machine](https://i.pinimg.com/736x/f8/82/cc/f882cccaa8d75a6854a3b3d40bdde9e2.jpg)

```javascript
// declare function named "megaCoffeeMachine"
const megaCoffeeMachine = () => {

}

console.log(megaCoffeeMachine()); 
```

<!-- ![img of coffee machine just a box with a hopper not much going on]() -->

Now that function isn't really going to do anything, but it's a start. Let's put in our coffee beans at least!

```javascript
// "beans" is a parameter
const megaCoffeeMachine = (beans) => {

}

// "fancyBeans" is an argument
console.log(megaCoffeeMachine(fancyBeans));
```

<!-- ![img of pouring beans in top]() -->

Now we have a machine that takes in some beans, but they seem to disappear inside. Our `console.log` statement doesn't give us anything...

What we're missing is the `return` statement. By using the return statement, that little slidey plastic door on the front of the coffee machine should open up and give us something back!

```javascript
const megaCoffeeMachine = (beans) => {
  return beans;
}

console.log(megaCoffeeMachine(fancyBeans)); // logs "sumatra"
```

<!-- ![drawing of beans coming out door]() -->

Alright, now we got something back, although our machine doesn't _do_ anything with the beans, we still have built a machine and are ready to add features to it!

Let's give back a simple string explaining what kind of coffee they're getting. Looks like a simple cup of black coffee.

```javascript
const megaCoffeeMachine = (beans) => {
  const yourDrink = "Here's a tasty cup of " + beans + " coffee. Enjoy!";
  return yourDrink;
}

console.log(megaCoffeeMachine(fancyBeans)); // logs "here's a tasty cup of sumatra coffee. Enjoy!"
```

<!-- ![fun pic of a black cup of coffee coming out of machine]() -->

But what of those folks who like cream in their coffee? Let's add some functionality to accommodate them.

```javascript
const megaCoffeeMachine = (beans) => {
  const yourDrink = "Here's a tasty cup of " + beans + " coffee with cream!";
  return yourDrink;
}

console.log(megaCoffeeMachine(fancyBeans)); // logs "here's a tasty cup of sumatra coffee with cream!"
```

So we have cream in our coffee now, but now we can't give out just black coffee. I _suppose_ we could build a whole 'nother coffee machine for black coffee, but that seems overkill, there's gotta be a better way.

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

<!-- ![Two cups of coffee!!]() -->

**Booyah functionality!!**

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

Now we have multiple options for our users for cream as well.


But we probably want our function to be used on the web, so someone could place a coffee order on a website for example! The key piece there is the DOM. The DOM will allow us to take our _logic_ we've written here, and then take inputs and give outputs on a webpage. And we'll learn that next week!

You're doing an awesome job, this is a lot of heavy stuff to take in, so give yourself a pat on the back for coming this far!
