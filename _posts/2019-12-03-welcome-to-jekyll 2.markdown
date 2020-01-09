---
title: React - CSS w JS
layout: post
date: '2019-12-03 17:27:00 +0100'
categories: react app web
---

Zdałem sobie sprawę żę warto opisać kilka prostych sposobów dołączania stylów CSS w reactie. Piszę to głównie żeby nie zapomnieć, jako że znalezienie odpowiednich informacji w Dokumentacji Reacta jest strasznie kłopotliwa. No to zaczynamy, wpis będzie krótki.

```
var style = {
  backgroundColor: "white",
  borderTop: "1px solid #E7E7E7",
  textAlign: "center",
  padding: "20px",
  position: "relative",
  left: "0",
  bottom: "0",
  height: "10%",
  width: "100%",
  paddingTop: "30vh",
};
```

Natomiast samo przypisanie zmiennej do komponentu, odbywa się poprzez atrybut elementu style. W sposób poniżej:

```
 <footer style={style } className="gradient">
```

Analogicznie jednak nadal możliwe jest dodanie zwykłej klasy do elementu poprzez className (to jednak React class tutaj jest zarezerwowanym słowem kluczowym). Wykonanie importu w wersji skróconej:

```
Import './Footer.css';
```


Inny sposób bierze pod uwagę inline styles, czyli tak jak poprzednio w miejsce "style" wrzuca się javascriptowe wersje identyfikatorów CSS-a.

To by było na tyle.