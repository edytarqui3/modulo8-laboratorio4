# PROYECTO:MÓDULO VIII - LABORATORIO 4
1.  Desplegar su aplicación de Frontend desarrollado en módulos anteriores   utilizando Docker (crear una copia del repositorio si se lo realizo en grupo).
2. Integrar su aplicación de Frontend y Backend dentro del mismo docker-compose.yml que se desarrolló en el laboratorio #3  

- Enviar la URL de donde se encuentre su docker-compose.yml y Dockerfile (recomendable crear un repositorio separado):
docker-compose.yml
    ```commandline
    https://github.com/edytarqui3/modulo8-laboratorio4/blob/main/docker-compose.yml
    ```
    Dockerfile
    ```commandline
    https://github.com/edytarqui3/modulo8-laboratorio4/blob/main/server/Dockerfile
    ```
- ->Enviar la URL de su repositorio de Frontend.
    ```commandline
    https://github.com/edytarqui3/modulo8-laboratorio4/tree/main/client
    ```
- ->Incluir un detalle del orden en el que se debe levantar los servicios (db, backend, frontend)
    ```
    version: '3.8'
    services: 
    mongo:
        container_name: mongo-contenedor
        image: mongo
        expose: 
        - "27017"
        ports: 
        - "27017:27017"
        volumes: 
        - apiDB:/data/db
    api:
        container_name: api-contenedor
        restart: always
        build: ./server
        ports: 
        - "8081:8081"
        depends_on: 
        - mongo
    client:
        container_name: client-contenedor
        restart: always
        build: ./client
        ports: 
        - "8080:8080"
        depends_on: 
        - api


    volumes: 
    apiDB:
    ```

# Integrantes
1. Edy Felix Tarqui Guarachi  

# Intrucciones
Este README, cuenta con los pasos para levantar en ambientes de desarrollo la App de MiniKardex, desarrollado con  :

- [x] Frontend (Vuejs)
- [x] MongoDB (with Mongoose schemas)
- [x] Backend (Node Express + mongo) 

### Pasos docker ###
```commandline
docker compose-compose up -d 
```
### Ejecucion ###

![Ejecucion](pantallas/frontend.png)
### Ejecucion servicios docker ###

![Ejecucion](pantallas/servicios.png)