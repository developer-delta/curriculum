# Open source software

![city lights as seen at night from a helicopter. A network of roads and connections.](https://images.unsplash.com/photo-1542382257-80dedb725088?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1400&q=80)

## What is open source software?

Open source software (OSS) is software developed in a collaborative public manner. It has no copyright constraints, and can be duplicated, modified, updated, and improved by the dev community. It encourages innovation and camaraderie, brings in diverse perspectives, and saves consumers money.

If that sounds like an unattainable utopian pipe dream to you, take a look at some OSS examples:

  * VSCode
  * Git
  * Chromium (what Chrome is built on)
  * Firefox
  * Linux

These aren't obscure second-tier applications, they're some of the very best you can get. And it's all thanks to open source.

---

## Why would you choose to make your software open source?

![Patrick star from Spongebob giving away money](https://media4.giphy.com/media/fNvXkjC50ywBW/giphy.gif)

OSS isn't just altruistic, it's also practical. By making your software available to all those who use it and want to improve it, you empower your users and build a sense of ownership. Diversity is a natural by product of OSS since the developer community is global. As Wikipedia says _"The mix of divergent perspectives, corporate objectives, and personal goals speeds up innovation."_ Wikipedia is also a great example of an open source model.

---

## OSS as a learning tool

From here on out, we are going to primarily be working in an open source setting. Occasionally there will be small individual projects, but mostly we'll be working on one single product that will grow, evolve, and improve.

#### [Here's what you'll be building](https://github.com/developer-delta/halogen)

As a class we will benefit first hand from OSS by building a sense of ownership and collaboration. It will also allow everyone to practice working on a team with version control (Git) and code review.

We will start with a very simple application that will only require the knowledge you have gained so far. But we will continually add features that will push the class to understand the value of new topics as they are introduced.

In the spirit of OSS, this will be a living, breathing piece of software. If you want to add a feature, change the general direction, or contribute anything you see as an improvement, you can. This is **your** software. I want you to own it and feel proud of what you will be building. 

![build, learn, and adjust in a repeating cycle](https://www.geckoboard.com/blog/content/images/the-dashboard-iteration-process.png)

> _Iteration is at the heart of this process_

---

## What you'll get out of OSS

![People working at a table on computers together](https://images.unsplash.com/photo-1521737852567-6949f3f9f2b5?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1330&q=80)

You will become a better developer by contributing to OSS. Open source breaks down the walls and silos that are created around people's individual knowledge bases. It allows you to learn from others, and share what you have learned with them. Most of this is done via code review and pull requests in GitHub.

It takes some courage to put your code out there and allow others to see it and offer up critique, but this is a crucial skill to have a dev, arguable more important than any amount of cold hard syntax you have memorized.

DevDelta is a safe space for us to practice this while still building something real. You will also be far more prepared to jump into a team and contribute since you'll know how the process works already. The name "DevDelta" won't mean anything to potential employers, but "Self-taught open source contributor" will perk up their ears. You will also have something real to show for it, not just a tutorial app they have seen many times.

> Learning this way will empower you, teach you to work on a team, and look good on your resume.

---

## Your first OSS contribution

Alright let's see how this works on a small scale.

You're going to be adding your name to a "Guest Book" of sorts. [Here's the repo.](https://github.com/developer-delta/first-open-source)

Here's what the process will look like:

#### `fork` the repository
This duplicates everything into a new repository under **your** github account.

#### `clone` the repo
This moves the code from the web (GitHub) to your computer so you can make changes.

#### Create a new `branch`

```shell
git checkout -b your-new-branch-name
```

#### Add
Make code changes, then run:

```shell
git add fileYouChanged
```

#### Commit

```shell
git commit -m "commit message explaining the changes you made"
```

#### Push

```shell
git push origin branch-name
```

#### Pull request

[This guide will help run you through it!](https://guides.github.com/activities/forking)

#### Get feedback

Now the real benefit of OSS kicks in! This is where "code review" happens. Others will be able to look at your code and say "good job!" or offer up suggestions.

#### Change requests

You may need to make changes to your code to improve it or make it follow the standards of the repository you want to contribute to. To do this you just go back to the "Add" step and make changes then `commit` and `push` again. Your pull request will reflect those new changes you made.

#### Approval

Once a repository maintainer `approves` your pull request, it can then be `merged` into the original repository and you'll see your changes, _and_ be an official open-source contributor!!

![ewoks celebrating](https://media1.giphy.com/media/3FQ9mRcb94aogeTvmj/giphy.gif)