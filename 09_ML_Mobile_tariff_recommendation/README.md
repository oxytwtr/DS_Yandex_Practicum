# Рекомендация тарифов

В вашем распоряжении данные о поведении клиентов, которые уже перешли на эти тарифы (из проекта курса «Статистический анализ данных»). Нужно построить модель для задачи классификации, которая выберет подходящий тариф. Предобработка данных не понадобится — вы её уже сделали.

Постройте модель с максимально большим значением *accuracy*. Чтобы сдать проект успешно, нужно довести долю правильных ответов по крайней мере до 0.75. Проверьте *accuracy* на тестовой выборке самостоятельно.

 # Построение модели для рекомендации тарифов
 
Исходные данные от заказчика:
 Требуется построить систему, способную проанализировать поведение клиентов и предложить пользователям новый тариф: «Смарт» или «Ультра».
 
 Предоставлен датасет с данными о поведении клиентов, которые перешли на тарифы  «Смарт» или «Ультра». Предобработка данных выполнена в предыдущем проекте. 
 
 Нужно построить модель для задачи классификации, которая выберет подходящий тариф. 
  
 План работы:

- Изучение общей информации о данных
- Разделение данных на `обучающую`, `валидационную` и `тестовую` выборки
- Исследование качеств разных моделей с разными гиперпараметрами
- Выбор оптимальной модели и ее гиперпараметров
- Проверка качества модели на тестовой выборке
- Проверка модели на вменяемость


Описание данных:

Каждый объект в наборе данных — это информация о поведении одного пользователя за месяц. Известно:

- `сalls` — количество звонков,
- `minutes` — суммарная длительность звонков в минутах,
- `messages` — количество sms-сообщений,
- `mb_used` — израсходованный интернет-трафик в Мб,
- `is_ultra` — каким тарифом пользовался в течение месяца («Ультра» — 1, «Смарт» — 0).