---
title: Тип слоя group
keywords: ember
sidebar: ember-flexberry-gis_sidebar
toc: true
permalink: ru/efg_group.html
lang: ru
published: true
---

## Спецификация

Групповой слой самостоятельно не ведет никакую рабуту с данными, визуально и поведенчески он является просто контейнером/каталогом для других слоев.
Роль контейнера выражается в основном в трех вещах:

* В дереве слоев групповые слои вместе с вложенными в них дочерними отображаются в видде иерархии;
* При включении/выключении видимости группового слоя на карте отображаются/исчезают и все вложенные в него дочерние слои;
* У групповых слоев отображается кнопка добавления в них новых дочерних слоев, как и у корня всей иерархии слоев карты, другие типы слоев такой возможностью не обладают;

## Ember-компонент слоя и его свойства

Ember-компонент группового слоя располагается по пути [ember-flexberry-gis/addon/components/layers/group-layer](https://github.com/Flexberry/ember-flexberry-gis/blob/develop/addon/components/layers/group-layer.js)

## Примеры использования

Пример добавления небольшой многоуровневой иерархии при помощи групповых слоев:

![](/images/pages/products/flexberry-gis/addons/ember-flexberry-gis/layers/efg_group/group-layer-example.png)

Обратите внимание, система координат и прочие атрибуты характерные для других типов слоев, не указываются при добавлении группового слоя,
указывается только тип слоя `group`, имя слоя, при необходимости еще опциональные описание и ключевые слова.
