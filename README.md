# Practice-with-MongoDB
A short practice using MongoDB

***

## Crar la base de datos "inventario"

~~~
use inventario
~~~

![image](https://github.com/Tebancedoo/Practice-with-MongoDB/assets/115185706/76bea586-22b5-489b-9ae4-4c3ff0f98993)

*** 

## Insertar varios datos

~~~
db.inventario.insertMany([
{item: "journal", qty: 25, tags:["black","red"], dim_cm: [14,21]},
{item: "notebook", qty: 50, tags:["red","blank"], dim_cm: [14,21]},
{item: "paper", qty: 100, tags:["red","blank","pain"], dim_cm: [14,21]},
{item: "planner", qty: 75, tags:["black","red"], dim_cm: [22.85,30]},
{item: "postcard", qty: 45, tags:["blue"], dim_cm: [10,15.25]}
]);
~~~

![image](https://github.com/Tebancedoo/Practice-with-MongoDB/assets/115185706/5081fad0-4033-417e-a6cb-2937d13d8f23)

***

## Base de datos realizada

![image](https://github.com/Tebancedoo/Practice-with-MongoDB/assets/115185706/5bf03b63-bc95-4a4b-b314-bd27924cd0a1)

***

## Consulta para buscar el dim_cm entre 10 y 15

~~~

db.inventario.find({ $and: [{"dim_cm": {$gt: 10}}, {"dim_cm": {$lt: 15}} ]});

~~~

![image](https://github.com/Tebancedoo/Practice-with-MongoDB/assets/115185706/2c24a8c8-c399-44d7-99f7-fefd10b31181)

***

## Crear una base de datos llamada "tienda"

~~~

use tienda;

~~~

![image](https://github.com/Tebancedoo/Practice-with-MongoDB/assets/115185706/9691645c-9248-4a5d-a394-70da2db935f5)

***

## Creo la colecciòn "telefonos"

~~~

db.createCollection("telefonos");

~~~

![image](https://github.com/Tebancedoo/Practice-with-MongoDB/assets/115185706/c2bb2c78-9a0e-4d5f-87c0-d25851d8e1f9)


***

## Insertamos numeros de telefono

~~~
db.telefonos.insertMany([{"name": "AC3 phone", "brand": "ACME", "type": "phone", "price": 200, "rating": 3.8, "warranty_years": 1, "available": true},
{"name": "AC7 phone", "brand": "ACME", "type": "phone", "price": 320, "rating": 4, "warranty_years": 1, "available": false},
{"name": "AC3 series charger", "type": ["accesory","charger"], "price": 19, "rating": 2.8, "warranty_years": 0.25, "for": ["ac3", "ac7", "ac9"]},
{"name": "AC3 case green", "type": ["accesory","case"], "color": "green", "price": 12, "rating": 1, "warranty_years": 0 },
{"name": "phone extended warranty", "type": "warranty", "price": 38, "rating": 5, "warranty_years": 2, "for": ["ac3", "ac7", "ac9", "qp7", "qp8", "qp9"] },
{"name": "AC3 case black", "type": ["accesory","case"], "color": "black", "price": 12.5, "rating": 2, "warranty_years": 0.25, "available": false, "for": "ac3"},
{"name": "AC3 case red", "type": ["accesory","case"], "color": "red", "price": 12, "rating": 4, "warranty_years": 0.25, "available": true, "for": "ac3"},
{"name": "phone service basic plan", "type": "service", "monthly_price": 40, "rating": 3, "limits": {"voice": {"units": "minutes", "n": 400, "over_rate": 0.05}, "data": {"units": "gigabytes", "n": 20, "over_rate": 1 }, "sms": {"units": "text sent", "n": 100, "over_rate" :0.001 } }, "term_years" : 2},
{"name": "phone service core plan", "type": "service", "monthly_price": 60, "rating": 3, "limits": {"voice": {"units": "minutes", "n": 1000, "over_rate": 0.05}, "data": { "n": "unlimited", "over_rate": 0 }, "sms": {"n": "unlimited", "over_rate":0} },"term_years" : 1},
{"name": "phone service family plan", "type": "service", "monthly_price": 90, "rating": 4, "limits": {"voice": {"units": "minutes", "n": 1200, "over_rate": 0.05}, "data": { "n": "unlimited", "over_rate": 0 }, "sms": {"n": "unlimited", "over_rate": 0 }}, "sales_tax": true, "term_years": 2}]);
~~~

![image](https://github.com/Tebancedoo/Practice-with-MongoDB/assets/115185706/b16eb919-a8e3-43b0-a100-57ff6aacbdb1)

***

## Consultas

### Consultar elementos cuyo "type" sea "service"

~~~
db.telefonos.find({"type": "service"});
~~~

![image](https://github.com/Tebancedoo/Practice-with-MongoDB/assets/115185706/83663da4-79ae-4a5f-8f5a-7f935c50d15e)


### Consultar elementos cuyo "type" sea "service" y el precio mensual mayor de 50

~~~
db.telefonos.find({ $and: [{"type": "service"}, {"monthly_price": {$gt: 50}} ]});
~~~

![image](https://github.com/Tebancedoo/Practice-with-MongoDB/assets/115185706/52ce1003-2e38-4d94-9a80-98867fdc8b8c)


### Consultar elementos cuyo "type" sea "service " o el precio mensual mayor de 50

~~~
db.telefonos.find({ $or: [{"type": "service"}, {"monthly_price": {$gt: 50}} ]});
~~~


![image](https://github.com/Tebancedoo/Practice-with-MongoDB/assets/115185706/4dd982b2-23c9-4061-b26d-f178bb62f305)

***

# Practice-with-MongoDB part 2

***

## Crear la base de datos "base1"

~~~
use base1
~~~

![image](https://github.com/Tebancedoo/Practice-with-MongoDB/assets/115185706/1c183e9f-389d-4091-b44a-08f223409213)

***

## Crear la collection "articulos"

~~~
db.createCollection("articulos");
~~~
***

![image](https://github.com/Tebancedoo/Practice-with-MongoDB/assets/115185706/5b6b3b9e-52ff-430b-94ac-4a6d8c17f779)


## Cargar 6 documentos

~~~
db.articulos.insertMany([
{_id: 1, nombre: "impresora lenovo", rubro: "impresora",  precio: 150000, stock: 200},
{_id: 2, nombre: "mouse tk", rubro: "mouse",  precio: 80000, stock: 50},
{_id: 3, nombre: "impresora multifuncional", rubro: "impresora",  precio: 200000, stock: 3},
{_id: 4, nombre: "pantalla lenovo", rubro: "pantalla",  precio: 100000, stock: 30},
{_id: 5, nombre: "teclado hp", rubro: "teclado",  precio: 50000, stock: 55},
{_id: 6, nombre: "audifonos gamer", rubro: "audifonos",  precio: 150000, stock: 90}
]);
~~~

![image](https://github.com/Tebancedoo/Practice-with-MongoDB/assets/115185706/01b14735-480f-4f54-a908-ee506be099c0)

***

## Imprimir todos los documentos de la colección "articulos"

~~~
db.articulos.find();
~~~

![image](https://github.com/Tebancedoo/Practice-with-MongoDB/assets/115185706/2ae376a6-eda3-427f-958a-dca40743bdc1)

***

## Imprimir todos los documentos de la colección "articulos" que no son impresoras

~~~
db.articulos.find({ $not: [rubro: "impresora"]});
~~~



