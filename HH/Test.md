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
       code INT PRIMARY KEY,
       rate DECIMAL
);

INSERT INTO currency (code, rate) VALUES
(1, 1),
(2, 95.5),
(3, 104.5);

INSERT INTO area(area_id, area_name, region_name, country_name) VALUES
(), --- country_name = 'Россия' 'Беларусь' 'Казахстан'
---   area_name Москва Санкт-Петербург Аламата Минск Самара Владивосток Норильск Екатеринбург
--- region_name in 'Московская область' 'Ленинградская область' 'Свердловская область' 'Самарская область' 'Приморский край' 'Минская область' 'Алматинская область' 'Красноярский край'

INSERT INTO resume (
       resume_id,
       disabled,  --- TRUE/FALSE
       is_finished, --- 1,2,3 need more 1 
       area_id, --- 1-6
       compensation, --- 30k - 500k
       currency, --- 1, 2, 3 code from currency
       position, --- должность . хз
       birth_day, --- от 17 лет до 66
       role_id_list --- хз что это - дропнуть нахуй
) VALUES
(),

INSERT INTO vacancy (
       vacancy_id, 
       name, --- водитель. чот ещё
       work_schedule, --- 'гибкий график'. удалёнка гибрид
       disabled BOOLEAN, --- FALSE/TRUE
       area_id INT,
       creation_time, --- 2020 2021 2022 2023
       archived --- FALSE/TRUE 
);

;


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
