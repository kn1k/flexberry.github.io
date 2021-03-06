---
title: Business logic
sidebar: flexberry-orm_sidebar
keywords: Flexberry ORM, business servers
summary: Principles of the architecture of the business server
toc: true
permalink: en/fo_business-logic.html
lang: en
---

Бизнес-логика является частью [трёхуровневой архитектуры](https://ru.wikipedia.org/wiki/%D0%A2%D1%80%D1%91%D1%85%D1%83%D1%80%D0%BE%D0%B2%D0%BD%D0%B5%D0%B2%D0%B0%D1%8F_%D0%B0%D1%80%D1%85%D0%B8%D1%82%D0%B5%D0%BA%D1%82%D1%83%D1%80%D0%B0), соединяющей клиентскую часть и базу данных.

Бизнес-логику приложения принято выносить в [бизнес-сервера](fd_business-servers.html). По умолчанию там располагаются лишь проверки обновления данных для определенных классов (методы OnUpdate), но также туда необходимо вынести методы, реализующие бизнес-операции и работу с данными ([вычитки из БД](fo_sql-query.html)).

## Ограничения

* Вся работа с данными и все бизнес-операции должны быть вынесены в бизнес-сервера.
* Никаких элементов пользовательского интерфейса в бизнес-серверах быть не должно (Форм, MessageBox'ов и пр).
* В каждом бизнес-сервере должен быть свой [сервис данных](fo_construction-ds.html)
