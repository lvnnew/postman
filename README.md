### Пример тестовой коллекции на ReqRes API
```JSON
{
	"info": {
		"_postman_id": "9944fa64-3b97-43cf-85fe-d1e0b694d53e",
		"name": "ReqRes",
		"schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json"
	},
	"item": [
		{
			"name": "Get List Users",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"// Статус код\r",
							"pm.test(\"Status code is 200\", function () {\r",
							"    pm.response.to.have.status(200);\r",
							"});\r",
							"// Проверка ответа\r",
							"pm.test(\"page = 2\", function () {\r",
							"    var jsonData = pm.response.json();\r",
							"    pm.expect(jsonData.page).to.eql(2);\r",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "GET",
				"header": [],
				"url": {
					"raw": "https://reqres.in/api/users?page=2",
					"protocol": "https",
					"host": [
						"reqres",
						"in"
					],
					"path": [
						"api",
						"users"
					],
					"query": [
						{
							"key": "page",
							"value": "2"
						}
					]
				}
			},
			"response": []
		},
		{
			"name": "Get Single User",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"// Статус код\r",
							"pm.test(\"Status code is 200\", function () {\r",
							"    pm.response.to.have.status(200);\r",
							"});\r",
							"// Проверка ответа\r",
							"pm.test(\"id = 2\", function () {\r",
							"    var jsonData = pm.response.json();\r",
							"    pm.expect(jsonData.data.id).to.eql(2);\r",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "GET",
				"header": [],
				"url": {
					"raw": "https://reqres.in/api/users/2",
					"protocol": "https",
					"host": [
						"reqres",
						"in"
					],
					"path": [
						"api",
						"users",
						"2"
					]
				}
			},
			"response": []
		},
		{
			"name": "Get Single User Not Found",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"// Статус код\r",
							"pm.test(\"Status code is 404\", function () {\r",
							"    pm.response.to.have.status(404);\r",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "GET",
				"header": [],
				"url": {
					"raw": "https://reqres.in/api/users/203",
					"protocol": "https",
					"host": [
						"reqres",
						"in"
					],
					"path": [
						"api",
						"users",
						"203"
					]
				}
			},
			"response": []
		},
		{
			"name": "Get List Resource",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"// Статус код\r",
							"pm.test(\"Status code is 200\", function () {\r",
							"    pm.response.to.have.status(200);\r",
							"});\r",
							"// Проверка ответа\r",
							"pm.test(\"page = 1\", function () {\r",
							"    var jsonData = pm.response.json();\r",
							"    pm.expect(jsonData.page).to.eql(1);\r",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "GET",
				"header": [],
				"url": {
					"raw": "https://reqres.in/api/unknown",
					"protocol": "https",
					"host": [
						"reqres",
						"in"
					],
					"path": [
						"api",
						"unknown"
					]
				}
			},
			"response": []
		},
		{
			"name": "Get Single Resource",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"// Статус код\r",
							"pm.test(\"Status code is 200\", function () {\r",
							"    pm.response.to.have.status(200);\r",
							"});\r",
							"// Проверка ответа\r",
							"pm.test(\"page = 1\", function () {\r",
							"    var jsonData = pm.response.json();\r",
							"    pm.expect(jsonData.page).to.eql(1);\r",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "GET",
				"header": [],
				"url": {
					"raw": "https://reqres.in/api/2",
					"protocol": "https",
					"host": [
						"reqres",
						"in"
					],
					"path": [
						"api",
						"2"
					]
				}
			},
			"response": []
		},
		{
			"name": "Get Single Resource Not Found",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"// Статус код\r",
							"pm.test(\"Status code is 404\", function () {\r",
							"    pm.response.to.have.status(404);\r",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "GET",
				"header": [],
				"url": {
					"raw": "https://reqres.in/api/unknown/560",
					"protocol": "https",
					"host": [
						"reqres",
						"in"
					],
					"path": [
						"api",
						"unknown",
						"560"
					]
				}
			},
			"response": []
		},
		{
			"name": "Create User",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"// Статус код\r",
							"pm.test(\"Status code is 201\", function () {\r",
							"    pm.response.to.have.status(201);\r",
							"});\r",
							"// Получение необходимых данных\r",
							"pm.test(\"Значение id заносим userID в enviroments\", function () {\r",
							"    var jsonData = pm.response.json();\r",
							"    // заносим значение id в userID в enviroment\r",
							"    pm.environment.set(\"userID\", jsonData.id);\r",
							"    // заносим значение id в userID в collectionVariables (не знаю зачем, но пусть будет)\r",
							"    pm.collectionVariables.set(\"userId\", jsonData.id);\r",
							"});\r",
							"// Проверка ответа\r",
							"pm.test(\"name = Stepan Ovcevodov, job = beauty blogger\", function () {\r",
							"    var jsonData = pm.response.json();\r",
							"    pm.expect(jsonData.name).to.eql(\"Stepan Ovcevodov\");\r",
							"    pm.expect(jsonData.job).to.eql(\"beauty blogger\");\r",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "POST",
				"header": [],
				"body": {
					"mode": "raw",
					"raw": "{\r\n    \"name\": \"Stepan Ovcevodov\",\r\n    \"job\": \"beauty blogger\"\r\n}",
					"options": {
						"raw": {
							"language": "json"
						}
					}
				},
				"url": {
					"raw": "https://reqres.in/api/users",
					"protocol": "https",
					"host": [
						"reqres",
						"in"
					],
					"path": [
						"api",
						"users"
					]
				}
			},
			"response": []
		},
		{
			"name": "Put Update User",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"// Статус код\r",
							"pm.test(\"Status code is 200\", function () {\r",
							"    pm.response.to.have.status(200);\r",
							"});\r",
							"// Проверка ответа\r",
							"pm.test(\"name = morpheus, job = zion resident\", function () {\r",
							"    var jsonData = pm.response.json();\r",
							"    pm.expect(jsonData.name).to.eql(\"morpheus\");\r",
							"    pm.expect(jsonData.job).to.eql(\"zion resident\");\r",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "PUT",
				"header": [],
				"body": {
					"mode": "raw",
					"raw": "{\r\n    \"name\": \"morpheus\",\r\n    \"job\": \"zion resident\"\r\n}",
					"options": {
						"raw": {
							"language": "json"
						}
					}
				},
				"url": {
					"raw": "https://reqres.in/api/users/{{userID}}",
					"protocol": "https",
					"host": [
						"reqres",
						"in"
					],
					"path": [
						"api",
						"users",
						"{{userID}}"
					]
				}
			},
			"response": []
		},
		{
			"name": "Path Update User",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"// Статус код\r",
							"pm.test(\"Status code is 200\", function () {\r",
							"    pm.response.to.have.status(200);\r",
							"});\r",
							"// Проверка ответа\r",
							"pm.test(\"name = Kot Kotofeich, job = Professional Cat\", function () {\r",
							"    var jsonData = pm.response.json();\r",
							"    pm.expect(jsonData.name).to.eql(\"Kot Kotofeich\");\r",
							"    pm.expect(jsonData.job).to.eql(\"Professional Cat\");\r",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "PUT",
				"header": [],
				"body": {
					"mode": "raw",
					"raw": "{\r\n    \"name\": \"Kot Kotofeich\",\r\n    \"job\": \"Professional Cat\"\r\n}",
					"options": {
						"raw": {
							"language": "json"
						}
					}
				},
				"url": {
					"raw": "https://reqres.in/api/users/{{userID}}",
					"protocol": "https",
					"host": [
						"reqres",
						"in"
					],
					"path": [
						"api",
						"users",
						"{{userID}}"
					]
				}
			},
			"response": []
		},
		{
			"name": "Delete User",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"// Статус код\r",
							"pm.test(\"Status code is 204\", function () {\r",
							"    pm.response.to.have.status(204);\r",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "DELETE",
				"header": [],
				"url": {
					"raw": "https://reqres.in/api/users/{{userID}}",
					"protocol": "https",
					"host": [
						"reqres",
						"in"
					],
					"path": [
						"api",
						"users",
						"{{userID}}"
					]
				}
			},
			"response": []
		},
		{
			"name": "Post Register Successful",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"// Статус код\r",
							"pm.test(\"Status code is 200\", function () {\r",
							"    pm.response.to.have.status(200);\r",
							"});\r",
							"// Проверка ответа\r",
							"pm.test(\"В ответе есть id и token\", function () {\r",
							"    pm.expect(pm.response.text()).to.include(\"id\");\r",
							"    pm.expect(pm.response.text()).to.include(\"token\");\r",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "POST",
				"header": [],
				"body": {
					"mode": "raw",
					"raw": "{\r\n    \"email\": \"eve.holt@reqres.in\",\r\n    \"password\": \"pistol\"\r\n}",
					"options": {
						"raw": {
							"language": "json"
						}
					}
				},
				"url": {
					"raw": "https://reqres.in/api/register",
					"protocol": "https",
					"host": [
						"reqres",
						"in"
					],
					"path": [
						"api",
						"register"
					]
				}
			},
			"response": []
		},
		{
			"name": "Post Register unsuccessful",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"// Статус код\r",
							"pm.test(\"Status code is 400\", function () {\r",
							"    pm.response.to.have.status(400);\r",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "POST",
				"header": [],
				"body": {
					"mode": "raw",
					"raw": "{\r\n    \"email\": \"sydney@fife\"\r\n}",
					"options": {
						"raw": {
							"language": "json"
						}
					}
				},
				"url": {
					"raw": "https://reqres.in/api/register",
					"protocol": "https",
					"host": [
						"reqres",
						"in"
					],
					"path": [
						"api",
						"register"
					]
				}
			},
			"response": []
		},
		{
			"name": "Post Login Successful",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"// Статус код\r",
							"pm.test(\"Status code is 200\", function () {\r",
							"    pm.response.to.have.status(200);\r",
							"});\r",
							"// Проверка ответа\r",
							"pm.test(\"В ответе есть token\", function () {\r",
							"    pm.expect(pm.response.text()).to.include(\"token\");\r",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "POST",
				"header": [],
				"body": {
					"mode": "raw",
					"raw": "{\r\n    \"email\": \"eve.holt@reqres.in\",\r\n    \"password\": \"cityslicka\"\r\n}",
					"options": {
						"raw": {
							"language": "json"
						}
					}
				},
				"url": {
					"raw": "https://reqres.in/api/login",
					"protocol": "https",
					"host": [
						"reqres",
						"in"
					],
					"path": [
						"api",
						"login"
					]
				}
			},
			"response": []
		},
		{
			"name": "Post Login Unsuccessful",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"// Статус код\r",
							"pm.test(\"Status code is 400\", function () {\r",
							"    pm.response.to.have.status(400);\r",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "POST",
				"header": [],
				"body": {
					"mode": "raw",
					"raw": "{\r\n    \"email\": \"peter@klaven\"\r\n}",
					"options": {
						"raw": {
							"language": "json"
						}
					}
				},
				"url": {
					"raw": "https://reqres.in/api/login",
					"protocol": "https",
					"host": [
						"reqres",
						"in"
					],
					"path": [
						"api",
						"login"
					]
				}
			},
			"response": []
		},
		{
			"name": "Get Delayed Response",
			"event": [
				{
					"listen": "test",
					"script": {
						"exec": [
							"// Статус код\r",
							"pm.test(\"Status code is 200\", function () {\r",
							"    pm.response.to.have.status(200);\r",
							"});"
						],
						"type": "text/javascript"
					}
				}
			],
			"request": {
				"method": "GET",
				"header": [],
				"url": {
					"raw": "https://reqres.in/api/users?delay=3",
					"protocol": "https",
					"host": [
						"reqres",
						"in"
					],
					"path": [
						"api",
						"users"
					],
					"query": [
						{
							"key": "delay",
							"value": "3"
						}
					]
				}
			},
			"response": []
		}
	],
	"event": [
		{
			"listen": "prerequest",
			"script": {
				"type": "text/javascript",
				"exec": [
					""
				]
			}
		},
		{
			"listen": "test",
			"script": {
				"type": "text/javascript",
				"exec": [
					""
				]
			}
		}
	],
	"variable": [
		{
			"key": "userId",
			"value": ""
		}
	]
}
© 2022 GitHub, Inc.
Terms
Privacy
Security
Status
Docs
Contact GitHub
Pricing
API
Training
Blog
About
```
