# Создание личного прокси за несколько минут

Для начала подключимся к серверу по SSH

# Выбор и заказ виртуального сервера

Для начала необходимо заказать сервер, рассмотрим на примере Aeza:

1. Перейдите на страницу с виртуальными серверами: <https://my-aeza.net/order/vps>
2. Выберите желаемую локацию, для 3x-ui подайдёт самые дешёвые тарифы по 4,94 € мес.:
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
>
> Скопировать текст в Termius вы можете просто выделя его, он сразу будет скопированным!

## Установка Hysteria2

Вставляем следующую команду:

``` bash
bash <(curl -Ls https://raw.githubusercontent.com/YukiKras/vless-scripts/refs/heads/main/hysteria-install.sh)
```
Жмём **Enter**, и ожидаем установку:

![WindowsTerminal_PEhM78eV4l.png](/hysteria2/WindowsTerminal_PEhM78eV4l.png)

После окончания установки можете копировать Vless ключ и вставлять в свой VPN клиент:

![cIUuDHjO1X.png](/hysteria2/cIUuDHjO1X.png)

## Подключение ключа в клиент Hysteria2

> **С тем как подключить клиентов к вашему серверу вы можете ознакомиться в [следующей статье](https://wiki.yukikras.net/ru/nastroikavpn)**
