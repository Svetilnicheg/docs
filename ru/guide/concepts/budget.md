# Управление личным счетом заказчика

Чтобы отправить задания на выполнение, нужно иметь средства на счете в Толоке. {% if locale == "ru-ru" %}Подробнее см. Пополнение счета [для резидентов России](refill-russia.md) и [для нерезидентов](refill.md).{% endif %}{% if locale == "en-com" %}Подробнее см. [Пополнение счета](refill.md).{% endif %}

Все расчеты между заказчиками и исполнителями ведутся в долларах США. Остаток на счете отображается в главном меню:
![](../_images/other/balance-ru.png)
- Зеленым — остаток на счете.

- Серым  — деньги, зарезервированные на задания на [отложенной приемке](../../glossary.md#left-off-acceptance-ru).


Деньги со счета расходуются на следующие статьи:

- [Плата за задания](#task-payment)

- [Комиссия](#comission)

- [Бонусы исполнителям](bonus.md)


[Отслеживать затраты](#track-budget) можно в своем профиле. Вы также можете скачать отчет о заданиях в PDF-файле. Чтобы контролировать наличие средств на счете, [настройте уведомления](#money-notification).


## Плата за задания {#task-payment}

Стоимость задания устанавливается заказчиком в настройках [пула](../../glossary.md#pool-ru). Деньги списываются со счета по мере выполнения заданий. Если вы используете [отложенную приемку](accept.md), деньги за [выполненные задания](../../glossary.md#submitted-answers-ru) сначала резервируются, а затем списываются.


## Комиссия {#comission}

За использование Толоки с заказчика взимается комиссия — процент от стоимости заданий, включая начисленные [бонусы](bonus.md). Она составляет 30%, но не менее 0,005 $.

Размер комиссии (по проектам) можно увидеть в вашем [профиле]({{ profile }}), (вкладка {% if locale == "ru-ru" %}**Затраты**{% endif %}{% if locale == "en-com" %}**Expences**{% endif %}). Общая сумма комиссии за задания пула доступна на странице пула (поля {% if locale == "ru-ru" %}**Израсходовано денег (+ комиссия)**{% endif %}{% if locale == "en-com" %}**Budget spent (+ markup)**{% endif %} и {% if locale == "ru-ru" %}**Приблизительный бюджет (+ комиссия)**{% endif %}{% if locale == "en-com" %}**Approximate budget (+ markup)**{% endif %}).


## Затраты в профиле заказчика {#track-budget}

Чтобы увидеть данные о расходах в вашем {% if locale == "ru-ru" %}[профиле]({{ profile }}){% endif %}, перейдите на вкладку {% if locale == "ru-ru" %}**Затраты**{% endif %}{% if locale == "en-com" %}**Expences**{% endif %}. Суммы сгруппированы по дате, [проекту](../../glossary.md#project-ru) и пулу:

- {% if locale == "ru-ru" %}**Сумма**{% endif %}{% if locale == "en-com" %}**Sum**{% endif %}: черным — потраченные деньги, серым — деньги, зарезервированные на задания на отложенной приемке.

- {% if locale == "ru-ru" %}**Комиссия**{% endif %}{% if locale == "en-com" %}**Markup**{% endif %}: плата за использование Толоки.


Вы можете настроить уведомления на почту и получать сообщения, если на вашем счете осталось менее 5 долларов.


## Отчет о заданиях {#stat-report}

Чтобы получить отчет о заданиях заказчика{% if locale == "en-com" %}Statistics on Requestor's tasks{% endif %} с данными о расходах:

1. Выберите период в [профиле заказчика]({{ profile }}) (вкладка {% if locale == "ru-ru" %}**Затраты**{% endif %}{% if locale == "en-com" %}**Expences**{% endif %}).

1. Нажмите кнопку {% if locale == "ru-ru" %}**Сформировать отчет (pdf)**{% endif %}{% if locale == "en-com" %}**Generate report (pdf)**{% endif %} и загрузите PDF-файл.

    Отчет содержит данные о расходах на каждый проект (включая комиссию) и выплаченных [бонусах](../../glossary.md#bonus-ru) (строка {% if locale == "ru-ru" %}**Вознаграждение**{% endif %}{% if locale == "en-com" %}**Reward**{% endif %}).



## Уведомления о состоянии счета {#money-notification}

Чтобы получать уведомления, когда на вашем счете остается менее 5 долларов, нажмите ссылку {% if locale == "ru-ru" %}**Редактировать**{% endif %}{% if locale == "en-com" %}**Edit**{% endif %} в [профиле заказчика]({{ profile }}). Выберите опции:

- {% if locale == "ru-ru" %}**Включить уведомления**{% endif %}{% if locale == "en-com" %}**Enable notifications**{% endif %};

- {% if locale == "ru-ru" %}**Дублировать уведомления по электронной почте**{% endif %}{% if locale == "en-com" %}**Send copies of notifications by email**{% endif %} — если вы хотите получать сообщения на электронную почту.



## Головной и дочерние аккаунты {#parent-child-accounts}

Заказчики, заключившие договор в бумажном виде, могут создавать головной и дочерние аккаунты.

#### Ограничения:

- головными и дочерними могут быть только аккаунты, в которых еще не создавались проекты;
- для головных и дочерних аккаунтов рекомендуется постоплатный тип договора.

#### Особенности:

- общие [навыки](../../glossary.md#skill-ru);
- каждый дочерний аккаунт — отдельный личный кабинет со своим логином и паролем;
- нет возможности сделать дочерний аккаунт головным;
- платежные операции доступны только для головного аккаунта, с его счета деньги распределяются по дочерним;
- финансовые отчеты и закрывающие документы выставляются на реквизиты головного аккаунта и не детализируются по дочерним.

Если вы хотите создать головной и дочерние аккаунты, [напишите в службу поддержки](../troubleshooting/support.md#new).


## Решение проблем {#troubleshooting}

#### Как подключиться к биллингу из Москвы или Санкт-Петербурга?

Если ваш адрес в самом Санкт-Петербурге, введите Санкт-Петербург в поле **Регион**, затем введите улицу, номер дома и индекс. Остальные поля заполнять не нужно.

Если ваш адрес в самой Москве, введите Москва в поле **Регион**, затем введите улицу, номер дома и индекс. [Подробнее](refill-russia.md#step-by-step) о подключении к биллингу.

Если всё равно не получается [напишите](../troubleshooting/troubleshooting.md) полный адрес с индексом, который вы пытаетесь ввести, по форме обратной связи. Подскажем, как правильно заполнить поля.

#### При пополнении счета вижу сумму, в 1000 раз большую, чем планировал — почему?

Это нормально. Например, если вы вводили 25 $, а видите 25,000 — это все еще 25 долларов с десятичной запятой. На счет вы получите 25 $ по актуальному курсу. Сумма в рублях появится, когда вы перейдете к оплате.

#### Почему мы пополняем счет не в российской валюте?

Толока — международная платформа для исполнителей из разных стран. Ее предоставляет швейцарская компания Yandex Services AG.

#### Почему мы платим НДС 20% в счете?

Согласно налоговому законодательству РФ мы внесли п.3.8. в [Соглашение с заказчиком]({{ customeragreement-probki }}) — НДС начисляется дополнительно к стоимости услуг и включается в счет на оплату. Так же мы все платим НДС в любом магазине. На свой счет в Толоке вы получите сумму, которую указывали при пополнении.

#### Сколько времени занимает оплата счета?

Если вы оплачиваете банковской картой, средства обычно поступают на ваш счет в Толоке в течение нескольких минут. Если ваши средства не отображаются в счете, [напишите нам](../troubleshooting/support.md#help) — разберемся. Укажите логин заказчика и номер счета, а также отметьте тему **Пополнение счета**.

#### Как узнать курс, по которому происходит валютный обмен при пополнении счета в Толоке?

Вы указываете сумму пополнения в долларах США. В **Балансе** она переводится в рубли с учетом НДС. Конверсия производится по курсу ЦБ РФ на момент выставления счета по всемирному времени (UTC). [Подробнее](refill-russia.md) о пополнении счета.

#### Как добавить деньги в Толоку?

Пополнить счет в Толоке можно с банковской карты или банковским переводом. На странице [Профиль]({{ profile }}) нажмите на кнопку Подключиться к биллингу, заполните форму, появится кнопка Пополнить счет. [Подробнее](refill-russia.md#step-by-step) по шагам.

[Получить закрывающие документы и акты](../troubleshooting/support.md#feedback_g3b_vj3_qjb)

[Вернуть средства, перечисленные на счет в Толоку](../troubleshooting/support.md#feedback_khw_wc3_qjb)

{% include [contact-support](../_includes/contact-support-help.md) %}