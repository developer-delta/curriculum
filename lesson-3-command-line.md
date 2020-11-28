# Introduction to Git and the Command Line

![Digital tree on an old green crt monitor. (the intro to the film blade runner)](https://i.ytimg.com/vi/XxRV2ZPAYYY/maxresdefault.jpg)

##### What is Git? 

_Git is a tool that allows us to save, organize, and version our code._

When we write code, we are creating `files`, and like any other program, we need to save those as we go along so we don't lose our work. `Git` provides a way for us to save our files, and _also_ have access to old versions of those same files.

Git is like a time machine that we can use to access our code at different points in the past. This is incredibly helpful for debugging, reverting mistakes, and releasing software. 

![A steampunk looking time machine (from the tv show Dark)](https://i.imgur.com/04N5TXU.jpg)

Not only does Git store copies of our work going back in time in case we need them, it also can be used to create copies and then work off of those to make different code changes. Our Git time machine not only goes back in time, but it can also create and navigate _alternate realities_. 

![four versions of reality in Rick's garage from the tv show Rick and Morty](https://i.imgur.com/YclMfE9.jpg)

Let's say you have a simple HTML file that you are using Git to keep track of. In this HTML file, you turn a button `green`. You save your work. But then you wonder what it might look like if the button was `red`. You could create a new `branch` (copy that Git knows about) and make the button `red`. Now you would have two separate "realities" (branches) you can visit to see the button as `red`, or see the button as `green`. Both versions are saved, and exist completely on their own. `Git` is our Time Machine that allows us to see things in the past and also in alternate versions.


##### Is GitHub the same as Git?

They are related, but not the same thing. All of the things that Git gives us by default just live on your computer. The time machine is powerful, and incredibly useful, but if your cat knocks a glass of water on your laptop and completely destroys it, __everything__ is gone, time machine included. 

![the Git logo shown as being not equal to the github logo](https://1.bp.blogspot.com/-WY2YpNr3W6g/UY6tZAc-H3I/AAAAAAAABLY/xJ9x3wIY8V8/s1600/Github2.png)

What __GitHub__ gives you is all the power of __Git__ on the _internet_. And not just online, but with a UI you can access in your browser to see code visualized. Not just your code either, but code from people all over the world is shared on GitHub. Sometimes people keep it private, but often it's available to look at or even change! Collaborating with people online and contributing to code on GitHub with others is called `open source` software development. Lots of software is created by developers working together to simply create awesome stuff. Including VSCode itself! 

##### Getting set up

* Go ahead and [download Homebrew](https://brew.sh/) on your machine. (Homebrew is like an "app store", but can be used in just the terminal, and we'll need it to install Git)

* Next go to the [Git website](https://git-scm.com/downloads) and follow their instructions for getting Git installed using Homebrew (sometimes called brew).

##### What's next?
This lesson is focused on learning the basics of the command line, Git is a vast topic that we will cover in depth in the near future. For now, we're just building an accurate mental model of what Git and GitHub __are__, we're not learning all the details of how to fully use it. 

---

#### IDE

IDE stands for Integrated Development Environment. Don't worry about the `integrated` part for now, it is just a piece of software to help you write the best code you can!

> _You could write a book with pen and paper, but it'd be easier with a typewriter, and even easier with a laptop._

Writing code is similar! You could use a regular notepad app to write code on your computer, but __IDE__'s are built to help us write code. Plugins, syntax help, running servers, navigating files, and a million more things.

For our DevDelta class, we will be using Microsoft's [Visual Studio Code](https://code.visualstudio.com/download). It is a free and open-source software that has quickly become the go-to IDE for developers all over the world. If you would like to use a different one, that's fine! But our examples moving forward will be for VSCode.

> __First important VSCode step:__
> Open VSCode and type `CMD + P`.
> Now type `> Install 'code' command in PATH` in the text box.
> Click on the result that shows up. 

This command we just ran will allow us to open VSCode from the terminal for any directory we are in, and it will make our workflow much faster in the future.

---

#### Command Line
##### For the lesson on the command line, please [check out the interactive repo](https://github.com/mikelbrierly/command-line).
