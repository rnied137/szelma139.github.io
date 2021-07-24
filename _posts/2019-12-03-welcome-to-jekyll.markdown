---
title: Jekyll and some important stuff..
layout: post
date: '2019-12-03 17:27:00 +0100'
categories: jekyll update commands
---

Dobrze jest mieć gdzieś pod ręką konkretną konfigurację dla jekylla, więc może na samym serwisie blogowym byłoby jej najlepsze miejsce, w końcu wtedy nie trzeba szukać prawda? No to poniżej kilka ważnych elementów.

It is worth to have configuration of jekyll, best place would be blog itself, so I don't really need to seach in several different places, right ?
So few important details about all this ruby-jekyll blogging.

This let's us change configuration:

`bundle update`

And run local server, just to check if it is working:
```
jekyll exec bundle serv
```

Code:
`gem 'jekyll-admin', group: :jekyll_plugins`
added to gemfile:  let's me use my administrator mode.

Layout is saved in _layouts and that's the place from which jekyll takes templates/css stuff.
