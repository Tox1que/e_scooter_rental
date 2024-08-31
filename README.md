# Статистический анализ данных сервиса кикшеринга.  

### Описание проекта
В нашем распоряжении имеются данные о некоторых пользователях из нескольких городов, а также об их поездках.  
Требуется проанализировать данные и проверить некоторые гипотезы, которые могут помочь бизнесу вырасти.

Чтобы совершать поездки по городу, пользователи сервиса GoFast пользуются мобильным приложением.  
Сервисом можно пользоваться:
- без подписки 
    - абонентская плата отсутствует;  
    - стоимость одной минуты поездки — 8 рублей;  
    - стоимость старта (начала поездки) — 50 рублей;  
- с подпиской Ultra  
    - абонентская плата — 199 рублей в месяц;  
    - стоимость одной минуты поездки — 6 рублей;  
    - стоимость старта — бесплатно.  

### Описание данных  
В основных данных есть информация о пользователях, их поездках и подписках.  

*Пользователи* - `users_go.csv`  
`user_id` - уникальный идентификатор пользователя  
`name` - имя пользователя  
`age` - возраст  
`city` - город  
`subscription_type` - тип подписки (free, ultra)  

*Поездки* - `rides_go.csv`    
`user_id` - уникальный идентификатор пользователя  
`distance` - расстояние, которое пользователь проехал в текущей сессии (в метрах)  
`duration` - продолжительность сессии (в минутах)  
`date` - дата совершения поездки  

*Подписки* - `subscriptions_go.csv`    
`subscription_type` - тип подписки  
`minute_price` - стоимость одной минуты поездки по данной подписке  
`start_ride_price` - стоимость начала поездки  
`subscription_fee` - стоимость ежемесячного платежа

### Предобработка данных:  
- строковые значения в колонке `date` преобразованы в даты;
- добавлен новый столбец с номером месяца поездки;
- в наборе данных `users_go.csv`устранены явные дубликаты;  
- удалены аномальные значение в столбце с информацией о продолжительности поездки;
- данные о пользователях, поездках и подписках объединены в один датафрейм.

### Проверка гипотез.  
Исходя из полученных результатов, можно предположить:
- пользователи с подпиской тратят больше времени на поездки;
- средняя дистанция, преодолённая пользователем с подпиской за поездку,  
не превышает оптимальное с точки зрения износа самоката расстояние;
- помесячная выручка от пользователей с подпиской выше, чем от клиентов без неё.  
