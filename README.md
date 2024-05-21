## Участники проекта, студенты группы 5130904/10105:
- Пужайкин Артем
- Тимошин Егор
- Цхай Демис
- Черепанов Никита

## 1. Описание проблемы
Проект решает проблему создания простой и эффективной платформы для обмена сообщениями в рамках форума или доски объявлений. Он обеспечивает удобное хранение и управление топиками и сообщениями, предоставляя пользователям возможность создавать, редактировать и удалять контент. Таким образом, проект способствует организации структурированного обмена информацией в онлайн-сообществе.

## 2. Требования
Есть топики (темы), в каждом топике может быть одно или более сообщений. Используется IMDB хранилище (H2) + реализован скрипт по наполнению тестовыми данными.
### Требования к топику:
- Топик должен содержать заголовок (название темы)
- Заголовок топика не может быть пустым или содержать более 20 символов
- Новый топик должен содержать сообщение, нельзя создать пустой топик без сообщения в нем
### Требования к сообщению:
- Сообщение должно содержать имя (ник) автора, текст сообщения, дату создания
- Сообщейние обязательно должно относиться к одному из топиков
- Текст сообщения не может быть пустым или содержать более 100 символов
### Реализовать клиентский REST-API, позволяющий пользователю:
- получать список топиков 
- получать сообщения в указанном топике 
- создать топик (с первым сообщением в нем)
- создать сообщение в указанном топике 
- отредактировать свое сообщение 
- удалить свое сообщение 
### Реализовать REST-API администратора, дополнительно позволяющий пользователю с правами администратора:
- отредактировать любое сообщение
- удалить любое сообщение
- удалить целый топик 

## 3. Диаграммы
<img width="468" alt="image" src="https://github.com/egortimoshin/greenatom/assets/122122063/8e88b5f2-cca8-4016-ba9b-d9a9ae23c074">
<img width="468" alt="image" src="https://github.com/egortimoshin/greenatom/assets/122122063/285f3d45-1355-4888-a3cb-1545956f96fd">

## 4.	В проекте реализованы юнит тесты, проверяющие функционал приложения. 
- Создание топика с сообщением внутри
- Обновление названия топика
- Проверка возможности удаления топика обычным пользователем
- Проверка возможности удаления топика админом
- Проверка добавления сообщения
- Проверка обновления/удаления своего сообщения
- Проверка обновления/удаления чужого сообщения обычным пользователем
- Проверка обновления/удаления чужого сообщения админом

## 5.	В проекте реализованы интеграционные тесты, проверяющие следующий функционал:
-	Получения всех топиков по get-запросу к адресу “/api/v1/topic”
-	Получение всех сообщений в топике по get-запросу к адресу “/api/v1/topic/e9494fd2-78ae-4adb-b805-d3b08f0399c9”
-	Создание нового топика по post-запросу к адресу “/api/v1/topic”
-	Создание нового сообщения в топике по post-запросу к адресу “/api/v1/topic/360df656-5c25-4157-8047-8fb64d0c9563/message”
-	Проверка функционала удаления топика обычным пользователем по delete-запросу к адресу “/api/v1/topic/ 0dd1644a-a854-46dd-bea7-8c36dd785d10”
-	Проверка функционала удаления топика админом по delete-запросу к адресу “/api/v1/topic/c3873100-8bef-48f3-958b-c07ff1cce17”
  
## 6.	Команды для запуска приложения:
- mvn spring-boot:run - запуск приложения
- mvn test -Dgroups=unit - запуск юнит тестов
- mvn test -Dgroups=it - запуск интеграционных теств
- docker-compose up -d - запуск приложения в docker

## Документация для API доступна по ссылке
http://localhost:8080/swagger-ui/index.html
![image](https://github.com/egortimoshin/greenatom/assets/122122063/f34f5e80-ece8-46c3-95b1-f9434a76a91c)
