# Test-Case Situansilat API Spec

![alt text for screen readers](situansilat-dark.png "Text to show on mouseover")

## 1. Login (High)

Endpoint : POST /api/login

Headers :

- Authorization : token

Request Body :

```json
{
  "email": "daffafifi@gmail.com",
  "password": "12345678"
}
```

Response Body Success :

```json
{
  "payload": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c",
  "message": "Login success"
}
```

Response Body Error :

```json
{
  "errors": "Email is not valid format"
}
```

## 2. Get All Users API (Low)

Endpoint : GET /api/users

Headers :

- Authorization : token

Response Body Success :

```json
{
  "payload": [
    {
      "id": 1,
      "name": "Daffa Afifi Syahrony",
      "email": "daffafifi@gmail.com",
      "NIK": "1234567891011121",
      "address": "Tempurejo, Jember",
      "phone": "089538550152",
      "gender": "L",
      "head_of_the_house": 0,
      "place_of_birth": "Jember",
      "date_of_birth": "05-02-2003",
      "age": 21,
      "business": "Barbershop"
    },
    {
      "id": 2,
      "name": "Heru Priyanto",
      "email": "herupriyanto@gmail.com",
      "NIK": "1234567891011345",
      "address": "Sumbersari, Jember",
      "phone": "089538987654",
      "gender": "L",
      "head_of_the_house": 1,
      "place_of_birth": "Jember",
      "date_of_birth": "01-02-1980",
      "age": 44,
      "business": "Taylor"
    }
  ],
  "message": "Get users succes"
}
```

Response Body Error :

```json
{
  "errors": "Users is not found"
}
```

## 3. Get User by ID API (Low)

Endpoint : GET /api/users/:id

Headers :

- Authorization : token

Response Body Success :

```json
{
  "payload": {
    "id": 1,
    "name": "Daffa Afifi Syahrony",
    "email": "daffafifi@gmail.com",
    "NIK": "1234567891011121",
    "address": "Tempurejo, Jember",
    "phone": "089538550152",
    "gender": "L",
    "head_of_the_house": 0,
    "place_of_birth": "Jember",
    "date_of_birth": "05-02-2003",
    "age": 21,
    "business": "Barbershop"
  },
  "message": "Get user success"
}
```

Response Body Error :

```json
{
  "errors": "Users is not found"
}
```

## 4. Get User Saved News API (Mid)

Endpoint : GET /api/users-saved-news/:id

Headers :

- Authorization : token

Response Body Success :

```json
{
  "payload": {
    "id": 1,
    "name": "Daffa Afifi Syahrony",
    "email": "daffafifi@gmail.com",
    "NIK": "1234567891011121",
    "address": "Tempurejo, Jember",
    "phone": "089538550152",
    "gender": "L",
    "head_of_the_house": 0,
    "place_of_birth": "Jember",
    "date_of_birth": "05-02-2003",
    "age": 21,
    "business": "Barbershop",
    "berita_tersimpan": [
      {
        "id": 1,
        "image": "news1.png",
        "title": "5 hair style for 2024",
        "subtitle": "Lorem ipsum dolor sit amet",
        "body": "Lorem ipsum dolor sit amet...",
        "created_at": "20-05-2024"
      },
      {
        "id": 2,
        "image": "news2.png",
        "title": "Mullet new trend",
        "subtitle": "Lorem ipsum dolor sit amet",
        "body": "Lorem ipsum dolor sit amet...",
        "created_at": "24-05-2024"
      }
    ]
  },
  "message": "Get saved news success"
}
```

Response Body Error :

```json
{
  "errors": "Users is not found"
}
```

## 5. Get User Facilities API (High)

Endpoint : GET /api/users-facilities/:id

Headers :

- Authorization : token

Response Body Success :

