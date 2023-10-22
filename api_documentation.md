## Message Blast API Documentation

<br>

### Authentication

<br>

Description: register new user <br>
Endpoint: `/api/v1/auth/register` <br>
Method: `POST` <br>
Headers:
```json
{
    "Content-Type": "application/json"
}
```
Body:
```json
{
    "firstName": "admin",
    "lastName": "new",
    "email": "admin@admin.com",
    "password": "admin123"
}
```
Response:
```json
{
    "statusCode": 201,
    "status": "success",
    "timestamp": "2023-10-22T00:00:00",
    "data": {
        "user": {
            "id": 1,
            "firstName": "admin",
            "lastName": "new",
            "email": "admin@admin.com",
            "createdAt": "2023-10-22T00:00:00",
            "updatedAt": "2023-10-22T00:00:00"
        },
        "accessToken": "eyJhUn50MdozI16IkpXV.CJ9eyjZXNxNjk3ODAyMjgzLCJpY.XQiOjE2OTc3MTU4ODMsImp0aS",
        "refreshToken": "eyJhUn50MdozI16IkpXV.CJ9eyjZXNxNjk3ODAyMjgzLCJpY.XQiOjE2OTc3MTU4ODMsImp0aS"
    }
}
```

<br>
<br>
<hr>
<br>
<br>

Description: login existing user <br>
Endpoint: `/api/v1/auth/login` <br>
Method: `POST` <br>
Headers:
```json
{
    "Content-Type": "application/json"
}
```
Body:
```json
{
    "email": "admin@admin.com",
    "password": "admin123"
}
```
Response:
```json
{
    "statusCode": 200,
    "status": "success",
    "timestamp": "2023-10-22T00:00:00",
    "data": {
        "user": {
            "id": 1,
            "firstName": "admin",
            "lastName": "new",
            "email": "admin@admin.com",
            "createdAt": "2023-10-22T00:00:00",
            "updatedAt": "2023-10-22T00:00:00"
        },
        "accessToken": "eyJhUn50MdozI16IkpXV.CJ9eyjZXNxNjk3ODAyMjgzLCJpY.XQiOjE2OTc3MTU4ODMsImp0aS",
        "refreshToken": "eyJhUn50MdozI16IkpXV.CJ9eyjZXNxNjk3ODAyMjgzLCJpY.XQiOjE2OTc3MTU4ODMsImp0aS"
    }
}
```

<br>
<br>
<hr>
<br>
<br>

Description: get new tokens <br>
Endpoint: `/api/v1/auth/refresh` <br>
Method: `POST` <br>
Headers:
```json
{
    "Content-Type": "application/json"
}
```
Body:
```json
{
    "refreshToken": "eyJhUn50MdozI16IkpXV.CJ9eyjZXNxNjk3ODAyMjgzLCJpY.XQiOjE2OTc3MTU4ODMsImp0aS"
}
```
Response:
```json
{
    "statusCode": 200,
    "status": "success",
    "timestamp": "2023-10-22T00:00:00",
    "data": {
        "accessToken": "eyJhUn50MdozI16IkpXV.CJ9eyjZXNxNjk3ODAyMjgzLCJpY.XQiOjE2OTc3MTU4ODMsImp0aS",
        "refreshToken": "eyJhUn50MdozI16IkpXV.CJ9eyjZXNxNjk3ODAyMjgzLCJpY.XQiOjE2OTc3MTU4ODMsImp0aS"
    }
}
```

<br>
<br>
<br>

### Dashboard

<br>
<br>
<br>

Description: get analytics for unique contacts reached <br>
Endpoint: `/api/v1/dashboard/unique-reach` <br>
Method: `GET` <br>
Headers:
```json
{
    "Authorization": "Bearer {{accessToken}}",
    "Content-Type": "application/json"
}
```
Params:
```json
{}
```
Response:
```json
{
    "statusCode": 200,
    "status": "success",
    "timestamp": "2023-10-22T00:00:00",
    "data": {}
}
```

<br>
<br>
<br>

### Contacts

<br>
<br>
<br>

