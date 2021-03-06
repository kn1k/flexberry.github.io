---
title: Диаграмма классов (Class diagram)
sidebar: flexberry-designer_sidebar
keywords: Flexberry Designer, диаграммы, диаграмма классов, ассоциация, композиция, наследование, класс
summary: Основные сведения о диаграмме классов и ее особенностях
toc: true
permalink: en/fd_class-diagram.html
lang: en
---

**Диаграмма классов** - один из доступных [видов диаграмм](fd_editing-diagram.html), поддерживаемых [Flexberry Designer](fd_landing_page.html).

Диаграмма классов является ключевым элементом [редактора UML-диаграмм](fd_editing-diagram.html), поскольку зачастую приложения генерируются именно с диаграммы классов.
Диаграмма классов - это набор статических, декларативных элементов модели. Диаграммы классов могут применяться и при прямом проектировании, то есть в процессе разработки новой системы, и при обратном проектировании - описании существующих и используемых систем. Информация с диаграммы классов напрямую отображается в исходный код приложения. Таким образом, диаграмма классов - конечный результат проектирования и отправная точка процесса разработки.

## Особенности построения диаграмм классов

Основные особенности построения диаграмм классов указаны в следующих статьях:
* [Ключевые понятия объектной структуры для прикладных систем, разрабатывающихся в Flexberry Designer](fd_key-concepts.html).
* [Особенности построения диаграммы классов](fd_class-diagram-constraction.html)

## Возможности диаграмм классов

Основные возможности при работе с диаграммами указаны в статье [Редактор UML-диаграмм](fd_editing-diagram.html).

Специфичные для диаграмм классов возможности:
* Изменение [стереотипа класса](fd_key-concepts.html) через контекстное меню.
* Просмотр зависимостей через контекстное меню (функционирование аналогично отображению зависимостей класса в [менеджере классов](fd_class-manager.html)).

## Основные элементы диаграммы классов

На диаграмме классов можно отобразить следующие элементы нотации UML, доступные в панели элементов: 

Элемент/Нотация | Предназначение
:------------------------------|:---------------------------------------
![](/images/pages/products/flexberry-designer/diagram/assoc.jpg) | [Ассоциация](fd_master-association.html) (Association)
![](/images/pages/products/flexberry-designer/diagram/aggregation.jpg) | Агрегация (Aggregation)
![](/images/pages/products/flexberry-designer/diagram/composition.jpg) | [Композиция](fo_detail-associations-properties.html) (Composition)
![](/images/pages/products/flexberry-designer/diagram/inheritance.jpg) | [Наследование](fd_inheritance.html)/обобщение (Inheritance/generalization)
![](/images/pages/products/flexberry-designer/diagram/implement.jpg) | Реализация (Realization)
![](/images/pages/products/flexberry-designer/diagram/nested.jpg) | Ассоциация вложенного класса (Nested class association)
![](/images/pages/products/flexberry-designer/diagram/class.jpg) | Класс (Class)
![](/images/pages/products/flexberry-designer/diagram/templateclass.jpg) | Класс-шаблон (Template class)
![](/images/pages/products/flexberry-designer/diagram/instance.jpg) | Экземпляр класса (instance)
![](/images/pages/products/flexberry-designer/diagram/activeobject.jpg) | Активный объект (Active object)
![](/images/pages/products/flexberry-designer/diagram/multiobject.jpg)  | Мультиобъект (Multiobject)
![](/images/pages/products/flexberry-designer/diagram/object.jpg) | Объект (Property object)
![](/images/pages/products/flexberry-designer/diagram/naryassoc.jpg) | N-арная ассоциация (N-ary association)
![](/images/pages/products/flexberry-designer/diagram/naryconn.jpg) | Коннектор n-арной ассоциации (N-ary association connector)
![](/images/pages/products/flexberry-designer/diagram/qcomposition.jpg) | Квалифицированная композиция (Qualified composition link)
![](/images/pages/products/flexberry-designer/diagram/qaggregation.jpg) | Квалифицированная агрегация (Qualified aggregation link)
![](/images/pages/products/flexberry-designer/diagram/moreclasses.jpg) | Ещё классы (More classes)
![](/images/pages/products/flexberry-designer/diagram/dependency.jpg) | Зависимость (Dependency)
![](/images/pages/products/flexberry-designer/diagram/package.jpg) | Пакет (Package)
![](/images/pages/products/flexberry-designer/diagram/corner.jpg) | Точка изгиба связей (Point)
![](/images/pages/products/flexberry-designer/diagram/note.jpg) | Комментарий (Note)
![](/images/pages/products/flexberry-designer/diagram/noteconn.jpg) | Коннектор комментария (Note connector)
