---
title: Развертывание прокси протокола VLESS с помощью Marzban
description: 
published: true
date: 2025-08-08T15:16:29.038Z
tags: 
editor: markdown
dateCreated: 2025-07-06T07:40:17.003Z
---

# 1. Развертывание прокси протокола VLESS с помощью Marzban

Marzban - панель для создания конфигов подключения к прокси различных протоколов, таких как VLESS, VMESS, Trojan, Shadowsocks. В данной инструкции мы рассмотрим подключение по протоколу VLESS.

## Создание личного прокси за несколько минут

Для установки Marzban подключитесь к серверу через [консоль](/kak-podklyuchitsya-po-ssh-i-sftp) и выполните следующую команду:

``` bash
bash -c "$(curl -sL https://github.com/Gozargah/Marzban-scripts/raw/master/marzban.sh)" @ install
```

![1.png](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/1.png)
На скриншоте выше можно наблюдать установленный и запущенный Marzban, для выхода нажмите CTRL+C

Далее создаем пользователя панели Marzban

``` bash
marzban cli admin create --sudo
```

![2.png](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/2.png)
Пользователь панели успешно создан

>В связи с последними обновлениями безопасности, есть два варианта доступа в панель:
>
>1. Через SSH-Туннель
>2. Через привязку доменного имени к серверу и получении SSL сертификата
>Рассмотрим оба случая
>
## 2.1 Вход в панель через SSH-Туннель

Для входа в панель без использования SSL сертификата и доменного имени, нам требуется создать туннель.
**Команда для создания туннеля строится следующим образом**:
ssh -L [локальный порт]:[удалённый хост]:[удалённый порт] [пользователь]@[адрес сервера]

В нашем случае команда выглядит следующим образом:

``` cmd
ssh -L 8000:localhost:8000 root@IP сервера
```

> Для Windows систем команду необходимо вводить в командной строке (cmd).
> Для Linux и MacOS - в терминале.

После ввода данной команды, подтверждаем подключение **вводом "Yes" и затем вводим пароль от сервера**, после подключения к серверу доступ к панели должен появиться с браузера вашего устройства.
![image.png](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image.png)
Теперь панель должна быть доступна в браузере по ссылке: <http://127.0.0.1:8000/dashboard/>
![image1.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image1.jpg)

