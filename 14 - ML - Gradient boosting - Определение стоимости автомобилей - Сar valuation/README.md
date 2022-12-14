# Определение стоимости автомобилей
**Описание проекта (оригинальное)**

Сервис по продаже автомобилей с пробегом «Не бит, не крашен» разрабатывает приложение для привлечения новых клиентов. В нём можно быстро узнать рыночную стоимость своего автомобиля. В вашем распоряжении исторические данные: технические характеристики, комплектации и цены автомобилей. Вам нужно построить модель для определения стоимости. 

Заказчику важны:

- качество предсказания;
- скорость предсказания;
- время обучения.

**Исходные данные от заказчика**

Набор данных находится в файле `/datasets/autos.csv`

Признаки

| №  | Наименование признака | Описание от заказчика                           | Примечание      |
|:---|:----------------------|:------------------------------------------------|:----------------|
| 1  | DateCrawled           | дата скачивания анкеты из базы                  |                 |
| 2  | VehicleType           | тип автомобильного кузова                       |                 |
| 3  | RegistrationYear      | год регистрации автомобиля                      |                 |
| 4  | Gearbox               | тип коробки передач                             |                 |
| 5  | Power                 | мощность (л. с.)                                |                 |
| 6  | Model                 | модель автомобиля                               |                 |
| 7  | Kilometer             | пробег (км)                                     |                 |
| 8  | RegistrationMonth     | месяц регистрации автомобиля                    |                 |
| 9  | FuelType              | тип топлива                                     |                 |
| 10 | Brand                 | марка автомобиля                                |                 |
| 11 | Repaired              | была машина в ремонте или нет                   |                 |
| 12 | DateCreated           | дата создания анкеты                            |                 |
| 13 | NumberOfPictures      | количество фотографий автомобиля                |                 |
| 14 | PostalCode            | почтовый индекс владельца анкеты (пользователя) |                 |
| 15 | LastSeen              | дата последней активности пользователя          |                 |
| 16 | Price                 | цена (евро)                                     | Целевой признак |


**Задача**

- Выбрать и построить модель определяющую целевой признак (цена)
- Для оценки качества моделей применить метрику RMSE
- Значение метрики RMSE должно быть меньше 2500
- Использовать минимум две модели, одна из них не бустинг, другая - LightGBM
 
**План работы**

- Открыть и изучить данные
- Выполнить предобработку данных
- Подготовить выборки
- Применить кодирование категориальных признаков.
- Выбрать модели и обосновать
- Обучить выбранные модели, используя разные гиперпараметры. Для обучения предполагается использовать кросс-валидацию
- Выбрать наилучшую модель и обосновать
- Предсказать на тестовой выборке, сохранить итоговые RMSE, время обучения и предсказания
