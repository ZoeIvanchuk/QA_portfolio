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
