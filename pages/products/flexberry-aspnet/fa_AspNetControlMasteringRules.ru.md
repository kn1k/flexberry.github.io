---
title: Правила разработки ASP.NET web-контролов
sidebar: flexberry-aspnet_sidebar
keywords: Flexberry ASP-NET
toc: true
permalink: ru/fa_asp-net-control-mastering-rules.html
folder: products/flexberry-aspnet/
lang: ru
---

В статье предлагается единый набор правил для грамотной/поддерживаемой/расширяемой организации архитектуры web-контролов.
Эта статья предназначена главным образом для технологов, занимающихся поддержкой и разработкой ASP.NET web-контролов.

## Работа с идентификаторами

Особенности генерации клиентских идентификаторов контролов в ASP.NET:
# Начиная с .NET Framework 4, для генерации `ClientId` используются несколько алгоритмов - т.н. `ClientIDMode` ([MSDN](http://msdn.microsoft.com/en-us/library/system.web.ui.control.clientidmode.aspx)).
# Если у контрола не указан `ID` (`ID == null`), то он будет автоматически сгенерирован при '''первом обращении''' к `ClientID` используя текущий `ClientIDMode`.
# Если у контрола указан id в атрибутах, и указан `ID`, то при рендеринге будет использован `CleintID`. Если `ID` не указан, то будет использовано значение из атрибута.

В связи с этим может появляться странное поведение при генерации идентификаторов в отладичке, например, при использовании Watch.

Пример:
```cs
_inputField = new HtmlGenericControl("div"); // ID не задан => _inputField.ID == null
_inputField.Attributes["id"] = "SomeID";     // Клиентский идентификатор задан через HTML атрибут.
                                             // Если где-то до рендеринга / в Watch будет вызван _inputField.ClinetID,
                                             // то ID != null => будет использован сгенерированный CleintID.
```
Ожидаемый результат рендеринга:
```html
<div id="ctl90"></div>
```

Полученный результат рендеринга (при обращении к `ClientID`):
```html
<div id="SomeID"></div>
```