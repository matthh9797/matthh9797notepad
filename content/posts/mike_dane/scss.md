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