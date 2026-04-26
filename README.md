Первый запуск
docker compose up --build

Следите за логами: db должен показать "database system is ready to accept connections".

Подключитесь к контейнеру web:
docker compose exec web bash

Это откроет терминал внутри контейнера web (где Django установлен).

Примените миграции (внутри контейнера)
python manage.py migrate
Это создаст все таблицы в БД. Должно пройти без ошибок, если db готов.

При необходимости работы с тестовыми данными, загрузите фикстуры (внутри контейнера):
python manage.py loaddata products/fixtures/categories.json
python manage.py loaddata products/fixtures/products.json
Это добавит тестовые данные (категории и продукты).

6. Выйдите из контейнера
exit (чтобы выйти из bash в контейнере).
