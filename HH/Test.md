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
       role_id_list int[]
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
(6, 'Владивосток', 'Приморский край', 'Россия'),
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
(1, FALSE, 3, 1, 30000, 'RUR', NULL, '2008-01-01', '{91, 42}'),
(2, FALSE, 3, 1, 25000, 'RUR', NULL, '2010-02-01', '{91, 2}'),
(3, FALSE, 3, 2, 10000, 'RUR', NULL, '2012-01-01', '{91}'),
(4, FALSE, 3, 2, 8000, 'EUR', NULL, '1980-01-01', '{91}'),
(5, FALSE, 3, 1, 6000, 'USD', NULL, '1976-01-01', '{91}'),
(6, FALSE, 3, 1, 234000, 'RUR', NULL, '1990-02-01', '{91}'),
(7, FALSE, 3, 2, 400000, 'RUR', NULL, '1980-11-09', '{91, 1}'),
(8, FALSE, 3, 1, 60000, 'RUR', NULL, '2000-11-05', '{91}'),
(9, FALSE, 3, 1, 350000, 'RUR', NULL, '1999-01-06', '{91}'),
(10, FALSE, 3, 1, 3000, 'EUR', NULL, '1988-12-11', '{91}'),
(11, FALSE, 3, 2, 780000, 'RUR', NULL, '1975-01-01', '{91, 55}'),
(12, FALSE, 3, 1, 80000, 'RUR', NULL, '2000-08-11', '{91}'),
(13, FALSE, 3, 2, 250000, 'RUR', NULL, '1999-01-21', '{91}'),
(14, FALSE, 3, 2, 32000, 'RUR', NULL, '2009-12-01', '{91}'),
(15, FALSE, 3, 1, 125000, 'RUR', NULL, '1980-01-01', '{91, 22}'),
(16, FALSE, 3, 1, 350000, 'RUR', NULL, '2000-11-21', '{91}'),
(17, FALSE, 3, 1, 66000, 'RUR', NULL, '2001-01-04', '{91}'),
(18, FALSE, 3, 1, 30000, 'RUR', NULL, '2000-01-01', '{91, 99}'),
(19, FALSE, 3, 1, 360000, 'RUR', NULL, '2000-12-01', '{91}'),
(20, FALSE, 3, 2, 500000, 'RUR', NULL, '1982-01-08', '{91}'),
(21, FALSE, 3, 1, 250000, 'RUR', NULL, '2003-04-11', '{91}'),
(22, FALSE, 3, 1, 330000, 'RUR', NULL, '2000-06-01', '{91}'),
(23, FALSE, 3, 1, 122000, 'RUR', NULL, '1990-11-17', '{91, 11}'),
(24, FALSE, 3, 1, 3000, 'EUR', NULL, '1994-12-11', '{91}'),
(25, FALSE, 3, 2, 10000, 'USD', NULL, '1993-06-07', '{91, 2}'),
(26, FALSE, 3, 2, 320000, 'RUR', NULL, '1991-05-15', '{91}'),
(27, FALSE, 3, 1, 130000, 'RUR', NULL, '1998-01-11', '{91}'),
(28, FALSE, 3, 1, 170000, 'RUR', NULL, '1995-05-01', '{91,77}'),
(29, FALSE, 3, 2, 190000, 'RUR', NULL, '1996-09-01', '{91}'),
(30, FALSE, 3, 1, 200000, 'RUR', NULL, '1976-08-09', '{91}'),
(31, FALSE, 3, 1, 230000, 'RUR', NULL, '1998-07-22', '{91}'),
(32, FALSE, 3, 2, 180000, 'RUR', NULL, '1999-11-06', '{91}'),
(33, FALSE, 3, 1, 160000, 'RUR', NULL, '1987-08-01', '{91}'),
(34, FALSE, 3, 1, 190000, 'RUR', NULL, '1986-07-11', '{91, 12}'),
(35, FALSE, 3, 2, 230000, 'RUR', NULL, '1985-08-12', '{91}'),
(36, FALSE, 3, 1, 220000, 'RUR', NULL, '1982-09-08', '{91}'),
(37, FALSE, 3, 2, 150000, 'RUR', NULL, '1991-09-16', '{91}'),
(38, FALSE, 3, 1, 4000, 'USD', NULL, '1989-08-23', '{91, 7}'),
(39, FALSE, 3, 2, 360000, 'RUR', NULL, '1987-07-15', '{91}'),
(40, FALSE, 3, 1, 500000, 'RUR', NULL, '1985-06-17', '{91}'),
(41, FALSE, 3, 1, 330000, 'RUR', NULL, '2001-06-18', '{91}'),
(42, FALSE, 3, 2, 290000, 'RUR', NULL, '2002-11-21', '{91}'),
(43, FALSE, 3, 1, 120000, 'RUR', NULL, '1979-11-12', '{91}'),
(44, FALSE, 3, 1, 250000, 'RUR', NULL, '1984-11-14', '{91, 1}'),
(45, FALSE, 3, 2, 150000, 'RUR', NULL, '1997-09-07', '{91}'),
(46, FALSE, 3, 1, 550000, 'RUR', NULL, '1996-12-29', '{91}'),
(47, FALSE, 3, 1, 370000, 'RUR', NULL, '1993-06-25', '{91}'),
(48, FALSE, 3, 2, 150000, 'RUR', NULL, '1992-08-17', '{91}'),
(50, FALSE, 3, 1, NULL, 'RUR', NULL, '1968-01-01', '{91, 42}'),
(51, FALSE, 3, 1, NULL, 'RUR', NULL, '1968-01-01', '{91, 42}'),
(52, FALSE, 3, 1, NULL, 'RUR', NULL, '1968-02-01', '{91, 2}'),
(53, FALSE, 3, 2, NULL , 'RUR', NULL, '1969-01-01', '{91, 66}'),
(54, FALSE, 3, 2, NULL, 'EUR', NULL, '1969-01-01', '{91}'),
(55, FALSE, 3, 1, NULL, 'USD', NULL, '1969-01-01', '{91}'),
(56, FALSE, 3, 1, NULL, 'RUR', NULL, '1969-02-01', '{91}'),
(57, FALSE, 3, 2, NULL, 'RUR', NULL, '1967-11-09', '{91, 41}'),
(58, FALSE, 3, 1, NULL, 'RUR', NULL, '1967-11-05', '{91}'),
(59, FALSE, 3, 1, NULL, 'RUR', NULL, '1967-01-06', '{91}'),
(60, FALSE, 3, 1, NULL, 'EUR', NULL, '1967-12-11', '{91, 2}'),
(61, FALSE, 3, 2, NULL, 'RUR', NULL, '1967-01-01', '{91, 55}'),
(62, FALSE, 3, 1, NULL, 'RUR', NULL, '1967-08-11', '{91, 1}'),
(63, FALSE, 3, 2, NULL, 'RUR', NULL, '1967-01-21', '{91}'),
(64, FALSE, 3, 2, NULL, 'RUR', NULL, '2009-12-01', '{91}'),
(65, FALSE, 3, 1, NULL, 'RUR', NULL, '1980-01-01', '{91, 22}'),
(66, FALSE, 3, 1, NULL, 'RUR', NULL, '1990-11-21', '{91}'),
(67, FALSE, 3, 1, NULL, 'RUR', NULL, '2001-01-04', '{91}'),
(68, FALSE, 3, 1, NULL, 'RUR', NULL, '2000-01-01', '{91, 99}'),
(69, FALSE, 3, 1, NULL, 'RUR', NULL, '2000-12-01', '{91}'),
(70, FALSE, 3, 2, NULL, 'RUR', NULL, '1982-01-08', '{91, 69}'),
(71, FALSE, 3, 1, NULL, 'RUR', NULL, '2003-04-11', '{91}'),
(72, FALSE, 3, 1, NULL, 'RUR', NULL, '2000-06-01', '{91}'),
(73, FALSE, 3, 1, NULL, 'RUR', NULL, '1990-11-17', '{91, 11}'),
(74, FALSE, 3, 1, NULL, 'EUR', NULL, '1994-12-11', '{91, 77}');

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
(17, 'Аналитик', 'Удаленная работа', FALSE, 1, '2021-01-12', FALSE), 
(18, 'Аналитик', 'Удаленная работа', FALSE, 1, '2021-02-12', FALSE),
(19, 'Аналитик', 'Удаленная работа', FALSE, 1, '2021-03-12', FALSE), 
(20, 'Аналитик', 'Удаленная работа', FALSE, 1, '2021-04-12', FALSE),
(21, 'Аналитик', 'Удаленная работа', FALSE, 1, '2021-01-14', FALSE), 
(22, 'Аналитик Разработчик', 'Удаленная работа', FALSE, 7, '2022-01-12', FALSE),
(23, 'Аналитик Разработчик', 'Удаленная работа', FALSE, 7, '2022-01-12', FALSE),
(24, 'Аналитик', 'Удаленная работа', FALSE, 2, '2021-01-14', FALSE), 
(25, 'Аналитик', 'Удаленная работа', FALSE, 2, '2022-03-24', FALSE),
(26, 'Разработчик', 'Удаленная работа', FALSE, 2, '2021-01-24', FALSE),
(27, 'Разработчик', 'Удаленная работа', FALSE, 2, '2021-03-22', FALSE);
 ```


### 1.Выгрузить число созданных вакансий (в динамике по месяцам), опубликованных в России, в названии которых встречается слово «водитель», предлагающих «Гибкий график» работы, за 2020-2021 годы.Важно, чтобы вакансии на момент сбора данных не были удаленными / заблокированными.

```SQL
--- код для постгре (ILIKE ищет регистронезависимо)
SELECT EXTRACT(YEAR FROM creation_time::TIMESTAMP) as year,
       EXTRACT(MONTH FROM creation_time::TIMESTAMP) as month,
       COUNT(*) count_vacancion
