---
layout: yandex2
style: |
    .pre-small pre code { font-size: 24px!important; line-height: 48px!important; }
    .pre-big pre code { font-size: 54px !important; line-height: 108px !important; } #  9 lines x 52 symbols
    .big-list { font-size: 80px!important; line-height: 160px!important; }
    .images-w { background-color: #fff !important; }
    .images-wide { width: 100%; }
    .slide-red { border-left: 9px solid #f00 !important; }
    figure.short { width: 480px !important; }
    .text-center { text-align: center !important; }
    img.center { margin: auto !important; }
    section.section-white { background-color: #fff !important; }
---
# ![](pictures/phpfest.jpg){:.logo}

## {{ site.presentation.title }}
{:.title}

## План

**Что будет в докладе**{:.slide.next}

**Чего не будет в докладе**{:.slide.next}

**План**{:.slide.next}

## План

- {:.next}Введение
- {:.next}Как работает
- {:.next}Проблемы
- {:.next}Решения
- {:.next}Вывод

## Введение в Composer
{:.section.section-white}

## Альтернативы

**PHing**{:.slide.next}

**Makefile**{:.slide.next}

**Gradle**{:.slide.next}

## Альтернативы, есть но ...

**Нативность**{:.slide.next}

**Качество**{:.slide.next}

**Популярность**{:.slide.next}

## Введение

**Composer - это ...**

- Менеджер пакетов для PHP
- Менеджер зависимостей для PHP

**Composer это ...**

- Управление пакетами для PHP
- Управление зависимостями для PHP
- Система автоматической сборки для PHP

## Пакеты или зависимости

- {:.next}Пакет - это добавка к вашему проекту, с помощью которой можно сделать больше.
- {:.next}Зависимость - это часть вашего проекта, без которой он (проект) не сможет сделать то, что должен.

## Как работает Composer
{:.section.section-white}

## Схема работы: Компоненты

**Компоненты**

* {:.next}Консольное приложение
* {:.next}Автолоадер
* {:.next}Логгер
* {:.next}Окружение запуска команд

## Схема работы

![](pictures/schema/composer.png){:.images-wide}

## Плагины

## Схема работы с плагинами

![](pictures/schema/composer-with-plugins.png){:.images-wide}

## Популярные плагины

* hirak/prestissimo
* brainmaestro/composer-git-hooks
* mouf/nodejs-installer
* neronmoon/scriptsdev

## Проблемы

1. Нельзя настроить Настройка окружения для запуска команд в композере
1. Настройка вывода результатов выполнения команды
1. Нет возможности запускать фоновые процессы
1. Ограничения схемы настроек на изменение самого файла настрок
1. Некоторая странность композитных команд (скриптов)
1. Нельзя повторно запускать комплексную команду со стадии, когда была ошибка

## Решения

* Настройка окружения для запуска команд в композере
* Настройка вывода результатов выполнения команды
* Нет возможности запускать фоновые процессы
* Нельзя повторно запускать комплексную команду со стадии, когда была ошибка

## Полезная ссылка

* https://github.com/jakoch/awesome-composer

## Контакты
{:.contacts}

<figure markdown="1">

### {{ site.author.name }}
{{ site.author.company.name }}

</figure>
<!-- разделитель контактов -->
-------

<!-- left -->
- {:.telegram}hanovruslan
- {:.mail}hanov.ruslan@gmail.com
- {:.github}hanovruslan41

<!-- right -->

- {:.telegram}symcode
- {:.telegram}symcode_live

<!-- right -->
