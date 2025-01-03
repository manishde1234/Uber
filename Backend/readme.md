# Register User Endpoint

## Description

Registers a new user with the provided information.

## Endpoint

`POST /users/register`

## Request Body

```json
{
    "fullname": {
        "firstname": "string (min 3 characters)",
        "lastname": "string (min 3 characters)"
    },
    "email": "string (valid email format, min 5 characters)",
    "password": "string (min 6 characters)"
}
```

## Responses

### 201 Created

```json
{
    "token": "JWT Token",
    "user": {
        // user object
    }
}
```

### 400 Bad Request

```json
{
    "errors": [
        {
            "msg": "Error message",
            "param": "field",
            // ...
        }
    ]
}
```