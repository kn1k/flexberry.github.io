---
title: Рекомендации по доработке форм редактирования
sidebar: flexberry-winforms_sidebar
keywords: Windows UI (Контролы)
summary: Приведены рекомендации по доработке внешнего вида форм, указаны наиболее часто применяемые механизмы и даны ссылки на статьи, описывающие их реализацию
toc: true
permalink: en/fw_forms-recommendations.html
lang: en
---

Важно понимать, что форма служит не только для редактирования данных, но и для просмотра данных, а также для управления данными - запуск операции экспорта, печати, работы с данными аудита и прочее.

Поэтому проработку внешнего вида лучше начинать с того, что следует определить какие задачи пользователи будут выполнять с помощью формы. Основные - уже перечислены, это: редактирование, просмотр, выполенение операций над объектом, редактируемым на форме (экспорт, печать и прочее).

Для того чтобы сделать форму удобной для ввода, следует обратить внимание на следующие моменты:

* порядок обхода (переход по Tab),
* визуальное выделение фокуса - неопытные пользователи могут даже и не знать, что такое фокус ввода и что он отображется мигающей вертикальной чертой в поле ввода,
* [предиктивный ввод](fw_predict-input.html),
* отображение полей, обязательных для ввода. <br> Вариант реализации: через [DataObjectErrorProvider](fw_data-object-error-provider.html). DataObjectErrorProvider позволит быстро и со вкусом прописать в коде перечень обязательных полей и пользователи приложения не смогут его менять.
* значения по умолчанию,
* автоматизация ввода пользовательских данных, например, ввод адреса или возможность ввести ключевые реквизиты другого объекта данных с возможностью автоматического поиска.

Для облегчения просмотра и поиска глазами на форме нужных данных применяются следующие механизмы:

* объединение элементов управления в логические группы (GroupBox) с указанием названия группы - общего признака всех атрибутов в этой группе,
* расположение контролов по сетке в несколько столбцов и строк. ширина полей ввода в одном столбце должна быть одинаковой, заголовки полей в столбцах начинаются с одной позиции в строке,
* увеличения шрифта. Бывают случаи, когда шрифт должен быть увеличен (например, когда большинство пользователей этой формы - пожилые люди с плохим зрением),
* реализация работы формы редактирования в режиме "[Только на чтение](fw_readonly-in-editmanager.html)" . Здесь работа заключается в проверке, что ненужные функции заблокированы, а нужные работают корректно.

Для выполнения операций над данными зачастую используется панель инструментов, на которой по умолчанию есть кнопки "Сохранить" и "Сохранить и закрыть". Для каждой операции лучше создавать отдельную кнопку на этой панели с чёткой иконкой, лаконичной надписью и понятной всплывающей подсказкой (tooltip). Между кнопками используйте вертикальный разделитель.

Расположение контролов на форме и группировка их в группы - комплексная задача, которая должна решаться совместно с аналитиком.

Также формы редактирования могут предоставлять следующие универсальные сервисы:

* аудирование изменений данных и предоставление доступа к данным аудита,
* проверка данных на соблюдение пользовательских условий,
* разграничение доступа к данным с помощью системы полномочий,
* хранение пользовательских настроек.