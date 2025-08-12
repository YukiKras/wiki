---
title: Развертывание прокси протокола VLESS с помощью 3x-ui
description: 
published: true
date: 2025-08-12T09:06:04.782Z
tags: 
editor: markdown
dateCreated: 2025-07-06T08:15:10.304Z
---

# Развертывание прокси протокола VLESS с помощью 3x-ui

3X-UI - удобная панель для создания конфигов подключения к прокси различных протоколов, таких как VLESS, VMESS, Trojan, Shadowsocks. В данной инструкции мы рассмотрим подключение по протоколу VLESS.

# Создание личного прокси за несколько минут

Для начала подключимся к серверу по SSH

# Выбор и заказ виртуального сервера

Для начала необходимо заказать сервер, рассмотрим на примере Aeza:

1. Перейдите на страницу с виртуальными серверами: <https://my-aeza.net/order/vps>
2. Выберите желаемую локацию, для Outline подайдёт самые дешёвые тарифы по 4,94 € мес.:
![msedge_z3zf5vjwy6.png](/outline/msedge_z3zf5vjwy6.png)
3. Выберите в качесте ОС сервера Ubuntu 24.04 и закажите его:
![msedge_h7fwolvsqu.png](/outline/msedge_h7fwolvsqu.png)

## Переустановка существующего сервера

Для этого перейдите на странице услуги, нажмите на кнопку "Переустановить"

![msedge_jferqj8vyu.png](/3xui/msedge_jferqj8vyu.png)

Выберите в качестве ОС сервера Ubuntu 24.04, и нажмите на "Переустановить"

![msedge_tqrfrqmqwt.png](/3xui/msedge_tqrfrqmqwt.png)

> Готово! После переустановки сервера можете переходить к следующему шагу.
{.is-success}

## Подключение к серверу по SSH

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

> Готово! Можете переходить к следующему шагу.
{.is-success}


## Установка 3x-ui вручную

Вставляем следующую команду:

``` bash
bash <(curl -Ls https://raw.githubusercontent.com/YukiKras/vless-scripts/refs/heads/main/3xinstall.sh)
```
Жмём **Enter**, и ожидаем установку:

![windowsterminal_lzu8me9zvy.png](/3xui/windowsterminal_lzu8me9zvy.png)

После окончания установки можете копировать Vless ключ и вставлять в свой VPN клиент:

![ely1uerdvx.png](/3xui/ely1uerdvx.png)

## Подключение ключа в клиент VLESS

