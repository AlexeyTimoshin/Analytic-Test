### LEVEL 2
#### Несколько запросов на PostgreSQL

```sql
-- средняя посещаемость
-- выполним групировку по дате, посчитаем число уникальных юзеров(1 юзер может быть в нескольких группах)
-- и разделим на кол-во групп в этот день

SELECT event_date 
       , COUNT( DISTINCT customer_id)::float / COUNT(DISTINCT group_ids) avg_customer_by_day   
FROM tablename
GROUP BY event_date

-- MAU
-- Извлечем из даты месяц и сгруппируем униальные id

SELECT EXTRACT(MONTH FROM event_date) as month
       , COUNT( DISTINCT customer_id) DAU
FROM tablename
GROUP BY month

```
