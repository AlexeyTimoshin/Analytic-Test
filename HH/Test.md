## Код для таблиц
```
CREATE TABLE vacancy (
       vacancy_id INT PRIMARY KEY,
       name VARCHAR,
       work_schedule VARCHAR,
       disabled BOOLEAN,
       area_id INT,
       creation_time VARCHAR,
       archived BOOLEAN
);

CREATE TABLE resume (
       resume_id INT PRIMARY KEY,
       disabled BOOLEAN,
       is_finished INT,
       area_id INT,
       compensation INT,
       currency VARCHAR,
       position VARCHAR,
       birth_day TIMESTAMP,
       role_id_list array
);

CREATE TABLE area (
       area_id INT PRIMARY KEY,
       area_name VARCHAR,
       region_name VARCHAR,
       country_name VARCHAR
);

CREATE TABLE currency (
       code VARCHAR PRIMARY KEY,
       rate DECIMAL
);

INSERT INTO currency (code, rate) VALUES
('RUR', 1),
('USD', 0.013074), 
('EUR', 0.01159);



INSERT INTO area(area_id, area_name, region_name, country_name) VALUES
(1, 'Москва','Москва', 'Россия'),
(2, 'Санкт-Петербург', 'Санкт-Петербург', 'Россия'),   
(3, 'Норильск', 'Красноярский край', 'Россия'),            
(4, 'Самара', 'Самарская область', 'Россия'),
(5, 'Екатеринбург', 'Свердловская область', 'Россия'),                     
(6, 'Владивосток', 'Приморский край' 'Россия'),
(7, 'Минск', 'Минская область', 'Беларусь'),
(8, 'Аламата', 'Алматинская область', 'Казахстан');


INSERT INTO resume (
       resume_id,
       disabled,  
       is_finished,  
       area_id, 
       compensation, 
       currency, 
       position, 
       birth_day, 
       role_id_list 
) VALUES
(1, FALSE, 3, 1, 30000, 'RUR', NULL, '2008-01-01', '{41, 42}');
(2, FALSE, 3, 1, 25000, 'RUR', NULL, '2010-02-01', '{41, 2}'),
(3, FALSE, 3, 2, 10000, 'RUR', NULL, '2012-01-01', '{41}'),
(4, FALSE, 3, 2, 8000, 'EUR', NULL, '1980-01-01', '{41}'),
(5, FALSE, 3, 1, 6000, 'USD', NULL, '1976-01-01', '{41}'),
(6, FALSE, 3, 1, 234000, 'RUR', NULL, '1990-02-01', '{41}'),
(7, FALSE, 3, 2, 400000, 'RUR', NULL, '1980-11-09', '{41, 1}'),
(8, FALSE, 3, 1, 60000, 'RUR', NULL, '2000-11-05', '{41}'),
(9, FALSE, 3, 1, 350000, 'RUR', NULL, '1999-01-06', '{41}'),
(10, FALSE, 3, 1, 3000, 'EUR', NULL, '1988-12-11', '{41}'),
(11, FALSE, 3, 2, 780000, 'RUR', NULL, '1975-01-01', '{41, 55}'),
(12, FALSE, 3, 1, 80000, 'RUR', NULL, '2000-08-11', '{41}'),
(13, FALSE, 3, 2, 250000, 'RUR', NULL, '1999-01-21', '{41}'),
(14, FALSE, 3, 2, 32000, 'RUR', NULL, '209-12-01', '{41}'),
(15, FALSE, 3, 1, 125000, 'RUR', NULL, '1980-01-01', '{41, 22}'),
(16, FALSE, 3, 1, 350000, 'RUR', NULL, '2000-11-21', '{41}'),
(17, FALSE, 3, 1, 66000, 'RUR', NULL, '2001-01-04', '{41}'),
(18, FALSE, 3, 1, 30000, 'RUR', NULL, '2000-01-01', '{41, 99}'),
(19, FALSE, 3, 1, 360000, 'RUR', NULL, '2000-12-01', '{41}'),
(20, FALSE, 3, 2, 500000, 'RUR', NULL, '1982-01-08', '{41}'),
(21, FALSE, 3, 1, 250000, 'RUR', NULL, '2003-04-11', '{41}'),
(22, FALSE, 3, 1, 330000, 'RUR', NULL, '2000-06-01', '{41}'),
(23, FALSE, 3, 1, 122000, 'RUR', NULL, '1990-11-17', '{41, 11}'),
(24, FALSE, 3, 1, 3000, 'EUR', NULL, '1994-12-11', '{41}'),
(25, FALSE, 3, 2, 10000, 'USD', NULL, '1993-06-07', '{41, 2}'),
(26, FALSE, 3, 2, 320000, 'RUR', NULL, '1991-05-15', '{41}'),
(27, FALSE, 3, 1, 130000, 'RUR', NULL, '1998-01-11', '{41}'),
(28, FALSE, 3, 1, 170000, 'RUR', NULL, '1995-05-01', '{41,77}'),
(29, FALSE, 3, 2, 190000, 'RUR', NULL, '1996-09-01', '{41}'),
(30, FALSE, 3, 1, 200000, 'RUR', NULL, '1976-08-09', '{41}'),
(31, FALSE, 3, 1, 230000, 'RUR', NULL, '1998-07-22', '{41}'),
(32, FALSE, 3, 2, 180000, 'RUR', NULL, '1999-11-06', '{41}'),
(33, FALSE, 3, 1, 160000, 'RUR', NULL, '1987-08-01', '{41}'),
(34, FALSE, 3, 1, 190000, 'RUR', NULL, '1986-07-11', '{41, 12}'),
(35, FALSE, 3, 2, 230000, 'RUR', NULL, '1985-08-12', '{41}'),
(36, FALSE, 3, 1, 220000, 'RUR', NULL, '1982-09-08', '{41}'),
(37, FALSE, 3, 2, 150000, 'RUR', NULL, '1991-09-16', '{41}'),
(38, FALSE, 3, 1, 4000, 'USD', NULL, '1989-08-23', '{41, 7}'),
(39, FALSE, 3, 2, 360000, 'RUR', NULL, '1987-07-15', '{41}'),
(40, FALSE, 3, 1, 500000, 'RUR', NULL, '1985-06-17', '{41}'),
(41, FALSE, 3, 1, 330000, 'RUR', NULL, '2001-06-18', '{41}'),
(42, FALSE, 3, 2, 290000, 'RUR', NULL, '2002-11-21', '{41}'),
(43, FALSE, 3, 1, 120000, 'RUR', NULL, '1979-11-12', '{41}'),
(44, FALSE, 3, 1, 250000, 'RUR', NULL, '1984-11-14', '{41, 1}'),
(45, FALSE, 3, 2, 150000, 'RUR', NULL, '1997-09-07', '{41}'),
(46, FALSE, 3, 1, 550000, 'RUR', NULL, '1996-12-29', '{41}'),
(47, FALSE, 3, 1, 370000, 'RUR', NULL, '1993-06-25', '{41}'),
(48, FALSE, 3, 2, 150000, 'RUR', NULL, '1992-08-17', '{41}'); 

INSERT INTO vacancy (
       vacancy_id, name, work_schedule, 
       disabled, area_id, creation_time, 
       archived )
VALUES
(1, 'водитель грузового', 'Гибкий график', FALSE, 1, '2020-01-01', TRUE),
(2, 'водитель', 'Гибкий график', FALSE, 1, '2020-02-01', TRUE),
(3, 'водитель грузового', 'Гибкий график', FALSE, 1, '2020-01-01', TRUE),
(4, 'водитель грузового', 'Гибкий график', FALSE, 1, '2020-02-01', TRUE),
(5, 'водитель грузового', 'Гибкий график', FALSE, 2, '2020-03-01', TRUE),
(6, 'водитель грузового', 'Гибкий график', FALSE, 1, '2020-04-01', TRUE),
(7, 'водитель грузового', 'Гибкий график', FALSE, 3, '2020-05-01', TRUE),
(8, 'водитель фуры', 'Гибкий график', FALSE, 1, '2020-06-01', TRUE),
(9, 'водитель грузового', 'Гибкий график', FALSE, 1, '2020-07-01', TRUE),
(10, 'водитель грузового', 'Гибкий график', FALSE, 4, '2020-08-01', TRUE),
(11, 'водитель лу', 'Гибкий график', FALSE, 1, '2020-09-01', TRUE),
(12, 'водитель грого', 'Гибкий график', FALSE, 1, '2020-10-01', TRUE),
(13, 'водитель грового', 'Гибкий график', FALSE, 6, '2020-12-01', TRUE),
(14, 'водитель грузового', 'Гибкий график', FALSE, 1, '2021-02-01', TRUE),
(15, 'водитель гр', 'Гибкий график', FALSE, 1, '2021-03-01', TRUE),
(16, 'водитель грузового', 'Гибкий график', FALSE, 2, '2021-12-01', TRUE),
(17, 'Аналитик', 'Удаленная работа', FALSE, 1, '2021-01-12', TRUE), 
(18, 'Аналитик', 'Удаленная работа', FALSE, 1, '2021-02-12', TRUE),
(19, 'Аналитик', 'Удаленная работа', FALSE, 1, '2021-03-12', TRUE), 
(20, 'Аналитик', 'Удаленная работа', FALSE, 1, '2021-04-12', TRUE),
(21, 'Аналитик', 'Удаленная работа', FALSE, 1, '2021-01-14', TRUE), 
(22, 'Аналитик Разработчик', 'Удаленная работа', FALSE, 7, '2022-01-12', TRUE),
(23, 'Аналитик Разработчик', 'Удаленная работа', FALSE, 7, '2022-01-12', TRUE),
(24, 'Аналитик', 'Удаленная работа', FALSE, 2, '2021-01-14', TRUE), 
(25, 'Аналитик', 'Удаленная работа', FALSE, 2, '2022-03-24', TRUE),
(26, 'Разработчик', 'Удаленная работа', FALSE, 2, '2021-01-24', TRUE),
(27, 'Разработчик', 'Удаленная работа', FALSE, 2, '2021-03-22', TRUE);
 ```


