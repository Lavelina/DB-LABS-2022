# Техническое задание
## Сущности
- Клиент
- Пекарь
- Аккаунт
- Изделие
- Вид изделия
- Состав
- Ингредиент
- Корзина
- Заказ
- Отзыв
- Доставка
---
<br>

## Роли пользователей
---
- Пекарь 
- Клиент
<br>

## Возможности пользователей
---
### Пекарь
- Регистрация на сайте
- Вход и выход из аккаунта
- Создание, редактирование, обновление, удаление изделия
- Подтверждение заказа
### Клиент
- Регистрация на сайте
- Вход и выход из аккаунта
- Создание, обновление, редактирование, удаление информации о себе на странице
- Добавление и удаление товаров из корзины
- Оформление заказа
- Написание отзывов на изделия
# Описание сущностей
(имя поля, тип, ограничения, связь с другими сущностями)
## Клиент (Client)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk | auto increment; not null; unique | первичный ключ |
| accountID | INT | not null | внешний ключ на аккаунт |
| cartID | INT | not null | внешний ключ на корзину |
| name | VARCHAR(50) | not null | имя клиента |
| surname | VARCHAR(255) | not null | фамилия клиента |
| email | VARCHAR(60)| not null | электронная почта |
| phone | VARCHAR(13)| not null; unique | номер телефона |
## Пекарь (backer)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk | auto increment; not null; unique | первичный ключ |
| accountID | INT | not null | внешний ключ на аккаунт |
| name | VARCHAR(50) | not null | имя пекаря |
| surname | VARCHAR(255) | not null | фамилия пекаря |
| email | VARCHAR(60)| not null | электронная почта |

## Аккаунт (Account)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk | auto increment; not null; unique | первичный ключ |
| login | VARCHAR(50) | not null; unique | логин |
| password | VARCHAR(255) | not null | пароль |
## Изделие (Product)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk | auto increment; not null; unique | первичный ключ |
| type_productID | INT | not null | внешний ключ на вид изделия |
| name | VARCHAR(100) | not null | название изделия |
| image | VARCHAR(255) | not null | ссылка на изображение |
## Вид изделия (type_product)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk | auto increment; not null; unique | первичный ключ |
| backerID | INT | not null | внешний ключ на пекаря |
| type | VARCHAR(100) | not null | вид изделия |
## Состав (Ingredients)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk | auto increment; not null; unique | первичный ключ |
| productID | INT | not null | внешний ключ на изделие |
| ingredientID | INT | not null | внешний ключ на ингредиенты состава |
## Ингредиет (Ingredient)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk | auto increment; not null; unique | первичный ключ |
| calories | float | not null | калорийность |
| fat | float | not null | жиры |
| protein | float | not null | белки |
| carb | float | not null | углеводы |
## Корзина (Cart)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk | auto increment; not null; unique | первичный ключ |
| orderID | INT | not null | внешний ключ на заказ |
## Заказ (Orders)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk | auto increment; not null; unique | первичный ключ |
| productID | INT | not null | внешний ключ на изделие |
| price | float | not null | стоимость заказа |
## Отзыв (feedback)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk | auto increment; not null; unique | первичный ключ |
| clientID | INT | not null | внешний ключ на клиента |
| feedback | VARCHAR(1000) | not null | текст отзыва |
## Доставка (Delivery)
|имя поля | тип | ограничения | описание |
|:---:|:---:|:---:|:---:|
| id | pk | auto increment; not null; unique | первичный ключ |
| orderID | INT | not null | внешний ключ на заказ |
| city | VARCHAR(60)| not null | город |
| street | VARCHAR(60)| not null | улица |
| house_num | VARCHAR(10)| not null | дом/корпус |
