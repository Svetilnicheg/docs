# condition.same-domain

Проверяет, что введенная ссылка принадлежит определенному сайту. При совпадении вернет `true`, иначе — `false`.

Ссылки надо указывать полностью, вместе с протоколом (http, https, ftp).

Поддомен `www.` при проверке не учитывается, то есть ссылки на сайты`www.example.ru` и `example.ru` будут считаться одинаковыми.

[Посмотреть пример в песочнице](https://clck.ru/UHYTp).

Как передать адрес ссылки:

- указать явно в виде строки;
- [получить значение из данных](../operations/work-with-data.md);
- сослаться на другой элемент с помощью `$ref`;
- использовать [хелперы](helpers.md) и [условия](conditions.md), чтобы получить значение.

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "condition.same-domain" | Задает тип компонента. ||
|| `data` | _any_ | Адрес ссылки, которую надо проверить. Если не задан, то используется значение, возвращаемое родительским компонентом (в котором находится `condition.same-domain`). ||
|| `hint` | _string_ | Сообщение об ошибке валидации, которое увидит исполнитель ||
|| `original`<span style="color: red">\*</span> | _any_ | Адрес ссылки, с которой сравнивается проверяемая ссылка. ||
|#