### 1.Выгрузить число созданных вакансий (в динамике по месяцам), опубликованных в России, в названии которых встречается слово «водитель», предлагающих «Гибкий график» работы, за 2020-2021 годы.Важно, чтобы вакансии на момент сбора данных не были удаленными / заблокированными.

```SQL
--- код для постгре (ILIKE ищет регистронезависимо)
SELECT EXTRACT(YEAR FROM creation_time) as year,
       EXTRACT(MONTH FROM creation_time) as month,
       COUNT(*) count_vacancion
FROM vacancy v
JOIN area a ON v.area_id = a.area_id
WHERE name ILIKE '%водитель%'
      AND disabled = FALSE
      AND work_shedule = 'Гибкий график'
      AND coгntry_name = 'Россия'
      AND creation_time LIKE '%2020%' OR '%2021%'
GROUP BY 1, 2

```

### 2. Выяснить, в каких регионах РФ (85 штук) выше всего доля вакансий, предлагающих удаленную работу. Вакансии должны быть не заархивированными, не заблокированными и не удаленными, и быть созданными в 2021-2022 годах.


```SQL
SELECT a.region_name, COUNT(*)::decimal / COUNT(*) OVER() as share_online_work
FROM vacancy v
JOIN area a ON v.area_id = a.area_id
WHERE disabled = FALSE
      AND work_shedule = 'Удалённая работа' --- нет поля для типа работы
      AND archived = FALSE
      AND coгntry_name = 'Россия'
      AND creation_time LIKE '%2021%' OR '%2022%'
GROUP BY a.region_name
ORDER BY 2 DESC
```


