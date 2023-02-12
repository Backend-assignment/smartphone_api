# Smartphone store api

This is a simple api for a smartphone store.

## Objectives

- User can create a new brand
- User can create a new smartphone
- User can get all brands
- User can get all smartphones
- User can get a brand by id
- User can get a smartphone by id
- User can update a brand by id
- User can update a smartphone by id
- User can delete a brand by id
- User can delete a smartphone by id
- User can get all smartphones by brand id
- User can get smartphones by price range
- User can get smartphones by date

## Database schema

Smartphone
| Field | Type | Description |
| --- | --- | --- |
| id | int | Primary key |
| name | varchar(255) | Brand name |
| created_at | datetime | Creation date |
| updated_at | datetime | Update date |
| brand_id | varchar(255) | Brand id |
| model | varchar(255) | Model name |
| price | decimal(10,2) | Price |
| memory | varchar(255) | Memory |
| color | varchar(255) | Color |
| description | text | Description |
| image | varchar(255) | Image |

Brand
| Field | Type | Description |
| --- | --- | --- |
| id | int | Primary key |
| name | varchar(255) | Brand name |
| created_at | datetime | Creation date |
| updated_at | datetime | Update date |
| email | varchar(255) | Email |
| phone | varchar(255) | Phone |
| address | varchar(255) | Address |
| website | varchar(255) | Website |

## API endpoints

| Method | Endpoint | Description |
| --- | --- | --- |
| GET | /api/brands | Get all brands |
| GET | /api/brands/{id} | Get brand by id |
| POST | /api/brands | Create a new brand |
| POST | /api/update/brands/{id} | Update a brand by id |
| DELETE | /api/delete/brands/{id} | Delete a brand by id |
| GET | /api/smartphones | Get all smartphones |
| GET | /api/smartphones/{id} | Get smartphone by id |
| POST | /api/smartphones | Create a new smartphone |
| POST | /api/update/smartphones/{id} | Update a smartphone by id |
| DELETE | /api/delete/smartphones/{id} | Delete a smartphone by id |

## Documentation

Get all brands

This endpoint returns all brands.

API request:

```bash
curl -X GET "http://localhost:8000/api/brands" -H "accept: application/json"
```

API response:

```bash
{
    "brands":[
        {
            "id":1,
            "name":"Apple",
            "created_at":"2020-05-01T12:00:00.000000Z",
            "updated_at":"2020-05-01T12:00:00.000000Z",
            "email":"apple@mail.com",
            "phone":"123456789",
            "address":"Apple street",
            "website":"www.apple.com"
        },
        {
            "id":2,
            "name":"Samsung",
            "created_at":"2020-05-01T12:00:00.000000Z",
            "updated_at":"2020-05-01T12:00:00.000000Z",
            "email":"samsung@mail.com",
            "phone":"123456789",
            "address":"Samsung street",
            "website":"www.samsung.com"
        }
    
    
    ]
}
```

Get brand by id

This endpoint returns a brand by id.

API request:

```bash
curl -X GET "http://localhost:8000/api/brands/1" -H "accept: application/json"
```

API response:

```bash
{
    "id":1,
    "name":"Apple",
    "created_at":"2020-05-01T12:00:00.000000Z",
    "updated_at":"2020-05-01T12:00:00.000000Z",
    "email":"example@gmail.com",
    "phone":"123456789",
    "address":"Apple street",
    "website":"www.apple.com"
}
```

Create a new brand

This endpoint creates a new brand.

API request:

```bash
curl -X POST "http://localhost:8000/api/brands" -H "accept: application/json" -H "Content-Type: application/json" -d "{ \"name\": \"Apple\", \"email\": \"
```

API response:

```bash
{
{
    "id":1,
    "name":"Apple",
    "created_at":"2020-05-01T12:00:00.000000Z",
    "updated_at":"2020-05-01T12:00:00.000000Z",
    "email":"example@gmail.com",
    "phone":"123456789",
    "address":"Apple street",
    "website":"www.apple.com"
}
```

Update a brand by id

This endpoint updates a brand by id.

API request:

```bash
curl -X POST "http://localhost:8000/api/update/brands/1" -H "accept: application/json" -H "Content-Type: application/json" -d "{ \"name\": \"Apple\", \"email\": \"
```

API response:

```bash
{
    "id":1,
    "name":"Apple",
    "created_at":"2020-05-01T12:00:00.000000Z",
    "updated_at":"2020-05-01T12:00:00.000000Z",
    "email":"example@gmail.com",
    "phone":"123456789",
    "address":"Apple street",
    "website":"www.apple.com"
}
```

