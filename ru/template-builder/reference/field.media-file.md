# field.media-file

Добавляет кнопки для разных видов загрузки файлов: загрузить фото или видео, выбрать файлы из файлового менеджера или галереи. Настройте в свойстве `accept`, какая из кнопок вам нужна.

По умолчанию разрешает загрузить только один файл, но можно позволить загружать несколько в свойстве `multiple`.

Компонент будет удобен при работе с мобильных устройств. Для загрузки файлов с компьютера лучше использовать [field.file](field.file.md) для более гибкой настройки типов загружаемых файлов.

В режиме проверки задания загруженные изображения появятся автоматически. Изображения можно просматривать, поворачивать и переключаться между ними.

[![](../_images/buttons/view-example.svg)](https://clck.ru/S69wM)

## Особенности работы в мобильном приложении Толоки

В мобильном приложении Толоки кнопки для фото и видео откроют камеру, а кнопки галереи и файлового менеджера — соответствующие приложения.

После того как исполнитель отправит задание, файлы сохранятся внутри приложения и при подключении к Wi-Fi постепенно загрузятся в Толоку. Пока подключения нет, задание будет находиться в статусе «Ожидает отправку по Wi-Fi».

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "field.media-file" | Задает тип компонента. ||
|| `data`<span style="color: red">\*</span> | _writable_ | Данные, значения которых будут обработаны или изменены. ||
|| `label` | _string_ | Надпись над компонентом. ||
|| `accept`<span style="color: red">\*</span> | _object_ | Добавляет разные кнопки для четырех видов загрузки. Передайте значение `true` тем из них, которые вам нужны.

Например, если нужна кнопка загрузки файлов из галереи, то добавьте в свойство `"gallery": true`. ||
|| `accept.fileSystem` | _boolean_ | Добавляет кнопку для загрузки файла из файлового менеджера. ||
|| `accept.gallery` | _boolean_ | Добавляет кнопку для загрузки файла из галереи. ||
|| `accept.photo` | _boolean_ | Добавляет кнопку для загрузки изображения. ||
|| `accept.video` | _boolean_ | Добавляет кнопку для загрузки видеофайла. ||
|| `hint` | _string_ | Текст подсказки. ||
|| `multiple` | _boolean_ | Определяет, разрешено ли загружать несколько файлов:

- `false` (по умолчанию) — запрещено;
- `true` — разрешено. ||
  || `requiredCoordinates` | _boolean_ | Если `true`, то нельзя будет загрузить файл без геотега. ||
  || `validation` | _condition_ | Валидация на основе условия _(condition)_. ||
  |#
