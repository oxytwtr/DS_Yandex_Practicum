**Базовый SQL**

Темы 1-6 

Схема базы данных:

<img src='https://github.com/oxytwtr/DS_Yandex_Practicum/raw/main/18%20-%20SQL%20EXER/description/BasicSQL_database_scheme.png' align="left">

**`actor`**

Содержит данные об актёрах и актрисах.

Таблица включает такие поля:

- первичный ключ `actor_id` — идентификатор актёра или актрисы;
- `first_name` — имя актёра или актрисы;
- `last_name` — фамилия актёра или актрисы;
- `last_update` — дата последнего обновления данных об актёре или актрисе.

**`album`**

Содержит информацию об альбомах.

Таблица включает такие поля:

- первичный ключ `album_id` — идентификатор альбома;
- `title` — название альбома;
- внешний ключ `artist_id` (ссылается на таблицу **`artist`** ) — идентификатор исполнителя.

**`artist`**

Содержит данные об исполнителях.

Таблица состоит из полей:

- первичный ключ `artist_id` — идентификатор исполнителя;
- name — имя исполнителя.

**`category`**

Содержит информацию о категориях фильмов.

Таблица состоит из полей:

- первичный ключ category_id — идентификатор категории;
- `name` — название категории, например:
  - Comedy — комедия;
  - Sci-Fi — научная фантастика.
- `last_update` — дата последнего обновления данных о категории.

**`client`**

Содержит данные о покупателях.

Таблица включает поля:

- первичный ключ `customer_id` — идентификатор покупателя;
- `first_name` — имя покупателя;
- `last_name` — фамилия покупателя;
- `company` — место работы;
- `address` — адрес покупателя;
- `city` — город проживания;
- `state` — штат или регион;
- `country` — страна;
- `postal_code` — почтовый индекс;
- `phone` — телефон;
- `fax` — факс;
- `email` — электронная почта;
- внешний ключ `support_rep_id` (отсылает к таблице **`staff`** ) — идентификатор сотрудника поддержки, который обрабатывал запрос покупателя.

**`film_actor`**

Содержит информацию о том, в каких фильмах играли актёры и актрисы из таблицы **`actor`**.

Таблица включает поля:

- составной первичный ключ: `actor_id` (отсылает к таблице **`actor`** ) — идентификатор актёра или актрисы;
- `film_id` (отсылает к таблице **`movie`** ) — идентификатор фильма;
- `last_update` — дата последнего обновления данных о фильмах.

**`film_category`**

Содержит информацию о категориях фильмов из таблицы **`movie`** .

В таблицу входят поля:

- первичный ключ `film_id` — идентификатор фильма;
- внешний ключ `category_id` (отсылает к таблице **`category`** ) — идентификатор категории;
- `last_update` — дата последнего обновления данных о фильмах и категориях.

**`genre`**

Содержит информацию о жанрах музыки и кино.

В таблицу входят поля:

- первичный ключ `genre_id` — идентификатор жанра;
- `name` — название жанра, например:
  - Blues — блюз;
  - Pop — поп-музыка.

**`invoice`**

Содержит данные о заказах и выставленных счетах.

Таблица включает поля:

- первичный ключ `invoice_id` — идентификатор счёта;
- внешний ключ `customer_id` (отсылает к таблице **`client`** ) — идентификатор покупателя;
- `invoice_date` — дата выставления счёта;
- `billing_address` — адрес выставления счёта;
- `billing_city` — город выставления счёта;
- `billing_state` — штат или регион выставления счёта;
- `billing_country` — страна выставления счёта;
- `billing_postal_code` — почтовый индекс адреса выставления счёта;
- `total` — стоимость заказа в долларах.

**`invoice_line`**

Содержит информацию о том, какие музыкальные треки входят в заказ.

Таблица состоит из полей:

- первичный ключ `invoice_line_id` — идентификатор строки;
- внешний ключ `invoice_id` (отсылает к таблице **`invoice`** ) — идентификатор заказа;
- внешний ключ `track_id` (отсылает к таблице **`track`** ) — идентификатор трека;
- `unit_price` — цена трека в долларах;
- `quantity` — количество таких треков в заказе.

**`media_type`**

Содержит информацию о форматах видео и аудио.

Таблица включает поля:

- первичный ключ `media_type_id` — идентификатор формата;
- `name` — название формата, например:
  - AAC audio file — аудиофайл в формате AAC;
  - Protected MPEG-4 video file — защищённый формат MPEG-4 для видео.

**`movie`**

Содержит информацию о фильмах.

Таблица состоит из полей:

- первичный ключ `film_id` — идентификатор фильма;
- `title` — название фильма;
- `description` — описание фильма;
- `release_year` — год выхода;
- `language_id` — идентификатор языка фильма;
- `rental_duration` — срок аренды в днях;
- `rental_rate` — цена аренды в долларах;
- `length` — продолжительность фильма в минутах;
- `replacement_cost` — стоимость замены;
- `rating` — возрастной рейтинг, например:
  - PG — детям рекомендуется смотреть такой фильм с родителями;
  - PG-13 — детям до 13 лет смотреть такой фильм нежелательно.
- `last_update` — дата последнего обновления данных о фильме в таблице;
- `special_features` — особые характеристики;
- `fulltext` — техническое поле для индексации.

**`playlist`**

Содержит информацию о плейлистах.

Таблица включает поля:

