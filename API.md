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

Allows to show every category with its information.

URL:
< /login >

Method:
GET

Success Response:
 {
     "id": 1,
     "name": "User",
     "email": "email@hotmail.es",
     "level": 1,
     "points": 0,
     "streak": 0,
     "fluency": 0,
     "dailyGoal": 0,
     "lastConnection": "2018-03-17/11:44:21",
     "lastUnit": 0,
     "lastLesson": 0,
     "progress": null,
     "remainingGoals": 0,
     "exp": 0
 }
Error response:
Code: 401 UNAUTHORIZED
