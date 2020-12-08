# A Cascade of Style

![A waterfall rises into mist over frost and snow covered stones at it's rocky base. A black bird flies in front of the water, showing the scale and grandeur of the landscape.](https://images.unsplash.com/photo-1582039668235-06af31894aa2?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80)

CSS is the second of the three pillars of the web, and it gives color, personality, movement, font variations, layouts, etc. Simply put, it gives it style!

---

![From Harry Potter, a gif of Kingsley Shacklebolt saying "You may not like him, Minister, but you can't deny: Dumbledore's got style." ](https://64.media.tumblr.com/tumblr_lkij4cGXN21qd6dnso1_500.gif)

## Terminology
`CSS` stands for "cascading style sheets". It works like a waterfall, in the sense that the browser reads your CSS from the top of your document down, literally! The most recent style change you made will take precedence, even if you gave a conflicting order higher up in your CSS.

_We'll look at an example in a second that hopefully makes this more clear. But this is the reason it's called the "cascade": it flows from the top down._

---

## Wiring it up

Let's take a quick look at _how_ we can leverage CSS to modify our HTML. We'll need a way for our HTML to communicate with the styles we'll be writing. There are three ways we can do this: [inline style attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/style), [style element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style), or using an _external stylesheet_. We'll be focusing on external stylesheets as they are generally considered best practice. They also follow the [separation of concerns](https://en.wikipedia.org/wiki/Separation_of_concerns).

* Let's create a basic html file and name it `index.html`.
  * We'll add a `<div>` element with a nested `<p>` element to the `<body>`so we have something to style.
    ```html
    <!DOCTYPE html>
    <html lang="en-US">

      <head>
        <meta charset="utf-8">
      </head>

      <body>
        <div>
          <p>I'm a paragraph in a div!</p>
        </div>
      </body>

    </html>
    ```

* To connect an external stylesheet to our HTML, we'll use the `<link>` element.

  ```html 
  <link>
  ```
  _Note that there is no __closing__ tag for the `link` element (because it contains no content)._
* There are two `attributes` that must be added to the `link` element to make it valid: `rel` and `href`.
  ```html
  <link rel="stylesheet" href="my-stylesheet.css">
  ```
  _This communicates that the __relationship__ we're creating for our HTML here is for styling, and the __location__ of our stylesheet is `my-stylesheet.css`._
* The link tag must live inside of our `<head>` element. _The `<head>` element contains information the browser needs, but doesn't render content. It's like we're giving the browser directions to find it's styles._
  ```html
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="my-stylesheet.css">
  </head>
  ```
* Next we need to make sure that we have a stylesheet created where we said it was. Our file structure should look like this:
  ![Screenshot of index.html alongside styles.css in the file browser tab of stackblitz](https://i.imgur.com/qkraNJi.png)
* Inside of `my-stylesheet.css` let's add some code to see if it's working:
  ```css
  body {
    background-color: orange;
  }
  ```
  _this should change the background of your page to be orange, if it doesn't, check your spelling, and make sure that your css file is in the same folder as your html._

---

## Syntax

_Now that we have our CSS plugged in to our HTML, we can leverage the power of CSS to do pretty much anything!_

The way we use CSS to make changes is by defining _rules_ for different portions of our html to be styled specific ways. Let's say our paragraph element wasn't as big as we wanted it to be, and we'd also like for it to be purple, we could create the following CSS `rule`:
```css
p {
  font-size: 100px;
  color: purple;
}
```
That will change this:
!["I'm a paragraph in a div!" written in plain text](https://i.imgur.com/Flxaot5.png)
To this:
!["I'm a paragraph in a div!" written in huge purple font](https://i.imgur.com/QYwUmM4.png)

let's take a closer look at that CSS `rule` we just created:
![Screenshot of CSS rule with a "p" selector, declaration of "font-size: 100px;" second declaration of "color: purple:", and the whole this is labelled as a "CSS Rule"](https://i.imgur.com/mGaHU2I.png)

I don't want you to get too overwhelmed with all of the possibilities here. Let's just focus on this part of CSS `rules`:
```css
p {

}

div {

}

span {

}
``` 
There we have 3 different CSS `rules` that `target` all paragraph elements, all div (content division) elements, and all span elements.

No styling has been added to those CSS blocks, but they are targeting elements with their `selectors`.

If we add styling to those rules, _every_ instance of our target element will be styled that way. So for example if we had 5 `<div>`s, and we put a blue border in our corresponding css rule, __all__ 5 divs would have a blue border.
```html
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
```
_The `padding` and `margin` is just to make the example more clear. They give the boxes shape and space between each other_
```css
div {
  padding: 5px;
  margin: 5px;
  border: 3px solid blue;
}
```
Renders to:
![Five blue bordered boxes spanning the width of the browser window.](https://i.imgur.com/pch3ZMy.png)

Maybe that's exactly what we want, and if so, awesome! But what if you wanted all grey boxes and only the third one was blue? We can do that by creating a more _specific_ rule.

---

## Specificity

__Specificity__ is created many ways with CSS, but the most common is by using `classes` and `ids` to target elements with our CSS `selectors`.

> _Remember adding attributes to our HTML elements in the last class? One of the primary reasons we would want to add a `class` attribute is for more specific CSS styling! Let's look at an example:_
```html
<div></div>
<div></div>
<div class="im-blue-daba-dee-daba-dai"></div>
<div></div>
<div></div>
```
```css
div {
  padding: 5px;
  margin: 5px;
  border: 3px solid grey;
}

.im-blue-daba-dee-daba-dai {
  border: 3px solid blue;
}
```
Renders to:
![five boxes. The third bordered in blue, the rest bordered in grey](https://i.imgur.com/lse0cRC.png)

Ok! Let's unpack what we just did there. 
> In our HTML, we have 5 `<div>` elements, and the third one has a `class` attribute of `im-blue-daba-dee-daba-dai`.

> In our CSS we used an `element` selector of `div` to style _all_ of the divs in our document with a grey border.

> Next we used a CSS `class` selector of `.im-blue-daba-dee-daba-dai` to style all divs with that class. In our case there was only one. And we are able to give it a wacky, specific name, so that there's no conflict of who gets what styles. (Note that `class` selectors start with a `.` before the class name)

__BUT!!__

> Our third div was styled initially to have a grey border, and then it was styled to have a blue border... We see that the blue border won out, but why?

> This is why CSS is a _cascade_! The styles are viewed and applied as the browser encounters them. Flowing from top to bottom like a waterfall. Let's look at another example:

```html
<span class="clone">Captain Rex</span>
<span class="jedi">Ahsoka Tano</span>
<span class="clone">Commander Cody</span>
```
```css
span {
  border-bottom: 2px solid orange;
  background-color: lightgrey;
}

.clone {
  color: blue;
}

.jedi {
  font-weight: bold;
  background-color: lightblue;
}
```
Will render to:

!["Captain Rex" on the first line in blue text, grey background, and orange underline. "Ahsoka Tano" on the second line in black text, blue background, and orange underline. "Commander Cody" on the third line in blue text, grey background, and orange underline.](https://i.imgur.com/gjXDpSS.png)

In that example, we... 
* Styled all three `span`s with a bottom border of orange, and a background color of lightgrey. 
* Styled the elements with a `class` attribute of `clone` to have blue colored text content.
* Styled the elements with a `class` attribute of `jedi` to be bold and have a lightblue background color.
  * This rule came _last_ in the cascade, so it overrode the background color set above on the `span` elements.

So far, we have seen element selectors (targeted by tag name) and class selectors (targeted by class name with a `.` preceding them). But there is one more very common CSS selector that you'll need to know, and that is the __id__ selector.

Any element with an `id` attribute can be targeted with `#` like so:
```html
<div id="special"></div>
```
```css
#special {
  width: 20px;
  height: 20px;
  background: red;
}
```
Renders to:
![small red square](https://i.imgur.com/JkuJNnE.png)

---

⚠️ When adding an `id` attribute to your HTML, know that they are intended to be unique. You should never have two `id` attributes in your document with the same name. If you want duplicates, you should use a `class` attribute. ⚠️

---

## Declarations and Properties

![Michael Scott from the Office saying 'I do declare!'](https://i.imgur.com/Ix5hIcr.gif)

So far we haven't really talked too much about all the cool stuff you can do _inside_ of your css rules for different elements. Part of the reason is that there are a huge number of `properties` you can use, and they often have many variations. _Let's look at some more syntax real quick:_

This is a `declaration`:
```
color: red;
```
`color` is a CSS property, and `red` is it's `value`.

_You need the colon `:` between them, and the semicolon `;` after the line to make it valid CSS._

---

## Hands On

The best way to learn some CSS properties and understand the nuances of the language is just to dive in. Think about how you might want to change your document, and then just look up how you might do that online. The [MDN reference for all CSS selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference) is a good place to look, and StackOverflow will have a lot of info for you as well.

An example of what this might look like could be - 

> "I have a div, but I want to center it inside of another div, and give it a shadow underneath..."

You probably don't have the syntax memorized for how to do that, but you do know how to target your elements and create CSS rules for them, so start with that. From there, go online and find what kind of `properties` exist to do what you want! Give them a try and don't be afraid of trial and error!

_We'll get more in depth with CSS and it's features, but for now let's just run with what we got!_

---

## A11y

I wanted to add a quick note here about accessibility. It's easy to think that when we're talking about visual presentation, that accessibility isn't a concern, but it definitely still is! 

Here's a couple examples:

> text that doesn't have enough contrast with its background
![white text on a lightgrey background with very little contrast](https://i.imgur.com/msj3QjV.png)

> Tooltips that only show text when hovered by a user. This could potentially never be accessed by someone using a screen reader, or maybe it pops up out of context and adds confusion to the flow of your page

> Motion is a big part of CSS, and can make the web awesome! But some folks suffer from motion sensitivity, and may experience vertigo, dizziness, or even seizures if they are assaulted with crazy animations or unexpected flashing colors.

When making your website beautiful, make sure it works for everyone still!

>Notes:
[Research some HTML attributes for `aria`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA) (accessible, rich internet applications). They allow for sighted users and screen-reader users to see/hear different content for certain elements depending on the context. This can be super powerful!!

---

## Homework

![Mike Wazowski from Monsters Inc burping and coughing up a microphone during his failing stand up comedy routine](https://i.imgur.com/lrS1lAN.png)

* _Fork the starter code for this lesson from [stackblitz](https://stackblitz.com/edit/css-starter?file=index.html). (Or make your own from scratch!!)_
* The main goal of this project is to experiment, google a lot, and have fun going crazy with CSS to modify your page! _The more code you write, the more you'll learn, ~~even~~ __especially__ if you've made mistakes!_
### Here are the main goals for your project:
  * Create a CSS file.
  * Link it to your HTML.
  * Add a hilarious joke.
  * Keep the punchline hidden, and then have it revealed in some way.
    * You could do this with a hover effect, scrolling, colors, etc. Think outside the box!
  * Add at least one image, and make it accessible with the `alt` attribute.
  * Use at least two different fonts
  * Use the `element` selector, `class` selector, and `id` selector to style different parts of your page.
  * Add a hyperlink that points to an MDN page where you learned and implemented something new!
  * Put borders on stuff!
#### Stretch Goals!
  * Make your hyperlink turn orange _after_ it is clicked.
  * Add movement by using CSS `transitions`.
  * Read about and use `flexbox` to center the content on your page!

_Here's an example 90's style - https://codepen.io/mikelbrierly/full/wvWLoNJ
Try not to look at the code if you can, but feel free to take ideas or try to replicate parts of it in your own way!_