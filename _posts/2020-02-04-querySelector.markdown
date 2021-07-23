---
title: JS - query Selector
layout: post
date: '2019-12-03 17:27:00 +0100'
categories: js javascript app web
---

Calling query selectors from HTML DOM in JS.

Typical vanilla js selector usage:

`let changer = document.querySelector(".changer");
const body = document.querySelector("body");`

Of course we might also use getElementById or getElementByBlassName, like we normally used to.
```
const colorValues = [
  "A", "B","C", "D", "E","F","1","2", "3","4", "5", "6","7", "8","9", "0];
  function getRandom() {
  let color = "#";
  for (i = 0; i < 6; i++) {
    color += colorValues[Math.floor(Math.random() * colorValues.length)] 
    //choose random element from array - yes length is used so we won't access index which is outside of array
    console.log(color)
  }
  alert(color)
  document.body.style.backgroundColor = color
  console.log(color)
}
```

Changing class for elements chosen by selector.

```
var el = elements[2];
//query selector returns only first appearing element in dom
//querySelectorAll - returns all
el.className = 'cool';   //now el has cool class.
let el = document.querySelector('li.hot');
```
And here is little tip, self refreshing (like a recurrent) function, yes this is just timeout function.

```
function updateTime(){
    let now = new Date(),
    time = now.getHours() + ':' + now.getMinutes() + ':' + now.getSeconds();
    console.log(time);
    document.getElementById('time').innerHTML = time;
    let test = document.querySelector('.test')
    setTimeout(updateTime, 1000); //update czasu
}
updateTime();
```

See ya'll.
