# FileStorage

FileStorage — это веб-приложение для хранения и управления файлами. Пользователи могут загружать файлы, организовывать их по категориям (папкам), а также управлять ими с помощью различных действий, таких как переименование, удаление и перемещение.

## Основные функции

- **Категории (папки)**:
  - Создание пользовательских категорий
  - Переименование и удаление категорий
  - Поддержка стандартных категорий (documents, images, music, video)

- **Работа с файлами**:
  - Загрузка, скачивание, переименование и удаление файлов
  - Перемещение файлов в **избранное** (favorites)
  - Перемещение файлов в **корзину** (trash) с возможностью восстановления или окончательного удаления

- **История действий**:
  - Сохранение всех действий пользователя (вход, регистрация, операции с файлами и категориями)
  - Просмотр истории на отдельной странице

- **Статистика и интерфейс**:
  - Sidebar с информацией о пользователе (никнейм, уведомления)
  - Статистика за день (загрузки, скачивания, удаления)
  - Отображение используемого дискового пространства

## Технологии

- Бэкенд: FastAPI (Python)
- Фронтенд: React.js
- База данных: MongoDB
- ORM/ODM: Beanie
- Хранение файлов: локальная директория `STORAGE`

## Запуск проекта

1. Клонируйте репозиторий:

    ```bash
    git clone https://github.com/AlekseyAmp/FileStorage-FastAPI-React.git
    cd FileStorage-FastAPI-React
    ```

2. Создайте директорию для хранения файлов:

    ```bash
    cd server/src
    mkdir STORAGE
    ```

3. Создайте файл `.env` в папке `server/src` и заполните его:

    ```env
    DATABASE_URL=mongodb://localhost:27017/file-storage
    DATABASE_NAME=file-storage

    JWT_ALGORITHM=RS256
    ACCESS_TOKEN_EXPIRES_IN=60
    REFRESH_TOKEN_EXPIRES_IN=15

    CLIENT_ORIGIN=http://localhost:3000

    JWT_PRIVATE_KEY=...
    JWT_PUBLIC_KEY=...
    ```

4. Запустите backend:

    ```bash
    python -m venv venv

    # Linux / MacOS
    source venv/bin/activate

    # Windows
    venv\Scripts\activate

    pip install -r requirements.txt
    uvicorn main:app --reload
    ```

5. Запустите frontend (в отдельном терминале):

    ```bash
    cd client
    npm install
    npm start
    ```

---
