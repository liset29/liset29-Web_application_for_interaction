# Веб-приложение для знакомств

## Описание

Данное приложение предоставляет функционал для создание пользователя, оценивание других пользователей и фильтрацию по заданным критериям

## Функциональные возможности

- **Регистрация и аутентификация пользователей**
- **Получение списка участников с возможностью фильтрации**
- **Обработка изображений** с наложением водяного знака на аватарки
- **Оценка участников** с уведомлением по электронной почте

## Эндпоинты

### USER

- **POST /api/login**
  - Описание: Выдаёт JWT токен по логину и паролю зарегистрированных пользователей.
  - Ответ: JWT токен.
  
- **GET /api/users/me**
  - Описание: Возвращает данные аутентифицированного пользователя (username и email).
  - Доступ: Только для аутентифицированных пользователей.


- **POST /api/clients/create**
  - Описание: Регистрация нового участника с обработкой аватарки и наложением водяного знака.
  - Широта и долгота в десятичной системе
  
- **GET /api/list**
  - Описание: Возвращает список всех зарегистрированных участников с возможностью фильтрации по полу, имени и фамилии, дате регистрации и дистанции ().


- **POST /api/clients/{id}/match**
  - Описание: Оценка другого участника, при взаимной симпатии отправляет уведомление на почту.


## Ограничения фильтрации по дистанции

Пожалуйста, обратите внимание, что функция фильтрации по дистанции может не быть полностью точной. Это связано с несколькими факторами:

- **Использование географических координат**: Фильтрация основана на расчётах расстояния между точками, что может приводить к погрешностям, особенно в случае, если координаты имеют небольшие отклонения.
- **Точность данных**: Данные о местоположении могут быть неточными или неполными, что также влияет на результаты фильтрации.
- **Методы расчёта**: Используемые формулы и алгоритмы для расчёта расстояния могут иметь свои ограничения.

## Установка 

1. Клонируйте репозиторий:
   git clone <URL-репозитория>
2. Скачайте зависимости:
    pip install -r requirements.txt
3. Запустите Postgresql:
    docker-compose up
4. Запустить сервер:
    python server.py
5. Открыть в страницу http://localhost/docs#/