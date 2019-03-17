

# santatecla-tiempos-2 - API REST Documentation
--------

## About our API
Our API REST is about categories, events, times and intervals in them. If you want to use it just
follow these rules, either way you will probably recieve error messages.

## API requests

### Resources
The resource API has GET, POST, PUT and DELETE methods.
http: // localhost: 8080 followed by the containt request URL.

**All API queries have been preceded by /api**
## **Every operation as addition, modification or delete is only available for admin role.**

#### LOGIN
Resource to log in the application.

* ##### URL

	< /login/ >

* ##### Method:

	`GET`

* ##### Login Role Used: Admin
	

* ##### Success Response:
	
	```
	{
    		"id": 66,
    		"username": "admin",
    		"password": "$2a$10$GfiWtkcdbkyVnUonmXYMEOK9vDSQ9llPEKj1T6kbYc8QUKWw7VBAa",
    		"rol": [
        		"ROLE_USER",
        		"ROLE_ADMIN"
    		]
	}
	```
	
* ##### Error Response:

	**Code**: 401 UNAUTHORIZED


* ##### Login Role Used: User
	

* ##### Success Response:
	
	```
	{
   	 	"id": 65,
    	 	"username": "Marcos",
   	 	"password": "$2a$10$icXSuiXsow7atuSbRfTH..BhU4cQnAdC2QFXsM/VBpOre5sJuowM6",
    	 	"rol": [
     	   		"ROLE_USER"
   	 	]
	}
	```
	
* ##### Error Response:

	**Code**: 401 UNAUTHORIZED

#### LOGOUT
Resource to log out the application.

* ##### URL

	< /logout/ >

* ##### Method:

	`GET`

* ##### Login Role Used: Admin
	

* ##### Success Response:
	
	```
	true
	```
	
* ##### Error Response:

	**Code**: 401 UNAUTHORIZED

#### Pagination
Resource search a specific page in the application.
For example searching first page after the default one in categories.

* ##### URL

	< /categories/ >

* ##### Method:

	`GET`

* ##### Example of query:

	* URL
		
		`/api/categories/?page=1`

* ##### Success Response:
	
	```
	{
    		"content": [
				{
            			"id": 6,
            			"nameCategory": "Categoria12"
				},
				{
            			"id": 7,
            			"nameCategory": "Categoria13"
				},
				{
            			"id": 8,
            			"nameCategory": "Categoria14"
				},
				{
           			"id": 9,
           			"nameCategory": "Categoria15"
				},
				{
            			"id": 10,
            			"nameCategory": "Categoria16"
				}
			]
	}
	```
	
* ##### Error Response:

	**Code**: No errors available

## Show items
Available for every role.

#### Categories
Shows all categories.

* ##### URL:

	< /categories/ >

* ##### Method:

	`GET`
	
* ##### Success Response:
  
  	```
	{
		"content":[
			{
	    			"id": 1,
	    			"nameCategory": "Examenes"
			},
			{
	    			"id": 2,
	    			"nameCategory": "Prácticas"
			},
			{
	    			"id": 3,
	    			"nameCategory": "Apuntes"
			},
			{
	    			"id": 4,
	    			"nameCategory": "Categoria10"
			},
			{
	    			"id": 5,
	    			"nameCategory": "Categoria11"
			},
		]	    		
	}
	```
  
* ##### Error response:

	**Code**: 401 UNAUTHORIZED
	
#### Events  
Shows all events.

* ##### URL:

	< /events/ >

* ##### Method:

	`GET`

