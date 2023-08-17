QA инженер

Проводила тестирование сайта: https://teachers.skyeng.ru/schedule :

* первоначально было проведено smoke тестирование. При прохождении smoke тестов (https://app.qase.io/project/LWN) не выявлено дальнейших препятствий для проведения функционального тестирования. (test run: https://app.qase.io/run/LWN/dashboard/5)

* функциональное тестирование было произведено по чек листуSitechco.ru, при прохождении которого не было обнаружено багов (test run: Sitechco.ru )

* приемочное тестирование https://app.qase.io/project/LWN, при прохождении которого (test run https://app.qase.io/run/LWN/dashboard/3) был выявлен баг https://qabugreport5.atlassian.net/jira/software/c/projects/KY1/issues/KY1-1

* проводилось регрессионное тестирование (проводилась проверка по добавлению новых уроков, отмене и переносу уроков) по чек листу Sitechco.ru 

* тестирования API по тест кейсам https://app.qase.io/project/LWN?suite=4


Опыт написания чек листов (например к сайту: https://cloud.ru/ru): https://docs.google.com/spreadsheets/d/1i9Fde0qkjNQSA48mW3uuMjaym68n9ovf/edit?usp=sharing&ouid=112700401287224399501&rtpof=true&sd=true

Опыт написания SQL запросов по следующим данным 

![документ](https://github.com/jmailgew5/QA-ENGINEER/assets/142330325/77c9341f-7968-40ed-8070-a8078ffd53d4)

-- Создание таблицы animal_classes

CREATE TABLE animal_classes (  
    id INTEGER,
    class TEXT
);

-- Проверка  таблицы animal_classes

SELECT *
FROM animal_classes ;

-- Создание таблицы animal_info

CREATE TABLE animal_info (  
    name TEXT,
    class INTEGER,
	owner TEXT
);

-- Проверка таблицы animal_info

SELECT *
FROM animal_info ;

-- Ввод данных в таблицу animal_classes


INSERT INTO animal_classes (id, class) 
VALUES (1, 'кошка'),
       (2, 'собака');

-- Ввод данных в таблицу animal_info
	   
INSERT INTO animal_info(name, class, owner) 
VALUES ('Кити', 1, 'Ваня'),
       ('Мити', 2, 'Ваня'),
	   ('Пити', 1, 'Петя');
	   
-- Сколько всего животных у Вани

SELECT owner, COUNT (*)
FROM animal_info
WHERE owner = 'Ваня'
GROUP BY owner ;


-- Уникальные имена всех кошек отсортированные по алфавиту

SELECT DISTINCT (i.name)
FROM animal_info AS i
INNER JOIN animal_classes AS c
ON c.id = i.class
WHERE c.class = 'кошка'
ORDER BY name ;



-- Найти количество животных каждого класса. Вывести количество и имя класса

SELECT COUNT (i.class),
c.class
FROM animal_classes AS c
INNER JOIN animal_info AS i
ON c.id = i.class
GROUP BY c.class ;





