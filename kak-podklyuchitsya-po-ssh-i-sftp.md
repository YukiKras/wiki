---
title: Как подключиться к серверу по SSH/SFTP
description: 
published: true
date: 2025-07-06T08:58:38.654Z
tags: 
editor: markdown
dateCreated: 2025-07-06T06:37:54.136Z
---

# Как подключиться по SSH и SFTP

К серверам на основе ОС Linux подключение производится при помощи протоколов SSH/sFTP. Давайте разберем!

## Как подключиться?

Чтобы подключиться к серверу с ОС Linux, Вам потребуется SSH и SFTP-клиенты.
Ссылки на самые популярные клиенты для Windows!

> Ссылки на самые популярные клиенты для Windows!

- [PuTTY](https://the.earth.li/~sgtatham/putty/latest/w32/putty.exe) — **SSH-клиент.**

- [Termius](https://termius.com/free-ssh-client-for-windows) — альтернативный **SSH-клиент.**

- [FileZilla](https://filezilla.ru/) — **FTP-клиент.**

- [WinSCP](https://winscp.net/eng/download.php) — альтернативный **FTP-клиент.**

- [Bitvise](https://bitvise.com/ssh-client-download) — SSH и SFTP клиент.

- [MobaXTerm](https://mobaxterm.mobatek.net/download-home-edition.html) — SSH и SFTP/FTP клиент.

В данном случае мы **рекомендуем** использовать именно **Bitvise** или **WinSCP** для подключения по SSH/SFTP, однако как наиболее подходящий вариант для новичков, ниже мы разберем подключение через FileZilla.

## Инструкция
>
> Данные для подключения можно посмотреть на странице услуги в личном кабинете и кликнуть на неё, открыв страницу услуги.

> Для подключения по SFTP и SSH используются идентичные данные.
>
### Порядок действий для подключения к VDS/VPS Linux по SSH

> Если у вас не установлен Termius то вы можете его скачать отсюда: https://termius.com/download/
{.is-info}

Прежде чем подключаться к серверу по SSH зайдите в настройки программы:

![termius_dcfmv4roas.png](/ssh-sftp/termius_dcfmv4roas.png)

Нужно включить данный пункт в настройках:

![termius_gl0rpeubja.png](/ssh-sftp/termius_gl0rpeubja.png)

> Эта настройка нужна для правильной вставки текста
{.is-info}

Для подключения к серверу по SSH нажмите на кнопку "**NEW HOST**"

![vatcjo0cp4.png](/ssh-sftp/vatcjo0cp4.png)

Далее заполните указанные тут поля:

![termius_fwsikykqmy.png](/ssh-sftp/termius_fwsikykqmy.png)

1. Тут необходимо указать IP адрес из ЛК со страницы услуги
2. Тут необходимо указать имя вашего пользователя, по умолчанию это **root**
3. Тут необходимо указать пароль от root пользователя, его узнать вы сможете на странице услуги в ЛК.
4. После заполнения всех полей нажимаем на кнопку "**Connect**"

> Вставить текст в Termius вы можете по нажатию **ПКМ** (правой кнопки мыши)
{.is-warning}
