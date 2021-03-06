---
title: Подсистема аудита для Flexberry ASP.NET
sidebar: flexberry-aspnet_sidebar
keywords: Flexberry Audit
toc: true
permalink: ru/fa_audit_entries.html
lang: ru
---

`Система аудита` позволяет отслеживать __действия пользователей__ и __состояние объектов системы__.

Отслеживается:

* Отслеживание совершаемых пользователем действий над объектами: создание, изменение, удаление.
* При каждой операции фиксируется время, автор изменений и тип операции. 
* При изменении поля фиксируется изменённое поле, его старое и новое значения.

Хранение данных аудита:

* База данных аудита может быть опционально отделена от базы данных приложения.
* Существует два режима записи собираемых аудитом данных: синхронный с выполнением операции и асинхронный (на момент написания статьи рабочим является только синхронный).

Настройка аудита: 

* Простая настройка аудита для класса, его собственных полей, мастеров и детейлов ([через Flexberry Tool](fo_audit-setup.html)).

## Особенности аудита в web-системах

Особенности аудите в web-системах описаны в [статье Аудит для Web-приложений](fa_audit-web.html).

## Аудит для web-форм

Аудит для web-форм описан в [статье Web-формы аудита](fa_audit-web-forms.html).

## Пример подключения аудита к существующему Web-приложению с использованием перегенерации проекта

Пример подключения аудита к существующему Web-приложению с использованием перегенерации проекта в соответствующей [статье](fa_audit-web-example.html).

## Пример подключения аудита к существующему Web-приложению без использования перегенерации проекта

Пример подключения аудита к существующему Web-приложению без использования перегенерации проекта описан в соответствующей [статье](fa_audit-web-example-manual.html).