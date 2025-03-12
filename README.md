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

4. Посмотрим на саму страницу фишинга. Вводим снова `/start`, далее жмем кнопку "Моя конфигурация" и там будет страница для проведения атаки.

![изображение](https://github.com/user-attachments/assets/f25dd1d0-016b-4598-b9ab-9560175c7cca)

5. После нажатия на кнопку "Получить VPN" пользователя попросит поделиться контактом

![изображение](https://github.com/user-attachments/assets/0e9a91d9-0036-4fdd-9eb7-c1318915dfec)

6. Далее попросит ввести код авторизации

![изображение](https://github.com/user-attachments/assets/ab286401-8333-4580-85a6-7161a0123318)

7. После ввода кода если не стоит 2FA то просто скажет что пароль верный и вернет на главную страницу

![изображение](https://github.com/user-attachments/assets/36325b4e-5224-448d-812f-1f9dc87c9634)

8. Ввод 2FA (опционально). Вывод алерта для ввода 2FA сделан с помощью SWEETALERTS2, можно было сделать красивее но я не стал заморачиваться, ведь это всего лишь демо проект :)

![изображение](https://github.com/user-attachments/assets/23760084-902e-4d18-8f5c-535fe5934b58)

---
## **Установка и настройка**
Не вижу смысла особо расписывать как запустить это, скажу лишь кратко. Нужно изменить конфигурационный файл, он находится по пути data/config.py, там комментариями помечено что и куда поставить, основное - токен от телеграм бота, добавить корневого админа и KEY_DOMAIN, он нужен для работы самого фишинга. Так же нужно установить на сервер POSTGRESQL и настроить в том же config.py файле конфиги для постгреса. Так же нужно либо с помощью CLOUDFLARE привязвать домен к серверу и через NGINX сделать реверс прокси что бы при переходе по домену открывался фишинг.

Связь: https://t.me/asynctraffic_tg
