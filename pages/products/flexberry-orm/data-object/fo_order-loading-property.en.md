---
title: How to load data object properties
sidebar: flexberry-orm_sidebar
keywords: DataObject , Flexberry ORM, loading objects
summary: Rules and order of loading of properties of objects
toc: true
permalink: en/fo_order-loading-property.html
lang: en
---

При загрузке объекта данных применяются следующие правила:

* Сначала создаются мастеровые объекты данных.
* Заполняются свои и мастеровые атрибуты в порядке, указанном `LoadingOrderAttribute`, затем все остальные.
* Заполняются детейлы, в соответствии с порядком, заданным в [представлении](fd_view-definition.html).

## Задание порядка загрузки свойств объекта данных (LoadingOrderAttribute)

Если необходимо явно задать порядок загрузки свойств объекта данных (например, в случае, когда это важно для правильного счёта [вычислимых атрибутов](fo_nonstored-calculated-properties.html)), то можно воспользоваться [атрибутом `LoadingOrderAttribute`](fd_data-classes.html) [класса данных](fo_data-object.html). Параметром передаётся одномерный строковый массив с именами [атрибутов](fo_attributes-class-data.html), расположенными в порядке, соответствующем порядку загрузки.