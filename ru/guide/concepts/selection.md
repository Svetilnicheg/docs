# Распознавание объектов и выделение областей

{% note info %}

Сначала запустите проект в [Песочнице]({{ sandbox }}). Так вы сможете избежать ошибок и потраченных средств, если окажется, что ваше задание не работает.

{% endnote %}


Для выделения области на картинках в Толоке есть специальный редактор. С его помощью исполнитель сможет выделить область в виде многоугольника или прямоугольника.

Предположим, у вас есть много фотографий с животными и вам нужно выделить собак и определить их породу. Для этого создадим задание: исполнитель видит фотографию, он должен выделить на ней собаку и указать ее породу.

#### Пример готового задания
![](../_images/tutorials/selection/dog_example.png)

Чтобы запустить задания и получить ответы:

1. [Создайте проект](#project)
1. [Добавьте пул заданий](#pool)
1. [Загрузите задания](#tasks_upload)
1. [Настройте контроль качества](#quality_control)
1. [Запустите пул и получите результаты](#launch)

## Создайте проект {#project}

{% include [toloka-requester-source-project-def](../_includes/toloka-requester-source/id-toloka-requester-source/project-def.md) %}


#### В интерфейсе:

1. Выберите шаблон:

    1. Нажмите кнопку **+ Создать проект**.

    1. Выберите шаблон **Выделение областей на изображении**.

1. Заполните общую информацию:

    1. Дайте проекту понятное название и краткое описание. Их увидят исполнители в списке доступных заданий.

    1. По желанию добавьте **Приватный комментарий**.

    1. Нажмите **Сохранить**.

1. Отредактируйте интерфейс задания:

    {% note info %}

    В этом туториале показано, как создать интерфейс задания в редакторе HTML/JS/CSS. Вы также можете попробовать создать интерфейс задания в [Конструкторе шаблонов]({{ tb-quickstart }}).

    {% endnote %}

    1. Определите, какие объекты будете передавать исполнителю и получать от него в ответ. Для этого необходимо создать поля входных и выходных данных в блоке **Спецификация данных**.

    #### Что такое входные и выходные данные?

    {% include [toloka-requester-source-input-data](../_includes/toloka-requester-source/id-toloka-requester-source/input-data.md) %}

    {% include [toloka-requester-source-output-data](../_includes/toloka-requester-source/id-toloka-requester-source/output-data.md) %}

    Подробнее о [полях входных и выходных данных](incoming.md).

    Шаблон включает в себя поля:

    - Поле входных данных — ссылка `image` для загрузки картинки.
    Измените тип данных на строку, чтобы использовать ссылки на свои файлы{% if locale == "ru-ru" %} или [загружать картинки](prepare-data.md), хранящиеся на Яндекс Диске{% endif %}.

    - Поле выходных данных — поле `result` с типом json, в которое будет записан объект JSON c координатами точек.

    Добавьте поле выходных данных — обязательная строка `breed`, в которую будет записана порода собаки, указанная исполнителем.

    #### Графический режим
    ![](../_images/tutorials/selection/data_specification.png)
    #### JSON
    ![](../_images/tutorials/selection/data_specification_json.png)

    Создайте интерфейс задания в блоке **HTML**. Он описывает, как будут расположены элементы задания.

    В HTML-интерфейсе можно использовать стандартные теги HTML и [специальные выражения](spec.md) в двойных фигурных скобках для полей входных и выходных данных.
    {% if locale == "ru-ru" %}
    ```
    {{field type="image-annotation"name="result" src=(proxyimage)}}
    {{field type="input"name="breed" placeholder="Укажите породу собаки" width="100%"}}
    ```
    {% endif %}{% if locale == "en-com" %}
    ```
    {{field type="image-annotation"name="result" src=(proxyimage)}}
    {{field type="input"name="breed" placeholder="Enter the dog's breed" width="100%"}}
    ```
    {% endif %}
    Эта запись означает, что задание будет выглядеть так:

    - картинка с инструментом для выделения области;
    - поле для ввода текста.

    Блоки CSS и JavaScript оставьте без изменений.

    1. Нажмите кнопку ![](../_images/tutorials/image-segmentation/preview-button.png) {% if locale == "ru-ru" %}**Предпросмотр задания**{% endif %}{% if locale == "en-com" %}**Preview task**{% endif %}, чтобы увидеть получившееся задание.

    {% note info %}

    В предварительном просмотре проекта отображается одно задание со стандартными данными. Количество заданий на странице вы сможете настроить далее.

    {% endnote %}

    1. {% include [toloka-requester-source-save](../_includes/toloka-requester-source/id-toloka-requester-source/save.md) %}

1. Напишите инструкцию для исполнителей:

    1. Напишите краткую и ясную инструкцию (см. [советы](faq.md)). Опишите в ней, что надо сделать, и приведите примеры.

    Вы можете подготовить инструкцию в формате HTML и вставить её в редактор. Чтобы переключиться в режим HTML, нажмите **<>**.

    1. Нажмите кнопку **Завершить**.

## Добавьте пул заданий {#pool}

Пул — это набор оплачиваемых заданий, которые одновременно выдаются исполнителям.

1. Откройте проект и нажмите **Добавить пул**.
1. Дайте пулу любое удобное название — оно доступно только вам, исполнитель увидит название проекта.
1. В блоке {% if locale == "ru-ru" %}**Аудитория**{% endif %}{% if locale == "en-com" %}**Audience**{% endif %} добавьте {% if locale == "ru-ru" %}**Фильтры**{% endif %}{% if locale == "en-com" %}**Filters**{% endif %} для отбора исполнителей. {% if locale == "ru-ru" %}Чтобы ваше задание было доступно только исполнителям, владеющим русским языком, установите фильтры **Регион по номеру телефона** и **Языки**: выберите исполнителей из России, Украины, Казахстана и Беларуси, которые в своем профиле отметили знание русского языка.{% endif %}

    {% include [toloka-requester-source-filter-client-about](../_includes/toloka-requester-source/id-toloka-requester-source/filter-client-about.md) %}

1. В блоке **Цена** установите цену за [страницу заданий](../../glossary.md#task-page-ru), например, `0.02`.
    #### Что такое страница заданий?

    На одной странице может отображаться одно или несколько заданий. Если задания простые, то можно добавлять 10–20 заданий на одну страницу. Не рекомендуем создавать длинные страницы, поскольку это снизит скорость загрузки данных у исполнителя.

    Исполнитель получит оплату, только если выполнил все задания на странице.

    Количество заданий на странице вы определите при [загрузке заданий](#smart-mixing).

    #### Как определить справедливую цену?

    Общее правило формирования цены — чем больше времени исполнитель тратит на выполнение, тем выше цена.

    Вы можете зарегистрироваться в Толоке как исполнитель и узнать, сколько платят другие заказчики за задания.

1. В блоке {% if locale == "ru-ru" %}**Контроль качества**{% endif %}{% if locale == "en-com" %}**Quality control**{% endif %} установите {% if locale == "ru-ru" %}**Перекрытие задания**{% endif %}{% if locale == "en-com" %}**Task overlap**{% endif %} — количество исполнителей, которые должны выполнить задание. Для заданий выделения области на картинках, как правило, 1.
1. Включите опцию **Отложенная приемка** и укажите количество дней на проверку для параметра **Срок проверки**. Например, 7.
    #### Что такое отложенная приемка?

    [Отложенная приемка](offline-accept.md) позволяет вам просматривать [выполненные страницы заданий](../../glossary.md#submitted-answers-ru) перед тем, как принять их и заплатить исполнителю. Задания, выполненные в несоответствии с инструкцией, можно отклонять. Максимальный срок проверки устанавливается в поле **Срок проверки**.

1. В блоке {% if locale == "ru-ru" %}**Дополнительные настройки**{% endif %}{% if locale == "en-com" %}**Additional settings**{% endif %} укажите {% if locale == "ru-ru" %}**Время на страницу заданий**{% endif %}{% if locale == "en-com" %}**Time per task suite**{% endif %}. Его должно быть достаточно, в том числе для чтения инструкции и загрузки задания. Например, 1200 секунд.
1. Нажмите кнопку {% if locale == "ru-ru" %}**Создать пул**{% endif %}{% if locale == "en-com" %}**Create a pool**{% endif %}.

## Загрузите задания {#tasks_upload}

{% include [toloka-requester-source-tsv-file](../_includes/toloka-requester-source/id-toloka-requester-source/tsv-file.md) %}


1. Нажмите кнопку {% if locale == "ru-ru" %}**Загрузить**{% endif %}{% if locale == "en-com" %}**Upload**{% endif %}. В открывшемся окне вы можете скачать шаблон файла.
    #### Использовать пример данных

    Если вы хотите посмотреть, как ваш проект будет выглядеть после запуска, но у вас еще нет заданий для разметки, вы можете загрузить в пул готовый пример данных.

    Нажмите {% if locale == "ru-ru" %}**Использовать пример данных**{% endif %}{% if locale == "en-com" %}**Use sample data**{% endif %} справа от надписи {% if locale == "ru-ru" %}**Прикрепите подготовленный файл с данными**{% endif %}{% if locale == "en-com" %}**Attach the prepared file with data**{% endif %}. Это позволит избежать дополнительных действий с файлами.

    После того, как вы поработали с примером данных и вас все устроило, подготовьте свои данные и загрузите их в пул.

1. Добавьте в файл входные данные. Заголовок столбца с входными данными содержит слово `INPUT`. Остальные столбцы оставьте пустыми.
    ![](../_images/tutorials/selection/dogs_tsv_text.png)

1. Загрузите задания, выбрав {% if locale == "ru-ru" %}**Указать вручную**{% endif %}{% if locale == "en-com" %}**Set manually**{% endif %} и установив, например, 4 задания на странице.

## Настройте контроль качества {#quality_control}

[Блоки контроля качества](control.md) позволяют отсеивать невнимательных исполнителей. Контроль качества можно настраивать как в проекте, так и в пуле.

{% note warning %}

Настройки контроля качества в проекте будут действовать во всех пулах проекта, и изменить их настройку в одном из пулов будет невозможно.

{% endnote %}


1. {% include [control_how-setQC](../_includes/concepts/control/id-control_how/setQC.md) %}

1. Добавьте блок **Быстрые ответы**.

    Значение параметра **Минимальное время на страницу** зависит от количества заданий на этой странице. Чтобы определить настроение кота, достаточно 2-4 секунды. Значит, на страницу с 10-ю заданиями может хватить 20-30 секунд.

    Один раз можно ошибиться неумышленно, а вот после 2-3 закономерных раз можно и заблокировать исполнителя на какое-то время.

    Укажите следующие значения:

    {% include [ban-banned-user-answers-note](../_includes/concepts/ban/id-ban/banned-user-answers-note.md) %}

1. Добавьте правило контроля качества {% if locale == "ru-ru" %}**Результаты проверки**{% endif %}{% if locale == "en-com" %}**Review results**{% endif %} и укажите следующие значения:

## Запустите пул и получите результаты {#launch}

1. Запустите пул, нажав кнопку ![](../_images/other/b-start-pool.png).
1. Следите за выполнением в блоке **Статистика пула**.
1. Как только получены первые результаты, вы можете начинать [проверку](accept.md). По истечении установленного срока все ответы будут автоматически приняты вне зависимости от их качества.
    Чтобы проверить задания, откройте пул и нажмите **Проверить задания**.
    {% note info %}

    Координаты точек будут записаны в [формате JSON](t-components/image-annotation.md#coordinates).

    {% endnote %}


## Что дальше {#what-next}

- Пройдите аналогичный [туториал с декомпозицией](image-segmentation-overview.md) задания на 3 разных проекта.
- Почитайте подробнее [про декомпозицию заданий](solution-architecture.md).


## Решение проблем {#troubleshooting}

#### Нужно ли подгонять все изображения для задания под один размер, или они могут быть разные?
Размеры изображений могут быть разные.
#### Как в image-annotation добавить горячую клавишу для добавления многоугольника?
Чтобы добавить горячую клавишу, в методе onKey пропишите следующее действие:
```
onKey: function(key) {
    var el = this.getDOMElement().querySelector(".image-annotation-editor__shape-polygon");

    if (key === 'D') {
      el.click();
      el.classList.add('image-annotation-editor__shape_active')
    }
```

#### Как размечать треугольники, чтобы они сами замыкались при выставлении последней точки?

Для замыкания используйте горячую клавишу **C**.

Вы также можете воспользоваться [библиотекой](https://github.com/vmit/image-annotation), чтобы настроить горячие клавиши под свои задачи.

#### Как создать задачу с выделением областей на изображении?

Задачу с выделением областей на изображении с помощью Толоки рекомендуем решать в трёх проектах:
1. Сортировка изображений, на которых есть объект.
    1. [Создайте задание](categorization.md), используя шаблон «Классификация изображений».
    1. Отсортируйте изображения, на которых есть искомый объект.
    1. Покажите изображение исполнителю и задайте вопрос: есть объект на картинке? Ответ — Да/Нет.

1. Выделение объекта на изображениях.
    1. Выделите объект на изображениях, которые отобрали в предыдущем проекте. Такой проект у вас уже есть. Задание запускается с отложенной приемкой.
    1. Используйте правила контроля качества: быстрые ответы, отложенная приемка, дооценка после приёмки. [Описание правил и примеры](control.md).

1. Проверка выделения объектов.
    1. Создайте задание, используя шаблон по выделению областей.
    1. Скройте редактор и задайте вопрос: объект выделен верно? Ответ — Да/Нет.
    1. Во входных данных передайте картинки и координаты размеченных областей из предыдущего задания.
    Запустив полученный пул с перекрытием 3-5 или с динамическим перекрытием, вы сможете агрегировать результаты, а затем загрузить данные для проверки в проект 2.
    Чтобы не допускать к проверке тех исполнителей, которые работали над вторым проектом, назначайте им навык. Используйте этот навык в качестве фильтра в пулах третьего проекта.

#### Как добавить валидацию ответа в зависимости от чекбокса?

Добавить валидацию ответа в зависимости от чекбокса можно с помощью JavaScript. Пример доступен в шаблоне «Поиск данных в сети».

#### Задание по выделению областей на картинке: что делать исполнителю, если на картинке нет предмета, который он должен выделить?

Основные варианты решения:

- Выделите произвольную область на картинке (например, поставьте квадрат в правый верхний угол). В этом случае в инструкции к проекту для проверяющих это тоже должно быть отражено.
- Предложите пропустить задание и сообщить о нём в личном сообщении. Сообщения проверяются заказчиком и, если объекта действительно нет, задание удаляется из пула путем обнуления перекрытия.
- Добавьте в интерфейс дополнительный чекбокс «нет объекта». Настройте в JS проверку, чтобы в задании был выделен объект, либо проставлен чекбокс. В этом случае в интерфейс задания для контроля также нужно добавить информацию о значении этого чекбокса.

#### Сколько будет стоить 2000 картинок с большим количеством объектов выделения разного типа? Как для такого объема работы создать задание?

Для краудсорсинга такое задание лучше декомпозировать. Чем проще задание, тем оно будет дешевле и качественнее итоговый результат. Стоимость разметки одного класса объектов на фото может составить примерно 0,01 $.

Возьмите за основу шаблон «Выделение областей на изображении». Пошаговое руководство по созданию проекта такого типа вы найдёте на [этой странице](selection.md).

Редактор, который используется в шаблоне, позволяет добавлять выпадающий список для маркировки выделенного объекта. Посмотрите как это сделать в описании редактора (вкладка [Выпадающий список](t-components/image-annotation.md)).

#### Как реализовать выделение 3-х разных областей на картинке? На скриншоте страницы товара нужно выделить название, изображение, цену.

Можно сделать выделение + выпадающий список с выбором категории. Посмотрите как это сделать в описании редактора (вкладка [Выпадающий список](t-components/image-annotation.md)).

#### Какие входные данные при разметке объектов на изображении: координаты объекта относительно изображения или координаты объекта в окне исполнителя Толоки?

Координаты относительно самого изображения.

#### Как в стандартном шаблоне с редактором для выделения областей использовать контрольные задания?

В стандартном шаблоне с редактором для выделения областей не получится использовать контрольные задания, поскольку для того, чтобы ответ засчитался системой верным, объект, выделенный исполнителем, должен в точности совпасть с эталоном. А это практически невозможно. Поэтому поле GOLDEN можно оставить пустым в файле с заданиями или просто удалить все столбцы кроме INPUT.
 {% if locale == "ru-ru" %}
#### Почему в задании по выделению объектов на изображении не отображаются изображения с Яндекс Диска?

Проблема в шаблоне задания. Проверьте, что:
- Для поля входных данных, куда вы передаете ссылку на файл, в проекте указан тип «строка».
- В компоненте в шаблоне задания используется выражение proxy.
- Формат относительных ссылок в файле с заданиями указан верно: <уникальное имя>/<путь и имя файла>.
Подробная инструкция и видео на странице [Использование файлов с Яндекс Диска](prepare-data.md).
{% endif %}
#### Как в стандартном шаблоне с редактором для выделения областей использовать контрольные и обучающие задания?

В стандартном шаблоне с редактором для выделения областей не получится использовать контрольные задания, поскольку для того, чтобы ответ засчитался системой верным, объект, выделенный исполнителем, должен в точности совпасть с эталоном. А это практически невозможно. Поэтому поле GOLDEN можно оставить пустым в файле с заданиями или просто удалить все столбцы кроме INPUT.

Использование [обучения](../../glossary.md#training-pool-ru) и основного пула с типом **Тренировка** в проекте по выделению областей на картинке не принесет результата, так как для правильного ответа необходимо, чтобы выделение исполнителя полностью совпало с эталоном. А это практически невозможно.

Поэтому такие задания обычно запускаются с отложенной приемкой: исполнитель дает ответ, а затем после проверки, задание отклоняется или принимается.

Для предварительного отбора исполнителей подойдет так называемое «экзаменационное задание». Проверяйте задания и выставляйте навык по проценту принятых ответов. Для этого добавьте в пул правило «Результаты проверки». Чтобы к разметке основного пула приступили только хорошие исполнители, поставьте в нем фильтр по навыку.
 {% if locale == "ru-ru" %}
#### Не загружаются файлы с Яндекс Диска

Если картинки, аудио или видео с Яндекс Диска не отображаются в [инструкции](../../glossary.md#task-instruction-ru) или на [странице задания](../../glossary.md#task-page-ru), убедитесь, что вы правильно подключили Диск и загрузили файлы.





####  Как сделать задание, в котором исполнитель должен просматривать видео с Яндекс Диска?

Для создания задания возьмите за основу [шаблон для разметки видео]({{ templates-video-new }}).

Чтобы разместить ваши видеоролики на Яндекс Диске, его нужно подключить и настроить проект.
 {% if locale == "ru-ru" %}
Подробная видеоинструкция об этом [в нашем блоге]({{ toloka-blog-yadisk }}).
{% endif %}
#### Почему в задании по выделению объектов на изображении не отображаются изображения с Яндекс Диска?

Проблема в шаблоне задания. Проверьте, что:
- Для поля входных данных, куда вы передаете ссылку на файл, в проекте указан тип «строка».
- В компоненте в шаблоне задания используется выражение proxy.
- Формат относительных ссылок в файле с заданиями указан верно: <уникальное имя>/<путь и имя файла>.
Подробная инструкцию и видео на странице [Использование файлов с Яндекс Диска]({{ using-files-yandex-disk }}).
 {% if locale == "ru-ru" %}
#### Частые ошибки при подключении Диска и загрузке файлов

- В настройках проекта в поле **Входные данные** указан тип _ссылка_. Необходимо выбрать тип _строка_.
- В [файле с заданиями](../../glossary.md#tsv-file-definition-ru) указаны абсолютные ссылки на файлы для заданий. Необходимо вставить ссылку вида `<уникальное имя>/<путь и имя файла>`. Например: `yadisk/image1.jpg` или `yadisk/photos/image1.png`.
- Фото с Яндекс Диска используются в инструкции к заданию в мобильном приложении. Чтобы фото отобразилось в инструкции, используйте только прямые ссылки.
- Файлы удалены или находятся не в той папке на Диске, на которую ведет ссылка.
- OAuth-токен не активен. Обновите токен на странице [Интеграция]({{ integration }}).

Чтобы файлы, загруженные на Яндекс Диск (картинки, аудио, видео), отображались у исполнителя, нужно:
1. Подключить Яндекс Диск в профиле.
1. Установить тип строка для поля [входных данных](../../glossary.md#input-output-data-ru).
1. Вставлять ссылку на файл при помощи компонента `proxy`.

[Подробная инструкция](prepare-data.md)
{% endif %}
{% endif %} {% if locale == "ru-ru" %}
#### Файлы на Яндекс Диск загружаются слишком медленно. Как ускорить загрузку?

Попробуйте воспользоваться рекомендациями с [этой страницы]({{ yadisk-uploading }}) или написать в службу поддержки Яндекс Диска.
{% endif %}

{% include [contact-support](../_includes/contact-support-help.md) %}