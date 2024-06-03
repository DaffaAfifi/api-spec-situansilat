# Test-Case Situansilat API Spec

## 1. Get All Users API (Low)

Endpoint : GET /api/users

Headers :
- Authorization : token

Response Body Success :

```json
{
    "data" : [
        {
            "id" : 1,
            "name" : "Daffa Afifi Syahrony",
            "email" : "daffafifi@gmail.com",
            "NIK" : "1234567891011121",
            "address" : "Tempurejo, Jember",
            "phone" : "089538550152",
            "gender" : "L",
            "head_of_the_house" : 0,
            "place_of_birth" : "Jember",
            "date_of_birth" : "05-02-2003",
            "age" : 21,
            "business" : "Barbershop",
        },
        {
            "id" : 2,
            "name" : "Heru Priyanto",
            "email" : "herupriyanto@gmail.com",
            "NIK" : "1234567891011345",
            "address" : "Sumbersari, Jember",
            "phone" : "089538987654",
            "gender" : "L",
            "head_of_the_house" : 1,
            "place_of_birth" : "Jember",
            "date_of_birth" : "01-02-1980",
            "age" : 44,
            "business" : "Taylor",
        }
    ]
}
```

Response Body Error :

```json
{
    "errors" : "Users is not found"
}
```

## 2. Get User by ID API (Low)

Endpoint : GET /api/users/:id

Headers :
- Authorization : token

Response Body Success :

```json
{
    "data" : {
        "id" : 1,
        "name" : "Daffa Afifi Syahrony",
        "email" : "daffafifi@gmail.com",
        "NIK" : "1234567891011121",
        "address" : "Tempurejo, Jember",
        "phone" : "089538550152",
        "gender" : "L",
        "head_of_the_house" : 0,
        "place_of_birth" : "Jember",
        "date_of_birth" : "05-02-2003",
        "age" : 21,
        "business" : "Barbershop",
    }
}
```

Response Body Error :

```json
{
    "errors" : "Users is not found"
}
```

## 3. Get User Saved News API (Mid)

Endpoint : GET /api/users-saved-news/:id

Headers :
- Authorization : token

Response Body Success :

```json
{
    "data" : {
        "id" : 1,
        "name" : "Daffa Afifi Syahrony",
        "email" : "daffafifi@gmail.com",
        "NIK" : "1234567891011121",
        "address" : "Tempurejo, Jember",
        "phone" : "089538550152",
        "gender" : "L",
        "head_of_the_house" : 0,
        "place_of_birth" : "Jember",
        "date_of_birth" : "05-02-2003",
        "age" : 21,
        "business" : "Barbershop",
        "saved_news" : [
            {
                "id" : 1,
                "image" : "news1.png",
                "title" : "5 hair style for 2024",
                "subtitle" : "Lorem ipsum dolor sit amet",
                "body" : "Lorem ipsum dolor sit amet...",
                "created_at" : "20-05-2024"
            },
            {
                "id" : 2,
                "image" : "news2.png",
                "title" : "Mullet new trend",
                "subtitle" : "Lorem ipsum dolor sit amet",
                "body" : "Lorem ipsum dolor sit amet...",
                "created_at" : "24-05-2024"
            }
        ]
    }
}
```

Response Body Error :

```json
{
    "errors" : "Users is not found"
}
```

## 4. Get User Facilities API (High)

Endpoint : GET /api/users-facilities/:id

Headers :
- Authorization : token

Response Body Success :

```json
{
    "data" : {
        "id" : 1,
        "name" : "Daffa Afifi Syahrony",
        "email" : "daffafifi@gmail.com",
        "NIK" : "1234567891011121",
        "address" : "Tempurejo, Jember",
        "phone" : "089538550152",
        "gender" : "L",
        "head_of_the_house" : 0,
        "place_of_birth" : "Jember",
        "date_of_birth" : "05-02-2003",
        "age" : 21,
        "business" : "Barbershop",
        "certificates" : [
            {
                "id" : 1,
                "name" : "Senior Barbershop Skill",
                "certificate_number" : "SBK00001",
                "published_date" : "01-01-2024",
                "expired_date" : "01-01-2029",
                "description" : "Lorem ipsum dolor sit amet..."
            },
        ],
        "trainings" : [
            {
                "id" : 1,
                "name" : "Senior Barbershop Skill by Dicoding",
                "organizer" : "Dicoding",
                "training_date" : "20-12-2023",
                "place" : "Politeknik Negeri Jember",
            },
            {
                "id" : 2,
                "name" : "Junior Web Developer by Ruangguru",
                "organizer" : "Ruangguru",
                "training_date" : "20-02-2024",
                "place" : "Universitas Jember",
            },
        ],
        "helps" : [
            {
                "id" : 1,
                "name" : "Barbershop tools",
                "coordinator" : "Nanang Heriyanto",
                "budget_source" : "APBN",
                "year_of_grant" : "02-04-2023",
                "tools" : [
                    {
                        "id" : 1,
                        "name" : "Hair chopper",
                        "qty" : 1
                    },
                    {
                        "id" : 2,
                        "name" : "Stand fan",
                        "qty" : 1
                    },
                ],
            },
        ],
    }
}
```

