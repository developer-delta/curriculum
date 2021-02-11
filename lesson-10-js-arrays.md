# Arrays

![Vintage vending machines](https://i.pinimg.com/originals/63/51/a3/6351a3e746f8fdfcdb3ddfebdd7ac353.jpg)

JavaScript **arrays** allow us to store multiple values together in a list. Similar to how vending machines can hold lots of individual snacks in one container.

> _If you'd like to follow along, you can create a new JS/HTML document and open it in your browser, use the Chrome snippets feature, or use Codepen! (make sure to open up the console to see your output!)_

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

Here's an array in it's simplest, empty form.

```javascript
[];
```

![empty vending machine](https://daily49er.com/wp-content/uploads/2020/09/vendingmachine2-1000x600.jpg)

**Arrays** allow us to store values as a group, but still retain individuality. Let's look at an example:

```javascript
const candyBars = ['Twix', 'Snickers', 'Bounty', 'Mars', 'NutRoll'];
```

`candyBars` is our variable that has been assigned to an array. If we `console.log` it we get:

```javascript
['Twix', 'Snickers', 'Bounty', 'Mars', 'NutRoll']
```

Now we have contained multiple values as a group in one variable. An array!

## Accessing specific array items

* Vending machine number 0 gif getting stuff for you
* 0 based index
* Using .length to get the last item

## Setting array values

* What do we mean when we say method?
* push
* unshift

## Get array values

* why this instead of get specific?
* pop
* shift

## IndexOf find in array

* Build vending machine orders per person

## Combining an array

* print out a sentence and concatenate with array.join(' ')

## Storing different value types

* Array can contain strings, numbers, booleans, and even functions!

## Homework

![Fallout 76 vending machines](https://cdn.mos.cms.futurecdn.net/PveeBUTk5pJap95EFus7mP.png)

Fork and clone [the array homework repository](https://github.com/developer-delta/iffy-quotes), and follow the steps in the `README` and `app.js` file. You'll be using arrays like a pro in no time!
