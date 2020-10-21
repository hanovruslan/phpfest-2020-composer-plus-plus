---
layout: yandex2
style: |
    .pre-small pre code { font-size: 24px!important; line-height: 48px!important; }
    .pre-big pre code { font-size: 54px !important; line-height: 108px !important; } #  9 lines x 52 symbols
    .big-list { font-size: 80px!important; line-height: 160px!important; }
    .images-w { background-color: #fff !important; }
    .images-wide { width: 100%; }
    .red { border-left: 9px solid #f00 !important; }
    figure.short { width: 480px !important; }
    .text-center { text-align: center !important; }
    img.center { margin: auto !important; }
    section.section-white { background-color: #fff !important; }
---
# ![](pictures/phpfest.jpg){:.logo}

## {{ site.presentation.title }}
{:.title}

## План

**Что будет в докладе**{:.next}

**Чего не будет в докладе**{:.red.next}

**План**{:.next}

## План

- {:.next}Введение
- {:.next}Как работает
- {:.next}Проблемы
- {:.next}Решения
- {:.next}Composer 2.0
- {:.next}Вывод

## Введение в Composer
{:.section.section-white}

## Альтернативы

**PHing**{:.next}

**Makefile**{:.next}

**Gradle**{:.next}

## Альтернативы, есть но ...

**Нативность**{:.next}

**Качество**{:.next}

**Популярность**{:.next}

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
- {:.next}Зависимость - это часть вашего проекта, без которой нельзя сделать нужное.

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

## Примеры использование плагинов

**composer require brainmaestro/composer-git-hooks**

```json
  "extra": {      
      "hooks": {
          "pre-commit": "your mighty bash one-liner"
      },     
  }       
```

**cat .git/hooks/pre-commit**
```bash
#!/bin/sh

your mighty bash one-liner
```

## Проблемы
{:.section.section-white}

## Проблемы

1. Работа с переменными окружение
1. Настройка вывода результатов выполнения команды
1. Нет возможности запускать фоновые процессы
1. Нельзя повторно запускать комплексную команду со стадии, когда была ошибка
1. Оффлайн-режим (Появился в composer 2.0)
1. Ограничения схемы настроек на изменение самого файла настроек (частично исправлено в Composer 2.0)

## Решения
{:.section.section-white}

## Выводы

1. Используйте скрипты
2. Используйте плагины
3. Используйте приватные репо

## Composer 2.0

1. Плагин `hirak/prestissimo` больше не нужен
1. `--dry-run` для всех команд управления пакетами
1. Опция `--no-suggest` удалена?!
1. Полноценная работа с extra из консоли
1. Работа с репозиториями
1. Оффлайн-режим

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