Response Body Error :

```json
{
    "errors" : "Users is not found"
}
```

## 5. Create User API (Low)

Endpoint : POST /api/users

Headers :
- Authorization : token

Request Body :

```json
{
    "name" : "Daffa Afifi Syahrony",
    "email" : "daffafifi@gmail.com",
    "NIK" : "1234567891011121",
    "address" : "Tempurejo, Jember",
    "phone" : "089538550152",
    "gender" : "L",
    "head_of_the_house" : 0,
    "place_of_birth" : "Jember",
    "date_of_birth" : "05-02-2003",
    "age" : 21,
    "business" : "Barbershop",
}
```

Response Body Success :

```json
{
    "data" : {
        "id" : 1,
        "name" : "Daffa Afifi Syahrony",
        "email" : "daffafifi@gmail.com",
        "NIK" : "1234567891011121",
        "address" : "Tempurejo, Jember",
        "phone" : "089538550152",
        "gender" : "L",
        "head_of_the_house" : 0,
        "place_of_birth" : "Jember",
        "date_of_birth" : "05-02-2003",
        "age" : 21,
        "business" : "Barbershop",
    }
}
```

Response Body Error :

```json
{
    "errors" : "Email is not valid format"
}
```

## 6. Add Tool to Help API - Trigger Tool Stock (Mid)

Endpoint : POST /api/add-tools

Headers :
- Authorization : token

Request Body :

```json
{
    "help_id" : 1,
    "tool_id" : 1,
    "qty" : 2
}
```

Response Body Success :

```json
{
    "data" : {
        "id" : 1,
        "name" : "Barbershop tools",
        "coordinator" : "Nanang Heriyanto",
        "budget_source" : "APBN",
        "year_of_grant" : "02-04-2023",
        "tools" : [
            {
                "id" : 1,
                "name" : "Hair chopper",
                "qty" : 2
            },
        ],
    }
}
```

Response Body Error :

```json
{
    "errors" : "Qty should be a number"
}
```

## 7. Update User API (Low)

Endpoint : PUT /api/users/:id

Headers :
- Authorization : token

Request Body :

```json
{
    "name" : "Daffa Afifi Syahrony",
    "email" : "daffafifi@gmail.com",
    "NIK" : "1234567891011121",
    "address" : "Tempurejo, Jember",
    "phone" : "089538550152",
    "gender" : "L",
    "head_of_the_house" : 0,
    "place_of_birth" : "Jember",
    "date_of_birth" : "05-02-2003",
    "age" : 21,
    "business" : "Barbershop",
}
```

Response Body Success :

```json
{
    "data" : {
        "name" : "Daffa Afifi Syahrony",
        "email" : "daffafifi@gmail.com",
        "NIK" : "1234567891011121",
        "address" : "Tempurejo, Jember",
        "phone" : "089538550152",
        "gender" : "L",
        "head_of_the_house" : 0,
        "place_of_birth" : "Jember",
        "date_of_birth" : "05-02-2003",
        "age" : 21,
        "business" : "Barbershop",
    }
}
```

Response Body Error :

```json
{
    "errors" : "Email is not valid format"
}
```

## 8. Update Tools Quantity API - Trigger Tool Stock (Mid)

Endpoint : PUT /api/add-tools

Headers :
- Authorization : token

Request Body :

```json
{
    "help_id" : 1,
    "tool_id" : 1,
    "qty" : 3
}
```

Response Body Success :

```json
{
    "data" : {
        "id" : 1,
        "name" : "Barbershop tools",
        "coordinator" : "Nanang Heriyanto",
        "budget_source" : "APBN",
        "year_of_grant" : "02-04-2023",
        "tools" : [
            {
                "id" : 1,
                "name" : "Hair chopper",
                "qty" : 3
            },
        ],
    }
}
```

Response Body Error :

```json
{
    "errors" : "Qty should be a number"
}
```

## 9. Remove News API (Low)

Endpoint : DELETE /api/news/:id

Headers :
- Authorization : token

Response Body Success :

```json
{
    "data" : "OK"
}
```

Response Body Error :

```json
{
    "errors" : "Contact is not found"
}
```

## 10. Remove Multiple News API (Mid)

Endpoint : DELETE /api/news/[:id, :id]

Headers :
- Authorization : token

Response Body Success :

```json
{
    "data" : "OK"
}
```

Response Body Error :

```json
{
    "errors" : "Contact is not found"
}
```