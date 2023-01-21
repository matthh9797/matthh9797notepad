---
title: "Mike Dane: SCSS"
date: 2023-01-18T10:59:29+07:00
draft: false
author: "Hendo"
authorLink: "https://github.com/matthh9797"
description: ""
images: []
resources:
- name: "featured-image"
  src: "featured-image.png"

tags: ["Courses", "Front End"]
categories: ["Mike Dane"]
---

## 0 Introduction

SASS is a styling framework which sits on top of CSS, which allows you to use loops, variables ... 

Every css file is a valid scss file (i.e. if you have a bunch of css files already you can simply convert them to .scss files to get started).

## 1 Installation

SASS is written in Ruby, hence you need to download Ruby to use SASS. The two programmes required to use SASS are Ruby and Ruby Gems (*a package manager for Ruby*).

### 1.1 Mac

On a Mac both Ruby and Ruby Gems are pre-installed. To check these are already installed run the below code on the terminal and if they return a version number you are ready to install SASS.

```bash
ruby -v
gem -v
```

Follow the [SASS Install](https://sass-lang.com/install) instruction to install SASS. Then check it has worked by running `sass --version`.

Issues (2022-01-18): I also had to install developer tools on the mac by running `xcode-select --install` 

## 2 Using SCSS

Worth noting that SCSS and SASS are a slightly different syntax but can be used for the exact same things. I prefer SCSS since any .css file is a valid .scss file.

### 2.1 Compile scss

To compile your scss files into css use the following in the terminal. 

```bash
sass --watch <NAME_OF_FOLDER> (i.e. style)
```

Then import the resulting .css file into your html document.

## 3 Variables

Variables are intuitive as in any other programming language. The syntax for variables is like the below.

```scss
$my-color = "blue"

.my_class {
  color: $my-color;
}
```

## 4 Nesting

This is also intuitive but a very useful feature of scss. You can nest css classes. This is much more readable when you have several nested elements.

```css
main article p {
  color: yellow
}
```

scss equivelant:

```scss
main {
  article {
    p {
      color: yellow;
    }
  }
}
```

## 5 Partials and Imports

You can create a partial in scss by naming your file with a leading _ (i.e. _header.scss). Then import the file with:

```scss
@import "_header"; /* relative link to file */

header {
  color: red; /* overrides the code inside _header.scss */
}
```

## 6 Mixins

These are reusable components which when created can be used within your css elements. You can also include parameters. (These are basically css functions).

```scss
@mixin fancy-border($size: 1px, $color:black) {
  border $size dashed $color;
  border-radius: 5px;
}

header {
  @include fancy-border(10px, blue);
  background-color: yellow;
}
```

## 7 Extends and Inheritance

Extends can be used to inherit all the parameters in a class to another. The key difference between extends and mixins is that with extends you can use the original class which you extend from in your html. This is like building a class on top of another class in python (i.e. `class MyClass2(MyClass1)`).

```scss
.message {
  font-size: 20px;
  border: 1px solid black;
}

.warning {
  @extend .message;
  color: yellow;
}
```

## 8 Operators

In css you can use operators like `*2` or `/2`. 

```scss 
$base-size: 20px;
$base-color: red;

p {
  font-size: $base-size;
  color: $base-color;
}
button {
  font-size: $base-size * 2;
  background-color: $base-color - 200; /* 200 shades lighter */
}
```

## 9 Conditionals

Basically just `if-else` statements. The following code makes the color of the text in the header to change based on the size of the page.

```scss
@mixin text-style($size) {
  font-size: $size;
  @if $size > 20px {
    color: blue;
  } @elseif $size == 20px {
    color: red;
  } @else {
    color: green;
  }
}

header {
  @include text-style(30px);
}
```

