# **Telegram phishing**

![GitHub License](https://img.shields.io/badge/license-MIT-blue) ![Python Version](https://img.shields.io/badge/python-3.9%2B-blue) ![FastAPI](https://img.shields.io/badge/FastAPI-latest-green) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-latest-blue)

---

## **Описание проекта**

Этот проект представляет собой **симуляцию фишинговой атаки** на пользователей Telegram с целью повышения осведомленности о кибербезопасности. Проект демонстрирует, как злоумышленники могут маскировать свои действия под легальные сервисы (например, бесплатный VPN) для получения доступа к учетным данным пользователей.

Проект создан исключительно в **образовательных целях**. Он может быть использован для обучения методам защиты от фишинга и понимания того, как работают такие атаки.

---

## **Технологии и инструменты**

Проект использует следующие технологии:

- **Backend:**
  - [FastAPI](https://fastapi.tiangolo.com/) — современный веб-фреймворк для создания API.
  - [PostgreSQL](https://www.postgresql.org/) — надежная база данных для хранения данных.
  
- **Telegram Bot:**
  - [Aiogram 3.5.0](https://docs.aiogram.dev/en/latest/) — мощная библиотека для создания Telegram-ботов.

- **Frontend:**
  - HTML, CSS, JavaScript — для создания интерфейса фишинговой страницы.

- **Язык программирования:**
  - Python 3.10+ — основной язык разработки.

---

## **Как это работает?**

1. **Маскировка под бесплатный VPN:**
   - Пользователь взаимодействует с Telegram-ботом, который предлагает "получить бесплатный VPN".
   - Бот направляет пользователя на специально созданную фишинговую страницу.

2. **Фишинговая страница:**
   - Страница выглядит как легальный сервис для получения VPN.
   - Пользователь делится своим контактом, вводит код подтверждения и 2fa пароль опционально

3. **Сбор данных:**
   - Введенные данные отправляются на сервер FastAPI.
   - Сервер сохраняет данные в базе данных PostgreSQL.
---

## **Скриншоты**
1. Открываем бота и запускаем командой `/start`
   
![изображение](https://github.com/user-attachments/assets/a940ce4c-e7d5-43db-86f5-5a041a970fab)


2. Входим в админку командой `/admin`. Кнопка выгрузки нужно для получения всех тг сессий (тг аккаунтов). 
   
![изображение](https://github.com/user-attachments/assets/630bc76a-0e76-4f14-bb73-335a4d9a9390)

3. Открываем вкладку для настройки конфигурации и следуем инструкции из сообщения
  
![изображение](https://github.com/user-attachments/assets/c7fae3ef-6589-465d-b2b3-367f7b69743d)