Description: fetch all contacts <br>
Endpoint: `/api/v1/contacts` <br>
Method: `GET` <br>
Headers:
```json
{
    "Authorization": "Bearer {{accessToken}}",
    "Content-Type": "application/json"
}
```
Params:
```json
{
    "pageNumber": 1,
    "pageSize": 10
}
```
Response:
```json
{
    "statusCode": 200,
    "status": "success",
    "timestamp": "2023-10-22T00:00:00",
    "data": {
        "currentPage": 1,
        "totalPages": 15,
        "contacts": [
            {
                "id": 1,
                "phoneNumber": 9875362782,
                "firstName": "john",
                "lastName": "doe",
                "createdAt": "2023-10-22T00:00:00",
                "updatedAt": "2023-10-22T00:00:00"
            },
            {
                "id": 2,
                "phoneNumber": 9467382198,
                "firstName": "tony",
                "lastName": "stark",
                "createdAt": "2023-10-22T00:00:00",
                "updatedAt": "2023-10-22T00:00:00"
            }
        ]
    }
}
```

<br>
<br>
<hr>
<br>
<br>

Description: fetch contact with given id <br>
Endpoint: `/api/v1/contacts/2` <br>
Method: `GET` <br>
Headers:
```json
{
    "Authorization": "Bearer {{accessToken}}",
    "Content-Type": "application/json"
}
```
Params:
```json
{}
```
Response:
```json
{
    "statusCode": 200,
    "status": "success",
    "timestamp": "2023-10-22T00:00:00",
    "data": {
        "id": 2,
        "phoneNumber": 9467382198,
        "firstName": "tony",
        "lastName": "stark",
        "createdAt": "2023-10-22T00:00:00",
        "updatedAt": "2023-10-22T00:00:00"
    }
}
```

<br>
<br>
<hr>
<br>
<br>

Description: add new contacts <br>
Endpoint: `/api/v1/contacts` <br>
Method: `POST` <br>
Headers:
```json
{
    "Authorization": "Bearer {{accessToken}}",
    "Content-Type": "application/json"
}
```
Body:
```json
{
    "contacts": [
        {
            "phoneNumber": 9467382198,
            "firstName": "tony",
            "lastName": "stark"
        },
        {
            "phoneNumber": 9056721267,
            "firstName": "steve",
            "lastName": "rogers"
        },
        {
            "phoneNumber": 9256389471,
            "firstName": "bruce",
            "lastName": "banner"
        }
    ]
}
```
Response:
```json
{
    "statusCode": 201,
    "status": "success",
    "timestamp": "2023-10-22T00:00:00",
    "data": {
        "createdCount": 32,
        "invalidCount": 12,
        "duplicateCount": 5
    }
}
```

<br>
<br>
<hr>
<br>
<br>

Description: update contact with given id <br>
Endpoint: `/api/v1/contacts/2` <br>
Method: `PATCH` <br>
Headers:
```json
{
    "Authorization": "Bearer {{accessToken}}",
    "Content-Type": "application/json"
}
```
Body:
```json
{
    "phoneNumber": 9251637899
}
```
Response:
```json
{
    "statusCode": 200,
    "status": "success",
    "timestamp": "2023-10-22T00:00:00",
    "data": {
        "id": 2,
        "phoneNumber": 9251637899,
        "firstName": "tony",
        "lastName": "stark",
        "createdAt": "2023-10-22T00:00:00",
        "updatedAt": "2023-10-22T00:00:00"
    }
}
```

<br>
<br>
<hr>
<br>
<br>

Description: delete multiple contact <br>
Endpoint: `/api/v1/contacts/remove` <br>
Method: `POST` <br>
Headers:
```json
{
    "Authorization": "Bearer {{accessToken}}",
    "Content-Type": "application/json"
}
```
Body:
```json
{
    "contactIds": [3, 4, 8, 10]
}
```
Response:
```json
{
    "statusCode": 200,
    "status": "success",
    "timestamp": "2023-10-22T00:00:00"
}
```

<br>
<br>
<br>

### Blasts

<br>
<br>
<br>

