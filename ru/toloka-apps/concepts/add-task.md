# Загрузка элементов разметки

Вы можете добавлять данные в Bespoke-проект в статусе **Активный** или **В обработке**.

## Создать новый пакет данных {#new-batch}

1. Откройте проект.
2. Нажмите кнопку **Создать пакет данных**.
3. Введите уникальное название пакета данных.
4. Добавьте элементы разметки одним из способов:

    - Загрузите готовый TSV-файл.
    - Внесите данные в текстовом формате.

5. Нажмите кнопку **Создать пакет данных**.

## Добавить элементы в уже существующий пакет данных {#edit}

1. Откройте проект и перейдите в нужный пакет данных.
2. Справа нажмите кнопку **Добавить элементы разметки**.
3. Добавьте элементы разметки одним из способов:

    - Загрузите готовый TSV-файл.
    - Внесите данные в текстовом формате.

## Что дальше {#whats-next}

Дождитесь окончания разметки и [скачайте результаты](download-results.md).

## Решение проблем {#troubleshooting}

{% cut "Что добавлять в пакет данных?" %}

Пакеты — это наборы данных, которые нужно разметить. Добавляйте в пакеты данных TSV-файлы, с идентификатором и ссылкой на медиафайл.

Пример заполнения TSV-файла:

```
id  image_url
1   https://yastat.net/s3/tb/static/file-examples/special/street.jpg
```

{% endcut %}

{% cut "Мой проект еще не прошел модерацию. Могу ли я добавлять в него элементы разметки?" %}

Да. Вы можете добавлять элементы разметки в проекты в статусе **Активный** или **В обработке**.

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}