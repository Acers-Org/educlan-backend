# EDUCLAN BACKEND

This repository serves as the backend for EDUCLAN- an edutech solution that allows schools to provided learning services to students and manage their data.

## Table of Content

- [Scripts](#scripts)
- [Motivation](#motivation)
- [API](#api)
- [Information for programmers](#information-for-programmer)
- [Credits](#credits)

## Motivation

This project was conceive as part of the AngelHack Hackaton in 2022.

## Scripts

In the project directory, you can run:

### `npm run dev`

Runs the app in the development mode.

### `npm test`

This runs tests for the app

### `npm start`

Builds the app for production.

## API

The API is a rest API which uses POST, GET, PATCH and DELETE HTTP methods to communicate. The HTTP response contains a message, status and errors. All responses come in standars JSON. All request must include a `content-type` of `application/json`.

- [Responses](#response)
- [Requests](#requests)

### Responses

The following **HTTP Response codes** are used by the API

```
200: Success
201: Resource Created
400: Bad request
401: Unauthorized
404: Not found
405: Method not allowed
422: Unprocessable Entity
50X: Server Error
```

#### Example Success Response Message

```json
http code 200
{

    "message": "Successfully created",
    "data": {},
    "success": 1
}
```

#### Example Error Response Message

```json
http code 404
{

    "message": "`OOPs!! Not found",
    "success": 0
}
```

### Requests

In requests that require a body, a valid JSON must be provided. To make it easier to locate available requests endpoints and how to use them, they are listed and described here. The api based path is given below:

- [School Requests](#school-requests)

#### School Requests

#### Create School

**You send:** Details to create a school.
**You get:** The newly created school.

**Request:**

```json
POST /schools
Accept: application/json
Content-Type: application/json
{
"message":"School Created",
"data":{
      "school_name": "Test University",
      "category":"university",
      "address": {
          "lines": ["No 10", "Welfare quarters"],
          "postcode":"",
          "city": "Makurdi",
          "state": "Benue",
         "country": "Nigeria"
  },
  "contact": {
    "phone": "",
    "email": ""
  }
}
  "success": 1
}
```

#### Get Schools

**You send:** ``
**You get:** All schools.

**Request:**

```json
GET /schools
Accept: application/json
Content-Type: application/json
{
"message":"All schools",
"data":[
  {
      "school_name": "Test University",
      "category":"university",
      "address": {
          "lines": ["No 10", "Welfare quarters"],
          "postcode":"",
          "city": "Makurdi",
          "state": "Benue",
         "country": "Nigeria"
  },
  "contact": {
    "phone": "",
    "email": ""
  }
}
],
"success": 1
}
```

#### Single School

**Request:**

```json
GET /schools/1234567890
Accept: application/json
Content-Type: application/json
{
"message":"school details",
"data":{
      "school_name": "Test University",
      "category":"university",
      "address": {
          "lines": ["No 10", "Welfare quarters"],
          "postcode":"",
          "city": "Makurdi",
          "state": "Benue",
         "country": "Nigeria"
  },
  "contact": {
    "phone": "",
    "email": ""
  },
},
  "success": 1
}
```

#### Update Schools

**You send:** ``
**You get:** All schools.

**Request:**

```json
PATCH /schools/1234567890
Accept: application/json
Content-Type: application/json
{
"message":"School update",
"data":
  {
      "school_name": "Test University",
      "address": {
          "lines": ["No 10", "Welfare quarters"],
          "postcode":"",
          "city": "Makurdi",
          "state": "Benue",
         "country": "Nigeria"
      }
  },
"success": 1
}
```

#### Delete School

**Request:**

```json
DELETE /schools/1234567890
Accept: application/json
Content-Type: application/json
{
"message":"School Dleted",
"data":{
      "school_name": "Test University",
      "category":"university",
      "address": {
          "lines": ["No 10", "Welfare quarters"],
          "postcode":"",
          "city": "Makurdi",
          "state": "Benue",
         "country": "Nigeria"
  },
  "contact": {
    "phone": "",
    "email": ""
  },
},
  "success": 1
}
```

## Information for programmers

This repo can be used as template for programmers who are looking to build `NodeJS/express APIs using MongoDB`. This repo does not accept contributions excepts from the listed contributors below.

## Credits

This project is possible as a result of the collaborative work of the members list below:

- Remilekun Odegbani
- Deelite
- Kotoye Gbemisola
- Evelyn Anyebe
