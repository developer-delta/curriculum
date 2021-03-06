# Objects

![Minifigure of Benny from the LEGO Movie](https://i.imgur.com/tBuVm9d.jpg)

In Javascript, sometimes we need to store a more complex set of information than an array will allow for. Whenever this need arises, it's time to reach for an `Object`.

`Objects` organize collections in a way that allows for easy retrieval and grouping. Objects are created by using curly braces `{}`.

```javascript
let benny = {};
```

Here we have defined a variable `benny`, and assigned it to an empty `Object`. Go ahead and create a new JS file, Chrome snippet, or Codepen if you'd like to follow along!

## When Objects are needed

Objects will come in handy if you are trying to group and relate multiple pieces of information together.

_Let's say that you're building an online LEGO Minifigure builder, and you want the user to be able to choose different colors and pieces._

* obj example with three or so properties. head, body, helmet(boolean)

```javascript
let benny = {
  helmet: true,
  torso: "Red",
  legs: "Blue"
}
```

Now our object has three `properties`! Properties of Objects always have a `name`, a colon `:`, and then a `value`. (`name: value`).

_If your Object has more than one property, you must separate them with a comma `,`, otherwise your code will break!_

Go ahead and `console.log` that object so we can take a look at it in the browser!

```javascript
console.log(benny);
```

![console.log(benny)](https://i.imgur.com/UvfIKhV.png)

> The browser is being helpful here by giving us a little preview of our object. But if we want to see the whole thing, just click on the little grey triangle on the left.

![Screen Shot 2021-03-03 at 9.58.42 AM](https://i.imgur.com/ZgNQFQf.png)

## Object Properties

Objects are made up of a collection of properties. You could have hundreds of properties in your Object, or just one! Properties contain information or functionality that is labelled by it's name (`key`).

In our object, The first `property` has a name (`key`) "helmet". And it's `value` is the boolean `true`.

```javascript
let benny = {
  helmet: true,
  torso: "Red",
  legs: "Blue"
}
```

### Retrieving Properties

Unlike arrays, you access Object properties by their name, not by an index. Try running this code to access the value of the "torso" property:

```javascript
console.log(benny.torso);
```

![Returns "Red"](https://i.imgur.com/z4OksEK.png)

What we just did there was use something called `dot notation` to access a property.

![Screen Shot 2021-03-06 at 9.10.20 AM](https://i.imgur.com/HAftEe8.png)

You can think of `dot notation` like directions for our code to find something. 

* When we say `benny.torso`, the computer sees `benny` first, and goes to find that variable (which is assigned to our object). 
* Then it sees the dot `.`, which tells the computer to look **inside** the object for what comes next. And what the computer is looking for is the property `torso`.
* When `torso` is found, the computer gives us back it's value. Which is `"Red"`!

_Try using dot notation to get the other 2 properties from the object!_

### Adding Properties

Dot notation isn't just helpful when we want to _retrieve_ properties from an object, but also when we want to _add_ a property!

Let's give `benny` a name to personalize him a bit.

```javascript
benny.name = [ 'Benny',  'Spaceman'];
```

Now `console.log` our object to see what that changed!

![Benny Object](https://i.imgur.com/TA5xTwy.png)

Look at that! `name` has been added to our object with an array value. An array was useful here because we wanted to give Benny a first name and a last name!

An Object can contain anything. They could have `arrays`, `booleans`, other `objects`, `functions`, `strings`, `numbers`, anything you want!

_Try and add a new property to `benny` called "age" that has a number value, then console.log to see if the object was updated!_

## Methods

When a function is added to an object, it is called a `method`. There are some special things we can do with these functions that live inside of Objects. To check them out, let's add a "catchphrase" `method` to Benny.

```javascript
let benny = {
  helmet: true,
  torso: "Red",
  legs: "Blue",
  name: ["Benny", "Spaceman"],
  catchphrase: () => {
    alert("Boy do I love Space!")
  }
}
```

Now lets `call` our method. _Remember a method is just a function that lives in an object, so we'll still need to `invoke` it._

```javascript
benny.catchphrase();
```

If you call a method and forget to `invoke` `()` it, the browser will just return the actual function _definition_ like this:

![benny.catchphrase function definition](https://i.imgur.com/kcYRajx.png)

So don't forget to invoke when you want to access a `method`!

![Screen Shot 2021-03-03 at 10.01.35 AM](https://i.imgur.com/9MNDAt3.jpg)

## This

Let's look at the concept of `this` in an object by adding another `method` to Benny.

```javascript
let benny = {
  helmet: true,
  torso: "Red",
  legs: "Blue",
  name: ["Benny", "Spaceman"],
  catchphrase: () => {
    alert("Boy do I love Space!")
  },
  greet: function() { 
    alert(`Hi! I'm ${this.name[0]}, and I build Spaceships`);
  }
}
```

* what is this, how to use. Do a function that alerts or something

## Nesting Objects

* sometimes called `sub-namespaces`

* drill down chaining dot notation to access deep objs

## Objects are everywhere

* quick note on how basically everything is an object

* how document. and Math. and all that jazz are methods on objects (Classes but don't get too in the weeds)

* Maybe a little preview of browser API's that we've already used

## Homework

![Screen Shot 2021-03-03 at 10.07.43 AM](https://i.imgur.com/rUHHLOZ.jpg)

* Now let's actually build a minifig generator for real!

* fork clone blah blah