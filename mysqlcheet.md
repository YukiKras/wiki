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
Генератор паролей можно найти тут: https://www.onlinepasswordgenerator.ru/
# Создание
## Создание БД
```
create database nameofbd;
```
## Создание пользователя БД
```
CREATE USER 'user'@'localhost' IDENTIFIED BY 'password';
```
## Выдача прав
```
GRANT ALL PRIVILEGES on nameofbd.* to 'user'@'localhost';
```
# Экспорт БД
```
mysqldump -u USER -p DBNAME > ~/DUMPFILE.sql
```
# Импорт БД
Перед импортом необходимо создавать БД.
```
mysql -u USER -p DBNAME < ~/DUMPFILE.sql 
```
# Удаление
## Удаление БД
```
DROP DATABASE nameofbd;
```
## Удаление пользователя БД
```
DROP USER 'user'@'localhost';
```