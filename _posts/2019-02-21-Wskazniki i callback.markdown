---
title: Wskazniki i obsluga myszy [vnc]
layout: post
date: '2020-02-21 12:48:00 +0100'
categories: vnc mysz obsluga c++ c
---

Jako że wygląda na to że w c++ bardzo przydzadzą się wskaźniki - szczególnie te bez słówka **new** to moze opiszę ich działanie.
Istnieją 4 rodzaje castowania (rzutowania) i istnieje sposób znany z c. Ten drugi a więc sposób z c to:
`(double)zmienna` - Wykonuje castowanie zmiennej na typ double.

 Jednak istnieją też trzy ważne inne sposoby:
`reinterpret_cast` - konwersja wskaznika jednego typu na inny wskaznik
`QMouseEvent * e = reinterpret_cast<QEvent*>(event) - tutaj event byl typu **QEvent** i zostaje skonwertowany do **QMouseEvent**
`const_cast` - stała do zmiennej
`static_cast`- jeden typ do innego ale obsluguje głównie typy proste.


No a tutaj tak właściwie dla siebie kod, rozpoznający obsługę myszy dla vnc w QT.

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
Dalej funkcja z wątku otrzymuje dane i przekazuje ją dalej do funkcji Send Pointer.

`SendPointerEvent(m_client,x, y,button_mask);`


To by było na tyle.
