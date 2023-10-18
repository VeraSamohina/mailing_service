#  Сервис рассылок "ПУЛЬС"

Сервис управления рассылками  позволяет пользователям создавать и настраивать рассылки,
На сервисе также есть раздел Блог для статей по продвижению
Разделение прав доступа обеспечивает безопасность. 
Кеширование данных повышает производительность.

### Технологии
- ``Django``
- ``Postgresql``
- ``Django-Apscheduler``
- ``Bootstrap``
- ``Redis``

### Run
- ``Склонируйте проект к себе на компьютер ``
- ``Установите все зависимости в соответствии с requirements.txt``
- ``Пропишите свои переменные окружения в .env в соответствии с примером (.env.sample) и данные по email в settings.py``
- ``Примените миграции``
- ``Запустите команду createsuper для создания суперюзера ``
- ``Запустите сервер ``
-  ``Для запуска планировщика заданий запустите команду runupscheduler ``

# Сущности системы
### Клиент сервиса:
- контактный email,
- ФИО,
- комментарий.
- дата рождения
- пользователь (создатель)
- 
### Рассылка (настройки):
- время начала рассылки;
- время окончания рассылки;
- периодичность: раз в день, раз в неделю, раз в месяц, один раз;
- статус рассылки: завершена, создана, запущена.
- пользователь(создатель)
- активность (активна/не активна)
- сообщение для рассылки - внешний ключ на модель Сообщения
- клиенты -внешний ключ на модель Клиенты

### Сообщение для рассылки:
- тема письма,
- тело письма.
- пользователь(создатель)
- 
### Логи рассылки:
- дата и время последней попытки;
- статус попытки;
- ответ почтового сервера, если он был.
- пользователь(создатель)
- рассылка внешний ключ на модель Рассылка

 ### Пользователь:
- email (поле по которому произвлдится авторизация);
- ФИО;
- Аватар.
- пользователь(создатель)
- рассылка внешний ключ на модель Рассылка
- 
   ### Статья :
- название;
- контент;
- фото;
- дата создания;
- количество просмотров