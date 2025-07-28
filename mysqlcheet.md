---
title: Шпоргалка по Mysql
description: Базовая команды mysql необходимые для администраторов сайтов
published: true
date: 2025-06-30T06:10:25.326Z
tags: 
editor: markdown
dateCreated: 2025-06-30T06:10:21.180Z
---

# Что тут такое?

Тут написаны часто используемые команды mysql необходимые для администрирования сайтов.
Генератор паролей можно найти тут: <https://www.onlinepasswordgenerator.ru/>

# Создание

## Создание БД

``` sql
create database nameofbd;
```

## Создание пользователя БД

``` sql
CREATE USER 'user'@'localhost' IDENTIFIED BY 'password';
```

## Выдача прав

``` sql
GRANT ALL PRIVILEGES on nameofbd.* to 'user'@'localhost';
```

# Экспорт БД

``` bash
mysqldump -u USER -p DBNAME > ~/DUMPFILE.sql
```

# Импорт БД

Перед импортом необходимо создавать БД.

``` bash
mysql -u USER -p DBNAME < ~/DUMPFILE.sql 
```

# Удаление

## Удаление БД

``` sql
DROP DATABASE nameofbd;
```

## Удаление пользователя БД

``` sql
DROP USER 'user'@'localhost';
```