- первичный ключ `playlist_id` — идентификатор плейлиста;
- `name` — название плейлиста.

**`playlist_track`**

Содержит информацию о том, какие треки входят в плейлисты.

В таблицу входят поля:

- первичный ключ `playlist_id` — идентификатор плейлиста;
- внешний ключ `track_id` (отсылает к таблице **`track`** ) — идентификатор трека.

**`staff`**

Содержит данные о сотрудниках.

В таблицу входят поля:

- первичный ключ `employee_id` — идентификатор сотрудника;
- `first_name` — имя сотрудника;
- `last_name` — фамилия сотрудника;
- `title` — должность сотрудника;
- внешний ключ `reports_to` (отсылает к другой записи таблицы **`staff`** ) — идентификатор менеджера сотрудника;
- `birth_date` — дата рождения сотрудника;
- `hire_date` — дата, когда сотрудника приняли на работу;
- `address` — адрес сотрудника;
- `city` — город проживания сотрудника;
- `state` — штат или регион проживания сотрудника;
- `country` — страна проживания сотрудника;
- `postal_code` — почтовый индекс;
- `phone` — телефон;
- `fax` — факс;
- `email` — электронная почта.

**`track`**

Содержит данные о музыкальных треках.

Таблица включает поля:

- первичный ключ `track_id` — идентификатор трека;
- `name` — название трека;
- внешний ключ `album_id` (отсылает к таблице **`album`** ) — идентификатор альбома;
- внешний ключ `media_type_id` (отсылает к таблице **`media_type`** ) — идентификатор аудиоформата;
- внешний ключ `genre_id` (отсылает к таблице **`genre`** ) — идентификатор жанра трека;
- `composer` — автор трека;
- `milliseconds` — длительность трека в миллисекундах;
- `bytes` — размер трека в байтах;
- `unit_price` — стоимость трека в долларах.

Тема 7 
Схемы данных и оконные функции

В практической части вы будете работать со схемой `tools_shop`. Некоторые таблицы этой схемы названы так же, как таблицы в схеме `online_store`. Это не значит, что содержание этих таблиц одинаковое, — схемы относятся к разным отделам интернет-магазина. В этом уроке вы познакомитесь с таблицами схемы `tools_shop`. 

Так выглядит ER-диаграмма схемы `tools_shop`.

<img src='https://github.com/oxytwtr/DS_Yandex_Practicum/raw/main/18%20-%20SQL%20EXER/description/tools_shop_ER_scheme.png' align="left">

Таблица **`users`**

Cодержит данные о пользователях.

- `user_id` — Идентификатор пользователя, первичный ключ таблицы
- `first_name` — Имя пользователя
- `last_name` — Фамилия пользователя
- `email` — Электронный адрес пользователя
- `created_at` — Дата создания аккаунта пользователя

Таблица **`events`**

Содержит данные о событиях.

- `event_id` — Идентификатор события, первичный ключ таблицы
- `event_time` — Дата и время события
- `event_name` — Название события
- `user_id` — Идентификатор пользователя, внешний ключ, отсылающий к таблице **`users`**
- `platform` — Тип устройства пользователя
- `referrer` — Источник события пользователя

Типов событий в поле event_name два: 
- view_item — просмотр товара;
- view_user_profile — просмотр сохранённых товаров другого пользователя.

Значение в поле referrer показывает, какой источник просматривал пользователь перед тем, как совершилось событие. Источники могут быть внешними:

- google_search — поисковая система Google;
- promo_email_click — рассылка магазина.

В поле referrer могут быть указаны и источники внутри сайта:
- item_page — страница товара;
- user_wishlist — страница сохранённых товаров другого пользователя;
- shopping_cart — корзина;
- home — главная страница магазина.

Таблица **`event_x_parameter`**

Содержит детальную информацию о событиях.

- `event_id` — Идентификатор события, внешний ключ, отсылающий к таблице **`events`**
- `parameter_name` — Параметр детализации
- `parameter_value` — Значение параметра

Если в поле `parameter_name` указан `item_id`, то в `parameter_value` будет храниться идентификатор товара, который просматривал пользователь.

Если в поле parameter_name указан `viewed_user_id`, то в `parameter_value` будет храниться идентификатор пользователя, чью страницу с сохранёнными товарами смотрел другой пользователь.

Таблица **`orders`**

Содержит детальные данные о заказах пользователей.

- `order_id` — Идентификатор заказа, первичный ключ таблицы
- `user_id` — Идентификатор пользователя, оформившего заказ
- `total_amt` — Общая сумма заказа
- `items_cnt` — Количество товаров в заказе
- `created_at` — Дата, когда пользователь оформил заказ, но ещё не оплатил его
- `paid_at` — Дата оплаты заказа

Таблица **`items`**

Содержит данные о товарах.

- `item_id` — Идентификатор товара, первичный ключ таблицы
- `category` — Категория товара
- `item_name` — Название товара
- `price` — Стоимость

Таблица **`order_x_item`**

Содержит данные о связи заказа с товарами.

- `order_id` — Идентификатор заказа, внешний ключ, отсылающий к таблице **`orders`**
- `item_id` — Идентификатор товара, внешний ключ, отсылающий к таблице **`items`**

Таблица **`costs`**

Содержит данные о стоимости привлечения пользователей.

- `created_at` — Дата
- `costs` — Стоимость привлечения