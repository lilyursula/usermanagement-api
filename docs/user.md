# User API Spec

## Register User

Endpoint : POST /api/users

Request Body
```json
{
    "username" : "username",
    "password" : "Password",
    "name" : "Full Name"
}
```

Response Body (Success)
```json
{
    "code" : "201",
    "error": "User registered"
}
```

Response Body (Failed)
```json
{
    "code" : "400",
    "error": "Bad Request"
}
```


## Login User
Endpoint : POST api/auth/login

Request Header 

X-API-Token : Token Mandatory

Request Body
```json
{
    "username" : "username",
    "password" : "password" 
}
```

Response Body (Success)
```json
{
    "token" : "string",
    "expiredAt" : 1231241234 // milliseconds
}
```

Response Body (Failed)
```json
{
    "code" : "401",
    "error": "Unauthorized"
}
```

## Update User
Endpoint : PUT /api/users/{current}

Request Header 

X-API-Token : Token Mandatory

Request Body
```json
{
    "name" : "Full Name", //put if you want to update new Full Name
    "password" : "new password" //put if you want to update new password
}
```

Response Body (Success)
```json
{
    "token" : "string",
    "expiredAt" : 1231241234 // milliseconds
}
```

Response Body (Failed)
```json
{
    "code" : "401",
    "error": "Unauthorized"
}
```


## Get User

Endpoint : GET /api/users/{current}

Request Header 

X-API-Token : Token Mandatory

Response Body (Success)
```json
{
    "username" : "username",
    "name" : "Full Name"
}
```

Response Body (Failed)
```json
{
    "code" : "401",
    "error": "Unauthorized"
}
```

## Logout User

Endpoint : DELETE /api/auth/logout

Request Header 

X-API-Token : Token Mandatory

Response Body (Failed)
```json
{
    "message" : "OK"
}
```