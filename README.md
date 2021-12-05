### Вложенные конечные точки для */users-profiles/*
>**На этих конечных точках работают:**
>1) *Фильтрации и сортировки по query параметрам*
>2) *Пагинация*
>3) *Поиск*
>4) *Extra actions для возвраемых моделей*
>5) *Details со всеми доступными методами*

Префикс | Конечная точка | Доступные методы | Сериализация |Описание 
---|---|---|---|---
**notices** | ***/api/v1/users-profiles/{id}/notices/*** | **GET** | [notifications]() | **GET** Возвращает уведомления пользователя c id = id
**notices** | ***/api/v1/users-profiles/{id}/notices/{id_2}*** | **GET, PUT, PATCH, DELETE** | [notification]() | **GET** Возвращает уведомление с id = id_2 пользователя c id = id
**sell-transactions** | ***/api/v1/users-profiles/{id}/sell-transactions/*** | **GET** | [transactions]() | **GET** Возвращает транзакции продажи пользователя c id = id
**sell-transactions** | ***/api/v1/users-profiles/{id}/sell-transactions/{id_2}*** | **GET, DELETE** | [transaction]() | **GET** Возвращает транзакцию продажи с id = id_2 пользователя c id = id
**buy-transactions** | ***/api/v1/users-profiles/{id}/buy-transactions/*** | **GET** | [transactions]() | **GET** Возвращает транзакции покупки пользователя c id = id
**buy-transactions** | ***/api/v1/users-profiles/{id}/buy-transactions/{id_2}*** | **GET, DELETE** | [transaction]() | **GET** Возвращает транзакцию покупки с id = id_2 пользователя c id = id
**sell-offers** | ***/api/v1/users-profiles/{id}/sell-offers/*** | **POST, GET** | [offers]() | **GET** Возвращает полученные предложения пользователя c id = id
**sell-offers** | ***/api/v1/users-profiles/{id}/sell-offers/{id_2}*** | **GET, PUT, PATCH, DELETE** | [offer]() | **GET** Возвращает полученное предложение с id = id_2 пользователя c id = id
**buy-offers** | ***/api/v1/users-profiles/{id}/buy-offers/*** | **POST, GET** | [offers]() | **GET** Возвращает отправленные предложения пользователя c id = id
**buy-offers** | ***/api/v1/users-profiles/{id}/buy-offers/{id_2}*** | **GET, PUT, PATCH, DELETE** | [offer]() | **GET** Возвращает отправленное предложение с id = id_2 пользователя c id = id
**collections** | ***/api/v1/users-profiles/{id}/collections/*** | **POST, GET** | [offers]() | **GET** Возвращает коллекции пользователя c id = id
**collections** | ***/api/v1/users-profiles/{id}/collections/{id_2}*** | **GET, PUT, PATCH, DELETE** | [offer]() | **GET** Возвращает отправленное предложение с id = id_2 пользователя c id = id
