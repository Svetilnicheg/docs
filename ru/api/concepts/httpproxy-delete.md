# Удалить регистрацию прокси-сервера

Чтобы удалить зарегистрированный сервер заказчика, отправьте AJAX-запрос из консоли браузера, авторизовавшись под именем заказчика.

## Запрос {#request}

```js
$.ajax({
      url: '/api/new/requester/proxy/proxy/{id}',
      method: 'DELETE'
});
```

## Ответ {#response}

Если запрос выполнен успешно, сервер возвращает HTTP-статус выполнения операции: «204 No Content» или «404 Not Found».