* ##### Success Response:

	```
	{
    		"content": [
				{
            			"id": 41,
            			"nameEvent": "DAW",
            			"date": "7-7-2019",
            			"location": "Aulario 1",
            			"wiki": "Aulario 1",
            			"hasImage": false,
            			"categories": [
					{
                    				"id": 1,
                    				"nameCategory": "Examenes"
					}
					],
            			"photo": null,
            			"encodedImage": null
				},
				{
            			"id": 42,
            			"nameEvent": "Seguridad",
            			"date": "20-12-18",
            			"location": "Aulario 1",
            			"wiki": "Aulario 1",
            			"hasImage": false,
            			"categories": [],
            			"photo": null,
            			"encodedImage": null
				},
				{
            			"id": 43,
            			"nameEvent": "Java",
            			"date": "1-1-19",
            			"location": "Aulario 2",
            			"wiki": "Aulario 2",
            			"hasImage": false,
            			"categories": [],
            			"photo": null,
            			"encodedImage": null
				},
				{
            			"id": 44,
            			"nameEvent": "DAW",
            			"date": "7-7-2019",
            			"location": "Aulario 1",
            			"wiki": "Aulario 1",
            			"hasImage": false,
            			"categories": [],
            			"photo": null,
            			"encodedImage": null
				},
				{
            			"id": 45,
            			"nameEvent": "Seguridad",
            			"date": "20-12-18",
            			"location": "Aulario 1",
            			"wiki": "Aulario 1",
            			"hasImage": false,
            			"categories": [],
            			"photo": null,
            			"encodedImage": null
				}
			]
	}
	```

  * ##### Error Response:

	**Code**: 401 UNAUTHORIZED OR 404 NOT FOUND

#### Times
Shows all times.

* ##### URL:

	< /times/ >

* ##### Method:

	`GET`

* ##### Success Response:

	```
	{
		"content": [
			{
            		"id": 52,
            		"nameInterval": "Intervalo 1",
            		"startDate": "5-7-2018",
            		"endDate": "1-1-2020",
            		"events": [
			{
                    	"id": 41,
                    	"nameEvent": "DAW",
                    	"date": "7-7-2019",
                    	"location": "Aulario 1",
                    	"wiki": "Aulario 1",
                    	"hasImage": false,
                    	"categories": [
			{
                            "id": 1,
                            "nameCategory": "Examenes"
			}
			],
                    	"photo": null,
                    	"encodedImage": null
			},
			{
                    	"id": 42,
                    	"nameEvent": "Seguridad",
                    	"date": "20-12-18",
                    	"location": "Aulario 1",
                    	"wiki": "Aulario 1",
                    	"hasImage": false,
                    	"categories": [],
                    	"photo": null,
                    	"encodedImage": null
			},
			{
                    	"id": 43,
                    	"nameEvent": "Java",
                    	"date": "1-1-19",
                    	"location": "Aulario 2",
                    	"wiki": "Aulario 2",
                    	"hasImage": false,
                    	"categories": [],
                    	"photo": null,
                    	"encodedImage": null
			}
			],
            		"subIntervals": [
                		{
                    		"nameSubTime": "2018",
                    		"startDate": "8-9-2018",
                   		"endDate": "10-10-2018",
                    		"subTimes": []
                		},
                		{
                    		"nameSubTime": "2019",
                    		"startDate": "10-1-2019",
                    		"endDate": "20-11-2019",
                    		"subTimes": []
				}
				]
			},
			{
            		"id": 55,
            		"nameInterval": "Intervalo 2",
            		"startDate": "2-1-2020",
            		"endDate": "1-3-2020",
            		"events": [],
            		"subIntervals": []
			},
			{
            		"id": 56,
            		"nameInterval": "Intervalo 3",
            		"startDate": "2-4-2021",
            		"endDate": "2-5-2021",
            		"events": [],
            		"subIntervals": []
			},
			{
           		"id": 57,
            		"nameInterval": "Intervalo 4",
            		"startDate": "5-7-2018",
            		"endDate": "1-1-2020",
            		"events": [],
            		"subIntervals": []
			},
			{
            		"id": 58,
            		"nameInterval": "Intervalo 5",
            		"startDate": "2-1-2020",
            		"endDate": "1-3-2020",
            		"events": [],
            		"subIntervals": []
			}
    			]
	}
	```

  * ##### Error Response:

	**Code**: 401 UNAUTHORIZED OR 404 NOT FOUND

### Search Category by name
Resource to show categories with a given name.

* ##### URL

	< /categories/{name} >

* ##### Method:

	`GET`
	
* ##### Example of query:

	* URL
		
		`/api/categories/Examenes`
  
* ##### Success Response:

  	```
	[
    	{
			"id": 1,
			"nameCategory": "Examenes"
    	}
	]		
	```
  