Description: fetch all blasts <br>
Endpoint: `/api/v1/blasts` <br>
Method: `GET` <br>
Headers:
```json
{
    "Authorization": "Bearer {{accessToken}}",
    "Content-Type": "application/json"
}
```
Params:
```json
{
    "pageNumber": 1,
    "pageSize": 10
}
```
Response:
```json
{
    "statusCode": 200,
    "status": "success",
    "timestamp": "2023-10-22T00:00:00",
    "data": {
        "currentPage": 1,
        "totalPages": 15,
        "blasts": [
            {
                "id": 1,
                "name": "Diwali Greetings",
                "message": "Wish you a very happy diwali!",
                "scheduledAt": "2023-10-22T00:00:00",
                "createdAt": "2023-10-22T00:00:00",
                "updatedAt": "2023-10-22T00:00:00"
            },
            {
                "id": 2,
                "name": "Christmas Greetings",
                "message": "Wish you a merry christmas!",
                "scheduledAt": "2023-10-22T00:00:00",
                "createdAt": "2023-10-22T00:00:00",
                "updatedAt": "2023-10-22T00:00:00"
            }
        ]
    }
}
```

<br>
<br>
<hr>
<br>
<br>

Description: fetch blast with given id <br>
Endpoint: `/api/v1/blasts/2` <br>
Method: `GET` <br>
Headers:
```json
{
    "Authorization": "Bearer {{accessToken}}",
    "Content-Type": "application/json"
}
```
Params:
```json
{}
```
Response:
```json
{
    "statusCode": 200,
    "status": "success",
    "timestamp": "2023-10-22T00:00:00",
    "data": {
        "id": 2,
        "name": "Christmas Greetings",
        "message": "Wish you a merry christmas!",
        "scheduledAt": "2023-10-22T00:00:00",
        "createdAt": "2023-10-22T00:00:00",
        "updatedAt": "2023-10-22T00:00:00",
        "recipientCount": 600,
        "attemptedCount": 432,
        "receivedCount": 380,
        "contacts": [
            {
                "id": 1,
                "phoneNumber": 9875362782,
                "firstName": "john",
                "lastName": "doe",
                "createdAt": "2023-10-22T00:00:00",
                "updatedAt": "2023-10-22T00:00:00"
            },
            {
                "id": 2,
                "phoneNumber": 9467382198,
                "firstName": "tony",
                "lastName": "stark",
                "createdAt": "2023-10-22T00:00:00",
                "updatedAt": "2023-10-22T00:00:00"
            }
        ]
    }
}
```

<br>
<br>
<hr>
<br>
<br>

Description: send new message blast <br>
Endpoint: `/api/v1/blasts` <br>
Method: `POST` <br>
Headers:
```json
{
    "Authorization": "Bearer {{accessToken}}",
    "Content-Type": "application/json"
}
```
Body:
```json
{
    "blast": {
        "name": "Christmas Greetings",
        "message": "Wish you a merry christmas!",
        "scheduledAt": "2023-10-22T00:00:00",
        "contactIds": [1, 2, 5, 8]
    }
}
```
Response:
```json
{
    "statusCode": 201,
    "status": "success",
    "timestamp": "2023-10-22T00:00:00",
    "data": {
        "id": 2,
        "name": "Christmas Greetings",
        "message": "Wish you a merry christmas!",
        "scheduledAt": "2023-10-22T00:00:00",
        "createdAt": "2023-10-22T00:00:00",
        "updatedAt": "2023-10-22T00:00:00"
    }
}
```

<br>
<br>
<hr>
<br>
<br>

Description: update blast message status <br>
Endpoint: `/api/v1/blasts/update-status` <br>
Method: `POST` <br>
Headers:
```json
{
    "X-Twilio-Signature": "{{twilio auth token}}",
    "Content-Type": "application/x-www-form-urlencoded"
}
```
Body:
```json
{
    "SmsSid": "SM2xxxxxx",
    "SmsStatus": "sent",
    "MessageStatus": "sent",
    "To": "+1512zzzyyyy",
    "MessageSid": "SM2xxxxxx",
    "AccountSid": "ACxxxxxxx",
    "From": "+1512xxxyyyy",
    "ApiVersion": "2010-04-01"
}
```
Response:
```json
{
    "statusCode": 200,
    "status": "success",
    "timestamp": "2023-10-22T00:00:00"
}
```

<br>
<br>
<br>

### Error

<br>
<br>
<br>

Description: error response <br>
```json
{
    "statusCode": 500,
    "status": "failed",
    "timestamp": "2023-10-22T00:00:00",
    "error": "Token expired"
}
```

