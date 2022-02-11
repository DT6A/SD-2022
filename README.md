# Интерпретатор командной строки Ezh

<img src="logo.png" align="right" />

## Краткое описание
Ezh &mdash; кроссплатформенный интерпретатор команд на языке Ezh. Поддерживаемые функции:
 - запуск встроенных команд: `cat`, `echo`, `pwd`, `wc`, `exit`
 - запуск внешних команд с перенаправлением потоков и задаваемыми переменными окружения
 - экранирование одинарными и двойными кавычками

**Ссылка на документацию:** https://glebsolovev.github.io/SD-2022/

## Состояние разработки
На данный момент в проекте:
- в `scheme.pdf` представлены схемы с архитектурой программы и ее элементов
- `ARCHITECTURE.md` содержит подробное текстовое описание архитектуры
- реализован, задокументирован и покрыт тестами основной функционал (описано выше)
- настроен CI: запуск тестов и линтеров, сборка и публикация документации

## Использование приложения
### Сборка и запуск
Сборка осуществляется при помощи Gradle из директории с проектом:
```bash
./gradlew assemble
```
Собранный `Ezh-1.0.jar` можно найти в директории `build/libs/`.

Чтобы его запустить, достаточно выполнить следующую команду из папки с проектом:
```bash
kotlin -cp build/libs/Ezh-1.0.jar ru.hse.ezh.EzhKt
```

### Альтернативный запуск
Альтернативный способ запуска приложения через Gradle:
```bash
./gradlew run --console=plain
```
Однако в таком случае Gradle может добавлять лишний вывод в консоль, а также при завершении Ezh-а с ненулевым кодом возврата закончится ошибкой. 

### Запуск тестов
Чтобы запустить тесты и получить по ним статистику:
```bash
./gradlew test
```
