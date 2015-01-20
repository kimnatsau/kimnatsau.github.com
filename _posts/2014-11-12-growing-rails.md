---
layout: post
title: "Growing rails"
description: ""
category: 
tags: []
---
{% include JB/setup %}
#1 вступление
В этой книге демонстрируются простые пособы создания гибких больших и монолитных приложений на рельсах.
Вместо введения паттернов или сервис орентированной архитектуры(service-oriented architecture), мы покажем как использовать 
строгость консистентность и организацию кода когда объем вашего кода увеличивается. Вместо использования новых гемов мы будем использовать функционал  Rails. 
#How we got here
Когда вы пначали писать на рельсах несколько лет назад, все казалось просто. Вы видели видео как создать блог за 10 минут. Вы повторяли результат. ActiveRecord felt great and everything had its place.
Через несколько лет. аш блог стал полноценной CMS с сотней моделей и контроллеров.
Ваша команда разрослась до четырех разработчиков. И каждое изменение проекта это проблема. Ваш код напоминает карточный домик.
Вы ищете помощи в интернете, и находите ее в том чтоб застрелится. Вы не хотите использовать огромные контроллеры, it says. Но избежать больших моделей не можете. And use DCI. Or CQRS. Or SOA. As you cycle
through patterns, your application is becoming a patchwork of different coding techniques. Новые члены команды в ужасе разбираются с существующим кодом. And you are beginning to question if all those
new techniques actually help, or if you are just adding layers of indirection.
Вы начинаете скучать о тех днях, когда код можно было писать легко не заботясь о том что он сломает что-то еще. Вы действительно любили ActiveRecord до того как утонули в море колбеков. If only
there was a way to do things “the Rails way” without it falling apart as your application grows.    
#Миф о бесконечно маштабируемой архитектуре
Мы хотим показать часть того как надо писать приложения на Rails чтоб это было просто для змения и понимания,каждого в команде при возрастании колличества кода. Эта книга описывает полный набор инструментов которые встречаются прирешении задач. Для начала нужно сообщить вам важный секрет: Большие приложения действительно большие. Лучшая реализация больших приложений всегда будет больше реализации маленьких приложений. Невозможно это как-то поменять. What we can do is to organize a codebase in a way that “scales logarithmically”. В два раза больше моделей не означает в два раза больше проблем.
A business management consultant would use a chart like this:

Vanilla Rails vs. Structured Rails
In order to achieve the green line in the chart above, you do not necessarily need to change the way
your application is built. You do not necessarily need to introduce revolutionary architectures to
your code. You can probably make it with the tools built into Rails, if you use them in a smarter
way.
Compare this to sorting algorithms. When a sorting function is too slow, your first thought is very
likely not “we should install a Hadoop cluster”. Instead you simply look for an algorithm that scales
better and go the Hadoop way when you become Amazon.
In a similar fashion this book is not about revolutionary design patterns or magic gems that make all
your problems go away. Instead, we will show how to use discipline, consistency and organization
to make your application grow more gently.
How we structured this book
