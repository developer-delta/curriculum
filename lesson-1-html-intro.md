# Introduction to HTML

![An aerial view of a river delta](https://images.unsplash.com/photo-1524009901480-a6fa1c0c8ab5?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80)

## HTML is the foundation of the web

HTML is the language used to give **structure** to content on the web. It stands for "Hyper Text Markup Language". _"Hyper Text"_ is "text that does special stuff". _"Markup"_ means that text or content may be bold, italicized, a list of bullet points, a table with content, etc.

![Concrete pillars under a large structure](https://images.unsplash.com/photo-1519176510496-cd5b5b74c808?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1349&q=80)

HTML is one of the three pillars of the web, along with CSS and JavaScript. it's the first type of file your browser encounters when it load up a web page, and it is responsible for connecting your CSS styles and JS functionality to the content contained in your website or app.

---

 ## Follow along!

![Darth Vader saying "Come with me"](https://64.media.tumblr.com/24fb00c6096c8af411858e1e8166d318/tumblr_olwzijmlRo1w60m4do1_1280.gif)

#### To start out, let's take a quick look at how your computer and browser interpret files. 

1. On the desktop of your computer, create a new file named `hello-world`.

![Screenshot 2021-10-04 074243](https://user-images.githubusercontent.com/13723156/140521527-c5a952b9-02ee-4e56-983e-c21bca9eeb91.png)

2. Double click on your newly created file, and it should open in a default text editor -

![Screenshot 2021-11-05 075609](https://user-images.githubusercontent.com/13723156/140521593-0c6fade9-416b-49fd-ae93-0ab40320f0e4.png)

3. Go ahead and add some text to the file, then open it with Chrome (right click -> open with -> Chrome)
    * _If you don't see Chrome as an option, you may need to click "Choose another app" and search your computer for Chrome_

![Screenshot 2021-11-05 075956](https://user-images.githubusercontent.com/13723156/140521641-d279d201-cc16-402b-b145-d9cfcb7677c2.png)

4. You should now be able to see your raw, unformatted text in Google chrome. The address it's pointing to is just right here on your computer! 

![Screenshot 2021-11-05 080219](https://user-images.githubusercontent.com/13723156/140521797-cd7b40b3-a3a2-4699-bdfe-8e7d22beb75e.png)

5. Next up let's add another line to our text document

```
<h1>General Kenobi.</h1>
```

![Screenshot 2021-11-05 080547](https://user-images.githubusercontent.com/13723156/140522051-cd2129c3-c9a0-4dde-9eb5-88935bbdf282.png)

6. Our page is displaying _exactly_ what we typed in, but what we just created was an `html` tag that creates a **heading**, and we want our browser to be able to interpret that [syntax](https://developer.mozilla.org/en-US/docs/Glossary/Syntax). Go ahead and edit the name of your file so that it has the extension `.html`.

![Screenshot 2021-11-05 081111](https://user-images.githubusercontent.com/13723156/140522153-c95ad489-b897-4dcb-b3b8-ef796b039229.png)

7. Save and open your file again in Chrome, and now you should see the text has been formatted, and your `html` is being interpreted by the browser!

![Screenshot 2021-11-05 082412](https://user-images.githubusercontent.com/13723156/140522207-bed79e2c-12c7-45c8-b51e-c70d22e14dd9.png)

Note: if you see your file open as `hello-world.html.txt`, then you'll need to open your file extension settings and uncheck "Hide extensions for known file types"

![Screenshot 2021-11-05 081558](https://user-images.githubusercontent.com/13723156/140522232-d43dc546-2946-4991-9505-f7f1684b277d.png)

8. If you want to see the `html` elements under the hood, you can right click on your webpage, and choose `Inspect`. This will open the **developer tools**. (We'll be using this tool a lot in the future!)

![Screenshot 2021-11-05 083109](https://user-images.githubusercontent.com/13723156/140522258-955f59a5-1977-4f70-a7db-e389983cbad0.png)

🎉🎉🎉

---

## Anatomy of an HTML tag

### Content

Take a look at this line of content:

 ```html
Big Gulps huh? Alright! Welp, see ya later!
 ```

If we want to be able to alter that content at all, it will have to be enclosed in an html tag. Here's what that would look like wrapped in a `paragraph` tag.

 ```html
 <p>Big Gulps huh? Alright! Welp, see ya later!</p>
 ```

When the browser inteprets this HTML to be displayed, it will only output the content, like so:

 <p>Big Gulps huh? Alright! Welp, see ya later!</p>

_Your HTML tags will never get rendered (displayed) on the screen, they are basically instructions to the browser to help alter your content._

### Tags

In our previous example, we used the `paragraph` tag, which is one of the most common HTML tags, due to there being a lot of text on the web! Let's take our example and make some more changes. What if we wanted to emphasize some of our text with bold or italics? Let's see how that would look:

 ```html
 <p><strong>Big Gulps</strong> huh? Alright! Welp, see ya later.</p>
 ```

Renders to:

 <p><strong>Big Gulps</strong> huh? Alright! Welp, see ya later.</p>

### Nesting

You'll notice that the `<strong>` tag we used is _inside_ of our `<p>` tag. This is called a nested HTML element, and it is a cornerstone of building and arranging content. Be careful of the order of your nested tags, you can end up with malformed HTML if things aren't nested correctly. When you have a lot of tags that are nesting, usually you will see HTML written like this:

 ```html
 <div>
>   <p>Big</p>
>   <p>Gulps</p>
>   <p>Huh?</p>
 </div>
 ```

That will render the same as this does,

 ```html
 <div><p>Big</p><p>Gulps</p><p>Huh?</p></div>
 ```

...but it's much harder to read for a developer working on the site if it's all scrunched together like that ^.

### Attributes

On a lot of web pages, you could have hundreds or even thousands of html tags. And a lot of those are probably plain old `paragraph` tags `<p></p>`. If we wanted to make one of those `<p>` tags unique by giving it a name that our JavaScript or CSS could access later, we could do that with an `attribute`. In this case the `id` attribute:

 ```html
 <p id="quotable-line"><strong>Big Gulps</strong> huh? Alright! Welp, see ya later.</p>
 ```

The syntax for HTML attributes is always the name of the attribute followed by an equal sign, and then opening and closing quotation marks that can contain different things.

> _Attributes help to communicate special information to the browser about your document without displaying what you typed onto the page._

---

##### _Diagram_

![Screenshot with labels for the anatomy of an html tag. Opening paragraph tag, attribute, a nested element with content, the tags own content, and the closing paragraph tag](https://i.imgur.com/Ay2GfUK.png)

---

## Commonly used HTML elements

There are an unlimited number of ways you could format your content and text on the web, and HTML allows for as much customization as you can imagine, but thankfully we are given some building blocks for the common ones right out of the box with HTML. Let's take a look at a few of those. 

First up, let's look at the smallest possible HTML document:
```html
<!DOCTYPE html>
<html lang="en-US">

  <head>
    <meta charset="utf-8">
  </head>

  <body>
  </body>

</html>
```
![Annotated screenshot of the above html, with explanations for the different tags and attributes.](https://i.imgur.com/aZe8fBj.png)
That will not actually render anything to our page, but we have set up the structure of our HTML document so that we can write _valid html_ in it.

### Let's add the following elements to our example page:

#### Title element
The title element defines what will be displayed in the browser tab when on your page.
```html
<title>School of Witchcraft and Wizardry</title>
```

#### Heading elements
There are 6 levels of heading elements, from `<h1>` to `<h6>`. They are rendered at different sizes, but more importantly they convey information about the page structure to search engines and users.
```html
<h1>Wizard Stuff</h1>
```
---
#### Anchor element (link)
This will create a hyperlink to another location. Could be a web page, a file, an email address, or even a different location on the same page.
```html
<a href="https://my.wizardingworld.com/sorting-hat">Take me to Hogwarts!!</a>
```
---
#### Lists
We can create lists in HTML with either the ordered list `<ol>` tag, or the unordered list `<ul>` tag. Ordered will be numbered (1. 2. 3...), and unordered will be a bulleted list.
The lists items will be the `li` tag.
```html
<ul>
  <li>Harry</li>
  <li>Hermoine</li>
  <li>Ron</li>
</ul>
```

---

```html
<!DOCTYPE html>
<html lang="en-US">

  <head>
    <meta charset="utf-8">
    <title>School of Witchcraft and Wizardry</title>
  </head>

  <h1>Wizard Stuff</h1>

  <body>
    <ul>
      <li>Harry</li>
      <li>Hermoine</li>
      <li>Ron</li>
    </ul>

    <a href="https://my.wizardingworld.com/sorting-hat">Take me to Hogwarts!!</a>
  </body>

</html>
```

Now our webpage will look like this:

![Screenshot of our simple website showing Harry, hermione, and ron in bullet points, followed by a purple hyperlink that says "Take me to Hogwarts!!"](https://i.imgur.com/CP1zvZW.png)

---

## Adding media
<img src="https://i.imgur.com/70BpceM.jpg" width="550px" alt="Man holding up a picture. (Screenshot from a Nickelback music video)">

The web wouldn't be the web if it weren't for memes, gifs, images, videos and the like. Adding _media_ to our pages is almost always something we'll want to do.

Here's what the `html` looks like for the lovely photograph(s) of Nickelback frontman Chad Kroeger above:
 ```html
 <img src="../images/nickelback.jpg" width="550px">
 ```

There are a couple special things you might have noticed about this tag in particular: 
* There is no closing tag, only an opening one. 
  *  Part of the reason for this is that the `img` tag doesn't encapsulate any `content`, so the creators of HTML decided to leave out the closing tag to try and avoid confusion.
* There are 2 `attributes`. 
  * Only the `src` attr is required, and there can also be more than just these two added to the tag. If you are ever curious about the details of an HTML tag, it's a good plan to make a habit of [checking Mozilla Developer Network for their documentation on it](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img).

> _Over time, you'll end up memorizing the syntax of __some__ things, but development is about fostering a new way of thinking, not memorizing things. You will develop the skills to research, read documentation, and find pertinent answers for specific issues. Right now you are learning a broad overview of the web, so don't let yourself get lost in the weeds just yet. Your __mental model__ will build over time, just be patient!_ 🤘

## The web is for everyone

We want our website and it's content (like images) to be easily accessible, and easy to understand. This idea is aptly called **web accessibility**. There are many facets to web accessibility, and many different ways to leverage it, but for now we are going to focus on screen reader compatibility. A **screen reader** is a tool created to help people with low/no vision navigate their computers and browsers with a keyboard.

> the term **A11y** is often used as shorthand for "web accessibility". 

_This is a topic we'll continue to explore throughout the course, and it is a mindset we want to cultivate from the very beginning._

Ok, back to our `<img>` tag. 

If you were using a screen reader to view this:
```html
<img src="../images/nickelback.jpg" width="550px">
```
You would hear something like this read to you:
> ![Screenshot of Mac's VoiceOver reading an unlabeled image.](https://i.imgur.com/dRngfiw.png)
> The key piece there is `Unlabeled image`. 

What a bummer. If your user is unable to make out the visible image, they are missing a huge piece of what this site has to offer, and it may even make your site unusable. To solve this, we can use the `alt` attribute.

### Alt text

Alternative text is an `attribute` you can add to your image tags that gives descriptions and context for your images! If you have ever seen this on the web, you have seen alt text:
> ![Screenshot of a broken image tag with it's alt text displayed on the screen](https://i.imgur.com/45uKktp.png)

That information isn't just to provide sighted users a description of broken images, it's primary purpose is for screen readers. Let's add some good alt text to our image:
```html
<img src="../images/nickelback.jpg" width="550px" alt="A bleached blonde man saying 'look at this photograph' while holding up said photo for you to look at.">
```
Which will be read as:
![Screenshot of VoiceOver reading the newly added alt text "A bleached blonde man saying 'look at this photograph' while holding up said photo for you to look at."](https://i.imgur.com/4dGJj4K.png)

Now our screen reader users can get the context they need to understand the content of our site easy peasy. All we have to do is give accurate descriptions of what is in our photos. 

---

_Alt text is not an enhancement to the web, it is the standard. By not using it, we would be neglecting a group of users that may visit our site!_

---

## Your turn!

* Open up this example file on stackblitz [here](https://stackblitz.com/edit/your-photograph?file=index.html).

* Click the `fork` button near the top of the page. 
  * A fork is like creating a copy of code for yourself, so now any changes you make will just affect your copy
* Open up the `index.html` file.
* In the `head` element, add a `title` tag right after `meta`.
* Add content to your `title` tag; anything you want!
* Add a `class` attribute to the html `body` element with the value of "content"
* Next up we'll look at the `div` element immediately following the `h1` tag. 
* Add a class attribute of "card" to it, and you should see some styling take effect.
* Now we'll look at the first image element in our html. It is the first "child" of the `section` element. There's an important attribute missing.
  * We need to add an alternative text attribute. 
* Inside of the `alt` attribute, go ahead an add your own description of the image we see displayed. Pretend you are explaining the image out loud to best convey it's meaning.
* Next let's add a second `img` tag, _inside_ the div with the class "small-frame". Give it a class attribute of "small-picture".
  * For this one, you can add any picture you want to it as long as there is a URL online that points to it.
  * Add your image URL to the `src` attribute, and then add an appropriate `alt` attribute with a good image description.
* Now if you don't see your small image showing up inside of the frame, there may be a small typo in one of the `attributes` in our html 😈. Read through it carefully and see if you can remedy it.
* Click "open in a new window" toward the top right of the page, and see your fresh html in all it's glory! You can also see the content of your `title` element displayed in the browser tab too!
* Once your site looks how you want it, we need to check it with a Screen Reader! Use it to navigate your images, make sure your `alt` text is being read, and your site makes sense!
  * **Mac**
    * Mac has a built in screen reader called Voice Over we can use
    * Press `command`+`F5` to open voice over.
    * The `tab` key can be used to navigate important elements on the page. (this should be sufficient for your first introduction to this kind of navigating)
      * `control`+`option`+ arrow keys allows for more granular navigation.
      * `control`+`option`+`space` will "click" on that item.
      * `control`+`option`+`shift`+ up or down arrow will go into or out of content.
  * **Windows**
    * One of the most common (and free!) screen readers for Windows is called [NVDA](https://www.nvaccess.org/download/)
    * The `tab` key can be used to navigate important elements on the page. (this should be sufficient for your first introduction to this kind of navigating)

> If you need to check your syntax, or want to add any other html tags, don't forget to bookmark the MDN page. This will come in super handy, and it's great reference material. https://developer.mozilla.org/en-US/docs/Web/HTML/Element