Delete a brand by id

This endpoint deletes a brand by id.

API request:

```bash
curl -X DELETE "http://localhost:8000/api/delete/brands/1" -H "accept: application/json"
```

API response:

```bash
{
    "message":"Brand deleted successfully"
}
```

Get all smartphones

This endpoint returns all smartphones.

API request:

```bash
curl -X GET "http://localhost:8000/api/smartphones" -H "accept: application/json"
```

API response:

```bash
{
    "smartphones":[
        {
            "id":1,
            "name":"Apple",
            "created_at":"2020-05-01T12:00:00.000000Z",
            "updated_at":"2020-05-01T12:00:00.000000Z",
            "brand_id":1,
            "model":"iPhone 11",
            "price":"1000.00",
            "memory":"64GB",
            "color":"Black",
            "description":"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec auctor, nisl eget ultricies lacinia, nisl nunc aliquet nunc, ege
            "image":"https://www.apple.com/v/iphone/home/ab/images/overview/compare/compare_iphone_11__f2x2.jpg"
        },
        {
            "id":2,
            "name":"Samsung",
            "created_at":"2020-05-01T12:00:00.000000Z",
            "updated_at":"2020-05-01T12:00:00.000000Z",
            "brand_id":2,
            "model":"Galaxy S20",
            "price":"1000.00",
            "memory":"64GB",
            "color":"Black",
            "description":"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec auctor, nisl eget ultricies lacinia, nisl nunc aliquet nunc, ege
            "image":"https://www.samsung.com/global/galaxy/galaxy-s20/images/galaxy-s20/compare/galaxy-s20_compare_01.jpg"
        }
    ]
}
```

Get smartphone by id

This endpoint returns a smartphone by id.

API request:

```bash
curl -X GET "http://localhost:8000/api/smartphones/1" -H "accept: application/json"
```

API response:

```bash
{
    "id":1,
    "name":"Apple",
    "created_at":"2020-05-01T12:00:00.000000Z",
    "updated_at":"2020-05-01T12:00:00.000000Z",
    "brand_id":1,
    "model":"iPhone 11",
    "price":"1000.00",
    "memory":"64GB",
    "color":"Black",
    "description":"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec auctor, nisl eget ultricies lacinia, nisl nunc aliquet nunc, ege
    "image":"https://www.apple.com/v/iphone/home/ab/images/overview/compare/compare_iphone_11__f2x2.jpg"
}
```

Create a new smartphone

This endpoint creates a new smartphone.

API request:

```bash
curl -X POST "http://localhost:8000/api/smartphones" -H "accept: application/json" -H "Content-Type: application/json" -d "{ \"name\": \"Apple\", \"email\": \"
```

API response:

```bash
{
    "id":1,
    "name":"Apple",
    "created_at":"2020-05-01T12:00:00.000000Z",
    "updated_at":"2020-05-01T12:00:00.000000Z",
    "brand_id":1,
    "model":"iPhone 11",
    "price":"1000.00",
    "memory":"64GB",
    "color":"Black",
    "description":"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec auctor, nisl eget ultricies lacinia, nisl nunc aliquet nunc, ege
    "image":"https://www.apple.com/v/iphone/home/ab/images/overview/compare/compare_iphone_11__f2x2.jpg"
}
```

Update a smartphone by id

This endpoint updates a smartphone by id.

API request:

```bash
curl -X POST "http://localhost:8000/api/update/smartphones/1" -H "accept: application/json" -H "Content-Type: application/json" -d "{ \"name\": \"Apple\", \"email\": \"
```

API response:

```bash
{
    "id":1,
    "name":"Apple",
    "created_at":"2020-05-01T12:00:00.000000Z",
    "updated_at":"2020-05-01T12:00:00.000000Z",
    "brand_id":1,
    "model":"iPhone 11",
    "price":"1000.00",
    "memory":"64GB",
    "color":"Black",
    "description":"Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec auctor, nisl eget ultricies lacinia, nisl nunc aliquet nunc, ege
    "image":"https://www.apple.com/v/iphone/home/ab/images/overview/compare/compare_iphone_11__f2x2.jpg"
}
```

Delete a smartphone by id

This endpoint deletes a smartphone by id.

API request:

```bash
curl -X DELETE "http://localhost:8000/api/delete/smartphones/1" -H "accept: application/json"
```

API response:

```bash
{
    "message":"Smartphone deleted successfully"
}
```
