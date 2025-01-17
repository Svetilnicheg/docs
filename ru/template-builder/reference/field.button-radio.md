# field.button-radio

Добавляет одну кнопку. Пригодится для оформления необязательного варианта ответа.

Если вы хотите добавить несколько кнопок, используйте [field.button-radio-group](field.button-radio-group.md).

Размер кнопки зависит от длины надписи.

[![](../_images/buttons/view-example.svg)](https://clck.ru/T6V8x)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "field.button-radio" | Задает тип компонента. ||
|| `data`<span style="color: red">\*</span> | _writable_ | Данные, значения которых будут обработаны или изменены. ||
|| `label` | _string_ | Надпись над компонентом. ||
|| `disabled` | _boolean_ | Свойство запрещает нажимать кнопки. Если значение — `true`, исполнителю будет недоступно нажатие. ||
|| `hint` | _string_ | Текст подсказки. ||
|| `rtl` | _object_ | Тексты на арабском, иврите и некоторых других языках принято писать слева направо. Используйте это свойство, чтобы задать правильный режим отображения для компонента.

[![](../_images/buttons/view-example.svg)](https://clck.ru/amHBJ)

[Подробнее про RTL-языки](https://www.w3.org/International/questions/qa-scripts).
||
|| `rtl.mode` | _string_ | Режим отображения:

- `ltr` — слева направо;
- `rtl` — справа налево.

Выбранное значение подставится в атрибут `dir` в HTML-коде компонента. [Подробнее про свойство dir](https://www.w3.org/International/questions/qa-html-dir). ||
|| `validation` | _condition_ | Валидация на основе условия _(condition)_. ||
|| `valueToSet` | _string_ | Значение выходных данных при нажатии на кнопку. ||
|#
