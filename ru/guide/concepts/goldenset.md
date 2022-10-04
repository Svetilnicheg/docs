# Контрольные задания

[Контрольные задания](../../glossary.md#control-task-ru) содержат образцы правильных ответов. С их помощью вы получите информацию о качестве работы исполнителей, не проверяя весь объем результатов. Контрольные задания упростят проверку, определят квалификацию исполнителей и сэкономят ваше время.

{% note info %}

Чтобы сэкономить время, вы можете воспользоваться опцией разметки контрольных заданий [с помощью экспертов Толоки](task_markup.md#auto-markup). В этом случае разметка будет происходить в рамках одного пула.

{% endnote %}


## Когда использовать {#when-use}

Используйте контрольные задания, чтобы устанавливать исполнителю [навык](../../glossary.md#skill-ru) на основе его ответов и [блокировать](../../glossary.md#banned-worker-ru) доступ исполнителям, которые дают неправильные ответы.

#### Не используйте, если:

- много вариантов ответа;
- к ответу нужно прикрепить файл;
- требуется расшифровка текста;
- требуется выделение объектов на фото;
- присутствуют задания, в которых нет правильного или неправильного ответа. Например: «Какой образ вам больше нравится?» или «Выберите вариант дизайна страницы, который вам нравится больше».

## Как настроить {#rule-golden}

{% note warning %}

Поля {% if locale == "ru-ru" %}**Если**{% endif %}{% if locale == "en-com" %}**If**{% endif %} и {% if locale == "ru-ru" %}**то**{% endif %}{% if locale == "en-com" %}**then**{% endif %} в этом правиле — обязательные. Если не заполнить хотя бы одно, правило сохранить не получится.

{% endnote %}



Поле | Описание
----- | -----
{% if locale == "ru-ru" %}**Учитывать последних ответов на контрольные и обучающие задания**{% endif %}{% if locale == "en-com" %}**Recent control and training task responses to use**{% endif %} | Количество последних ответов исполнителя на контрольные задания.<br/><br/>Если поле не заполнено, в расчете учитываются ответы на все контрольные задания только того пула, к которому применяется правило.<br/><br/>Если поле заполнено, то правило считает ответы на контрольные задания в рамках значения, указанного в поле. При этом учитываются не только ответы из этого пула, но и из других пулов, где это поле заполнено.<br/><br/>Подробнее об этом параметре см. в разделе [Параметр «Помнить значений»](remember-values.md).
{% if locale == "ru-ru" %}**Если**{% endif %}{% if locale == "en-com" %}**If**{% endif %} | Условие, при котором выполняется действие в поле {% if locale == "ru-ru" %}**то**{% endif %}{% if locale == "en-com" %}**then**{% endif %}:<br/>- {% if locale == "ru-ru" %}**количество ответов**{% endif %}{% if locale == "en-com" %}**number of responses**{% endif %} — количество выполненных [обучающих](../../glossary.md#training-task-ru) и контрольных заданий;<br/>    <br/>- {% if locale == "ru-ru" %}**процент правильных ответов**{% endif %}{% if locale == "en-com" %}**correct responses (%)**{% endif %} — доля правильных ответов на контрольные и обучающие задания (от 0 до 100);<br/>    <br/>- {% if locale == "ru-ru" %}**процент неправильных ответов**{% endif %}{% if locale == "en-com" %}**incorrect responses (%)**{% endif %} — доля неправильных ответов на контрольные и обучающие задания (от 0 до 100);<br/>    <br/>- {% if locale == "ru-ru" %}**количество контрольных ответов**{% endif %}{% if locale == "en-com" %}**number of control responses**{% endif %} — количество выполненных контрольных заданий;<br/>- {% if locale == "ru-ru" %}**процент правильных контрольных ответов**{% endif %}{% if locale == "en-com" %}**correct control responses (%)**{% endif %} — доля правильных ответов на контрольные задания (от 0 до 100);<br/>- {% if locale == "ru-ru" %}**процент неправильных контрольных ответов**{% endif %}{% if locale == "en-com" %}**incorrect control responses (%)**{% endif %} — доля неправильных ответов на контрольные задания (от 0 до 100).<br/><br/>Чтобы добавить несколько условий, нажмите ![](../_images/add.svg).
{% if locale == "ru-ru" %}**то**{% endif %}{% if locale == "en-com" %}**then**{% endif %} | Действие, выполняемое при условии:<br/><br/>- {% if locale == "ru-ru" %}**установить значение навыка**{% endif %}{% if locale == "en-com" %}**assign skill value**{% endif %} — присвоить исполнителю фиксированное значение [навыка](nav.md).<br/>    <br/>- {% if locale == "ru-ru" %}**принять все ответы исполнителя в пуле**{% endif %}{% if locale == "en-com" %}**accept all assignments from this performer in the pool**{% endif %} — требует настройки [отложенной приемки](offline-accept.md).<br/>    <br/>    Пригодится, если исполнитель выполняет большинство заданий качественно. Пример: исполнитель выполнил больше 80% заданий правильно и вас устраивает такой результат. Правило сработает автоматически — все ответы в пуле будут приняты.<br/>    <br/>- {% if locale == "ru-ru" %}**заблокировать**{% endif %}{% if locale == "en-com" %}**ban**{% endif %} — закрыть доступ к проекту или всем проектам заказчика на указанное количество дней. Причина блокировки отображается только заказчику.<br/>    <br/>    Если доступ к заданиям блокируется на ограниченный срок (например, на 7 дней), после снятия блокировки история ответов исполнителя не сохраняется. Навык рассчитывается на основании новых ответов.<br/>    <br/>- {% if locale == "ru-ru" %}**приостановить**{% endif %}{% if locale == "en-com" %}**suspend**{% endif %} — приостановить доступ исполнителя к пулу на указанное количество дней. Причина отображается только заказчику.<br/>    <br/>- {% if locale == "ru-ru" %}**установить значение навыка из поля**{% endif %}{% if locale == "en-com" %}**assign skill from the field**{% endif %} — сохранить долю правильных ответов исполнителя на контрольные задания как значение навыка.


## Примеры правил {#examples}

**Задача**: отсеять исполнителей, которые часто ошибаются.

Варианты решения:

- [Заблокировать на основе контрольных заданий и доли правильных ответов](goldenset.md#qcr-control_example1)

- [Установить навык и запретить доступ к заданиям при его низком уровне](goldenset.md#nav)

- [Заблокировать при доле правильных ответов на контрольные задания меньше 40%](goldenset.md#qcr-control_example3)


{% include [ban-banned-user-answers-note](../_includes/concepts/ban/id-ban/banned-user-answers-note.md) %}


#### Заблокировать на основе контрольных заданий и доли правильных ответов

#### Правильная настройка

Оба правила работают независимо:

1. Если исполнитель дал не меньше 3 ответов на контрольные задания, то доля правильных ответов будет записана как значение навыка. Это будет полезно в том случае, если вы хотите запретить исполнителям с низким навыком выполнять ваши задания.
1. Если исполнитель дал не меньше 3 ответов на контрольные задания и доля правильных ответов меньше 60%, то он будет заблокирован на проекте.

В расчете используется не более 10 последних ответов исполнителя на контрольные задания в рамках проекта.

#### Неправильная настройка

Исполнитель будет заблокирован, когда даст первый неправильный ответ на первое, второе или третье контрольное задание. При этом навык не будет установлен. Поскольку причина блокировки не указана, будет невозможно выяснить, почему исполнитель заблокирован.

#### Альтернативная настройка

Все правила действуют независимо:
1. Если исполнитель дал не меньше 3 ответов на контрольные и обучающие задания, то доля правильных ответов будет записана как значение навыка.
1. Если исполнитель дал 2 неправильных ответа на 3 контрольных задания, то он будет заблокирован в пуле на 10 дней.
1. Если исполнитель дал 2 неправильных ответа на 4 контрольных задания, то он будет заблокирован в пуле на 10 дней.
1. Если исполнитель дал 5 или больше ответов на контрольные задания и доля правильных ответов меньше 80%, то он будет заблокирован в пуле на 10 дней.

Такой набор правил позволяет не блокировать исполнителей за один неправильный ответ и поддерживать высокую точность.

#### Установить навык и запретить доступ к заданиям при его низком уровне

Навык помогает определять, насколько хорошо исполнитель справляется с заданиями. Если у исполнителя низкий навык, ему можно запретить выполнять задания в вашем пуле или проекте.

#### Правильная настройка

Если исполнитель ответит на 3 контрольных или обучающих задания, ему будет установлен навык. Используйте значение навыка для доступа к другому пулу с помощью [фильтра](filters.md).

#### Пример установки фильтра
![](../_images/other/qcr-control_example_filter.png)

#### Неправильная настройка

Это правило никогда не начнет действовать, потому что количество учитываемых ответов ({% if locale == "ru-ru" %}**Учитывать последних ответов на контрольные и обучающие задания**{% endif %}{% if locale == "en-com" %}**Recent control and training task responses to use**{% endif %}) меньше числа ответов в правиле ({% if locale == "ru-ru" %}**количество контрольных ответов**{% endif %}{% if locale == "en-com" %}**number of control responses**{% endif %}).

#### Заблокировать при доле правильных ответов на контрольные задания меньше 40%

#### Правильная настройка

Если доля правильных ответов на контрольные задания меньше 40%, то исполнитель будет заблокирован на проекте на 30 дней.

Это правило не учитывает ответы на обучающие задания для блокировки.

#### Неправильная настройка

Если доля правильных ответов на контрольные задания меньше 40%, то исполнитель будет заблокирован на проекте на 30 дней. Правило cработает один раз — сразу после пятого ответа на контрольное задание.


## Решение проблем {#troubleshooting}

#### Сколько контрольных заданий нужно добавлять?

Рекомендуем добавлять не менее 1% контрольных заданий в пул. А для маленьких пулов — 5–10%.

#### Почему так

Все контрольные задания показываются исполнителю только один раз. Если вы используете умное смешивание, то определяете, сколько контрольных заданий должно быть на каждой странице. Если на странице одно контрольное задание, то максимальное число страниц, которое может выполнить исполнитель, равно количеству контрольных заданий в пуле. Если вы увеличиваете количество контрольных заданий на странице, во столько же раз снижается число доступных исполнителю страниц.

Доступных страниц не должно быть слишком мало. Иначе:

- правильно оценить качество его ответов не получится;
- исполнитель не будет заинтересован выполнять такие задания, так как потратит много времени на изучение инструкций, а получит мало заработка.

#### Пример

#### Большой пул 1% контрольных заданий (хорошо)

В пуле 10 000 заданий, из них 100 контрольных (1%). На одной странице 10 заданий, из них 1 контрольное. Следовательно, один исполнитель может сделать до 100 страниц.

#### Маленький пул 1% контрольных заданий (плохо)

В пуле 100 заданий, из них 1 контрольное (1%). На одной странице 10 заданий, из них 1 контрольное. Следовательно, один исполнитель может сделать только 1 страницу.

#### Маленький пул 10% контрольных заданий (хорошо)

В пуле 100 заданий, из них 10 контрольных (10%). На одной странице 10 заданий, из них 1 контрольное. Следовательно, один исполнитель может сделать до 10 страниц.

Если в открытом пуле мало контрольных заданий, [добавьте новые контрольные задания](#add-gs).

#### Зачем

Если пул большой, а контрольных заданий мало, может сложиться ситуация, что активным исполнителям, которые сделали много заданий в проекте, перестают показываться новые страницы с заданиями. Это происходит, когда исполнитель выполнил все контрольные задания в пуле.

{% note info %}

Чтобы отсеивать исполнителей, используйте блок контроля качества [Контрольные задания](control.md). Чтобы ранжировать исполнителей по качеству ответов на контрольные задания, используйте [навык](nav.md).

{% endnote %}


#### Как засчитываются правильные ответы на контрольные вопросы?

Правило контрольных заданий начинает действовать после того, как исполнитель дал ответы на заданное число контрольных заданий. Если у вас в пуле есть и [обучающие](../../glossary.md#training-task-ru), и контрольные задания, то вы можете установить учитывать ответы на те и другие (параметр **Количество ответов**) или только на контрольные (параметр **Количество контрольных ответов**).

Как только нужное количество ответов набрано, Толока подсчитывает процент правильных и неправильных ответов и выполняет действие (назначить навык, заблокировать в пуле или на проекте). Далее этот процент обновляется по мере выполнения заданий исполнителем. Количество последних ответов исполнителя, которое учитывается в расчете, задается в поле **Учитывать последних ответов на контрольные и обучающие задания**. Если оставить его пустым, будут учитываются все ответы исполнителя в пуле.

#### Нужно ли создавать навык для каждого пула?

Лучше использовать один [навык](../../glossary.md#skill-ru) в проекте. Можно выбрать способ подсчета навыка:

- Подсчет навыка для каждого пула отдельно. Текущее значение навыка — это значение навыка в пуле, который выполнялся последним. Такой вариант удобен, если:

    - Пулы предназначены для разных групп исполнителей (например, настроены фильтры по городам, странам).

    - Пулы запускаются последовательно, и вы не хотите учитывать качество ответов в предыдущих пулах при подсчете навыка в выполняемом пуле.

    Этот способ подсчета действует по умолчанию при добавлении блока контроля качества в пул. Для блока по контрольным заданиям оставьте пустым поле **Учитывать последних ответов на контрольные и обучающие задания**.

- Подсчет навыка по всем выполненным заданиям в проекте. Такой вариант удобен, если пулы небольшие и вам не нужно рассчитывать навык для каждого пула.

    Этот способ подсчета доступен только для навыков по контрольным заданиям. Чтобы использовать его, заполните поле **Учитывать последних ответов на контрольные и обучающие задания** в блоках контроля качества в пулах.


#### Можно ли использовать навык не только в пуле или в одном проекте, но и в разных проектах?

Да, конечно, один и тот же навык можно назначать и использовать на различных проектах. Но чаще всего один навык используется в рамках одного проекта. Если исполнитель хорошо выполняет одно задание, это не значит, что он так же успешно справится с другим. Кроме того, используя фильтры по давно настроенным навыкам, вы ограничиваете количество доступных исполнителей.

#### Как перенести разметку контрольных заданий из Песочницы в основной пул?

Сами задания не переносятся, только конфигурация проекта и настройки выбранного пула. Вы можете скачать размеченные задания из пула в Песочнице и загрузить их в экспортированный пул.

Чтобы скачать только контрольные задания (если вы размечали в интерфейсе), зайдите в **Разметчик**, затем на вкладку **Контрольные задания** и нажмите **Скачать**.

#### Если недобросовестный исполнитель дает много неправильных ответов, а спустя время система его блокирует за ошибки в контрольных заданиях, деньги за уже данные ответы все равно снимаются?

Если исполнителю уже начислены деньги за задания, то обратно их не вернуть.

#### Так и задумано, что при экспорте проекта из Песочницы файлы с заданиями не переносятся? Я неожиданно потерял разметку контрольных заданий, которые сделал в песочнице.

Сами задания не переносятся, только конфигурация проекта и настройки выбранного пула. Но вы можете скачать размеченные задания из пула в **Песочнице** и загрузить их в созданный пул. Чтобы скачать только контрольные задания (если вы размечали их в интерфейсе), зайдите в **Разметчик**, затем во вкладку **Контрольные задания** и нажмите **Скачать**.

#### Если мы загружаем задания через Умное смешивание, то в одном файле должны быть и контрольные, и обычные задания, или мы можем загрузить их отдельно?

Умное смешивание задается при загрузке заданий в пул. После создания пула нажмите **Загрузить** и выбираете соответствующий способ формирования страниц с заданиями. При этом вы можете загрузить их отдельными файлами, либо одним файлом, расположив в любом порядке.

{% include [contact-support](../_includes/contact-support-help.md) %}