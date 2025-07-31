---
title: Развертывание прокси протокола VLESS с помощью 3x-ui
description: 
published: true
date: 2025-07-31T22:45:42.804Z
tags: 
editor: markdown
dateCreated: 2025-07-06T08:15:10.304Z
---

# Развертывание прокси протокола VLESS с помощью 3x-ui

3X-UI - удобная панель для создания конфигов подключения к прокси различных протоколов, таких как VLESS, VMESS, Trojan, Shadowsocks. В данной инструкции мы рассмотрим подключение по протоколу VLESS.

# Выбор и заказ виртуального сервера

Для начала необходимо заказать сервер, рассмотрим на примере Aeza:

1. Перейдите на страницу с виртуальными серверами: <https://my-aeza.net/order/vps>
2. Выберите желаемую локацию, для Outline подайдёт самые дешёвые тарифы по 4,94 € мес.:
![msedge_z3zf5vjwy6.png](/outline/msedge_z3zf5vjwy6.png)
3. Выберите в качесте ОС сервера Ubuntu 24.04 и закажите его:
![msedge_h7fwolvsqu.png](/outline/msedge_h7fwolvsqu.png)

# Создание личного прокси за несколько минут

Для начала подключимся к серверу по SSH

## Подключение к серверу по SSH

1. В поле **Host Name** — укажите IP-адрес Вашего сервера.
2. Далее введите порт. По умолчанию это — 22
3. Нажмите на кнопку для подключения — **Open.**
![putty_sopx8qrdn5.png](/ssh-sftp/putty_sopx8qrdn5.png)
Далее необходимо указать имя пользователя (по умолчанию это — **root**).

Затем вводим **пароль.**
![image.jpg](/ssh-sftp/image.jpg)
> Пароль в PuTTY вводится невидимыми символами!

Чтобы вставить текст в PuTTY, необходимо нажать **ПКМ** (правая кнопка мыши) для Windows.

## Установка 3x-ui

Вставляем следующую команду:

``` bash
bash <(curl -Ls https://raw.githubusercontent.com/YukiKras/vless-scripts/refs/heads/main/3xinstall.sh)
```
Жмём **Enter**, и ожидаем установку:

![windowsterminal_lzu8me9zvy.png](/3xui/windowsterminal_lzu8me9zvy.png)

После окончания установки можете копировать Vless ключ и вставлять в свой VPN клиент:

![ely1uerdvx.png](/3xui/ely1uerdvx.png)

## Подключение ключа в клиент VLESS

С тем как подключить клиентов к вашему серверу вы можете ознакомиться в [следующей статье](https://wiki.yukikras.net/ru/nastroikavpn)

# Часто задаваемые вопросы (FAQ)

## Как добавлять новых клиентов?
Вводим в консоле сервера следующую команду:

``` bash
cat /root/3x-ui.txt
```

Копируем ссылку и открываем ее в вашем браузере и попадаем на страницу входа в панель 3x-ui. Указываем данные из консоли и производим вход.

![image(4).png](/3xui/image(4).png)

После входа мы увидим главную страницу панели:

![image(5).png](/3xui/image(5).png)

Переходим во вкладку **Инбаунды**, далее нажимаем по существующему подключения нажимаем на три точки и нажимаем на **Создать клиента**:

![waterfox_wwlqygggad.png](/3xui/waterfox_wwlqygggad.png)

Выбираем Flow xtls-rprx-vision и нажимаем на **Добавить**:

![waterfox_czcoto7w8e.png](/3xui/waterfox_czcoto7w8e.png)

Далее переходим в раздел с информацией нового клиента:

![waterfox_1qdv8gjbor.png](/3xui/waterfox_1qdv8gjbor.png)

И отсюда вы уже сможете скопировать Vless ключ нового клиента:

![waterfox_qhz7vjkakp.png](/3xui/waterfox_qhz7vjkakp.png)

## Как исправить ошибку 9curl: No such file or directory

![waterfox_nrr8n4ogpw.png](/3xui/waterfox_nrr8n4ogpw.png)

Вероятнее всего вы подключились по VNC, для правильной установки к серверу нужно подкючаться по SSH: https://wiki.yukikras.net/ru/razvertyvanie-proksi-protokola-vless-s-pomoshyu-3x-ui#%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA-%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D1%83-%D0%BF%D0%BE-ssh