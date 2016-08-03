﻿# ПарсерМодуля

Автор: ret-Phoenix

Версия: 0.0.0.2

Парсер модулей с 1С подобным синтаксисом.
За основу разметки взят JavaDoc.
Добавлен свой тег '@Module', может принимать значения: <Имя модуля>, #lib.config - взять имя модуля из описания библиотеки.
lib.config ищется в каталоге скрипта и на 1 уровень выше.
Ссылки вида '{\\link <Ссылка>}' преобразуются в <Ссылка>.html.

## Методы

### Публичные

#### ПолучитьМетодыСОписанием

**Синтаксис**

ПолучитьМетодыСОписанием()



**Возвращаемое значение:**

Массив

Массив с методами модуля.

**Описание:**

Получает список методов модуля. Для каждого метода создается структура.
Структура модуля:
- Тип - Процедура / Функция
- Имя - Имя метода
- Описание - Описание метода
- Экспорт - Булево. Истина - экспортный, иначе приватный
- Параметры - ТаблицаЗначений параметров:
- Имя
- ПоЗначению
- ЗначениеПоУмолчанию
- Описание
- ВозвращаемоеЗначение - Массив возможных возвращаемых значений

#### ПолучитьОписание

**Синтаксис**

ПолучитьОписание()



**Возвращаемое значение:**

Структура

с описанием модуля

**Описание:**

Возвращает описание модуля в виде структуры с ключами:
- Описание
- Автор
- Версия
- Имя

#### ПолучитьФайлМодуля

**Синтаксис**

ПолучитьФайлМодуля()



**Возвращаемое значение:**

Строка

Путь к файлу модуля

**Описание:**

Получить путь к файлу модуля

#### УстановитьФайлМодуля

**Синтаксис**

УстановитьФайлМодуля(<ИмяФайла>)

**Параметры:**

_<ИмяФайла>_ (обязательный)



**Описание:**

Установка файла модуля для парсера

### Приватные

#### ПолучитьИмяМодуляИзОписанияПакета

**Синтаксис**

ПолучитьИмяМодуляИзОписанияПакета()



**Возвращаемое значение:**

Строка, Неопределено

Имя пакета, если не найдено Неопределено

**Описание:**

Получает имя модуля из описания библиотеки (lib.config).
Ищет файл lib.config в каталоге с модулем и на 1 ур. выше.

#### ПолучитьТекстИзФайла

**Синтаксис**

ПолучитьТекстИзФайла(<ИмяФайла>)

**Параметры:**

_<ИмяФайла>_ (необязательный)

Строка - Путь к файлу с модулем, если файл не указан берется основной файл модуля



**Возвращаемое значение:**

Строка

Если файл прочитан
