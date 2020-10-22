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

**что будет в докладе**{:.next}

**чего не будет в докладе**{:.red.next}

## План

- {:.next}введение
- {:.next}как работает
- {:.next}проблемы
- {:.next}решения
- {:.next}composer 2.0
- {:.next}выводы

## Введение в composer
{:.section.section-white}

## Альтернативы

**Phing**{:.next}

**Makefile**{:.next}

**Gradle**{:.next}

## Альтернативы, есть но ...

**нативность**{:.next}

**богатый набор фич**{:.next}

**качество**{:.next}

**популярность**{:.next}

## Введение

**Composer - это ...**

- менеджер пакетов для PHP
- менеджер зависимостей для PHP

**Composer это ...**

- управление пакетами для PHP
- управление зависимостями для PHP

## Пакеты или зависимости

- {:.next}Пакет - это добавка к вашему проекту, с помощью которой можно сделать больше.
- {:.next}Зависимость - это часть вашего проекта, без которой нельзя сделать нужное.

## Как работает Composer
{:.section.section-white}

## Схема работы: Компоненты

**Компоненты**

* {:.next}консольное приложение
* {:.next}автолоадер
* {:.next}логгер
* {:.next}окружение запуска команд
* {:.next}плагины

## Схема работы без плагинов

![](pictures/schema/composer.png){:.images-wide}

## Плагин

**`composer-plugin` пакет**

**шина событий**

**набор методов**

1. `PluginInterface::activate`
1. `PluginInterface::deactivate`
1. `PluginInterface::uninstall`
1. `EventSubscriberInterface::getSubscribedEvents`

## Схема работы с плагинами

![](pictures/schema/composer-with-plugins.png){:.images-wide}

## Популярные плагины

* hirak/prestissimo
* brainmaestro/composer-git-hooks
* mouf/nodejs-installer
* neronmoon/scriptsdev
* symfony/flex*

### использую за исключением *

## Экзотические плагины

* clue/graph-composer
* wikimedia/composer-merge-plugin
* slince/composer-registry-manager
* Composer Patches

### изучал, но предпочел не использовать

## Примеры использования плагинов

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

## Проблемы
{:.section.section-white}

## Проблемы

1. раздутый набор скриптов
1. вывод результатов выполнения команды
1. реременные окружения
1. фоновые процессы
1. редактирование всех настроек из консоли (Composer 2.0*)
1. оффлайн-режим (Composer 2.0)
1. повторный запуск команды после последнего успешного шага

### * - только секция extra

## Проблема: фоновый процесс : пример
{:.pre-big}
```json

"scripts": {
  "report": "firefox report.html"
}
```

## Проблема: фоновый процесс : костыль
{:.pre-big}
```json

"scripts": {
  "report": "(nohup ... 1>>/dev/null 2>&1 &); true"
}
```

## Решения
{:.section.section-white}

## Раздутый набор скриптов : решение
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

## Вывод результатов выполнения команды : решение

**Интеграция с monolog/monolog или аналогами**

или

**Пропатчить компонент symfony/console**

## Вывод результатов выполнения команды (2) : решение
{:.fullscreen}
```php

class CustomVerbosityCommand extends BaseCommand {
    public function run(/** */) {
        // $output->write(/** */);
        $this->writeWithCustomVerbosity(/** */);
    }

  protected function writeWithCustomVerbosity(/** */) {
        $customVerbosity = $this->getVerbosity($defaultVerbosity);
        $output->write(
            $message,
            $newline,
            $customVerbosity
        );
    }
}
```

## Переменные окружения : решение

**`init` событие**

**`extra` для реестра переменных**

**`getenv` и `putenv`**

## Фоновый процесс : решение

**& или hohup или dosown**

**уход в фоновый процесс на уровне запускаемого скрипта**

**замена symfony/process на noname/background-process**

## Редактирование composer.json из консоли : решение

**своя схема для composer.json**

## Повторный запуск команды после последнего успешного шага : решение

**решения не знаю (**{:.red}

**но знаю где подсмотреть (Gradle)**

## Composer 2.0
{:.section.section-white}

## Composer 2.0

1. `hirak/prestissimo` больше не нужен
1. `--dry-run` для всех команд управления пакетами
1. `dump-autoload` -> `check-platform-reqs`
1. `--no-suggest` удалили?!
1. `extra` полностью из консоли
1. работа с репозиториями
1. оффлайн-режим

## Выводы
{:.section.section-white}

## Выводы

1. используйте скрипты
1. используйте плагины
1. форк composer-а? Может быть не надо?!

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
- {:.github}hanovruslan

<!-- right -->

- {:.telegram}symcode
- {:.telegram}symcode_live

<!-- right -->
