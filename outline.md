---
title: Настройка Outline сервера
description: 
published: true
date: 2025-07-24T18:24:54.403Z
tags: 
editor: markdown
dateCreated: 2025-07-24T18:07:12.378Z
---

# Outline - Создание личного прокси
Outline - бесплатный, безопасный прокси с открытым исходным кодом. Сервер Outline запускает экземпляры прокси-серверов Shadowsocks и предоставляет API, используемый приложением Outline Manager и сайтом Outline Manager Web.

# Выбор и заказ виртуального сервера
Для начала необходимо заказать сервер, рассмотрим на примере Aeza:
1. Перейдите на страницу с виртуальными серверами: https://my-aeza.net/order/vps
2. Выберите желаемую локацию, для Outline подайдёт самые дешёвые тарифы по 4,94 € мес.:
![msedge_z3zf5vjwy6.png](/msedge_z3zf5vjwy6.png)
3. Выберите в качесте ОС сервера Ubuntu 24.04 и закажите его:
![msedge_h7fwolvsqu.png](/msedge_h7fwolvsqu.png)

# Установка Outline
Расмотрим наиболее прострй способ, через автоустановку Outline с помощью сайта Outline Manager Web
## 1. Регистрация в Outline Manager Web
Это можно сделать по следующей ссылке: https://outlinemanager.com/register

После регистрации вы попадёте в Dashboard Outline Manager (https://outlinemanager.com/dashboard)

## 2. Добавление сервера
Далее вам нужно добавить сервер.

Нажимаем на сайте Outline Manager добавление сервера
![b4efozicep.png](/b4efozicep.png)

Выберем автоустановку
![doaijp5ryu.png](/doaijp5ryu.png)

В ЛК Aeza нужно перейти на страницу сервера, это можно сделать из раздела "Мои услуги":
![msedge_zvu1id9dds.png](/msedge_zvu1id9dds.png)

Далее необходимо вставить данные для подключения к серверу как на этом скриншоте и нажать на кнопку "Setup":
![msedge_kgygskvjsk.png](/msedge_kgygskvjsk.png)

Далее ожидайте автоматической установки Outline на сервер, страницу не закрывайте
![msedge_pf74hfnw6j.png](/msedge_pf74hfnw6j.png)

После установки у вас на странице "Servers" (https://outlinemanager.com/servers) появится ваш сервер, вам необходимо перейти в него, вот так примерно это выглядит:
![msedge_gd4ndpomdx.png](/msedge_gd4ndpomdx.png)

## 3. Копирование Outline ключа
Для того чтобы скопировать Outline ключ с сервера нажмите на "Share":
![3lcnzeddpc.png](/3lcnzeddpc.png)

Далее откроется окошко с Outline ключом, оттуда вы сможете его скопировать и вставить в нужный вам клиент:
![qyqnwulrhc.png](/qyqnwulrhc.png)

## 4. Outline клиенты
Для ключей Outline есть несколько приложений для подключения:

[Nekoray](/nekoray-universal-client) (Для Операционных систем Windows, Linux)
[Happ](https://www.happ.su/main/ru) (Для Android), инструкция по Happ: https://www.happ.su/main/ru/faq/adding-configuration-subscription#id-2.-dobavlenie-cherez-url-ssylku
[V2RayTun](https://apps.apple.com/ru/app/v2raytun/id6476628951) (MacBook на процессорах от M1 и выше, Iphone, Ipad)

## 5. Создание новых Outline ключей
Для этого на странице вашего сервера нажмите на кнопку "Add new key":
![kxduquhfir.png](/kxduquhfir.png)

Далее соглашаемся на добавление нового ключа нажатием на кнопку "Add key":
![msedge_jsvhwxwtbu.png](/msedge_jsvhwxwtbu.png)

Готово! Новый Outline ключ появится на странице сервера:
![msedge_esxokaurxp.png](/msedge_esxokaurxp.png)