### 3.Подсчитать «вилку» (10,25,50,75 и 90 процентиль) ожидаемых зарплат (в рублях) из московских и питерских резюме,имеющих роль «разработчик» (id = 91),
по городам и возрастным группам (группы сделать как в примере таблицы ниже, не учитывать резюме без указания даты рождения — такие тоже есть). 
Возрастные группы считать на дату составления запроса.
Резюме должно быть не удалено и иметь статус «завершено». Дополнительно выяснить (при помощи того же запроса)
долю резюме по каждой группе, в которых указана ожидаемая зарплата. 

```SQL
SELECT  a.area_name,
        CASE  
        WHEN EXTRACT(YEAR FROM NOW() - r.birth_day) < 17 THEN '17 лет и младше'
        WHEN 17 < EXTRACT(YEAR FROM NOW() - r.birth_day) <= 24 THEN '17-24'
        WHEN 25 >= EXTRACT(YEAR FROM NOW() - r.birth_day) <= 34 THEN '25-34'
        WHEN 35 >= EXTRACT(YEAR FROM NOW() - r.birth_day) <= 44 THEN '35-44'
        WHEN 45 >= EXTRACT(YEAR FROM NOW() - r.birth_day) <= 54 THEN '45-54'
        ELSE '55 и старше'
        END as 'Возрастная группа',
        


FROM resume r
JOIN --- притянуть area, currency
WHERE resume_id = 91
      AND birth_day IS NOT NULL
      AND disabled = FALSE --- проверить как записывается тру/фолс
      AND is_finished = 3
      AND archived = FALSE
      AND area_name IN ('Москва', 'Питер')
      AND creation_time LIKE '%2021%' OR '%2022%'

```
