# JavaScript Conditionals

![Choose your own adventure book. Maybe from black mirror](https://miro.medium.com/max/3066/1*o6N2_Yvw9nsWAmi8qK_4pQ.jpeg)

As we have been learning Javascript, our code has been very "static" so far. Everything that happens has been laid out in stone by us when we wrote the code. But letting our code make it's own decisions based on a set of parameters is where the real power of programming will start to shine. And we get to implement that sci-fi majesty with a simple piece of JS syntax called `conditionals`.

# JS Recap

## Variables

Variables are containers for values we want to store. Let's say we have some nice Dutch Bros coffee beans that we want to put into a container to use later.

```javascript
// variable declaration and assignment
const beanVariety = "Dutch";
```

that container is _only_ for Dutch beans. If we wanted a variable where we could change what type of beans go in, we'd use a `let`.

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

Let's build a coffee machine for our new coffee beans. And not _just_ a Mr. Coffee, let's make one of those awesome vending monoliths with all kinds of bells and whistles.

![awesome waiting room machine](https://images.unsplash.com/photo-1572612361555-50ea11ec50b7?ixlib=rb-1.2.1&ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&auto=format&fit=crop&w=2100&q=80)

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

// "beanVariety" is an argument
console.log(megaCoffeeMachine(beanVariety));
```

<!-- ![img of pouring beans in top]() -->

Now we have a machine that takes in some beans, but they seem to disappear inside. Our `console.log` statement doesn't give us anything...

What we're missing is the `return` statement. By using the return statement, that little slidey plastic door on the front of the coffee machine should open up and give us something back!

```javascript
const megaCoffeeMachine = (beans) => {
  return beans;
}

console.log(megaCoffeeMachine(beanVariety)); // logs "sumatra"
```

<!-- ![drawing of beans coming out door]() -->

Alright, now we got something back, although our machine doesn't _do_ anything with the beans, we still have built a machine and are ready to add features to it!

Let's give back a simple string explaining what kind of coffee they're getting. Looks like a simple cup of black coffee.

```javascript
const megaCoffeeMachine = (beans) => {
  const yourDrink = "Here's a tasty cup of " + beans + " coffee. Enjoy!";
  return yourDrink;
}

console.log(megaCoffeeMachine(beanVariety)); // logs "here's a tasty cup of sumatra coffee. Enjoy!"
```

<!-- ![fun pic of a black cup of coffee coming out of machine]() -->

But what of those folks who like sugar in their coffee? Let's add some functionality to accommodate them.

```javascript
const megaCoffeeMachine = (beans) => {
  const yourDrink = "Here's a tasty cup of " + beans + " coffee with sugar!";
  return yourDrink;
}

console.log(megaCoffeeMachine(beanVariety)); // logs "here's a tasty cup of sumatra coffee with sugar!"
```

So we have sugar in our coffee now, but now we can't give out just black coffee. I _suppose_ we could build a whole 'nother coffee machine for black coffee, but that seems overkill, there's gotta be a better way.

# Conditionals

![three cups of coffee, one black, one with sugar, and one with lots of sugar](https://i.imgur.com/6yxh8Jb.png)

_Let's add `conditionals` to save the day for our coffee machine!_

`conditionals` allow your code to make decisions based on inputs. They use the statements `if` and `else` to make this happen. Let's take a look -

```javascript

let chad = "Energy drink fan";

if(chad === "Energy drink fan") {
  console.log("Got a cool guy over here. Way too cool for coffee.");
} else {
  console.log("Carmel macchiato it is!");
}
```

The `condition` in an `if` `else` statement lives between the parentheses `()`. Everything in those parentheses **has** to evaluate to `true` to be run. So this for example will do absolutely nothing -

```javascript
if(false) {
  console.log("I will never ever happen");
}
```

And this will print `"But I'll ALWAYS happen!"` every time -

```javascript
if(false) {
  console.log("I will never ever happen");
} else {
  console.log("But I'll ALWAYS happen!");
}
```

`if` and `else` statements are one of the more "readable" pieces of JS that naturally just make sense and _do what they look like they're doing_.

**_But back to our coffee machine!!_**

Let's use a `conditional` to solve our sugar problem!

```javascript
const megaCoffeeMachine = (beans, sugar) => {
  
  let yourDrink;

  if(sugar) {

    yourDrink = "Here's a tasty cup of " + beans + " coffee with sugar!";

  } else {

    yourDrink = "Here's a tasty cup of " + beans + " coffee, black as night!";

  }

  return yourDrink;
}

console.log(megaCoffeeMachine(beanVariety, true)); 
console.log(megaCoffeeMachine(beanVariety));
```

Here's that same code with some added notes -

```javascript
const megaCoffeeMachine = (beans, sugar) => {
  
  // declare yourDrink (like an empty cup waiting for coffee)
  let yourDrink;

  // use a conditional that checks if the sugar parameter is true
  if(sugar) {
    // if sugar is true, then reassign the yourDrink variable to a sentence about sugar
    yourDrink = "Here's a tasty cup of " + beans + " coffee with sugar!";

  // if sugar is NOT true (or doesn't exist), then reassign yourDrink variable to a sentence without sugar
  } else {
    yourDrink = "Here's a tasty cup of " + beans + " coffee, black as night!";
  }
  return yourDrink;
}

console.log(megaCoffeeMachine(beanVariety, true)); // logs "here's a tasty cup of sumatra coffee with sugar!"
console.log(megaCoffeeMachine(beanVariety)); // logs "here's a tasty cup of sumatra coffee, black as night!"
```

<!-- ![Two cups of coffee!!]() -->

**Booyah functionality!!**

We can use another feature of `conditionals` called `else if` if we want to have multiple options. What if somebody wants a dairy alternative sugarer?

```javascript
const megaCoffeeMachine = (beans, sugar) => {
  
  let yourDrink;

  if(sugar) {

    yourDrink = "Here's a tasty cup of " + beans + " coffee with sugar!";

  } else if(sugar === "splenda") {

    yourDrink = "Here's a tasty cup of " + beans + " coffee with Splenda, enjoy!";

  } else {

    yourDrink = "Here's a tasty cup of " + beans + " coffee, black as night!";

  }

  return yourDrink;
}

console.log(megaCoffeeMachine(beanVariety, true)); 
console.log(megaCoffeeMachine(beanVariety));
console.log(megaCoffeeMachine(beanVariety, "splenda"));
```

> _Now we have multiple options for our users!_

---

#### Coming up

But we probably want our function to be used on the web, so someone could place a coffee order on a website for example! The key piece there is the `DOM`. The `DOM` will allow us to take our _logic_ we've written here, and then take inputs and give outputs on a webpage. And we'll learn that next week!

You're doing an awesome job, this is a lot of dense stuff to absorb, be proud of how far you've come!

# Homework

![Grogu (Baby Yoda) being placed into a school desk alongside a classroom full of school children](https://64.media.tumblr.com/caa2bfd13cc1907370e3195cccc5cd6b/690b941ee8341d9b-e2/s500x750/1461703cad7b49a220128b5650b5d74333d8b99f.gif)

[Copy this JavaScript file](https://github.com/developer-delta/code-examples/blob/main/conditionals.js) into a [Chrome snippet](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets), and follow each step carefully. You'll be building on what we have already learned, and solidifying some of your new knowledge of conditionals!