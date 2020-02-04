---
title: JS - query Selector
layout: post
date: '2019-12-03 17:27:00 +0100'
categories: js javascript app web
---

Wywołania query selectorów z drzewa DOM dla HTML z poziomu javascripta.


Standardowe wybranie lementu w js wygląda tak:

`let changer = document.querySelector(".changer");
const body = document.querySelector("body");`

```
const colorValues = [
  "A", "B","C", "D", "E","F","1","2", "3","4", "5", "6","7", "8","9", "0];
  function getRandom() {
  let color = "#";
  for (i = 0; i < 6; i++) {
    color += colorValues[Math.floor(Math.random() * colorValues.length)] 
    //wybieranie losowego elementu z tablicy ktora ma dl max
    console.log(color)
  }
  alert(color)
  document.body.style.backgroundColor = color
  console.log(color)
}
```

Podmiana klasy dla wybranych elementów za pomocą selectora.

```
var el = elements[2];
//query selector zwraca tylko pierwzy z kolei
//querySelectorAll zwraca wszystkie
el.className = 'cool';   //zmien element ktory mial klase how na klase cold
//analogicznie mozna dodać:
let el = document.querySelector('li.hot');
```
Natomiast tak wygląda samo odświeżająca się funkcja. W zasadzie polega to na dosyć prostym wywoływaniu rekurencji z poziomu globalnego:


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

To by było na tyle.
