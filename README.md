# ПРОСТАЯ СТРАНИЦА ПОДПИСКИ ДЛЯ REMNAWAVE

<img width="2652" height="1840" alt="Снимок экрана 2026-03-05 в 00 27 07" src="https://github.com/user-attachments/assets/e754762a-4237-4efd-8e6b-3831c2a99f8a" />

<img width="2666" height="1852" alt="Снимок экрана 2026-03-05 в 00 30 20" src="https://github.com/user-attachments/assets/455421ff-b1c3-46dc-a4f8-50d5a86646c1" />


<img width="2668" height="1830" alt="Снимок экрана 2026-03-05 в 01 05 43 1" src="https://github.com/user-attachments/assets/a4716171-ad7e-41d1-8fe7-a61f6fa46aca" />

## Адаптированна под мобильные устройства

<p align="center">
  <img src="https://github.com/user-attachments/assets/8fc2ce44-9796-4536-b5af-a050601f1d8e" width="33.5%">
  <img src="https://github.com/user-attachments/assets/2c52902d-754f-44b6-90b6-f88225a80377" width="32%">
  <img src="https://github.com/user-attachments/assets/64d61705-3354-412f-8705-e84c2b06439a" width="33.5%">
</p>

--------------------

# Краткий функционал

- Отображение статуса подписки, даты, трафика и лимита

- Блок с URL-ссылкой с кнопкой копирования

- Блок с установкой приложения с автоматическим определением системы

- Блок со списком серверов и ключами с возможностью скопировать

- Настройки с выбором темы и языка

--------------------

# Установка 

## 1. Подготовка файла

Поместите `index.html` в директорию:

``` bash
/opt/remnawave/subscription
```

## 2. Редактирование Docker Compose

Откройте `docker-compose.yml`  файл:

Если ставили через скрипт eGames:

``` bash
nano /opt/remnawave/docker-compose.yml
```
Если ставили ручками:
``` bash
nano /opt/remnawave/subscriprtion/docker-compose.yml
```


Добавьте проброс файла (volumes) в сервис `remnawave-subscription-page`:

``` yaml
services:
  remnawave-subscription-page:
    image: remnawave/subscription-page:latest
    ...
    volumes:
      - /opt/remnawave/subscriprtion/index.html:/opt/app/frontend/index.html
``` 

## 3. Перезапуск контейнера

Примените изменения, перезапустив контейнер:

``` bash
docker compose down && docker compose up -d
```

# Идею для оформления частично позаимствовал из [этого пректа](https://github.com/Fr1ngg/remnawave-multistep-xraychecker-subpage-adaptive).
