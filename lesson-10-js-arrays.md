# Arrays

![Vintage vending machines](https://i.pinimg.com/originals/63/51/a3/6351a3e746f8fdfcdb3ddfebdd7ac353.jpg)

JavaScript **arrays** allow us to store multiple values together. Kind of like how vending machines can hold lots of individual snacks in one container.

> _If you'd like to follow along, you can create a new JS/HTML document and open it in your browser, use the Chrome snippets feature, or just write directly in your console! (make sure to open up the console to see your output!)_

<details>
  <summary><em>How to follow along in the console!</em></summary>
  <img src="https://i.imgur.com/NPX7chl.gif" alt="" width="300px" height="200px">
</details>

![A bunch of little mini Twix bars](https://i.imgur.com/e9nioE3.png)

So far we have only assigned variables to a _single_ value.

```javascript
const snack = "Twix";
const slot = 18;
```

Here we have a variable `snack` assigned a single string value, and we have a variable `slot` assigned a single number value.

Let's try concatenating those two variables:

```javascript
let name = snack + " " + slot;
```

_Even_ the variable `name` is assigned to a single value. The value it is assigned to is **`"Twix 18"`**. _One value._

## Creating arrays

Arrays allow us to store values as a group, but still retain individuality. Let's look at an array in it's simplest, empty form:

```javascript
[];
```

Alright. Now let's put some values in there!

![empty vending machine](https://daily49er.com/wp-content/uploads/2020/09/vendingmachine2-1000x600.jpg)

```javascript
const candyBars = ['Twix', 'Snickers', 'Bounty', 'Mars', 'NutRoll'];
```

`candyBars` is our variable that has been assigned to an array. If we `console.log` it we get:

```javascript
['Twix', 'Snickers', 'Bounty', 'Mars', 'NutRoll']
```

Now we have contained multiple values as a group in one variable. An array!

## Accessing array items

![A monkey trying to grab chips out of a vending machine](https://media1.tenor.com/images/1814b8a61f663cbe3c45c9b5ef577baa/tenor.gif?itemid=3538273)

Before we get items out of our array, it's important to know how JavaScript understands the _location_ of each item.

### Indexes

The term for "location" in an array is called an `index`. And JavaScript starts counting `indexes` from `0`. It's sometimes called a **zero based index**.

```javascript
//                    0         1         2        3         4
const candyBars = ['Twix', 'Snickers', 'Bounty', 'Mars', 'NutRoll'];
```

So if we wanted to get just the **Snickers** bar, and assign it to it's own value, we could write:

```javascript
let myFave = candyBars[1];
console.log(myFave); // logs Snickers
```

We use brackets `[]` to tell our code we want to access a value in the array, and inside those brackets, we pass the `index`. So if we wanted to get the **Twix** bar, we'd write:

```javascript
let yourFave = candyBars[0];
console.log(yourFave); // logs Twix
```

### Length

Another useful feature of arrays is their `.length` property. This is a built-in property that will return the arrays length.

```javascript
const candyBars = ['Twix', 'Snickers', 'Bounty', 'Mars', 'NutRoll'];

console.log(candyBars.length) // logs 5
```

> _It's important to note that although JS uses a **zero based index** to **access** items, the length property simply returns the number of items in the array, it doesn't **count** them starting at `0`_

The `.length` property is most valuable when it is used for `iteration`, or looping. Loops and iteration are their own lesson, but it's good to keep in mind!

For now though, we could use `.length` to grab the last item in the array, even if we don't know how long it is! The `index` of the last item is going to be the arrays length **minus one**. This will account for the **zero based index**.

```javascript
//                    0         1         2        3         4
const candyBars = ['Twix', 'Snickers', 'Bounty', 'Mars', 'NutRoll'];

let last = candyBars.length;
console.log(last); // logs 5

console.log(candyBars[last -1]); // logs 'NutRoll'
```

> _It's also important to note that we were able to place an **expression** between the brackets. The **result** of the expression is used for the index. In this case `4`._

![Screen Shot 2021-02-12 at 12.57.07 PM](https://i.imgur.com/3qfSKpZ.png)

## Setting values

Not only can we retrieve items and values from our array, but we can also **add** new items and values. There are a few different ways we can do this, but the most common is by using the `push` method. 

> _remember a `method` is just a function_

`push` takes one argument, and will put that argument at the end of the array you call it on.

```javascript
const candyBars = ['Twix', 'Snickers', 'Bounty', 'Mars', 'NutRoll'];

candyBars.push('Kit Kat');

console.log(candyBars); // logs ["Twix", "Snickers", "Bounty", "Mars", "NutRoll", "Kit Kat"]
```

## Removing items

To remove the last item of an array, you can use the `pop` method. It's good to keep in mind though that this doesn't just _give_ you the value of the last item, it _removes_ it from the array altogether.

```javascript
const candyBars = ['Twix', 'Snickers', 'Bounty', 'Mars', 'NutRoll'];

console.log(candyBars.pop()); // logs "NutRoll"

console.log(candyBars); // logs ["Twix", "Snickers", "Bounty", "Mars"]
```

## Searching an array

If you want to find a specific value in an array, you can do that with `indexOf`. If it exists, it will return the index of that item. If nothing is found, it will return `-1`.

```javascript
//                    0         1         2        3         4
const candyBars = ['Twix', 'Snickers', 'Bounty', 'Mars', 'NutRoll'];

console.log(candyBars.indexOf('Bounty')); // logs 2

console.log(candyBars.indexOf('Milky Way')); // logs -1
```

## Array contents

Arrays in JavaScript can contain **anything** and everything. They can contain other arrays, numbers, strings, booleans, functions, literally anything. And that goes for mixing and matching too! Here are some mixed arrays:

```javascript
let junk = ["", 3, ["stuff", true], 109, "things"];

let arrayOfArrays = [[], [], [], []];

let boolArray = [true, false];

let string = ['c', 'h', 'e', 'e', 's', 'e'];
```

## Homework

![Fallout 76 vending machines](https://cdn.mos.cms.futurecdn.net/PveeBUTk5pJap95EFus7mP.png)

> _There's a lot more to arrays that we'll learn in the future, but for now let's stop and run with what we've learned._

Fork and clone [the array homework repository](https://github.com/developer-delta/iffy-quotes), and follow the steps in the `README` and `app.js` file.

**You'll be using arrays like a pro in no time!**
