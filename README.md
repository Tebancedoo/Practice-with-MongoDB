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
db.telefonos.insert([

{"name": "AC3 phone", "brand": "ACME", "type": "phone", "price": "200", "rating": 3.8, "warranty_years": 1, "available": true},
{"name": "AC7 phone", "brand": "ACME", "type": "phone", "price": "320", "rating": 4, "warranty_years": 1, "available": false},
{"name": "AC3 series charger", "type": ["accesory","charger"], "price": "19", "rating": 2.8, "warranty_years": 0.25, "for": ["ac3", "ac7", "ac9"]},
{"name": "AC3 case green", "type": ["accesory","case"], "color": "green", "price": "12", "rating": 1, "warranty_years": 0 },
{"name": "phone extended warranty", "type": "warranty", "price": "38", "rating": 5, "warranty_years": 2, "for": ["ac3", "ac7", "ac9", "qp7", "qp8", "qp9"] },
{"name": "AC3 case black", "type": ["accesory","case"], "color": "black", "price": "12.5", "rating": 2, "warranty_years": 0.25, "available": false, "for", "ac3"},
{"name": "AC3 case red", "type": ["accesory","case"], "color": "red", "price": "12", "rating": 4, "warranty_years": 0.25, "available": false, "for", "ac3"},
{"name": "phone service basic plan", "type": "service", "monthly_price": "40", "rating": 3, "limits": {"voice": {"units": "minutes", "n": 400, "over_rate": 0.05}, "data": {"units": "gigabytes", "n": 20, "over_rate": 1 }, "sms": {"units": "text sent", "n": 100, "over_rate":0.001 } }, "terms_years" : 2},
{"name": "phone service core plan", "type": "service", "monthly_price": "60", "rating": 3, "limits": {"voice": {"units": "minutes", "n": 1000, "over_rate": 0.05}, "data": { "n": "unlimited": "over_rate": 0 } },"term_years" : 1},
{"name": "phone service family plan", "type": "service", "monthly_price": "90", "rating": 4, "limits": {"voice": {"units": "minutes", "n": 1200, "over_rate": 0.05}, "data": {"unlimited", "over_rate": 0 , "sms": {"n": "unlimited", "over_rate": 0 }}, "sales_tax": true, "term_years": 2}

]);
~~~
