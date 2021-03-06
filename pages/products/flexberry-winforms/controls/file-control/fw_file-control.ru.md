---
title: FileControl (Winforms)
sidebar: flexberry-winforms_sidebar
keywords: Flexberry Winforms, Windows UI (Контролы)
summary: Описаны основные моменты использования FileControl
toc: true
permalink: ru/fw_file-control.html
folder: products/flexberry-winforms/
lang: ru
---


## Описание
FileControl - это контрол для работы с файлами, дающий следующую функциональность:
* выбор файла из каталога (при этом создаётся копия содержимого файла, с которым и работает приложение).
* сохранение файла в каталог.
* удаление файла.
* запуск файла (файл открывается в ассоциированном с ним приложении).

![](/images/pages/products/flexberry-winforms/controls/file-control/file-control.png)

## Как подключить к проекту FileControl
Для работы FileControl необходима ICSSoft.STORMNET.FileType.dll (есть в стандартной поставке Flexberry). 

Чтобы подключить FileControl к проекту, необходимо выполнить следующее: 

* Определить на диаграмме классов класс File [со стереотипом "typedef"](fd_typedef.html). 

* Настроить карту типов (открыть карту типов можно, например, так: .NET CSharp -> Редактировать -> Карта типов), добавив строку:

    Маппинг выглядит вот так:

    File | ICSSoft.STORMNET.FileType.File | ICSSoft.STORMNET.UserDataTypes.dll 

    Сборка _ICSSoft.STORMNET.FileType.dll_ исключена из билда Flexberry.

* Настроить карту отображения типов (открыть карту отображения типов можно, например, так: MSSQLServer Direct Generator -> Редактировать -> Карта типов), добавив строку:

     File | TEXT

## Свойства и методы FileControl
### Как показать/скрыть кнопки на FileControl
У контрола есть свойства, позволяющие показывать/скрывать кнопки изменением их на false или true.

```csharp
ctrlФайл.HideOpenButtons = false; //показать кнопку выбора файла из каталога
ctrlФайл.HideSaveButtons= false; //показать кнопку сохранения файла в каталог
ctrlФайл.HideDeleteButtons = false; //показать кнопку удаления файла
ctrlФайл.HideStartButtons = false; //показать кнопку запуска файла (открытия в ассоциированном приложении)
```

По умолчанию все кнопки на контроле на форме редактирования скрыты.

### Другие свойства и методы

| Свойство | Тип | Описание |
| ------------- | ------------- | ------------- |
| `ButtonChooseFileFromFolder` | `Button` | Кнопка выбора файла из каталога |
| `ButtonSaveFileToFolder` | `Button` | Кнопка сохранения файла в каталог
| `ButtonDelete` | `Button` | Кнопка удаления файла
| `ButtonOpenFile` | `Button` | Кнопка запуска файла (открытия в ассоциированном приложении)
| `GetDisplayValue` | `string` | Получение отображаемого значения для поля [GroupEdit](fw_group-edit.html), с которым связан контрол; предусмотрена возможность пустых значений
| `InnerFile` | `MemoryStream` | Поле, где хранится файл без zip-архивации
| `ToolTipControl` | `ToolTip` | Контрол, отвечающий за тултипы
| `Value` | `object` | Поле, где хранится файл с zip-архивацией


| Метод | Тип возвращаемого значения |Описание |
| ------------- | ------------- | ------------- |
| `GetDisplayValue` | `string` | Получение отображаемого значения для поля [GroupEdit](fw_group-edit.html), с которым связан контрол; предусмотрена возможность пустых значений|

## FileControl и формы списка

{% include important.html content="Не рекомендуется включать поля, обрабатываемые с помощью FileControl, в [представления](fd_key-concepts.html), обрабатываемые на [форме списка](fd_key-concepts.html), поскольку в этом случае при просмотре списка в память грузятся все файлы (кроме того, не гарантируется, что отображаемое имя файла будет «осмысленным»)." %}


## Изменение открытых через FileControl файлов
Если в открытые через FileControl файлы внести изменения во внешней программе (не в ту версию, что лежит в каталоге, откуда взят файл, а ту, что находится в FileControl), то файл в FileControl автоматически обновится.