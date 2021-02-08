* I really like the silly story generator from MDN
* math.random is pretty critical to make a function that does anything to randomly get a value from the array
* Magic 8 ball app maybe?
* MDN really has some good shit for this one.
* 

# Arrays

![Aerial view of shipping containers](https://images.unsplash.com/photo-1511578194003-00c80e42dc9b?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=2100&q=80)

> JavaScript **arrays** allow us to store multiple values together in a list. 

So far we have always assigned variables to a _single_ value. 

```javascript
const prefix = "THX";
const designation = 1138;
```

Here we have a variable `prefix` assigned a single string value, and we have a variable `designation` assigned a single number value.

Let's try concatenating those two variables:

```javascript
let name = prefix + " " + designation;
```

_Even_ the variable `name` is assigned to a single value. The value it is assigned to is `"THX 1138"`. _One value._

## Creating arrays

![concept art of the collectors room from guardians of the galaxy](https://external-preview.redd.it/-k4uZeUzc67hEfSk_YJSYV1-wLDxEaWy6Bs1GAqHwcA.jpg?auto=webp&s=26f087be1afa08ae75cec054406e72602d46c688)

**Arrays** allow us to store values as a group, but still retain individual values. Let's look at an example:

```javascript
const guardians = ['Groot', 'Star-Lord', 'Gamora', 'Rocket', 'Drax'];
```

`guardians` our variable that has been assigned to an array. If we `console.log` that variable:

```javascript
console.log(guardians);
```
It will print out the array `['Groot', 'Star-Lord', 'Gamora', 'Rocket', 'Drax']`.

Now we have contained multiple values as a group in one variable.

## Accessing array values





<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
    <meta name="viewport" content="width=device-width">

    <title>Silly story generator</title>

    <style>

    body {
      font-family: helvetica, sans-serif;
      width: 350px;
    }

    label {
      font-weight: bold;  
    }

    div {
      padding-bottom: 20px;
    }

    input[type="text"] {
      padding: 5px;
      width: 150px;
    }

    p {
      background: #FFC125;
      color: #5E2612;
      padding: 10px;
      visibility: hidden;
    }

    </style>
  </head>

  <body>
    <div>
      <label for="customname">Enter custom name:</label>
      <input id="customname" type="text" placeholder="">
    </div>
    <div>
      <label for="us">US</label><input id="us" type="radio" name="ukus" value="us" checked>
      <label for="uk">UK</label><input id="uk" type="radio" name="ukus" value="uk">
    </div>
    <div>
      <button class="randomize">Generate random story</button>
    </div>
    <!-- Thanks a lot to Willy Aguirre for his help with the code for this assessment -->
    <p class="story"></p>
    <script src="main.js"></script>
  </body>
</html>





---


const customName = document.getElementById('customname');
const randomize = document.querySelector('.randomize');
const story = document.querySelector('.story');

function randomValueFromArray(array){
  const random = Math.floor(Math.random()*array.length);
  return array[random];
}

let storyText = 'It was 94 fahrenheit outside, so :insertx: went for a walk. When they got to :inserty:, they stared in horror for a few moments, then :insertz:. Bob saw the whole thing, but was not surprised — :insertx: weighs 300 pounds, and it was a hot day.';
let insertX = ['Willy the Goblin','Big Daddy','Father Christmas'];
let insertY = ['the soup kitchen','Disneyland','the White House'];
let insertZ = ['spontaneously combusted','melted into a puddle on the sidewalk','turned into a slug and crawled away'];

randomize.addEventListener('click', result);

function result() {
  let newStory = storyText;

  let xItem = randomValueFromArray(insertX);
  let yItem = randomValueFromArray(insertY);
  let zItem = randomValueFromArray(insertZ);

  newStory = newStory.replace(':insertx:',xItem);
  newStory = newStory.replace(':insertx:',xItem);
  newStory = newStory.replace(':inserty:',yItem);
  newStory = newStory.replace(':insertz:',zItem);

  if(customName.value !== '') {
    const name = customName.value;
    newStory = newStory.replace('Bob',name);
  }

  if(document.getElementById("uk").checked) {
    const weight = Math.round(300*0.0714286) + ' stone';
    const temperature =  Math.round((94-32) * 5 / 9) + ' centigrade';
    newStory = newStory.replace('94 fahrenheit',temperature);
    newStory = newStory.replace('300 pounds',weight);
  }

  story.textContent = newStory;
  story.style.visibility = 'visible';
}