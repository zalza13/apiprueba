# API Prueba

Este proyecto contiene dos apis web que se ejecutan mediante el comando docker-compose

### Tecnologías utilizadas

* Ubuntu 18.04 LTS (Codename: bionic)
* dotnet core 2.1.302
* Docker version 18.03.1-ce, build 9ee9f40
* docker-compose version 1.21.2, build a133471

### Como ejecutar las dos web apis

```
cd apiprueba
sudo docker-compose -f docker-compose.linux.yml -f docker-compose.override.yml up
```

#### Para probar que se esta ejecutando correctmente hay que testear en el browser los siguientes links

[WebApi 1](http://localhost:5000/api/values)

[WebApi 2](http://localhost:5001/api/values)

### Generar las imagenes de forma independiente

##### API 1
```
cd apiprueba/src/Prueba1.API
sudo docker build -t webapi/prueba1:v1 -f ./Infraestructura/Dockerfile .
sudo docker run -d -p 15000:80 --name=webapi1 webapi/prueba1:v1
```

##### API 2
```
cd apiprueba/src/Prueba2.API
sudo docker build -t webapi/prueba2:v1 -f ./Infraestructura/Dockerfile .
sudo docker run -d -p 15001:80 --name=webapi2 webapi/prueba1:v1
```