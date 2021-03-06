---
title: Flexberry toggler
sidebar: ember-flexberry_sidebar
keywords: Flexberry Ember
toc: true
permalink: en/ef_flexberry-toggler.html
lang: en
summary: Свойства flexberry-toggler, настройка flexberry-toggler
---

## Описание

[flexberry-toggler](https://github.com/Flexberry/ember-flexberry/blob/master/addon/components/flexberry-toggler.js) - компонент, позволяющий пользователю, показывать или скрывать вложенное в него содержимое. В нем могут быть размещены поля формы, [список](ef_object-list-view.html), [детейлы](ef_groupedit.html) и другое.

### Список свойств

| Название свойства | Краткое описание |
|:-------------------:|:------------------|
| `expanded` | Текущее состояние видимости: развернут элемент или нет|
| `caption` | Общий заголовок в заголовке компонента|
| `expandedCaption` | Заголовок компонента для развернутого состояния|
| `collapsedCaption` | Заголовок компонента для свернутого состояния|
| `currentCaption` | Текущий заголовок компонента|
| `iconClass` | Иконка компонента|
| `hasResizableOLV` | Флаг указывает, когда toogler содержит изменяемый размер OLV `duration` Продолжительность в миллисекундах открытия анимации. При установленном `0` анимация отключена. _Важно_: используется только при первоначальном рендеринге|

### Пример использования

Настройка `flexberry-toggler` осуществляется в [шаблоне страницы](https://github.com/Flexberry/ember-flexberry/blob/master/addon/components/flexberry-toggler.js#L10):

```hbs
{% raw %}
{{#flexberry-toggler
    expandedCaption='Expanded caption'
    collapsedCaption='Collapsed caption'
    expanded=true
}}
    Content
{{/flexberry-toggler}}
{% endraw %}
```

При загрузке страницы компонент находится в развернутом состоянии, заголовок для развернутого сосостояния `Expanded caption`, а для свернутого - `Collapsed caption`.

### Пользовательские настройки

Состояние `flexberry-toggler` может быть сохранено в [пользовательских настройках](ef_model-user-settings-service.html) приложения.

Для использования сервиса настроек пользователя компонент `flexberry-toggler` должен содержать следующие атрибуты:

```hbs
{% raw %}{{flexberry-toggler
  ...
  componentName="..."
  ...
}}{% endraw %}
```

* `componentName` - обязательный атрибут служащий для привязки пользовательских настроек. Он должен быть уникальным в пределах одной отображаемой страницы.
