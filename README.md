# Портфолио тестировщика
В портфолио собраны проекты, выполненные во время обучения по специальности [Инженер по тестированию программного обеспечения](https://software-testing.ru/edu/3-online/331-qa-engineer#%D0%BF%D0%BE%D0%B4%D1%80%D0%BE%D0%B1%D0%BD%D0%B0%D1%8F-%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B0) 

## Исследование тестируемого продукта
**О проекте:**

Cайт [TURIZM.RU](https://www.turizm.ru/) об отдыхе и путешествиях. Новости, рассказы туристов, фотографии, впечатления, опросы и живое общение. 
На сайте возможен подбор туров, билетов и отелей.
<details>
<summary>Mindmap</summary>

***
![текст](https://raw.githubusercontent.com/ZoeIvanchuk/QA_portfolio/main/mindmap.png)

***
</details>

<details>
<summary>Тест-кейс</summary>

***
**Предварительные шаги**

Зарегистрироваться на сайте (см. тест-кейс «Регистрация»)

**Шаги**

1. Перейти на сайт https://www.turizm.ru/
2. Авторизоваться (n.karasyowa2012@yandex.ru / F7Tut4WycB)
3. Перейти на вкладку «Форум»
4. Выбрать из выпадающего списка «Советы туристам»
5. На появившейся странице нажать на «+ Задать свой вопрос»
6. Заполнить появившиеся обязательные поля:
 - «Тема» (Виза в Китай)
- «Текст вопроса» (Добрый день! Нужна ли виза в Китай?)
7. Нажать на кнопку «Опубликовать»

**Ожидаемый результат**

1. На форуме в разделе «Советы туристам» появилась новая тема для обсуждения с введенными на шаге 5 названием и текстом. Тема активна, на нее можно ответить.
2. Новая тема отображается первой в списке тем раздела «Советы туристам» (как самая релевантная по времени создания).

***
</details>

<details>
<summary>SQL-запросы</summary>
 
***
 
Написать запрос для создания двух таблиц и всех индексов/констрейнтов, где любое текстовое поле размеров 50 символов.
```
  CREATE TABLE students (
  id_student bigint NOT NULL,
  name varchar(50),
  course varchar(50) NOT NULL
);

CREATE TABLE courses (
  id_course bigint NOT NULL,
  course_name varchar(50) NOT NULL,
  course_desc varchar(50)
);

ALTER TABLE students
ADD CONSTRAINT pk_course PRIMARY KEY (course);

INSERT INTO courses (id_course, course_name, course_desc)
VALUES (1, 'REST', 'Изучаем API'),
       (2, 'ШНАТ', 'Школа для новичков'),
       (3, 'Postman', 'Автоматизация API');

COMMIT;

ALTER TABLE courses 
ADD CONSTRAINT fg_course FOREIGN KEY (course_name)
REFERENCES students (course);

COMMIT;
```

//Удалить тестовые данные
- colors — в тайтле цвета есть слово "Тестовый" или "Лабуда"
- размеры — размер 9999
- orders — в адресе есть слово "тест"
- items — в title / description есть слово "Тестовый" или "Лабуда". Или размер — 9999

DELETE FROM colors
WHERE title LIKE '%Тестовый%' OR title LIKE '%Лабуда%';
COMMIT;

DELETE FROM sizes
WHERE title = '9999';
COMMIT;

DELETE FROM orders
WHERE addr LIKE '%тест%';
COMMIT;

DELETE FROM items
WHERE title LIKE '%Тестовый%' OR title LIKE '%Лабуда%' OR description LIKE '%Тестовый%' OR description LIKE '%Лабуда%' OR sizes = '9999';
COMMIT;

//Сделать запрос в интернет-магазине. Нас интересует таблица last_views. Сколько товаров просматривал какой пользователь:
id пользователя
сколько товаров он просмотрел
Вначале вывести тех, кто просматривает много — ищем потенциальных клиентов, чтобы предложить им рекламу.
Те, кто просматривал меньше 4 товаров, меня не интересуют.

SELECT user_id, COUNT(item) AS viewed_items
FROM last_views
GROUP BY user_id
HAVING COUNT(item) > 3
ORDER BY viewed_items DESC

***
</details>
