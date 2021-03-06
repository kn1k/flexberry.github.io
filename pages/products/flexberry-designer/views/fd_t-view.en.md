---
title: T-представление
sidebar: flexberry-designer_sidebar
keywords: Flexberry Desinger, View, представление, мастер, генерация, аудит
summary: Представление для работы с фильтрами и ограничениями
toc: true
permalink: en/fd_t-view.html
lang: en
---

Среди создаваемых [представлений](fd_key-concepts.html) выделяют T-представление (то есть [представление](fd_key-concepts.html), имеющее имя «<имя класса>T», например «УченикT»).

Согласно неофициальному соглашению T-представление  - это представлениe, содержащее в себе все поля объекта, а также все [мастера](fo_masters-details.html).

С T-представлением можно встретиться, например, на [компоненте создания ограничений](fw_limitation-editform.html): если [настройки фильтра](fw_filter-settings.html) уже [сгенерированы](fw_filtersand-limits.html), то в [стандартном виде компоненты](fw_standart-view-limits-editor.html) присутствует древовидная структура, аналогичная T-представлению.

## Настройки

[Видимость](fd_hidden-properties-view.html) не влияет на отображение атрибутов, поскольку будут видимы все поля вне зависимости значения поля «Видимость». По умолчанию, видимость должна быть установлена для всех атрибутов.

Поля [аудита](efs_audit.html) должны быть только у объекта, для которого создается представление. Поля аудита мастеров в данном представлении не должны указываться.

Важен порядок следования атрибутов. Порядок определяет порядок следования атрибутов в фильтре.

Заголовок должен быть понятен относительно только объекта мастера (ввиду иерархичности представления). Для свойств мастера прописываем только названия свойств (например: мастер – `Адрес проживания`, свойства мастера – `Территория `, `Улица`). 

В случае, когда атрибут-мастер дублируется строковым атрибутом, располагаем сначала строковое поле, затем мастер, при этом заголовок мастера формируем следующим образом: <Название> + ` (из справочника)`. Например: строковое поле – ДолжностьСтрокой, заголовок строкового поля - `Должность`, мастер – Должность, заголовок мастера – `Должность (из справочника)`.
