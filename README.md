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

db.inventario.find({dim_cm:{$gt:10{$and $lt:{15}}});

~~~