Далее можете переходить к [следующему шагу](https://wiki.yukikras.net/ru/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban#h-23-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%BE%D1%82%D0%BE%D0%BA%D0%BE%D0%BB%D0%B0-vless-tcp-reality-%D0%B2-%D0%BF%D0%B0%D0%BD%D0%B5%D0%BB%D0%B8-marzban-%D0%B8-%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F)

### **Рассмотрим способ получения доступа к панели с мобильных устройств.**

Нам потребуется программа [Termius](https://play.google.com/store/apps/details?id=com.server.auditor.ssh.client) - Android
<https://apps.apple.com/ru/app/termius-terminal-ssh-client/id549039908> - IOS и MacOS
**После установки переходим в нее и первый раз авторизуемся на сервере через SSH, после чего выходим в главное меню и выбираем вкладку "Port Forwarding"**

В нижнем углу нажимаем "+" после чего выбираем Local и нажимаем Continue

| ![image2.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image2.jpg) | ![image3.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image3.jpg) |
|----------------------------|----------------------------|
|                            |                            |

Выбираем сервер из списка, после чего указываем следующие данные:
![image4.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image4.jpg)
Задаем имя данному туннелю и нажимаем на "Галочку" чтобы сохранить настройки:
![image5.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image5.jpg)
Активируем туннель путем нажатия на данное правило:
![image6.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image6.jpg)
Теперь панель должна быть доступна в браузере по ссылке: <http://127.0.0.1:8000/dashboard/>
![image7.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image7.jpg)
После входа мы увидим главную страницу панели:
![image9.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image9.jpg)
Далее можете переходить к [следующему шагу](https://wiki.yukikras.net/ru/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban#h-23-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%BE%D1%82%D0%BE%D0%BA%D0%BE%D0%BB%D0%B0-vless-tcp-reality-%D0%B2-%D0%BF%D0%B0%D0%BD%D0%B5%D0%BB%D0%B8-marzban-%D0%B8-%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F)

## 2.2 Вход в панель Marzban через HTTPS

Для входа в панель Marzban через браузер без настройки SSH Туннелей требуется:

1. Приобрести и привязать доменное имя к серверу с панелью Marzban (возможно использование собственного доменного имени)
2. Выпустить SSL сертификат для доменного имени и указать сертификат в конфигурации панели Marzban

> Вы можете быстро и легко приобрести домен у нас на сайте за несколько минут - <https://my.aeza.net/order/domain>
{.is-info}

Если доменное имя уже имеется либо приобретено в другом месте, **нужно добавить A-запись направленую на сервер с панелью Marzban**

Правильно добавленная А-запись выглядит следующим образом:
![image10.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image10.jpg)
После установки А-записи, необходимо дождаться обновления данных в глобальной сети:
**Обычно это происходит в течении 5-15 минут, но иногда время обновления DNS-записей занимает до 24 часов.**

Проверить обновление данных в сети можно в различных сервисах, например: <https://dnschecker.org>

После глобального обновления доменного имени, переходим в SSH-консоль сервера и выпустим SSL-сертификат с использованием скрипта Acme.sh

Ниже пошагово указаны команды для получения SSL-сертфиката через Acme.sh:

``` bash
apt install cron socat
```

``` bash
curl https://get.acme.sh | sh -s email=Ваша почта
```

``` bash
mkdir -p /var/lib/marzban/certs/
```

> В команде ниже необходимо обязательно указать Ваше используемое доменное имя после параметра -d

``` bash
~/.acme.sh/acme.sh --set-default-ca --server letsencrypt --issue --standalone -d Ваше_доменное_имя \
 --key-file /var/lib/marzban/certs/key.pem \
 --fullchain-file /var/lib/marzban/certs/fullchain.pem
```

После выполнения команд вы увидите подобное сообщение о успешном  выпуске сертификата:
![image(1).png](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image(1).png)
> Данный сертификат действует 3 месяца. Для автоматического продления его через cron, требуется оставить открытым 80 порт.
Откроем конфигурационный файл панели через редактор nano и укажем пути до SSL-сертификата:

``` bash
nano /opt/marzban/.env
```

![image11.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image11.jpg)
После внесения изменений, сохраняем файл и перезагружаем панель командой:

``` bash
marzban restart
```

После перезапуска переходим в браузер по ссылке `https://доменное_имя:8000/dashboard` и наблюдаем окно входа в панель Marzban:
![image12.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image12.jpg)
После входа мы увидим главную страницу панели:
![image9.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image9.jpg)

## 2.3 Настройка протокола Vless TCP Reality в панели Marzban и создание пользователя

Для качественной работы данного протокола необходимо:

1. Добавить протокол Vless TCP Reality в панель Marzban
2. Сменить Server Names ( по умолчанию установлен example.com)
3. Сменить Dest ( по умолчанию установлен example.com:443)
4. Смена ключа шифрования и параметра shortIds
5. Фикс ошибки Timeout при подключении через приложение Hiddify
6. Создание пользователя
Дальнейшие изменения будут проводиться в настройках, которые находятся в правом верхнем углу (знак настройки)
![image(2).png](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image(2).png)
Начнем с добавления протокола Vless TCP Reality
Открываем данные настройки
![image13.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image13.jpg)
Наблюдаем что в блоке "Inbounds" только Shadowsocks TCP, **добавим Vless TCP Reality в начало блока после квадратной скобки**

``` json
{
      "tag": "VLESS TCP REALITY",
      "listen": "0.0.0.0",
      "port": 8443,
      "protocol": "vless",
      "settings": {
        "clients": [],
        "decryption": "none"
      },
      "streamSettings": {
        "network": "tcp",
        "tcpSettings": {},
        "security": "reality",
        "realitySettings": {
          "show": false,
          "dest": "заменить:443",
          "xver": 0,
          "serverNames": [
            "заменить"
          ],
          "privateKey": "заменить",
          "shortIds": [
            "заменить"
          ]
        }
      },
      "sniffing": {
        "enabled": true,
        "destOverride": [
          "http",
          "tls",
          "quic"
        ]
      }
    },
```

![image14.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image14.jpg)
После добавления протокола, конфигурация должна выглядеть данным образом
![image15.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image15.jpg)
**После добавления протокола Vless TCP Reality требуется изменить значения:**

1. ServerNames
2. Dest
3. Privatekey
4. shortIds
**Сменим Server Name и Dest**

>Подбор Server Name и Dest рекомендуем выполнять командой **ping**
>Чем ниже пинг до определенного сайта, тем меньше задержка при работающем соединении
>Необходимо выбирать надежные сайты, если сайт будет недоступен, соединения не будет.
>**Обязательно выбирайте не популярные но надежные сайты в качестве Server Name и Dest для вашей конфигурации Vless TCP Reality.**
**Требования к сайту:

1. TLS 1.3
2. HTTP/2
3. Не должен находиться за CDN сервисом**
Проверить ping можно командой:

``` bash
ping сайт -c 4
```

Если вы не нашли сайт подходящий под данные требования, можно использовать сайты указанные ниже:
**
Лучше подходит для серверов в Швеции:**

``` plaintext
teamdocs.su
```

**Лучше подходит для серверов в Германии:**

``` plaintext
wikiportal.su
```

**Лучше подходит для серверов в Москве:**

``` plaintext
docscenter.su
```

![image(3).png](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image(3).png)
В данном случае ping до сайта teamdocs.su оказался самым низким, выберем его в качестве Server Name и Dest, укажем их в данные строки
![image16.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image16.jpg)
Сгенерируем новые ключи шифрования и параметр shortIds в командной строке вашего сервера командами

``` bash
docker exec marzban_marzban_1 xray x25519
```

Если вышла ошибка, попробуйте другую команду:

``` bash
docker exec marzban-marzban-1 xray x25519
```

shortIds:

``` bash
openssl rand -hex 8
```

![image17.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image17.jpg)
Нам необходимо скопировать параметры **Private key** и **shortIds** после чего заменить их в панели
![image18.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image18.jpg)
После внесения изменений, необходимо **сохранить изменения, перезагрузить ядро и перезагрузить страницу в браузере**
![image19.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/image19.jpg)
>На данном моменте Vless TCP Reality настроен.
>
## 3. Подключение ключа в клиент VLESS

С тем как подключить клиентов к вашему серверу вы можете ознакомиться в [следующей статье](https://wiki.yukikras.net/ru/nastroikavpn)

## Часто задаваемые вопросы (FAQ)

### Как исправить ошибку "Таймаут" в Hiddify?

Возвращаемся в конфигурацию панели и находим пункт "Routing"

![timeoutfix1.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/timeoutfix1.jpg)

Вставляем следующее правило в самое начало блока rules после квадратной скобки

``` json
{
        "outboundTag": "DIRECT",
        "domain": [
          "full:cp.cloudflare.com",
          "domain:msftconnecttest.com",
          "domain:msftncsi.com",
          "domain:connectivitycheck.gstatic.com",
          "domain:captive.apple.com",
          "full:detectportal.firefox.com",
          "domain:networkcheck.kde.org",
          "full:*.gstatic.com"
        ],
        "type": "field"
      },
```

![timeoutfix2.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/timeoutfix2.jpg)

После внесения изменений, необходимо их **сохранить** и **перезагрузить ядро**

![timeoutfix3.jpg](/razvertyvanie-proksi-protokola-vless-s-pomoshyu-marzban/timeoutfix3.jpg)

Готово! Ошибка должна пропасть.

