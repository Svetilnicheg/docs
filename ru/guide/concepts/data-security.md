# Безопасность данных

Толока заботится о безопасности ваших данных и результатах разметки. В этом разделе описаны ключевые принципы работы с данными в Толоке.

Советуем также прочитать наши [рекомендации по защите данных в Толоке.](protect-your-data.md#protect-from-them)

## Ключевые принципы {#data-security-important_1}

- Права на результаты разметки принадлежат заказчику и никому больше.

- Данные, которые заказчик передает в Толоку, строго конфиденциальны. Доступ к этим данным есть у сотрудников службы поддержки. Список сотрудников с этим доступом регулярно пересматривается, а их деятельность контролируется нашими службами.

    {% note warning %}

    Если это необходимо, заказчик может дать другим пользователям [доступ](multiple-access.md#ul_pyj_v3k_xlb) к своему аккаунту, например сотрудникам своей компании.

    {% endnote %}

- Для исполнителей данные заказчика позиционируются как конфиденциальные — это прописано в [соглашении с исполнителем]({{ useragreement }}). Мы следим, чтобы в Толоке не было мошенников — недобросовестные исполнители получают предупреждение или бан.

## Персональные данные {#personal-data}

Передавая данные в Толоку вы автоматически даете согласие на обработку этих данных третьими лицами — исполнителями в Толоке.

Чтобы не передавать персональные данные, вы можете самостоятельно обезличить их. Например, замазать лица людей на фотографиях, а в записях речи поменять тональность голоса.

Для распознавания фотографий паспорта или анкеты можно предварительно вырезать заполненные поля и отправлять их в отдельных заданиях, например по отдельности отправить на распознавание фамилию, имя и отчество.

## Что дальше {#what-next}

- [Прочитайте рекомендации по защитите своих данных](protect-your-data.md#protect-from-them)

- [Узнайте, как размещать задания](first-project.md)

- Посмотрите документы, регулирующие порядок работы с Толокой

    - Для заказчика:

        - {% if locale == "ru-ru" %} [Соглашение для заказчиков, зарегистрированных на территории РФ]({{ customeragreement-probki }}) {% endif %}

        - [Соглашение для заказчиков, зарегистированных на территории США]({{ customeragreement-usa }})

        - [Соглашение для остальных заказчиков]({{ customeragreement }})

    - Для исполнителей:

        - [Пользовательское соглашение]({{ useragreement }})

        - [Лицензионное соглашение на использование программы «Толока» для мобильных устройств]({{ mobile-agreement }})

        - [Политика конфиденциальности]({{ confidential }})

## Решение проблем {#troubleshooting}

{% if locale == "ru-ru" %}

{% cut"Я владелец аккаунта. Хочу сделать владельцем другую учетную запись, чтобы пользователь мог подключить свой Яндекс Диск и самостоятельно управлять финансами." %}

Аккаунт заводится на адрес электронной почты, указанный при регистрации. Привязать аккаунт к другой учетной записи невозможно. Подключить Яндекс Диск другой учетной записи к действующему аккаунту заказчика также не получится.

Чтобы управлять финансами и взаимодействовать с внешними сервисами, нужно входить под логином и паролем, указанными при регистрации. Если эти данные вы не можете передать, то другому пользователю необходимо завести свой аккаунт.

{% endcut %}

{% endif %}

{% cut "Как перевести аккаунт с «Заказчика» на «Исполнителя»?" %}

Изменить тип аккаунта с «Заказчика» на «Исполнителя» невозможно.

Для выполнения заданий вам необходимо повторно зарегистрироваться в Толоке как исполнитель, но с другим логином.

Чтобы создать аккаунт исполнителя:

1. Выйдите из аккаунта заказчика.
1. Перейдите на главную страницу [Толоки]({{ toloka-index }}).
1. Нажмите кнопку **Присоединиться**.
1. Следуйте указаниям системы.

{% note info %}

Для создания новой учетной записи можно использовать тот же самый номер телефона. Пошаговое описание процесса регистрации вы можете найти на странице [Регистрация и вход]({{ user-documentation }}).

{% endnote %}

{% endcut %}

{% cut "Этот номер телефона принадлежит другому пользователю" %}

Если вы получили такое предупреждение, убедитесь, что вы правильно ввели номер.

Учтите, что на один номер телефона можно завести только 1 аккаунт заказчика (см. [Пользовательское соглашение]({{ useragreement }})).

Если в [Яндекс ID]({{ phones }}) привязан неверный номер, измените его. Подробнее о привязке номера см. [Справку Яндекс ID]({{ authorization-phone }}).

Если вы не помните ваш аккаунт в Толоке, воспользуйтесь [Восстановлением доступа]({{ restore }}).

Если вы удалили ваш аккаунт в Толоке, создайте новый Яндекс ID и зарегистрируйтесь в Толоке.

{% endcut %}

{% cut "Как поменять номер телефона в моем аккаунте?" %}

Чтобы поменять номер телефона, перейдите в [Яндекс ID]({{ phones }}) и измените основной номер.

{% note info %}

Если старый номер вам недоступен, замена номера займет месяц. Подробнее про изменение номера телефона см. [Справку Яндекс ID]({{ change-phone }}).

{% endnote %}

{% endcut %}

{% include [contact-support](../_includes/contact-support-initial-consultation.md) %}