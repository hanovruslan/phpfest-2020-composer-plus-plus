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
- {:.next}Выводы

## Введение в Composer
{:.section.section-white}

## Альтернативы

**PHing**{:.next}

**Makefile**{:.next}

**Gradle**{:.next}

## Альтернативы, есть но ...

**Нативность**{:.next}

**Богатый набор фич**{:.next}

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
* symfony/flex*

### Использую, за исключением *

## Экзотические плагины

* clue/graph-composer
* wikimedia/composer-merge-plugin
* slince/composer-registry-manager
* Composer Patches

### Изучал сам, но предпочел не использовать

## Примеры использование плагинов

**composer require brainmaestro/composer-git-hooks**

```json
"extra": {
    "hooks": {
        "pre-commit": "#my mighty bash one-liner"
    }
}
```

**cat .git/hooks/pre-commit**
{:.fullscreen}
```bash
#!/bin/sh

#my mighty bash one-liner
```

## Система автоматической сборки для PHP

## Проблемы
{:.section.section-white}

## Проблемы

1. Раздутый набор скриптов
1. Редактирование composer.json из консоли (Composer 2.0)
1. Вывод результатов выполнения команды
1. Переменные окружения
1. Фоновые процессы
1. Повторый запуск команды после последнего успешного шага
1. Оффлайн-режим (Composer 2.0)

### Без учета откровенных багов

## Проблем: фоновый процесс
{:.pre-big}
```json

"scripts": {
  "report": "firefox report.html"
}
```

## Костыль: фоновый процесс
{:.pre-big}
```json

"scripts": {
  "report": "(nohup ... 1>>/dev/null 2>&1 &); true"
}
```

## Решения
{:.section.section-white}

## Решение: Раздутый набор скриптов
```php
class ScriptsCommandProvider implements CommandProvider
{
    public function getCommands()
    {
        $commands = [];
        /** fullfill $commands */
        return $commands;
    }
}
```

## Решение: редактирование composer.json из консоли

**Своя схема для composer.json**

## Решение: вывод результатов выполнения команды

**Интеграция с monolog/monolog или аналогами**
или
**Замена \Symfony\...\Command**
```php

use Symfony\Component\Console\Command\Command as BaseCommand;

interface MyCommand extends BaseCommand {
    protected $verbosity;

    public function run(/** */) {
        // $output->write(/** */);
        $$this->writeWithVerbosity(/** */)
    }

    protected function writeWithVerbosity(/** */) {
        $this->getVerbosity($output->getVerbosity())
    }

    protected function getVerbosity($output) {
        return $this->verbosity ?? $output->getVerbosity();
    }
}
```

## Решение: Переменные окружения

## Решение: фоновый процесс

**hopuh или dosown**

**уход в фоновый процесс на уровне запускаемого скрипта**

**Замена symfony/process на backgroundable/process**

## Composer 2.0
{:.section.section-white}

## Composer 2.0

1. Плагин `hirak/prestissimo` больше не нужен
1. `--dry-run` для всех команд управления пакетами
1. `check-platform-reqs` встроена в `dump-autoload`
1. Опция `--no-suggest` удалена?!
1. Полноценная работа с `extra` из консоли
1. Работа с репозиториями
1. Оффлайн-режим

## Выводы
{:.section.section-white}

## Выводы

1. Используйте скрипты
1. Используйте плагины
1. Форк composer-а? Может быть не надо?!

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
