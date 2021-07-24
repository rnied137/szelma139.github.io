---
title: Pointers and mouse support [vnc]
layout: post
date: '2020-02-21 12:48:00 +0100'
categories: vnc mysz obsluga c++ c
---
So because it looks like I won't go far in c++ without pointers knowledge - especially without **new** magical word.

There are 4 ways - at least for now, of casting variables, one well known from c. This c way is:
`(double)variable` - casts variable to double type.


 
But there are more:  
`reinterpret_cast` - convert one pointer type to different

 
`QMouseEvent * e = reinterpret_cast<QEvent*>(event) -in this case **QEvent** is converted to **QMouseEvent**  

`const_cast` - const to variable 

`static_cast`- one type to other but only applies to generics.  


And some vnc sssshenanigansss.

```
 switch(event->type()){

    case QEvent::MouseMove:
    {

QMouseEvent * newEvent = static_cast<QMouseEvent*>(event);
mouseEventHandler(newEvent->x(),newEvent->y(),newEvent->button());
//return true;
        break;
    }
    case QEvent::MouseButtonPress:
     {
        if(event->type() == QEvent::MouseButtonPress)
        qDebug() << "Key press event";
       // mouseEventHandler(static_cast<QMouseEvent*> (event));
        QMouseEvent * newEvent = static_cast<QMouseEvent*>(event);
        mouseEventHandler(newEvent->x(),newEvent->y(),newEvent->button());

        //return true;
        break;
    }
    case QEvent::MouseButtonRelease:
     {
        int button = 0;
        QMouseEvent * newEvent = static_cast<QMouseEvent*>(event);
        mouseEventHandler(newEvent->x(),newEvent->y(),button);
        break;
    }
    case QEvent::MouseButtonDblClick:
    {
        QMouseEvent * newEvent = static_cast<QMouseEvent*>(event);
        mouseEventHandler(newEvent->x(),newEvent->y(),newEvent->button());
        break;
    }


        //obs klawiatury
    default:
        //QWidget::event(event);

        break;
    }
    QWidget::event(event);


```
Next thread function is getting date and passing it to sendPointer event.

`SendPointerEvent(m_client,x, y,button_mask);`


See y'all.
