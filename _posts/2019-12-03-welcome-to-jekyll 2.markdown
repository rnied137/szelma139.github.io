---
title: React - CSS w JS
layout: post
date: '2019-12-03 17:27:00 +0100'
categories: react app web
---

So I've realised that it might be worth to explain few easy way of adding css in react. I am writing this mainly for myself, whole blog is one big cheatsheet, palce where it's easier to find how something is done. 
React documentation even if quite clean is quite troublesome with navigation. This time really short post.

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

Object few lines above is passed to style. And later on it is transpiled to string. It is worth to remember, this time it is already destructured.

```
 <footer style={style } className="gradient">
```

Nowadays I am not using normal css files, but I tend to forget how to import simple css file. Most likely because too much usage of styled-components, basics go back to this dark place.

```
Import './Footer.css';
```

See y'all.
