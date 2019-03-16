santatecla-tiempos-2 - API REST Documentation
--------

About our API
--------

Our API REST is about categories, events, times and intervals in them. If you want to use it just
follow these rules, either way you will probably recieve error messages.
--------


API requests
---------

The resource API has GET, POST, PUT and DELETE methods. http: // localhost: 8080 followed by the containt request URL.

All API queries have been preceded by /api

All these are done with admin authentication
----------
----------

Show categories
----------

Allows to show every category.

URL:
< /login >

Method:
GET

Success Response:
{"content":
[{"id":1,"nameCategory":"Examenes"},
{"id":2,"nameCategory":"Practicas"},
{"id":3,"nameCategory":"Apuntes"},{"id":4,"nameCategory":"Categoria10"},
{"id":5,"nameCategory":"Categoria11"}]}

Error response:
Code: 401 UNAUTHORIZED
