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

1. В поле **Host Name** — укажите IP-адрес Вашего сервера.
2. Далее введите порт. По умолчанию это — 22
3. Нажмите на кнопку для подключения — **Open.**
![putty_sopx8qrdn5.png](/ssh-sftp/putty_sopx8qrdn5.png)
Далее необходимо указать имя пользователя (по умолчанию это — **root**).

Затем вводим **пароль.**
![image.jpg](/ssh-sftp/image.jpg)
> Пароль в PuTTY вводится невидимыми символами!

Чтобы вставить текст в PuTTY, необходимо нажать **ПКМ** (правая кнопка мыши) для Windows.
