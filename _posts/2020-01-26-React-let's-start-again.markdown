---
title: React once again this time - cheatsheet
layout: post
date: '2020-01-26 21:53:00 +0100'
categories: react
---

Defining state where function has pointer for event:
```
handleChange = (e) => {
 
    this.setState({
        currentData: e.target.value        
    });
```

Mapping by elements of array, really standard stuff. Item is one element of array, same as used normally in foreach - well know in different languages. foreach element in *element**s**.

```
{this.state.list.map((item) => {
    return (
<div> <ToDo text={item.content} random={colors[Math.floor(Math.random() * colors.length)]}/> </div>   )
 }
)}
```
Yes random being up there can also be often found in different database, or even yt.

Similarly in not really intuitive way, defining array of objects, and applying new object to it. It is well known spread object which can be used on iterables. 

```
submitData = (e) => 
{
    e.preventDefault();
    let newObject = {}
    newObject.content=this.state.currentData;
    let newArray = [...this.state.list, newObject]  //wrzuc do nowej tablicy starą listę (...this) i dorzuc tam nowy obiekt
    this.setState(prevState => ({
        list: newArray,
        currentData: '',
        

    }))

    console.log("Nowa lista to " + this.state.list);
}
```

Array of objects `this.state { list: [{content:"some text}, {content:"sample other text")];` 
In this case object have property otherwise won't be passed to new array. 
`list:newArray`. 

See ya'll.