> **С тем как подключить клиентов к вашему серверу вы можете ознакомиться в [следующей статье](https://wiki.yukikras.net/ru/nastroikavpn)**
{.is-info}

## Настройка 3x-ui через предустоновленное ПО

**Подключаемся к серверу посредством WinSCP** и логина, пароля из личного кабинета, либо письма с вашей почты (в случае переустановки ОС).

![3xui_pred1.png](/3xui/3xui_pred1.png)

В корневом каталоге необходимо открыть файл "3x-ui.txt" с данными для подключения к панели управления 3x-ui:

![3xui_pred2.jpg](/3xui/3xui_pred2.jpg)

![3xui_pred3.jpg](/3xui/3xui_pred3.jpg)

Копируем ссылку и открываем ее в вашем браузере и попадаем на страницу входа в панель 3x-ui. Указываем данные из файла и производим вход.

![image(4).png](/3xui/image(4).png)

После входа мы увидим главную страницу панели:

![image(5).png](/3xui/image(5).png)

Переходим во вкладку **Подключения**, далее нажимаем **Добавить подключение**

![3xui_pred4.png](/3xui/3xui_pred4.png)

Настроим Vless TCP Reality более правильно.

> Подбор Server Name и Dest рекомендуем выполнять командой **ping**
> Чем ниже пинг до определенного сайта, тем меньше задержка при работающем соединении
> **Необходимо выбирать надежные сайты, если сайт будет недоступен, соединения не будет.**
> **Обязательно выбирайте не популярные но надежные сайты в качестве Server Name и Dest для вашей конфигурации Vless TCP Reality.**
{.is-warning}

**Требования к сайту:**
**1. TLS 1.3**
**2. HTTP/2**
**3. Не должен находиться за CDN сервисом**

Проверить ping можно командой:

``` bash
ping сайт -c 4
```

**Лучше подходит для серверов в Швеции и Финляндии:**

``` plaintext
teamdocs.su 
```

**Лучше подходит для серверов в Германии и Нидерландов:**

``` plaintext
wikiportal.su
```

**Лучше подходит для серверов в Москве:**

``` plaintext
docscenter.su
```

![image(3).png](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image(3).png)

В данном случае ping до сайта teamdocs.su оказался самым низким, выберем его в качестве Server Name и Dest, укажем их в данные строки
Необходимо установить порт на значение **443**, так же нажать на кнопку **"Get New Cert"**
После внесения изменений, необходимо нажать кнопку **"Создать"**

![3xui_pred5.jpg](/3xui/3xui_pred5.jpg)

Соединение создано, откроем список пользоваталей.

Далее переходим в раздел с информацией нового клиента:

![waterfox_1qdv8gjbor.png](/3xui/waterfox_1qdv8gjbor.png)

И отсюда вы уже сможете скопировать Vless ключ нового клиента:

![waterfox_qhz7vjkakp.png](/3xui/waterfox_qhz7vjkakp.png)

> Готово! Вы скопировали Vless ключ для своего клиента, с настройкой клиентов вы можете ознакомиться в [следующей статье](https://wiki.yukikras.net/ru/nastroikavpn)
{.is-success}

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

## Как исправить ошибку предупреждение системы безопасности

Если у вас в панели выводится следующее сообщение:

![waterfox_kxahx68ipf.png](/3xui/waterfox_kxahx68ipf.png)

Данную ошибку можно исправить привязав DNS к панели 3x-ui, для этого требуется:

1. Приобрести и привязать доменное имя к серверу с панелью 3x-ui (возможно использование собственного доменного имени)
2. Выпустить SSL сертификат для доменного имени и указать сертификат в конфигурации панели 3x-ui

> Вы можете быстро и легко приобрести домен у нас на сайте за несколько минут - <https://my.aeza.net/order/domain>
{.is-info}

Если доменное имя уже имеется либо приобретено в другом месте, **нужно добавить A-запись направленую на сервер с панелью 3x-ui**

Правильно добавленная А-запись выглядит следующим образом:
![image10.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image10.jpg)
После установки А-записи, необходимо дождаться обновления данных в глобальной сети:
**Обычно это происходит в течении 5-15 минут, но иногда время обновления DNS-записей занимает до 24 часов.**

Проверить обновление данных в сети можно в различных сервисах, например: <https://dnschecker.org>

Далее [подключаемся к серверу по SSH](https://wiki.yukikras.net/ru/kak-podklyuchitsya-po-ssh-i-sftp)

Вводим следующую команду:

``` bash
x-ui
```

Откроется меню управления x-ui, необходимо ввести цифру 18 и нажать на **Enter**:

![termius_tlkt7vjd5f.png](/3xui/termius_tlkt7vjd5f.png)

Далее необходимо ввести цифру 1 и нажать на **Enter**:

![termius_6k8qqzqtil.png](/3xui/termius_6k8qqzqtil.png)

Далее тут необходимо указать ваше доменное имя и нажать на **Enter**:

![termius_qb03gyzthh.png](/3xui/termius_qb03gyzthh.png)

Далее спросят про порт, тут ничего вводить не надо, просто нажмите на **Enter**:

![termius_jxvuwkuq1i.png](/3xui/termius_jxvuwkuq1i.png)

При ответе на вопрос:

> Would you like to modify --reloadcmd for ACME? (y/n):

Вводим английскую букву `y` и жмём **Enter**:

![termius_j4n7ljntqp.png](/3xui/termius_j4n7ljntqp.png)

При ответе на вопрос:

> Would you like to set this certificate for the panel? (y/n):

Вводим английскую букву `y` и жмём **Enter**:


![termius_pawvhwlkxg.png](/3xui/termius_pawvhwlkxg.png)

Теперь вам нужно будет входить в панель по указанной в Access URL ссылке:

![termius_4opwb9urk3.png](/3xui/termius_4opwb9urk3.png)

> Готово! После выполнения данной инструкции предупреждения не будет!
{.is-success}

![waterfox_iabxj20q8q.png](/3xui/waterfox_iabxj20q8q.png)

## Как исправить ошибку 9curl: No such file or directory

![waterfox_nrr8n4ogpw.png](/3xui/waterfox_nrr8n4ogpw.png)

Вероятнее всего вы подключились по VNC, для правильной установки к серверу нужно подкючаться по SSH: https://wiki.yukikras.net/ru/razvertyvanie-proksi-protokola-vless-s-pomoshyu-3x-ui#%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA-%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D1%83-%D0%BF%D0%BE-ssh