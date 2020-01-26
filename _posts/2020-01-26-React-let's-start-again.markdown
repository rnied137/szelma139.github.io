---
title: React jeszcze raz tym razem porzadnie.. [komend]
layout: post
date: '2019-12-03 17:27:00 +0100'
categories: react
---

Postanowilem sie wreszcie nauczyc czegos w porzadny sposob. No to maly skrot tutaj:


Definiowanie stanu dla gdy funkcja zawiera wskaznik na event:
```
handleChange = (e) => {
 
    this.setState({
        currentData: e.target.value        
    });
```

Mapowanie po elementach danej listy. Tutaj item jest po prostu jednym elementem z listy i przybiera jego wartosci tak jak np. w przypadku foreach element in *element**s**.

```
{this.state.list.map((item) => {
    return (
<div> <ToDo text={item.content} random={colors[Math.floor(Math.random() * colors.length)]}/> </div>   )
 }
)}
```
Random ktory tam jest tez sie moze przydać. Zapamiętać.

Analogicznie w mega intuicyjny (i nieczysty) sposob definiowanie tablica obiektow z nowym obiektem - musi przybierac pole obiektu takie samo jakie jest w tablicy obiektow starej. Co za chwilke wytlumaczę: 

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

Tablica obiektow `this.state { list: [{content:"some text}, {content:"sample other text")];` W tym przypadku nowy obiekt musi rowniez posiadac wlasciwosc content inaczej nie bedzie prawidlowo przekazany do nowej tablicy. Tak jak wyzej zrobilem dodająć:
`list:newArray`. No to byloby na tyle.
