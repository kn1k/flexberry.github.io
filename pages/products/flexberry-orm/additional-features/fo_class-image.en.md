---
title: Associating pictures with data classes
sidebar: flexberry-orm_sidebar
keywords: DataObject, Flexberry ORM, Image, class, property, object
summary: A way to associate an image with a class, object, or data property
toc: true
permalink: en/fo_class-image.html
lang: ru
---

С [классом данных](fo_data-object.html) может быть ассоциировано изображение.

* `ClassImageFile`. Если требуется всегда указывать одно и то же изображение для различных экземпляров класса данных, следует поместить это изображение в сборку как встроенный (`embedded`) ресурс и указать атрибут `ClassImageFile`.
* `ClassImageProperty`. Если изображение у различных экземпляров класса данных может быть различным, используется атрибут `ClassImageProperty`, указывающий свойство класса данных, возвращающее изображение `System.Drawing.Image`.
* `ExternalImageProvider`. Картинки могут быть предоставлены и некоторым внешним провайдером (атрибут `ExternalImageProvider`).

Кроме того, что картинка отображается в пользовательском интерфейсе (например, контролы для работы с группой объектов), разработчик может получить:

* картинку для конкретного объекта данных методом [Information](fo_methods-class-information.html)`.GetImageForInstance`, 
* картинку для класса методом  `Information.GetClassImage`, 
* имя свойства, предоставляющее картинку, методом `Information.GetClassImageProperty`.

{% include note.html content="В свойствах сборки с картинкой должен быть указан правильный `Default Namespace` (соответствующий пространству имён того класса, к которому привязывается картинка)." %}