* ##### Error Response:

	**Code**: NADA

### Search Event by name
Resource to show events with a given name.

* ##### URL

	< /categories/{event} >

* ##### Method:

	`GET`
	
* ##### Example of query:

	* URL
		
		`/api/events/DAW`
  
* ##### Success Response:

  	```
	[
    		{
        			"id": 41,
        			"nameEvent": "DAW",
        			"date": "7-7-2019",
        			"location": "Aulario 1",
        			"wiki": "Aulario 1",
        			"hasImage": false,
        			"categories": [
            			{
                			"id": 1,
                			"nameCategory": "Examenes"
            			}
        			],
        			"photo": null,
        			"encodedImage": null
    		},
    		{
        			"id": 44,
        			"nameEvent": "DAW",
        			"date": "7-7-2019",
        			"location": "Aulario 1",
        			"wiki": "Aulario 1",
        			"hasImage": false,
        			"categories": [],
        			"photo": null,
        			"encodedImage": null
    		}
	]	
	```
  
* ##### Error Response:

	**Code**: NADA

### Search Times by ID
Resource to show times with a given ID

* ##### URL

	< /times/{ID} >

* ##### Method:

	`GET`
	
* ##### Example of query:

	* URL
		
		`/api/times/55`
  
* ##### Success Response:

  	```
	{
    		"id": 55,
    		"nameInterval": "Intervalo 2",
    		"startDate": "2-1-2020",
    		"endDate": "1-3-2020",
    		"events": [],
    		"subIntervals": []
	}
	```
  
* ##### Error Response:

	**Code**: RESOURCE NOT FOUND


#### Add a category
Resource to add a category.

* ##### URL

	< /categories/ >

* ##### Method:

	`POST`

* ##### Body:
	```
	{
		"nameCategory": "nueva"
	}
	```

* ##### Success Response:
	
	```
	{
    		"id": 67,
    		"nameCategory": "nueva"
	}
	```
	
* ##### Error Response:

	**Code**: 401 UNAUTHORIZED


#### Add an event
Resource to add an event

* ##### URL

	< /events/ >

* ##### Method:

	`POST`

* ##### Body:
	```
	{
            "nameEvent": "special",
            "date": "20-12-18",
            "location": "Aulario 1",
            "wiki": "Aulario 1",
            "hasImage": false,
            "categories": [],
            "photo": null,
            "encodedImage": null
	}
	```

* ##### Success Response:
	
	```
	{
    		"id": 69,
    		"nameEvent": "special",
    		"date": "20-12-18",
    		"location": "Aulario 1",
    		"wiki": "Aulario 1",
    		"hasImage": false,
    		"categories": [],
    		"photo": null,
    		"encodedImage": null
	}
	```
	
* ##### Error Response:

	**Code**: 401 UNAUTHORIZED


#### Add a time
Resource to add a time.

* ##### URL

	< /times/ >

* ##### Method:

	`POST`

* ##### Body:
	```
	{
		"nameInterval": "newTime",
		"startDate": "2-1-2020",
		"endDate": "1-3-2020",
		"events": [],
		"subIntervals": []
	}
	```

* ##### Success Response:
	
	```
	{
    		"id": 72,
    		"nameInterval": "newTime",
    		"startDate": "2-1-2020",
    		"endDate": "1-3-2020",
    		"events": [],
    		"subIntervals": []
	}
	```
	
* ##### Error Response:

	**Code**: 401 UNAUTHORIZED


#### Deleting a category
Resource to delete a category with a given ID.

* ##### URL

	< /categories/ >

* ##### Method:

	`DELETE`

* ##### Example of query:

	* URL
		
		`/api/categories/1`

* ##### Success Response:
	
	```
	{
   		"id": 1,
    		"nameCategory": "Examenes"
	}
	```

* ##### Result after delete:
	
	```
	{
		"content": [
			{
            		"id": 2,
            		"nameCategory": "Practicas"
			},
			{
            		"id": 3,
            		"nameCategory": "Apuntes"
			},
			{
            		"id": 4,
            		"nameCategory": "Categoria10"
			},
			{
            		"id": 5,
            		"nameCategory": "Categoria11"
			},
			{
            		"id": 6,
            		"nameCategory": "Categoria12"
			}
    		]
	}
	```
	
