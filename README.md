## rush
**rush** это многофункциональное приложение по анализу рынка Steam и сторонних маркетов.

## Особенности
1. Поддержка прокси (работает так и без них)
2. Поддержка многопоточности
3. Использует прокси по максимуму
4. Расширенная настройка
5. Работа по всем 3 сервисам (https://market.dota2.net, https://rust.tm, https://market.csgo.com/ru)

### Установка phpMyAdmin на Windows
1. Переходим по ссылке http://www.denwer.ru/
2. Нажимаем **скачать Denwer 3**
3. Выбираем версию PHP 5.2

После успешнй установки нам будет доступен phpMyAdmin по ссылке http://localhost/Tools/phpMyAdmin/

1. Переходим во вкладку **Базы данных**
2. Создаем новую базу данных, указанное название запоминаем, понадобиться (по умолчанию название базы данных - **rush**)

### Конфигурация Telegram бота
> configs/bot.json
 
```json
{
    "ID": 603,
    "Token": "602...:AAF..."
}
```
1. `ID` - ваш **telegram ID**
2. `Token` - **токен** бота

### Конфигурация фильтра
> configs/filter.json

```json
{
    "min": 1250.5,
    "max": 1750.0,
    "percent": 33.3
}
```
1. `min` - минимальная цена на не офф. маркете
2. `max` - `max` - макс. цена на не офф. маркете
3. `percent` - разница цен в %


### Конфигурация маркет-клиента
> configs/market.json

```json
{
    "games": [
        "newitems_go",
        "newitems_gt"
    ],
    "key": "haj..."
}
```
1. `games` - игры.
2. `key` - **API-ключ** маркетплейса (https://market.dota2.net/docs-v2#anchor2)


#### Доступные игры
1. `newitems_go` - **CS:GO**
2. `newitems_gt` - **Rust**
3. `newitems_cs` - **Dota 2**.

### Конфигурация базы данных
> configs/storage.json

```json
{
    "protocol": "127.0.0.1",
    "username": "root",
    "password": "",
    "database": "rush"
}
```
оставляем как есть если используем локальную машину.
1. `protocol` - IP:PORT хоста
2. `username` - логин от phpMyAdmin
3. `password` - пароль от phpMyAdmin
4. `database` - имя созданной базы данных

### Запуск приложения
Открываем файл `rush.exe`, если всё правильно настроено увидим сообщение `The bot has been successfully launched`.
Можем пользоваться Telegram ботом. Чтобы запустить сам авто-скупку пишем команду `/start N`, где `N` - **количество потоков**