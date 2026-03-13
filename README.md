# Car Catalog

## Аналитические запросы
В файле `sql/queries.sql` реализованы:
1. Топ-3 самых дорогих автомобилей
2. Средняя цена по марке
3. Фильтр: новые и недорогие машины
4. Распределение по цветам (только популярные)
5. Классификация по возрасту (новый/старый)

## Запуск с Docker

1. Установи Docker Desktop
2. Выполни:
   ```bash
   docker-compose up -d

3. Открой http://localhost:8080

System (Движок): PostgreSQL

Server (Сервер): db ← именно так называется сервис!

Username (Имя пользователя): postgres

Password (Пароль): postgres (если менял, то свой пароль)

Database (База данных): car_catalog_db

4. Или подключись через VS Code (порт 5432)

## Исследование
Внутри контейнера выполнены команды:

sql
SELECT color, AVG(price) FROM cars GROUP BY color;
Вывод:
 color  |         avg          
--------+----------------------
 Silver | 1350000.000000000000
 Black  | 2975000.250000000000
 White  | 1800000.000000000000
 Blue   |  110000.000000000000
 Gray   |  950000.000000000000
 Red    | 1050000.000000000000
 Green  | 2100000.000000000000
(7 rows)

sql
SELECT brand, COUNT(*) FROM cars GROUP BY brand;
Вывод:
  brand    | count 
-----------+-------
 Toyota    |     1
 BMW       |     1
 Lada      |     1
 Ford      |     1
 Hyundai   |     1
 Kia       |     1
 Mercedes  |     1
 Audi      |     1
 Volkswagen|     1
 Nissan    |     1
(10 rows)
   