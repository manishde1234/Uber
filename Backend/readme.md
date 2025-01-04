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

# Login User Endpoint

## Description

Logs in a user with the provided credentials.

## Endpoint

`POST /users/login`

## Request Body

```json
{
    "email": "string (valid email format)",
    "password": "string (min 6 characters)"
}
```

## Responses

### 200 OK

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

### 401 Unauthorized

```json
{
    "message": "Invalid email or password"
}
```

# Get User Profile Endpoint

## Description

Gets the profile of the authenticated user.

## Endpoint

`GET /users/profile`

## Responses

### 200 OK

```json
{
    // user object
}
```

### 401 Unauthorized

```json
{
    "message": "Unauthorized"
}
```

# Logout User Endpoint

## Description

Logs out the authenticated user.

## Endpoint

`GET /users/logout`

## Responses

### 200 OK

```json
{
    "message": "Logged out successfully"
}
```

### 401 Unauthorized

```json
{
    "message": "Unauthorized"
}
```