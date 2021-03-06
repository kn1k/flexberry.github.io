---
title: Access to the object's own attributes and attributes of related objects
sidebar: flexberry-orm_sidebar
keywords: DataObject, Flexberry ORM, attributes
summary: Getting Object Properties
toc: true
permalink: en/fo_own-object-attributes.html
lang: en
---

## Получение значения свойства

Доступ к атрибутам [объекта данных](fo_data-object.html) и атрибутам связанных объектов стандартен.

```csharp
SimpleDataObject sdo = new SimpleDataObject();
sdo.Name="Something";//Доступ к собственному атрибуту
sdo.Master.DblAttr=3.14;//Доступ к мастеровому атрибуту
sdo.Details[0).StringAttr="DetailAttribute";//Доступ к детейловому атрибуту
```

## Cтроготипизированное получение свойств в виде строк

Вместо того, чтобы использовать названия атрибутов в виде строк-констант, например:

```csharp
var propertyName = ((Пользователь)dataObject).Наименование;
```

Можно использовать строготипизированный доступ с использованием лямбды методами [`Information`](fo_methods-class-information.html):

```csharp
var propertyName = Information.ExtractPropertyName<Пользователь>(x => x.Наименование);
```

Все доступные методы: `ExtractPropertyName`, `ExtractPropertyPath`, `ExtractPropertyInfo` описаны в статье [Получение метаданных объектов](fo_methods-class-information.html).