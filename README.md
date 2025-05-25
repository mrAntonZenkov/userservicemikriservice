🧩 User Service — Микросервисная система с API Gateway, Service Discovery и Circuit Breaker
Этот проект представляет собой микросервисную систему, реализующую CRUD-функционал управления пользователями с использованием следующих паттернов:

Service Discovery (Eureka Server)
API Gateway (Spring Cloud Gateway)
Circuit Breaker (Resilience4j)
External Configuration (Spring Cloud Config)
📦 Структура проекта
Проект состоит из нескольких модулей/сервисов:

СЕРВИС
ОПИСАНИЕ
user-service
Микросервис для работы с пользователями
discovery-server
Eureka Server для регистрации сервисов
api-gateway
Шлюз для маршрутизации запросов
config-server
Централизованное хранение конфигураций


🚀 Как запускать проект
 Клонирование репозитория
 
bash
git clone https://github.com/yourname/user-service-microservices.git 
cd user-service-microservices

 Запуск сервисов по порядку
   
1. Discovery Server (Eureka)

cd discovery-server
mvn spring-boot:run

Откройте: http://localhost:8761

2. Config Server
   
cd config-server
mvn spring-boot:run

Откройте: http://localhost:8888/actuator

3. User Service

cd user-service
mvn spring-boot:run

После запуска он зарегистрируется в Eureka.

4. API Gateway

cd api-gateway
mvn spring-boot:run

🌐 Доступ к API через Gateway

После запуска всех сервисов, вы можете обратиться к API через шлюз:

GET
http://localhost:8080/api/users

Получить список пользователей

POST
http://localhost:8080/api/users

Создать нового пользователя

GET
http://localhost:8080/api/users/{id}

Получить пользователя по ID

PUT
http://localhost:8080/api/users/{id}

Обновить пользователя

DELETE
http://localhost:8080/api/users/{id}

Удалить пользователя

Пример тела запроса: 

{
  "name": "Alice",
  "email": "alice@example.com"
}

Swagger UI доступен по адресу:
http://localhost:8080/swagger-ui/index.html

🧪 Проверка работоспособности
Откройте Eureka Dashboard: http://localhost:8761
Убедитесь, что все сервисы зарегистрированы.
Используйте Postman или curl для тестирования API через Gateway.