```json
{
  "payload": {
    "id": 1,
    "name": "Daffa Afifi Syahrony",
    "email": "daffafifi@gmail.com",
    "NIK": "1234567891011121",
    "address": "Tempurejo, Jember",
    "phone": "089538550152",
    "gender": "L",
    "head_of_the_house": 0,
    "place_of_birth": "Jember",
    "date_of_birth": "05-02-2003",
    "age": 21,
    "business": "Barbershop",
    "sertifikat": [
      {
        "id": 1,
        "name": "Senior Barbershop Skill",
        "certificate_number": "SBK00001",
        "published_date": "01-01-2024",
        "expired_date": "01-01-2029",
        "description": "Lorem ipsum dolor sit amet..."
      }
    ],
    "pelatihan": [
      {
        "id": 1,
        "name": "Senior Barbershop Skill by Dicoding",
        "organizer": "Dicoding",
        "training_date": "20-12-2023",
        "place": "Politeknik Negeri Jember"
      },
      {
        "id": 2,
        "name": "Junior Web Developer by Ruangguru",
        "organizer": "Ruangguru",
        "training_date": "20-02-2024",
        "place": "Universitas Jember"
      }
    ],
    "bantuan": [
      {
        "id": 1,
        "name": "Barbershop tools",
        "coordinator": "Nanang Heriyanto",
        "budget_source": "APBN",
        "year_of_grant": "02-04-2023",
        "alat": [
          {
            "id": 1,
            "name": "Hair chopper",
            "qty": 1
          },
          {
            "id": 2,
            "name": "Stand fan",
            "qty": 1
          }
        ]
      }
    ]
  },
  "message": "Get facilities success"
}
```

Response Body Error :

```json
{
  "errors": "Users is not found"
}
```

## 6. Create User API (Low)

Endpoint : POST /api/users

Headers :

- Authorization : token

Request Body :

```json
{
  "name": "Daffa Afifi Syahrony",
  "email": "daffafifi@gmail.com",
  "NIK": "1234567891011121",
  "address": "Tempurejo, Jember",
  "phone": "089538550152",
  "gender": "L",
  "head_of_the_house": 0,
  "place_of_birth": "Jember",
  "date_of_birth": "05-02-2003",
  "age": 21,
  "business": "Barbershop"
}
```

Response Body Success :

```json
{
  "payload": {
    "fieldCount": 0,
    "affectedRows": 1,
    "insertId": 112,
    "info": "",
    "serverStatus": 2,
    "warningStatus": 0,
    "changedRows": 0
  },
  "message": "Register success"
}
```

Response Body Error :

```json
{
  "errors": "Email is not valid format"
}
```

## 7. Add Tool to Help API - Trigger Tool Stock (Mid)

Endpoint : POST /api/add-tools

Headers :

- Authorization : token

Request Body :

```json
{
  "help_id": 1,
  "tool_id": 1,
  "qty": 2
}
```

Response Body Success :

```json
{
  "payload": {
    "fieldCount": 0,
    "affectedRows": 1,
    "insertId": 112,
    "info": "",
    "serverStatus": 2,
    "warningStatus": 0,
    "changedRows": 0
  },
  "message": "Add tools success"
}
```

Response Body Error :

```json
{
  "errors": "Qty should be a number"
}
```

## 8. Update User API (Low)

Endpoint : PUT /api/users/:id

Headers :

- Authorization : token

Request Body :

```json
{
  "name": "Daffa Afifi Syahrony",
  "email": "daffafifi@gmail.com",
  "NIK": "1234567891011121",
  "address": "Tempurejo, Jember",
  "phone": "089538550152",
  "gender": "L",
  "head_of_the_house": 0,
  "place_of_birth": "Jember",
  "date_of_birth": "05-02-2003",
  "age": 21,
  "business": "Barbershop"
}
```

Response Body Success :

```json
{
  "payload": {
    "fieldCount": 0,
    "affectedRows": 1,
    "insertId": 112,
    "info": "",
    "serverStatus": 2,
    "warningStatus": 0,
    "changedRows": 0
  },
  "message": "Update user success"
}
```

Response Body Error :

```json
{
  "errors": "Email is not valid format"
}
```

## 9. Update Tools Quantity API - Trigger Tool Stock (Mid)

Endpoint : PUT /api/add-tools

Headers :

- Authorization : token

Request Body :

```json
{
  "help_id": 1,
  "tool_id": 1,
  "qty": 3
}
```

Response Body Success :

```json
{
  "payload": {
    "fieldCount": 0,
    "affectedRows": 1,
    "insertId": 112,
    "info": "",
    "serverStatus": 2,
    "warningStatus": 0,
    "changedRows": 0
  },
  "message": "Update tools qty success"
}
```

Response Body Error :

```json
{
  "errors": "Qty should be a number"
}
```

## 10. Remove News API (Low)

Endpoint : DELETE /api/news/:id

Headers :

- Authorization : token

Response Body Success :

```json
{
  "data": "OK"
}
```

Response Body Error :

```json
{
  "errors": "News is not found"
}
```

## 11. Remove Multiple News API (Mid)

Endpoint : DELETE /api/news/[:id, :id]

Headers :

- Authorization : token

Response Body Success :

```json
{
  "data": "OK"
}
```

Response Body Error :

```json
{
  "errors": "News is not found"
}
```
