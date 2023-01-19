---
title: "Mike Dane: CSS"
date: 2023-01-13T16:54:11+07:00
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

## 1 Positions

 - **Relative**: move elements relative to the elements around them
 - **Absolute**: move elements relative to the container, hence if there are several elements, them will be positioned on top of eachother
 - **Fixed**: Is like absolute but when you scroll the element stays in the fixed position (This may be used for a nav bar)

#### Example

This will place elements to the top left relative their nearest neighbour:
```css
.class {
  position: relative;
  left: 0px;
  top: 0px; 
}
```
{{< example-position position="relative" >}}

This will place elements to the top left of their parent:
```css
.class {
  position: absolute;
  left: 0px;
  top: 0px; 
}
```

{{< example-position position="absolute" >}}

This will place elements to the top left of the page and when you scroll the element will not move:
```css
.class {
  position: fixed;
  left: 0px;
  top: 0px; 
}
```
{{< example-position position="fixed" >}}

## 2 Shadows, Opacity and radius

This parameters allow you to control aesthetic properties which are useful for overlapping elements. 

 - **text-shadow**: h-shadow, v-shadow blur-radius(*optional*) color(*optional*)
 - **box-shadow**: none|h-offset v-offset blur(*optional*) spread(*optional*) color |inset|initial|inherit(*optional*);

#### Example

```css
h1 {
  text-shadow: 2px 2px 2px red;
  ...
}
img {
  opacity: 0.3;
  box-shadow: 2px 2px 2px grey;
  border-radius: 10%; 
  ...
}
```

{{< example-image opacity="0.3" border-radius="10%" >}}

## 3 Font Size

 - em: The relative size of the default text on the browser (*This is recommended to use*)

Check the browser accepts the font and defaults if the font doesn't work on [w3 schools css web safe fonts](https://www.w3schools.com/cssref/css_websafe_fonts.php).

Other attributes:
 - font-style: italic or bold
 - font-variant: small or caps

#### Example

{{< example-font font-family="Brush Script MT" font-size="1.2em" font-variant="small-caps">}}

## 4 Stylesheets, Classes and IDs

You can use style tags in the `<head> ... </head>` part of the html page. These are used together with css selectors. 

In hugo we can add custom css usually in the config file. To do this without messing up the theme, we probably want to wrap the component in a class wrapper. 

### 4.1 ID's and Classes

What's the difference?

 - An **ID** can only be assigned to one unique element (*one-one*). Hence. id's should be used for identifying a unique element.
 - A **class** can be assigned to multiple elements and multiple classes can be assigned to one element (*many-many*)

*An element can only have one id, whilst a class can be assigned to multiple elements*

You can select id's or classes like so:

```css
#my_id {
  ...
}
.my_class {
  ...
}
```

You can assign multiple classes to a html element like so:

```html
<div class="my_class1 my_class2"> ... </div>
```

### 4.2 Advanced Selectors

You can find a full list on [w3 schools css selectors](https://www.w3schools.com/cssref/css_selectors.php).

To practice css selectors use the w3 [CSS Selector Tester](https://www.w3schools.com/cssref/trysel.php).

```css

[href] { ... } */ element which use the href html attribute */
li[title="lemons"] */ list element with html attribute title equal to lemons */
p[title*="fir"] */ title contains fir */
```

## 5 Flexbox

This is used to create a responsive (*respond to resizing the page*) grid layout for several listed items.

```css
    .my-flex-container {
        display: flex; /* create flex boc */
        flex-direction: row-reverse; /* control layout*/
        justify-content center; /* side elements line up from  */
        flex-wrap: wrap; /* elements wrap when page resized */
        align-items: center; /* where items are aligned from */
        ...
    }
    .my-flex-container .box:nth-child(4) {
        align-self: flex-start; /* individual item alignment */
        ...
    }
```

{{< example-flex-container >}}

For more details on flexbox you can look at this [flexbox cheatsheet](https://jonitrythall.com/content/flexboxsheet.pdf).

## 6 Animations

You can use the `@keyframes` css magic to create animations. These can be used with the `:hover` property to start the animation when a user hovers over the element.

```css
@keyframes change-color {
    0% {background-color: blueviolet;}
    25% {background-color: aqua; left: 200px;}
    50% {background-color: chocolate; left: 400px;}
    75% {background-color: black; left: 200px;}
    100% {background-color: blueviolet; left: 0px;}
}

.my-box-animation .my-box {
    position: relative;
    background-color: blueviolet;
    animation-name: change-color;
    animation-duration: 5s;
    animation-iteration-count: infinite;
    animation-delay: 2s;  
    ...
}
```

{{< example-animations >}}

## 7 CSS Frameworks

Css frameworks are a collection of css and javascript which is pre-written to take the hard work away from styling websites. 

[Bootstrap 5](https://getbootstrap.com/docs/5.3/getting-started/introduction/) is a good css framework for works well on mobile and computers. 

