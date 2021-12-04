# API documentation 

## Правила формирования запросов
### Базовый URL

***https://dev.artgraphite.ru/api/v1***

### Сортировка
```sh
# Упорядочить по полю username
http://example.com/api/users?ordering=username

# Упорядочить по полю username в обратном порядке
http://example.com/api/users?ordering=-username

# Упорядочить сначала по полю account, а затем по username
http://example.com/api/users?ordering=account,username
```

### Базовые функции поиска
```sh
# Вернет пользователей со значением поля age = 18
http://example.com/api/users?age=18

# Вернет пользователей со значением поля age < 18
http://example.com/api/users?age__lt=18

# Вернет пользователей со значением поля age <= 18
http://example.com/api/users?age__lte=18

# Вернет пользователей со значением поля age > 18
http://example.com/api/users?age__gt=18

# Вернет пользователей со значением поля age =>= 18
http://example.com/api/users?age__gte=18

# Вернет пользователей со значением поля age 5, 10 или 15
http://example.com/api/users?age__in=5,10,15

# Вернет пользователей со значением поля age от 5 до 10
http://example.com/api/users?age__range=5,10

# Вернет пользователей со значением поля name содержащем подстроку foo
http://example.com/api/users?name__incontains=foo

# Вернет пользователей со значением поля name не содержащем подстроку foo
http://example.com/api/users?name__incontains!=foo

```
### Фильтр по вложенным объектам
```sh
# Вернет пользователей, присоединившихся между 2010 и 2015 через связанную модель пользователя (o2m)
example.com/users/?profile__joined__range=2010-01-01,2015-12-31
```
### Сложный фильтр
```sh
# Комбинация нескольких условий в одном запросе
http://example.com/api/users?age__range=5,10&name__incontains=foo&profile__joined__range=2010-01-01,2015-12-31
```

## Конечные точки
### Authorization 
#### Получение JWT токена
***https://dev.artgraphite.ru/api/auth/jwt/create/ \
/api/v1/auth/jwt/create***
```sh
# POST ожидает
    {
        "wallet_number": <str>,
        "password": <str>
    }
```
Параметр | Тип | Обязательный | Описание | 
---|---|---|---
`wallet_number` | ***str*** | :heavy_check_mark: | Номер кошелька пользователя 
`password` | ***str*** | :heavy_check_mark: | Пароль пользователя (уникальный идентификатор пользователя на wax)
```sh
# POST возвращает
    {
        "refresh": <str>,
        "access": <str> 
    }
```
Параметр | Тип  | Описание | 
---|---|---
`refresh` | ***int*** | Refresh JWT token пользователя
`access` | ***str*** | Access JWT token пользователя

#### Проверка валидности JWT токена 
***https://dev.artgraphite.ru/api/auth/jwt/verify/ \
/api/v1/auth/jwt/verify***
```sh
# POST ожидает
    {
        "token": <str> 
    }
# При валидном токене возвращает status 200
```
Параметр | Тип | Обязательный | Описание | 
---|---|---|---
`token` | ***str*** | :heavy_check_mark: | JWT token пользователя

### User
#### Создание пользователя
***https://dev.artgraphite.ru/api/v1/users-profiles/ \
/api/v1/users-profiles/***

```sh
# POST ожидает 
    {
        "owner_key": <str>,
        "wallet_number": <str>,
        "password": <str>
    }
```
Параметр | Тип | Обязательный | Описание | 
---|---|---|---
`owner_key` | ***str*** | :heavy_check_mark: | Общий идентификатор wax
`wallet_number` | ***str*** | :heavy_check_mark: | Номер кошелька пользователя 
`password` | ***str*** | :heavy_check_mark: | Пароль пользователя (уникальный идентификатор пользователя на wax) 

#### Получение списка пользователей
***https://dev.artgraphite.ru/api/v1/users-profiles/ \
/api/v1/users-profiles/***

```sh
# GET возвращает 
    {
    "count": 1,
    "next": null,
    "previous": null,
    "results": [
        {
            "id": <int>,
            "first_name": <str>,
            "last_name": <str>,
            "avatar": <str(image_path)>,
            "wallet_number": <str>,
            "instagram": null,
            "twitter": null,
            "discord": null,
            "telegram": null,
            "website": null,
            "profile_type": null,
            "is_viewed": false,
            "is_subscribed": false
        }
      ]
    }

```
Параметр | Тип  | Описание | 
---|---|---
`id` | ***int*** | Уникальный ключ пользователя
`first_name` | ***str*** | Имя
`last_name` | ***str*** | Фамилия
`avatar` | ***str*** | Ссылка на аватар пользователя
`wallet_number` | ***str*** | Номер кошелька пользователя
`instagram` | ***str*** | Инстаграм
`twitter` | ***str*** | Твиттер
`discord` | ***str*** | Дискорд
`telegram` | ***str*** | Телеграм
`website` | ***str*** | Адрес сайта
`profile_type` | ***str*** | Тип профиля
`is_viewed` | ***bool*** | Просмотрен ли этот профиль текущим юзером 
`is_subscribed` | ***bool*** | Подписан ли на этот профиль текущий юзер 