FROM vacancy v
JOIN area a ON v.area_id = a.area_id
WHERE name ILIKE '%водитель%'
      AND disabled = FALSE
      AND work_schedule = 'Гибкий график'
      AND country_name = 'Россия'
      AND (creation_time LIKE '%2020%' OR creation_time LIKE '%2021%')
GROUP BY 1, 2
```

### 2. Выяснить, в каких регионах РФ (85 штук) выше всего доля вакансий, предлагающих удаленную работу. Вакансии должны быть не заархивированными, не заблокированными и не удаленными, и быть созданными в 2021-2022 годах.


```SQL
--- всего 9 вакансий, 2 не в РФ, 5 в мск (0.55), 4 в спб (0.45)
--- при группировке по egion_name, значения почему то окрглюятся, надо разобраться(!)
SELECT DISTINCT a.region_name, 
	ROUND(COUNT(*) OVER(PARTITION BY a.region_name)::decimal / COUNT(*) OVER(), 3) as share_online_work
FROM vacancy v
JOIN area a ON v.area_id = a.area_id
WHERE disabled = FALSE
      AND work_schedule = 'Удаленная работа' 
      AND archived = FALSE
      AND country_name = 'Россия'
      AND (creation_time LIKE '%2021%' OR creation_time LIKE '%2022%')

