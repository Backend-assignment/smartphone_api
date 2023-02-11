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