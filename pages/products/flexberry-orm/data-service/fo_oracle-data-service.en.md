---
title: Data service for working with Oracle Server
sidebar: flexberry-orm_sidebar
keywords: Flexberry ORM, data service, oracle
summary: Features of the operation and requirements of Oracle Data Service
toc: true
permalink: en/fo_oracle-data-service.html
lang: en
---

`OracleDataService`- это [сервис данных](fo_data-service.html) для работы с Oracle Server напрямую, минуя ODBC; является реализацией [абстрактного класса SQLDataService](fo_sql-data-service.html).

При указании OracleDataService в качестве сервиса данных используется строка `ICSSoft.STORMNET.Business.OracleDataService, ICSSoft.STORMNET.Business.OracleDataService`.

Поскольку для ORACLE понятие "грязного чтения" и блокировок неактуально, то при настройке [DRDataService](fo_dr-data-service.html) также указывается строка `ICSSoft.STORMNET.Business.OracleDataService, ICSSoft.STORMNET.Business.OracleDataService`.

## Требования к наличию компонентов

* Если приложение использует .NET Framework версии ниже 4.0, то для работы с [`OracleDataService` требуется наличие клиентского ПО Oracle](fo_tools-oracle-ds.html).
Данное требование обусловлено тем, что в данном случае для создания соединений с БД  Oracle используется класс `System.Data.OracleClient.OracleConnection`.
Существуют ограничения на именование каталогов, в которых размещается ПО, использующее ORACLE. Если ПО разместить в каталоге, в наименовании которого присутствуют спецсимволы (точки, скобки), то всё может перестать работать. Для исправления этой ситуации достаточно переименовать каталог.
* Для .NET Framework начиная с версии 4.0 установка клиентского ПО Oracle не требуется. 
Работа с соединениями осуществляется с помощью `Oracle.ManagedDataAccess.Client.OracleConnection`. В этом случае необходимо установить nuget-пакет 
[`Oracle.ManagedDataAccess`](http://nuget.ics.perm.ru/packages/Oracle.ManagedDataAccess/).

## Особенности функционирования

Как любой [сервис данных](fo_data-service.html), `OracleDataService` поддерживает отображение типов данных с учётом особенностей их использования в конкретной СУБД. А также позволяет учесть следующие ключевые требования Oracle, в т.ч. синтаксические:

* Длина идентификатора, поддерживаемого ORACLE, ограничена 30 байтами. Причём данное ограничение действует как для имен объектов БД (т.е. учитывается при определении имен хранения  объектов генератором `Oracle SQL Generator` и сервисом данных `OracleDataService`), так и для алиасов, используемых в запросах (учитывается `OracleDataService`).
При формировании короткого варианта имени идентификатор, создаваемый базовым методом, обрезается до требуемой длины и дополняется хэш-кодом для обеспечения уникальности.
* Идентификаторы заключаются в двойные кавычки.
* Аналогом функции ifnull является функция NVL.
* Ограничение на количество строк в выборке, реализуемое с помощью ключевого слова `<nowiki>TOP</nowiki>` в базовом `SQLDataService`, реализуется посредством задания ограничения на `rownum` в выражении `WHERE`.

### Регистронезависимость строк в запросах

Поиск строк в базах данных Oracle по-умолчанию является регистрозависимым, т.е., например, при выполнении запроса

``` sql
SELECT * FROM Table1 WHERE Field1='что-то'
```

строки таблицы Table1, в которых Field1 имеет значение 'Что-то','ЧТО-ТО',..., в результирующую выборку не попадут.  

Для организации поиска независимого от регистра следует воспользоваться параметром [CaseInsensitive](fo_insensitivity-register-ds.html) файла конфигурации.

См. также статью [Обработка регистров в именах объектов для СУБД](fo_processing-registers-names.html).
