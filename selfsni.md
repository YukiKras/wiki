---
title: Установка своего SNI сайта
description: 
published: true
date: 2025-07-28T13:12:40.522Z
tags: 
editor: markdown
dateCreated: 2025-07-28T13:12:40.522Z
---

# Настройка SNI сайта для Reality

В данной инструкции будет описана пошаговая настройка сайта для работы Reality, с использованием веб сервера Nginx и Certbot

## Привязка IP адреса сервера к доменному имени

**SNI сайт невозможно поднять без доменного имени, Вы можете быстро и легко приобрести домен у нас на сайте за несколько минут** - https://my-aeza.net/order/domain 

Нам требуется добавить А запись которая будет направлена на сервер
**Сделать это можно указав знак @ и IP сервера**

![image_(1).jpg](/selfsni/image_(1).jpg)

**Сохраняем информацию и подтверждаем добавление данной А записи**
**Ожидаем от 5 минут до 24х часов глобального обновления после чего продолжаем настройку**

## Установка скрипта

**В данном случае будет описана настройка на сервере с операционной системой Ubuntu 24.04**

Для этого подключитесь к консоле сервера с помощью [SSH](/kak-podklyuchitsya-po-ssh-i-sftp)
И введите следующую команду:

``` bash
bash <(curl -Ls https://raw.githubusercontent.com/YukiKras/vless-scripts/refs/heads/main/fakesite.sh)
```

Вас запросят ввести доменное имя, которое вы настраивали в предедущем шаге:

![windowsterminal_ijrctmuc6p.png](/selfsni/windowsterminal_ijrctmuc6p.png)

Вводите его и нажимаете на **Enter**

Далее скрипт запросит выбрать внутренний SelfSNI порт, вы можете его оставить по умолчанию просто нажав на **Enter**:

![windowsterminal_wyzkp2ftgv.png](/selfsni/windowsterminal_wyzkp2ftgv.png)

Готово! Просто дожидайтесь установки, результат успешной установки выглядит так:

![windowsterminal_sytorbczbs.png](/selfsni/windowsterminal_sytorbczbs.png)

Рассмотрим внесение настроек SNI в 3x-ui и в Marzban панелях

## Настройка Vless в 3x-ui панели

Для этого откройте 3x-ui панель и перейдите в раздел "Инбаунды":

![bbchexvq6n.png](/selfsni/bbchexvq6n.png)

Далее у вашего Vless подключения нажимаем на троеточие и кнопку "Изменить":

![waterfox_fzhgnhtep4.png](/selfsni/waterfox_fzhgnhtep4.png)

Далее копируем настройки из консоли и вставляем в панель, нажимаем на "**Get New Cert**" и "**Обновить**":

![waterfox_da9mtlg2br.png](/selfsni/waterfox_da9mtlg2br.png)

Далее необходимо скопировать новые Vless ключи и перенастроить ваших клиентов.

## Настройка Vless в Marzban панели

Для этого откройте Marzban панель и перейдите в его настройки:

![n0khshl0hn.png](/selfsni/n0khshl0hn.png)

Скопируйте и вставьте настройки из консоли, нажмите на перезагрузку ядра и сохранения изменений:

![waterfox_phziqluthw.png](/selfsni/waterfox_phziqluthw.png)

Далее нажмите на клавишу **F5** и скопируйте новые Vless ключи и перенастройте на работу с ними ваших клиентов.
