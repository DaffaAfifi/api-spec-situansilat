# Test-Case Situansilat API Spec

![alt text for screen readers](situansilat-dark.png "Text to show on mouseover")

## 1. Login (Mid)

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
  "payload": {
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTAyLCJlbWFpbCI6Im5hbmFuZ2hlckBnbWFpbC5jb20iLCJuYW1hIjoiTmFuYW5nIEhlcml5YW50byIsInJvbGUiOjIsImV4cCI6MTcyOTQ5MTAzNn0.fEOEPkUMFspg5TL_4Y1J90Ct3bxqQr-PGk8PXiKmKic"
  },
  "message": "success login",
  "metadata": {
    "current": "",
    "next": "",
    "prev": ""
  }
}
```

Response Body Error :

```json
{
  "error": "Email or password is incorrect"
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
  "message": "Get users succes",
  "metadata": {
    "current": "",
    "next": "",
    "prev": ""
  }
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
  "message": "Get user success",
  "metadata": {
    "current": "",
    "next": "",
    "prev": ""
  }
}
```

Response Body Error :

```json
{
  "errors": "Users is not found"
}
```

## 4. Get User Saved News API (Mid)

Endpoint : GET /api/users/saved-news/:id

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
  "message": "Get saved news success",
  "metadata": {
    "current": "",
    "next": "",
    "prev": ""
  }
}
```

Response Body Error :

```json
{
  "errors": "Users is not found"
}
```

## 5. Get User Saved News Comment API (High)

Endpoint : GET /api/users/saved-news/comment/:id

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
        "created_at": "20-05-2024",
        "comment": [
          {
            "comment": "Saya tertarik untuk ikut serta di pelatihan ini.",
            "user": "77",
            "created_at": "2024-09-17 04:23:04"
          },
          {
            "comment": "Informasi yang menarik, terima kasih.",
            "user": "11",
            "created_at": "2024-09-17 04:23:04"
          }
        ]
      }
    ]
  },
  "message": "Get saved news comment success",
  "metadata": {
    "current": "",
    "next": "",
    "prev": ""
  }
}
```

Response Body Error :

```json
{
  "errors": "Users is not found"
}
```

## 6. Get User Facilities API (High)

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
  "message": "Get facilities success",
  "metadata": {
    "current": "",
    "next": "",
    "prev": ""
  }
}
```

Response Body Error :

```json
{
  "errors": "Users is not found"
}
```

## 7. Create User API (Low)

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
  "message": "User created successfully",
  "metadata": {
    "current": "",
    "next": "",
    "prev": ""
  },
  "payload": null
}
```

Response Body Error :

```json
{
  "errors": "Email is not valid format"
}
```

## 8. Add Tool to Assistance Tools - Trigger Total Harga (High)

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
  "message": "Tools added successfully",
  "metadata": {
    "current": "",
    "next": "",
    "prev": ""
  },
  "payload": null
}
```

Response Body Error :

```json
{
  "errors": "Qty should be a number"
}
```

## 9. Update User API (Low)

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
  "message": "User udated successfully",
  "metadata": {
    "current": "",
    "next": "",
    "prev": ""
  },
  "payload": null
}
```

Response Body Error :

```json
{
  "errors": "Email is not valid format"
}
```

## 10. Get News Comment by ID (Mid)

Endpoint : GET /api/users/news/comment/:id

Headers :

- Authorization : token

Response Body Success :

```json
{
  "payload": {
    "id": 1,
    "image": "news1.png",
    "title": "5 hair style for 2024",
    "subtitle": "Lorem ipsum dolor sit amet",
    "body": "Lorem ipsum dolor sit amet...",
    "created_at": "20-05-2024",
    "comment": [
      {
        "comment": "Saya tertarik untuk ikut serta di pelatihan ini.",
        "user": "77",
        "created_at": "2024-09-17 04:23:04"
      },
      {
        "comment": "Informasi yang menarik, terima kasih.",
        "user": "11",
        "created_at": "2024-09-17 04:23:04"
      }
    ]
  },
  "message": "Get news comment success",
  "metadata": {
    "current": "",
    "next": "",
    "prev": ""
  }
}
```

Response Body Error :

```json
{
  "errors": "News is not found"
}
```
