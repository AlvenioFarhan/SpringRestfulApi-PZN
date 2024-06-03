# Contact API Spec

## Create Contact

Endpoint : POST /api/contact

Request Header :

- X-API-TOKEN : Token (Mandatory)

Request Body : 

```json
{
  "firstName": "Alvenio Farhan",
  "lastName": "Prayogo",
  "email": "alveniofarhan@gmail.com",
  "phone": "085156066856"
}
```

Response Body (Success) :

```json
{
  "data": {
    "id": "random-string",
    "firstName": "Alvenio Farhan",
    "lastName": "Prayogo",
    "email": "alveniofarhan@gmail.com",
    "phone": "085156066856"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Email format invalid, phone format invalid, ..."
}
```

## Update Contact

Endpoint : PUT /api/contact/{idContact}

Request Header :

- X-API-TOKEN : Token (Mandatory)

Request Body :

```json
{
  "firstName": "Alvenio Farhan",
  "lastName": "Prayogo",
  "email": "alveniofarhan@gmail.com",
  "phone": "085156066856"
}
```

Response Body (Success) :

```json
{
  "data": {
    "id": "random-string",
    "firstName": "Alvenio Farhan",
    "lastName": "Prayogo",
    "email": "alveniofarhan@gmail.com",
    "phone": "085156066856"
  }
}
```

Response Body (Failed) :

```json
{
  "errors": "Email format invalid, phone format invalid, ..."
}
```

## GET Contact

Endpoint : GET /api/contacts/{idContact}

Request Header :

- X-API-TOKEN : Token (Mandatory)

Response Body (Success) :

```json
{
  "data": {
    "id": "random-string",
    "firstName": "Alvenio Farhan",
    "lastName": "Prayogo",
    "email": "alveniofarhan@gmail.com",
    "phone": "085156066856"
  }
}
```

Response Body (Failed, 404) :

```json
{
  "errors": "Contact is not found"
}
```

## Search Contact

Endpoint : GET /api/contacts

Query Param :

- name : String, contact first name or last name, using like query, optional
- phone : String, contact name, using like query, optional
- email : String, contact email, using like query, optional
- page : Integer, start from 0, default 0
- size : Integer, default 10

Request Header :

- X-API-TOKEN : Token (Mandatory)

Response Body (Success) :

```json
{
  "data": [
    {
      "id": "random-string",
      "firstName": "Alvenio Farhan",
      "lastName": "Prayogo",
      "email": "alveniofarhan@gmail.com",
      "phone": "085156066856"
    }
  ],
  "paging": {
    "currentPage": 0,
    "totalPage": 10,
    "size": 10
  }
}
```

Response Body (Failed) :

```json
{
  "errors" : "Unauthorized"
}
```

## Remove Contact

Endpoint : DELETE /api/contacts/{idContact}

Request Header :

- X-API-TOKEN : Token (Mandatory)

Response Body (Success) :

```json
{
  "data": "OK"
}
```

Response Body (Failed) :

```json
{
  "errors": "Contact is not found"
}
```