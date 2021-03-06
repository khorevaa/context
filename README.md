# context

[![Stars](https://img.shields.io/github/stars/khorevaa/context.svg?label=Github%20%E2%98%85&a)](https://github.com/khorevaa/context/stargazers)
[![Release](https://img.shields.io/github/tag/khorevaa/context.svg?label=Last%20release&a)](https://github.com/khorevaa/context/releases)
[![Открытый чат проекта https://gitter.im/EvilBeaver/oscript-library](https://badges.gitter.im/khorevaa/context.png)](https://gitter.im/EvilBeaver/oscript-library)

[![Build Status](https://travis-ci.org/khorevaa/context.svg?branch=master)](https://travis-ci.org/khorevaa/context)
[![Coverage Status](https://coveralls.io/repos/github/khorevaa/context/badge.svg?branch=master)](https://coveralls.io/github/khorevaa/context?branch=master)

# Библиотека context

> Короткое название `context`

## Возможности

__Данная библиотека предназначена для формирования виртуального контекста в OScript.__

* Реализует класс:
  * `Контекст` - основной класс реализации методов и свойств

* Реализует модули:
  * `ГлобальныйКонтекст` - глобальный модуль обертка на классом `Контекст`
  * `КонтекстПриложения` - глобальный модуль обертка на классом `Контекст`, для использования как контекст приложения

## Установка

Для установки необходимо:
* Скачать файл context*.ospx из раздела [releases](https://github.com/khorevaa/context/releases)
* Воспользоваться командой:

```
opm install -f <ПутьКФайлу>
```
или установить с хаба пакетов

```
opm install context
```

## Пример работы

* Через класс `Контекст`
```bsl

	Контекст = Новый Контекст();
	Контекст.В_("Ключ1", "ЗначениеКлюча");

	Ожидаем.Что(Контекст.Из_("Ключ1"), "Значения контекста должны быть равны").Равно("ЗначениеКлюча");

```

* Через класс `ГлобальныйКонтекст`
```bsl
	#Использовать context

	ГлобальныйКонтекст.В_("Ключ1", "ЗначениеКлюча");

	Ожидаем.Что(ГлобальныйКонтекст.Из_("Ключ1"), "Значения контекста должны быть равны").Равно("ЗначениеКлюча");

```

* Добавление сразу нескольких ключей и их значений
```bsl

	Значение1 = "Знач1";
	Значение2 = "Знач2";
	Значение3 = "Знач3";

	Контекст = Новый Контекст();
	Контекст.Добавить("Ключ1, Ключ2, Ключ3", Значение1, Значение2, Значение3);

	Ожидаем.Что(Контекст.Из_("Ключ1"), "Значения контекста должны быть равны").Равно(Значение1);
	Ожидаем.Что(Контекст.Из_("Ключ2"), "Значения контекста должны быть равны").Равно(Значение2);
	Ожидаем.Что(Контекст.Из_("Ключ3"), "Значения контекста должны быть равны").Равно(Значение3);


```

[Больше примеров к каталоге тестов](tests)

## Публичный интерфейс

[Документация публичного интерфейса](docs/README.md)

## Доработка

Доработка проводится по git-flow. Жду ваших PR.

## Лицензия

Смотри файл [`LICENSE`](LICENSE).
