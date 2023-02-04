# api_final
api final

Описание проекта:
Проект API_Yatube - это API социальной сети yatube.
С помощью api_yatube можно запрашивать данные о постах, группах, комментариях в социальной сети Yatube, а также создавать новые.

Как запустить проект:
1. Клонировать репозиторий командой "git clone <ссылка на репозиторий>."

2. Создать и активировать виртуальное окружении в корневой директории проекта:
    python -m venv venv (Создать виртуальное окружение)
    source venv/bin/activate (Активировать виртуальное окружение)

3. Установить зависимости командой <pip install -r requirements.txt>

4. Выполните миграции командой <python manage.py migrate>

5. <python manage.py runserver> для запуска dev-сервера =)

Эндпоинты для взаимодействия с ресурсами:
1.  Получить список всех постов (GET):
http://127.0.0.1:8000/api/v1/posts/

2.  Получить определенный пост (GET):
http://127.0.0.1:8000/api/v1/posts/1/

3.  Получить коментарии определенного поста (GET):
http://127.0.0.1:8000/api/v1/posts/1/comments/

4.  Получить список всех групп (GET):
http://127.0.0.1:8000/api/v1/groups/

5.  Создать новый пост (POST): (Требуется аутентификация)
http://127.0.0.1:8000/api/v1/posts/

------Примеры запросов к API:

Пример POST-запроса. Добавление нового поста.
POST http://127.0.0.1:8000/api/v1/posts/
{
    "text": "текст для README"
}


------Пример ответа:


{
    "id": 1,
    "author": "Санечка",
    "text": "текст для README",
    "pub_date": "2023-02-03T20:55:58.888496Z",
    "image": null,
    "group": null
}



------Пример GET-запроса: получаем весь список постов.
GET http://127.0.0.1:8000/api/v1/posts/


------Пример ответа:


[
    {
        "id": 1,
        "author": "Санечка",
        "text": "текст для README",
        "pub_date": "2023-02-03T20:55:58.888496Z",
        "image": null,
        "group": null
    },
    {
        "id": 2,
        "author": "Санечка",
        "text": "текст для README2",
        "pub_date": "2023-02-03T21:04:50.436645Z",
        "image": null,
        "group": null
    }
]