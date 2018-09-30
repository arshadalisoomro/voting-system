**Under development**

Graduation Project of Topjava Online Intership
REST API project with basic authentication for admin and regular users. 
Voting app for deciding in which restaurant 

Technology stack:
- Spring Boot
- Spring Security
- Spring Data JPA
- HSQL database, embedded
- Java 8 Stream API


Clone: https://github.com/JolaPsh/voting-system.git
Execute it with Maven: mvn spring-boot:run


Test
CURL

Git Bash

**restaurants**:
GET all restaurants:
curl -s http://localhost:8080/rest/admin/restaurants --user admin@gmail.com:admin
GET restaurant with id 1001:
curl -s http://localhost:8080/rest/admin/restaurants/1001 --user admin@gmail.com:admin
DELETE restaurant with id 1001:
curl -s -X DELETE http://localhost:8080/rest/admin/restaurants/1001 --user admin@gmail.com:admin
CREATE restaurant: POST
curl -s -X POST -d '{ "title": "Tiget", "location": "3A Lenina Street"}' -H 'Content-Type:application/json;charset=UTF-8' http://localhost:8080/rest/admin/restaurants --user admin@gmail.com:admin
UPDATE restaurant: PUT
curl -s -X PUT -d '{"id": 1004, "title":"FRONTO", "location":"3 Chapel Street, Lviv"}' -H 'Content-Type: application/json' http://localhost:8080/rest/admin/restaurants/1004 --user admin@gmail.com:admin

**dishes**:

GET all dishes:
curl -s http://localhost:8080/rest/admin/dishes --user admin@gmail.com:admin
GET dish with id 1013
curl -s http://localhost:8080/rest/admin/dishes/1013 --user admin@gmail.com:admin
DELETE dish with id 1013:
 curl -s -X DELETE http://localhost:8080/rest/admin/dishes/1010 --user admin@gmail.com:admin
CREATE dish: POST
curl -s -X POST -d '{"date":"2018-09-20", "name": "Shrimp&vegetables", "price": 84, "restaurant": {"id": 1002, "title": "Kruivka", "location": "11 Mykolaja street, Ternopil"}}' -H 'Content-Type:application/json;charset=UTF-8' http://localhost:8080/rest/admin/dishes --user admin@gmail.com:admin
UPDATE dish: PUT
curl -s -X PUT -d '{"id": 1015, "date":"2018-09-20", "name":"Cocoa", "price": 72, "restaurant": {"id": 1000, "title": "Local", "location": "33 Dark Spurt, Lviv"}}' -H 'Content-Type: application/json' http://localhost:8080/rest/admin/dishes/1015 --user admin@gmail.com:admin

user actions:
**vote**
GET user vote history:
curl -s http://localhost:8080/rest/profile/vote/1008 --user herbert@gmail.com:herbert
GET all restaurants:
curl -s http://localhost:8080/rest/profile/restaurants --user dominik@gmail.com:12345678
GET all restaurant with today dishes today:
curl -s http://localhost:8080/rest/profile/restaurants/dishes?date=2018-10-04 --user herbert@gmail.com:herbert
POST add vote:
curl -s -X POST -d ' {"user_id": 1009, "restaurant_id": 1002"} ' -H 'Content-Type:application/json;charset=UTF-8' http://localhost:8080/rest/profile/vote/1004 --user dominik@gmail.com:12345678

**REST API/ Spring Boot / JPA / HSQL**