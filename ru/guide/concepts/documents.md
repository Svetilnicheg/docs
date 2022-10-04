# Отчетные документы

Вся работа с платежными документами ведется в личном кабинете [**Яндекс Баланса**]({{ balance }}).

Вы можете попасть в сервис из личного кабинета в Толоке, для этого:

1. На странице [Профиль]({{ profile }}) нажмите кнопку {% if locale == "ru-ru" %}**Пополнить счет**{% endif %}{% if locale == "en-com" %}**Transfer funds**{% endif %}.

1. Введите любую сумму пополнения в долларах США. Минимальная сумма — 1 доллар.
1. Нажмите {% if locale == "ru-ru" %}**Пополнить**{% endif %}{% if locale == "en-com" %}**Transfer**{% endif %}.

    Вы будете перенаправлены в Яндекс Баланс. Отчетные документы находятся в разделе **Акты**.


{% note warning %}

Если вы зашли в Яндекс Баланс не для пополнения средств, не нажимайте кнопку **Выставить счет**.

{% endnote %}

#### Список отчетных документов

#### Для резидентов России

- {% include [toloka-requester-source-accounting-doc](../_includes/toloka-requester-source/id-toloka-requester-source/accounting-doc.md) %}

    Вы можете отправить копию акта на электронную почту или заказать оригинал акта. Подробнее о заказе документов читайте в [Помощи Баланса]({{ balance-support }}).

    Также вы можете запросить оригиналы актов через форму ниже.

    <iframe width="100%" frameborder="0" src="https://forms.yandex.com/surveys/10015610/?lang=ru&iframe=1&service=toloka-ai"></iframe>

- Расширенный отчет

    Содержит данные по всем актам и оплатам. Доступен только в электронном виде.

    Чтобы получить Расширенный отчет, перейдите на страницу **Акты**, выберите период отчетности в полях **Дата от** и **по**, введите ваш e-mail и нажмите кнопку **Отправить по электронной почте**.

- Акт сверки

    Вы можете настроить формирование акта за нужный период. Акты сверки будут приходить на электронную почту. Подробнее о заказе документов читайте в [Помощи]({{ balance-acts-settlements }}) Баланса.

#### Для нерезидентов России

- {% include [toloka-requester-source-accounting-doc](../_includes/toloka-requester-source/id-toloka-requester-source/accounting-doc.md) %}

    Чтобы скачать копию акта, перейдите на страницу **Счета** и нажмите на номер нужного счета. В разделе **История актов** нажмите **Печатная форма**.

- Расширенный отчет

    Содержит данные по всем актам и оплатам. Доступен только в электронном виде.

    Чтобы получить Расширенный отчет, перейдите на страницу **Акты**, выберите период отчетности в полях **Дата от** и **по**, введите ваш e-mail и нажмите кнопку **Отправить по электронной почте**.

## Изменить платежные данные {#section_obr_lvl_m3b}

{% note alert %}

Даты и суммы закрывающих документов изменить невозможно.

{% endnote %}

#### Изменить адреса доставки документов и платежные реквизиты

Вы можете изменить адрес электронной почты, фактический адрес для доставки корреспонденции, а также некоторые платежные реквизиты. Для этого:

1. Перейдите на страницу [**Плательщики**]({{ persons }}).
1. Нажмите ссылку **изменить** в блоке с нужным плательщиком.
1. Измените необходимые данные.
1. Нажмите кнопку **Сохранить изменения**.

Также вы можете отправить запрос на изменение платежных данных на электронную почту группы документооборота: `docs-project@support.yandex.com`. В запросе укажите список новых и старых реквизитов, адрес эл почты, с которой регистрировались в Толоке а также прикрепите копию документа, подтверждающего изменения (с подписью руководителя и печатью организации).

{% cut "Заполнить форму на получение закрывающих документов и актов" %}

<iframe width="100%" frameborder="0" src="https://forms.yandex.com/surveys/10015610/?lang=ru&iframe=1&service=toloka-ai"></iframe>

{% endcut %}