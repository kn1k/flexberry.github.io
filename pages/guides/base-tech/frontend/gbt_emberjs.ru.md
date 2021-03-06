---
title: Ember JS
keywords: Programming, ember-cli, ember weekly, ember times, frontend
sidebar: guide-base-tech_sidebar
toc: true
permalink: ru/gbt_emberjs.html
lang: ru
---

## Краткое описание

**Ember.js** — свободный JavaScript каркас веб-приложений, реализующий MVC шаблон, предназначенный для упрощения создания масштабируемых одностраничных веб-приложений. Фреймворк используется такими компаниями как TED, Yahoo!, Twitch.tv и Groupon.

В декабре 2011 года каркас веб-приложений SproutCore 2.0 был переименован в Ember.js, дабы не быть перепутанным с версией 1.0. Авторами проекта являются Tom Dale и Yehuda Katz, а всего в Ember Core Team более 10 разработчиков.

**Основные принципы**
* **Маршруты** являются одним из основополагающих принципов Ember.js и подчеркивают важность URL в управлении состоянием приложения. Маршруту объекта соответствует URL-адрес, который определяет текущее состояние приложения. Маршруты определены в единственном объекте маршрутизатора.
* **Модели**, каждому маршруту соответствует модель, в которой содержатся данные, соответствующие текущему состоянию приложения. И несмотря на то, что есть возможность использовать jQuery чтобы загружать с сервера JSON-объекты, большинство приложений все-таки использует для этих целей библиотеку с моделью данных, например, Ember Data.
* **Контроллеры** используются для того, чтобы добавить модели некую логику отображения. Ранее стандартной практикой было наследовать контроллер от ObjectController если модель представляла собой один объект, и от ArrayController - если модель была массивом записей. Сейчас эти базовые классы считаются устаревшими и нормальной практикой считается обращение к свойствам модели из Ember.Controller.
* **Шаблоны** написаны на языке HTMLBars (HTML + [handlebars](http://handlebarsjs.com/) = HTMLbars) и описывают пользовательский интерфейс. Шаблоны используются для построения HTML кода приложения и позволяют встраивать в него динамически обновляемые выражения.

##  Ссылки на материалы для изучения

### Примеры

* [Приложение для сайта с арендой недвижимости (eng)](https://guides.emberjs.com/v2.16.0/tutorial/ember-cli/)

### Базовые сведения

* [Официальная документация по Ember.js](https://guides.emberjs.com/v2.16.0/)
* [Официальная документация по Ember-CLI](https://ember-cli.com/user-guide/)
* [Ember.js — идеальный фреймворк для веб приложений](https://medium.com/devschacht/graham-cox-ember-the-perfect-framework-for-web-applications-970e817ded98)
* [Базовая структура приложения](https://guides.emberjs.com/release/getting-started/core-concepts/)
* Состав приложения
    * [Маршрутизация](https://guides.emberjs.com/release/routing/)
    * [Контроллеры](https://guides.emberjs.com/release/controllers/)
    * [Шаблоны](https://guides.emberjs.com/release/templates/handlebars-basics/)
    * [Компоненты](https://guides.emberjs.com/release/components/defining-a-component/)
* [Тестирование](https://guides.emberjs.com/release/testing/)
    * [Приемочные тесты](https://guides.emberjs.com/release/testing/acceptance/)
    * [Основы модульного тестирования](https://guides.emberjs.com/release/testing/unit-testing-basics/)
    * [Тестирование контроллеров](https://guides.emberjs.com/release/testing/testing-controllers/)
    * [Тестирование маршрутов](https://guides.emberjs.com/release/testing/testing-routes/)
    * [Тестирование моделей](https://guides.emberjs.com/release/testing/testing-models/)
    * [Тестирование компонентов](https://guides.emberjs.com/release/testing/testing-components/)

### Детальный обзор

* [Управление зависимостями приложения](https://guides.emberjs.com/release/addons-and-dependencies/managing-dependencies/)
    * [Установка ember-addon-ов](gbt_embaddon.html)
    * [Установка npm-пакетов](gbt_embnpm.html)
    * [Установка bower-пакетов](gbt_embbower.html)
    * [Vendor](gbt_embvendor.html)
    * [Каталог assets](gbt_embassets.html)
    * [Ember-cli-build](gbt_embclibuild.html)
* [Конфигурирование Ember.js](https://guides.emberjs.com/release/configuring-ember/configuring-your-app/)
    * [Базовая структура конфигурационного файл](gbt_embbaseconf.html)
    * [Настройки зависящие от окружения](gbt_embsetting.html)
    * [Как импортировать его в свои классы  и вычитывать оттуда настройки](gbt_embiosetting.html)
    * [Ember.getOwner и свойства экзепляра приложения](gbt_embgetowner.html)
* [Маршрутизация](gbt_embrout.html)
* [Контроллеры](gbt_embcontr.html)
* [Шаблоны](gbt_embtemp.html)
* [Разработка Ember-компонентов](gbt_devcomp.html)
* [Разработка Ember-сервисов](gbt_devservic.html)
* [Ember Data](gbt_emddata.html)
* [Profiling Ember.js Apps](https://speakerdeck.com/selvagsz/profiling-emberjs-apps)

## Подписка на новости от команды EmberJS и сообщества

* [The Ember.js Times](https://the-emberjs-times.ongoodbits.com/)
* [Ember Weekly](http://www.emberweekly.com/)

## Программное обеспечение

* [Ember-CLI](https://guides.emberjs.com/v2.16.0/getting-started/quick-start/)

## Перейти

* [Серверная разработка](gbt_backend.html)
* [Главная страница курса](gbt_landing-page.html)