* ##### Error Response:

	**Code**: 401 UNAUTHORIZED

#### Deleting an event
Resource to delete an event with a given ID.

* ##### URL

	< /events/ >

* ##### Method:

	`DELETE`

* ##### Example of query:

	* URL
		
		`/api/events/41`

* ##### Success Response:
	
	```
	{
    		"id": 41,
    		"nameEvent": "DAW",
    		"date": "7-7-2019",
    		"location": "Aulario 1",
   		"wiki": "Aulario 1",
    		"hasImage": false,
    		"categories": [],
    		"photo": null,
    		"encodedImage": null
	}
	```

* ##### Result after delete:
	
	```
	{
		"content": [
			{
            			"id": 42,
           			"nameEvent": "Seguridad",
            			"date": "20-12-18",
            			"location": "Aulario 1",
            			"wiki": "Aulario 1",
            			"hasImage": false,
            			"categories": [],
            			"photo": null,
            			"encodedImage": null
			},
			{
            			"id": 43,
            			"nameEvent": "Java",
            			"date": "1-1-19",
            			"location": "Aulario 2",
            			"wiki": "Aulario 2",
            			"hasImage": false,
            			"categories": [],
            			"photo": null,
            			"encodedImage": null
			},
			{
            			"id": 44,
            			"nameEvent": "DAW",
            			"date": "7-7-2019",
            			"location": "Aulario 1",
            			"wiki": "Aulario 1",
            			"hasImage": false,
            			"categories": [],
            			"photo": null,
            			"encodedImage": null
			},
			{
            			"id": 45,
            			"nameEvent": "Seguridad",
            			"date": "20-12-18",
            			"location": "Aulario 1",
            			"wiki": "Aulario 1",
            			"hasImage": false,
            			"categories": [],
            			"photo": null,
            			"encodedImage": null
			},
			{
            			"id": 46,
            			"nameEvent": "Java",
            			"date": "1-1-19",
            			"location": "Aulario 2",
            			"wiki": "Aulario 2",
            			"hasImage": false,
            			"categories": [],
            			"photo": null,
            			"encodedImage": null
        		}
    	]
	}
	```
	
* ##### Error Response:

	**Code**: 401 UNAUTHORIZED

#### Deleting a time
Resource to delete a time with a given ID.

* ##### URL

	< /times/ >

* ##### Method:

	`DELETE`

* ##### Example of query:

	* URL
		
		`/api/times/56`

* ##### Success Response:
	
	```
	{
    		"id": 56,
    		"nameInterval": "Intervalo 3",
    		"startDate": "2-4-2021",
    		"endDate": "2-5-2021",
    		"events": [],
    		"subIntervals": []
	}
	```

* ##### Result after delete:
	
	```
	{
		"content": [
			{
            			"id": 55,
            			"nameInterval": "Intervalo 2",
            			"startDate": "2-1-2020",
            			"endDate": "1-3-2020",
            			"events": [],
            			"subIntervals": []
			},
			{
            			"id": 57,
            			"nameInterval": "Intervalo 4",
            			"startDate": "5-7-2018",
            			"endDate": "1-1-2020",
            			"events": [],
            			"subIntervals": []
			},
			{
            			"id": 58,
            			"nameInterval": "Intervalo 5",
            			"startDate": "2-1-2020",
            			"endDate": "1-3-2020",
            			"events": [],
            			"subIntervals": []
			},
			{
            			"id": 59,
            			"nameInterval": "Intervalo 6",
            			"startDate": "2-4-2021",
           			"endDate": "2-5-2021",
           			"events": [],
            			"subIntervals": []
			},
			{
            			"id": 60,
            			"nameInterval": "Intervalo 7",
            			"startDate": "2-4-2021",
            			"endDate": "2-5-2021",
            			"events": [],
            			"subIntervals": []
			}
		]
	}
	```
	
* ##### Error Response:

	**Code**: 401 UNAUTHORIZED