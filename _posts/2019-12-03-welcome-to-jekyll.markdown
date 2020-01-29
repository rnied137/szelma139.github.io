---
title: Jekyll i kilka ważnych ważności..
layout: post
date: '2019-12-03 17:27:00 +0100'
categories: jekyll update commands
---

Dobrze jest mieć gdzieś pod ręką konkretną konfigurację dla jekylla, więc może na samym serwisie blogowym byłoby jej najlepsze miejsce, w końcu wtedy nie trzeba szukać prawda? No to poniżej kilka ważnych elementów.


Aktualizuje zmiany w konfiguracji:

`bundle update`

Pozwoli odpalić lokalny serwer:
```
jekyll exec bundle serv
```

Kod:
`gem 'jekyll-admin', group: :jekyll_plugins`
dodany do gemfile:  pozwoli używać panelu administratora.

Layout zapisuje się w _layouts i właśnie stąd Jekyll czerpie szablony.
