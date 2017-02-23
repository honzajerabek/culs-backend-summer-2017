# Express Mongoose

Steps to reproduce:

## Run the containers

`docker-compose -f docker-compose-dev.yml up`

## Curl commands

Please bear in mind, that the Token will different for you DB.

1. Create user `curl -v -X POST --data "login=pepe&password=secret&confirmation=secret&name=Josef&email=jo@po.com" http://localhost:8080/users`
2. Authenticate the User to get the Token `curl -v -X POST --data "login=pepe&password=secret" http://localhost:8080/users/authenticate`
3. Create a Presentation `curl -v -X POST -H "Token: 58adbcd85bd0ff002fa22edb" --data "name=Some&document=# Some long one" http://localhost:8080/presentations`
4. Get the list of all Presentations of the User by the Token `curl -v -H "Token: 58adbcd85bd0ff002fa22edb" http://localhost:8080/presentations`

## What you need to do

1. Add path for listing one Presentation by Id and  User's Token `curl -v -X POST -H "Token: 58af11bb80125400132fbba7" --data "id=58af1eb1804499003a20c929" http://localhost:8080/presentations/show`
2. Add path for deleting one Presentation by Id and User's Token `curl -v -X POST -H "Token: 58af11bb80125400132fbba7" --data "id=58af14388828fc00133d41f0" http://localhost:8080/presentations/remove`