```


### 3.Подсчитать «вилку» (10,25,50,75 и 90 процентиль) ожидаемых зарплат (в рублях) из московских и питерских резюме,имеющих роль «разработчик» (id = 91),
по городам и возрастным группам (группы сделать как в примере таблицы ниже, не учитывать резюме без указания даты рождения — такие тоже есть). 
Возрастные группы считать на дату составления запроса.
Резюме должно быть не удалено и иметь статус «завершено». Дополнительно выяснить (при помощи того же запроса)
долю резюме по каждой группе, в которых указана ожидаемая зарплата. 

```SQL
WITH filter_resume AS (
	SELECT resume_id, area_id, compensation, currency,  
              (EXTRACT(YEAR FROM NOW()) - DATE_PART('year', birth_day)) as age
  	FROM resume 
  	WHERE '91' = ANY(role_id_list)  
  	  AND birth_day IS NOT NULL
      	  AND disabled = FALSE 
     	  AND is_finished = 3
), filter_area as (
	SELECT area_id, area_name
  	FROM area 
  	WHERE area_name IN ('Москва', 'Санкт-Петербург')
)

SELECT area_name,
       "Возрастная группа", 
       percentile_disc(0.10) within group (ORDER BY compensation_rub) as "10_percentile",
       percentile_disc(0.25) within group (ORDER BY compensation_rub) as "25_percentile",
       percentile_disc(0.50) within group (ORDER BY compensation_rub) as "50_percentile",
       percentile_disc(0.75) within group (ORDER BY compensation_rub) as "75_percentile",
       percentile_disc(0.90) within group (ORDER BY compensation_rub) as "90_percentile"
FROM
       (SELECT f_a.area_name,
       		CASE
       		WHEN age <= 17 THEN '17 лет и младше'
       		WHEN 17 <  age AND age <= 24 THEN '17-24'
       		WHEN 25 <= age AND age <= 34 THEN '25-34'
       		WHEN 35 <= age AND age <= 44 THEN '35-44'
       		WHEN 45 <= age AND age <= 54 THEN '45-54' 
       		ELSE '55 и старше'
       		END AS "Возрастная группа",
		f_r.compensation * c.rate as compensation_rub ---  rate некорректный в ориг.файле 
	FROm filter_resume f_r
	JOIN filter_area as f_a ON f_r.area_id = f_a.area_id
	JOIN currency AS c ON f_r.currency = c.code
) prep_tab
GROUP BY 1, 2
ORDER BY 1 
```
