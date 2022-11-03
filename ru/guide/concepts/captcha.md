# Капча

Капча и правило [быстрые ответы](quick-answers.md) обеспечивают высокий уровень защиты от роботов.

Чтобы показывать капчу исполнителям, установите {% if locale == "ru-ru" %}[частоту показа капчи](pool_poolparams.md#captcha){% endif %}{% if locale == "en-com" %}[captcha frequency](pool_poolparams.md#captcha){% endif %} в настройках [пула](../../glossary.md#pool).

Обычно капчу показывают один раз на 10 страниц с заданиями. Если задания выполняются быстро и капча мешает исполнителям, ее можно показывать через каждые 20 страниц.

## Когда использовать {#when-use}

Ограничьте доступ к заданиям исполнителям, которые неправильно вводят капчу несколько раз подряд. Такая настройка необходима, если вы хотите обеспечить дополнительную защиту от роботов.

#### Не используйте, если:

- в пулах мало заданий. Например, если задание — опрос на одну страницу, то капча не поможет контролировать качество, так как минимальная частота показа капчи — каждые 10 страниц заданий;

- сложно или невозможно автоматизировать работу: выделение областей, полевые задания, везде, где надо прикрепить файлы, писать осмысленные тексты.

## Как настроить {#rule}

{% include [goldenset-obligatory](../_includes/concepts/goldenset/id-goldenset/obligatory.md) %}

#|
||**Поле**|**Описание**||
||{% if locale == "ru-ru" %}**Учитывать последних вводов капчи**{% elsif locale == "en-com" %}**Recent captchas to use**{% endif %} | Количество последних раз, когда исполнителю была предложена капча.

Если поле не заполнено, в расчете учитываются все вводы капчи только того пула, к которому применяется правило.

Если поле заполнено, то правило считает вводы капчи в рамках значения, указанного в поле. При этом учитываются не только вводы капчи из этого пула, но и из других пулов, где это поле заполнено.

[Подробнее](remember-values.md) о том, как работает это поле.||
||{% if locale == "ru-ru" %}**Если**{% elsif locale == "en-com" %}**If**{% endif %} | Условие, при котором выполняется действие в поле {% if locale == "ru-ru" %}**то**{% elsif locale == "en-com" %}**then**{% endif %}:

- {% if locale == "ru-ru" %}**количество ответов**{% elsif locale == "en-com" %}**number of responses**{% endif %} — количество вводов капчи (меньше или равно количеству в поле {% if locale == "ru-ru" %}**Учитывать последних вводов капчи**{% elsif locale == "en-com" %}**Recent values to use**{% endif %}).

- {% if locale == "ru-ru" %}**процент правильных ответов**{% elsif locale == "en-com" %}**correct responses (%)**{% endif %} — доля правильных ответов (от 0 до 100).

- {% if locale == "ru-ru" %}**процент неправильных ответов**{% elsif locale == "en-com" %}**incorrect responses (%)**{% endif %} — доля неправильных ответов (от 0 до 100).

Чтобы добавить несколько условий, нажмите ![](../_images/add.svg).||
||{% if locale == "ru-ru" %}**то**{% elsif locale == "en-com" %}**then**{% endif %} | Действие, выполняемое при условии:

- {% if locale == "ru-ru" %}**заблокировать**{% elsif locale == "en-com" %}**ban**{% endif %} — закрыть доступ к проекту или всем проектам заказчика на указанное количество дней. Причина блокировки отображается только заказчику.

    Если доступ к заданиям блокируется на ограниченный срок (например, на 7 дней), после снятия блокировки история ответов исполнителя не сохраняется. Навык рассчитывается на основании новых ответов.

- {% if locale == "ru-ru" %}**установить значение навыка из поля**{% elsif locale == "en-com" %}**assign skill from the field**{% endif %} — сохранить долю правильных ответов исполнителя на контрольные задания как значение навыка.

- {% if locale == "ru-ru" %}**приостановить**{% elsif locale == "en-com" %}**suspend**{% endif %} — приостановить доступ исполнителя к пулу на указанное количество дней. Причина отображается только заказчику.

- {% if locale == "ru-ru" %}**принять все ответы исполнителя в пуле**{% elsif locale == "en-com" %}**accept all assignments from this performer in the pool**{% endif %} — требует настройки [отложенной приемки](offline-accept.md).

    Пригодится, если исполнитель выполняет большинство заданий качественно. Пример: исполнитель выполнил больше 80% заданий правильно и вас устраивает такой результат. Правило сработает автоматически — все ответы в пуле будут приняты.

- {% if locale == "ru-ru" %}**установить значение навыка**{% elsif locale == "en-com" %}**assign skill value**{% endif %} — присвоить исполнителю фиксированное значение [навыка](nav.md).||
|#

## Пример правила {#examples}

Поскольку человек тоже может ошибиться при вводе капчи, целесообразно добавлять поле **количество ответов** и указывать цифру большую, чем 1. В противном случае исполнитель может быть заблокирован после первого ввода капчи.

{% include [ban-banned-user-answers-note](../_includes/concepts/ban/id-ban/banned-user-answers-note.md) %}

#### Блокировка за неправильные ответы на капчу

{% list tabs %}

- Правильная настройка

  ![](../_images/control-rules/captcha/qcr-captcha_example1.png)

  Если исполнитель ввел капчу не меньше 5 раз и доля правильных ответов меньше 65%, он будет заблокирован и не сможет выполнять ваши задания 10 дней.

- Неправильная настройка

  ![](../_images/control-rules/captcha/qcr-captcha_example-1.png)

  Исполнитель будет заблокирован после первого ввода капчи.

{% endlist %}

## Решение проблем {#troubleshooting}

{% cut "Нужно ли создавать навык для каждого пула?" %}

Лучше использовать один [навык](../../glossary.md#skill) в проекте. Можно выбрать способ подсчета навыка:

- Подсчет навыка для каждого пула отдельно. Текущее значение навыка — это значение навыка в пуле, который выполнялся последним. Такой вариант удобен, если:

    - Пулы предназначены для разных групп исполнителей (например, настроены фильтры по городам, странам).

    - Пулы запускаются последовательно, и вы не хотите учитывать качество ответов в предыдущих пулах при подсчете навыка в выполняемом пуле.

    Этот способ подсчета действует по умолчанию при добавлении блока контроля качества в пул. Для блока по контрольным заданиям оставьте пустым поле **Учитывать последних ответов на контрольные и обучающие задания**.

- Подсчет навыка по всем выполненным заданиям в проекте. Такой вариант удобен, если пулы небольшие и вам не нужно рассчитывать навык для каждого пула.

    Этот способ подсчета доступен только для навыков по контрольным заданиям. Чтобы использовать его, заполните поле **Учитывать последних ответов на контрольные и обучающие задания** в блоках контроля качества в пулах.

{% endcut %}

{% cut "Можно ли использовать навык не только в пуле или в одном проекте, но и в разных проектах?" %}

Да, конечно, один и тот же навык можно назначать и использовать на различных проектах. Но чаще всего один навык используется в рамках одного проекта. Если исполнитель хорошо выполняет одно задание, это не значит, что он так же успешно справится с другим. Кроме того, используя фильтры по давно настроенным навыкам, вы ограничиваете количество доступных исполнителей.

{% endcut %}

{% cut "Я настроил правило отправления в бан при первой же неправильно введенной капче, чтобы максимально исключить ботов. Такое правило не слишком строгое? Как бывает на практике?" %}

Действительно, такое правило выглядит слишком строго. Даже самый внимательный исполнитель может ошибиться — правило лучше сделать менее строгим. Помимо блокировки у отдельных заказчиков, у нас есть системные процессы, которые блокируют в Толоке исполнителей, которые систематически проваливают проверку капчей.

{% endcut %}

{% cut "Частоту выдачи капчи работникам можно как-то регулировать? Некоторых работников это несколько демотивирует." %}

Частота показа [капчи](captcha.md) настраивается в пуле.

Нет

: Не показывать капчу.

Низкая

: Показывать капчу каждые 20 страниц заданий.

Средняя / Высокая

: Показывать капчу каждые 10 страниц заданий.

{% endcut %}

{% cut "Есть ли какое-то подробное описание, как лучше использовать капчу: для какого типа проектов ее лучше использовать и насколько интенсивно?" %}

[Капча](captcha.md) используется обычно в простых проектах с автоприемкой: классификация, категоризация, поиск информации; то есть там, где мало вариантов ответов, не нужно загружать файлы или писать тексты. Она позволяет отсеивать ботов и исполнителей, которые размечают очень небрежно.

Частота показа капчи настраивается в пуле.

Нет

: Не показывать капчу.

Низкая

: Показывать капчу каждые 20 страниц заданий.

Средняя / Высокая

: Показывать капчу каждые 10 страниц заданий.

{% endcut %}

{% cut "В справке есть понятия для капчи: «Доля правильных ответов» и «Доля неправильных ответов» — они определяются из контрольной выборки?" %}

Процент правильных ответов определяется исходя из общего количества обработанных исполнителем капч в пределах «окна», указанного в поле **Учитывать последних ответов на контрольные и обучающие задания**. Если значение в поле не указано, то в расчет попадают все капчи, которые появляются при выполнении заданий пула, использующего данное правило.

{% endcut %}

{% include [contact-support](../_includes/contact-support-help.md) %}