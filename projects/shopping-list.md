---
layout: project
type: project
image: img/shopping-list/shopping-list-cover.png
title: "Shopping List"
date: 2020
published: false
labels:
  - CSS
  - HTML
  - JavaScript
summary: "A user interaction website project that I made in high school."
---

<div class="text-center">
  <img width="400px" src="../img/shopping-list/dne.png" >
  <img width="400px" src="../img/shopping-list/full.png" >
</div>

## Design of the project

Shopping List project is a simple project that uses the Document Object Model (DOM), a programming interface for web documents. The HTML file contains an ordered list (shows user’s input in number order), HTML input field (user can enter things they want), and two buttons (to add user’s input or delete it). The CSS file contains the colors and font.

In the JavaScript file, everything is input and output from the DOM with no window alerts or prompts. There is a global variable to keep track of the user's input. The user can only add up to four items in the list. If a user tries to add more than four items, the item will not be added and will show up “LIST IS FULL” (just like the second image above). The user can remove things on the list by using only the number on the list. If the user did not input a number, “NUMBER DOES NOT EXIST” will show up. If the user makes an invalid selection, “ITEM DOES NOT EXIST” will show up. If the user makes a valid selection, then the item will be deleted from the list. Here is my implementation in JavaScript.

```
var num = 0;
var max = 4;

function addOne()
{
  if(num < max)
  {
    document.getElementById('warning').innerHTML = "";
    num++;
    var item = document.getElementById('item').value;
    document.getElementById('item').value = "";
    var list = document.createElement('li');
    var tn = document.createTextNode(item);
    list.appendChild(tn);
    var pos = document.getElementsByTagName('ol')[0];
    pos.appendChild(list);
  }
  else
  {
    document.getElementById('warning').innerHTML = "LIST IS FULL";
  }
}

function removeOne()
{
  var item = parseInt(document.getElementById('item').value);
  document.getElementById('item').value = "";
  
  if(isNaN(item))
  {
    document.getElementById('warning').innerHTML = "NUMBER DOES NOT EXIST";
  }
  else if(item > num)
  {
    document.getElementById('warning').innerHTML = "ITEM DOES NOT EXIST";
  }
  else if(item < 0)
  {
    document.getElementById('warning').innerHTML = "ITEM DOES NOT EXIST";
  }
  else
  {
    num--;
    var choice = document.getElementsByTagName('li')[item-1]
    var parent = choice.parentNode;
    parent.removeChild(choice);
    document.getElementById('warning').innerHTML = "";
  }
}
```

## My Role

This is an individual project that was done by myself.

## My experience

Before learning about DOM, I have only been using window alerts or prompts, so this project will be a little bit difficult for me at first. After doing a little research on DOM, I think that I have an understanding of how to use it. I was able to use different document functions to make the simple user interaction feature.
