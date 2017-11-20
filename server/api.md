FORMAT: 1A

# Velox Data API
Velox Data is an API allowing crud manipulation of users, lists & notes.

## Velox System
+ Here are some link
+ To other pages for this project
+ Which are yet to be made

# Velox Data API Root [/]

## API status [GET]
Responds with the active status of the api.

+ Response 405 (application/json)

    + Headers
    
        Location: /
        
    + Body
    
        ```json
        {
            "status": "DATABASE UNAVAILABLE"
        }
        ```
        
+ Response 200 (application/json)

    + Headers
    
        Location: /
        
    + Body
    
        ```json
        {
            "status": "OK"
        }
        ```

# User Information
Allows CRUD manipulation of users.

## Users [/users]

## Create a new user [POST]
You may create a new user by using this action. It takes a JSON
object containing a user data object.

+ username (string, required) - The username
+ password (string, required) - The password
+ firstName (string, required) - The user's first name
+ lastName (string, required) - The user's last name

+ Request (application/json)

    ```json
    {
        "data": {
            "username": "pimaster",
            "password": "secret",
            "firstName": "jonathan",
            "lastName": "beaumont"
        }
    }
    ```
    
+ Response 201 (application/json)

    + Headers
    
        Location: /users/2
        
    + Body
    
        ```json
        {
            "status": "OK",
            "data": {
                "id": 2,
                "username": "pimaster",
                "password": "secret",
                "firstName": "jonathan",
                "lastName": "beaumont",
                "createdAt": "2017-11-19 23:23:23",
                "modifiedAt": "2017-11-19 23:23:23"
            }
        }
        ```
        
+ Response 422 (application/json)

    + Headers
    
        Location: /users
        
    + Body
    
        ```json
        {
            "status": "INVALID DATA",
            "data": {
                "username": "pimaster",
                "password": "secret",
                "firstName": "jonathan",
                "lastName": "beaumont"
            }
        }
        ```
        
# User [/users/:id]
This route is for accessing, modifying and deleting existing users.

+ id (number) - The id of the user.

## Fetch a user [GET]
You may fetch a user using their id.

+ Response 200 (application/json)

    + Headers
    
        Location: /users/2
        
    + Body
    
        ```json
        {
            "status": "OK",
            "data": {
               "id": 2,
               "username": "pimaster",
               "password": "secret",
               "firstName": "jonathan",
               "lastName": "beaumont",
               "createdAt": "2017-11-19 23:23:23",
               "modifiedAt": "2017-11-19 23:23:23"
           }
       }
       ```
       
+ Response 404 (application/json)

    + Headers
    
        Location: /users
        
    + Body
    
        ```json
        {
            "status": "NOT FOUND"
        }
        ```
        
## Update a user [PUT]
You may update a user.

+ username (string) - The username
+ password (string) - The password
+ firstName (string) - The user's first name
+ lastName (string) - The user's last name

+ Request (application/json)

    ```json
    {
        "data": {
            "username": "pimaster",
            "password": "secret",
            "firstName": "jonathan",
            "lastName": "beaumont"
        }
    }
    ```

+ Response 200 (application/json)

    + Headers
    
        Location: /users/2
        
    + Body
    
        ```json
        {
            "status": "OK",
            "data": {
                "id": 2,
                "username": "pimaster",
                "password": "secret",
                "firstName": "jonathan",
                "lastName": "beaumont",
                "createdAt": "2017-11-19 23:23:23",
                "modifiedAt": "2017-11-19 23:23:23"
            }
        }
        ```

+ Response 404 (application/json)

    + Headers
    
        Location: /users
        
    + Body
    
        ```json
        {
            "status": "NOT FOUND"
        }
        ```

+ Response 422 (application/json)

    + Headers
    
        Location: /users/2
        
    + Body
    
        ```json
        {
            "status": "INVALID DATA",
            "data": {
                "username": "pimaster",
                "password": "secret",
                "firstName": "jonathan",
                "lastName": "beaumont"
            }
        }
        ```
    
## Delete a user [DELETE]
You may delete a user.

+ Response 200 (application/json)

    + Headers
    
        Location: /users/2
        
    + Body
    
        ```json
        {
            "status": "OK",
            "data": {
                "id": 2,
                "username": "pimaster",
                "password": "secret",
                "firstName": "jonathan",
                "lastName": "beaumont",
                "createdAt": "2017-11-19 23:23:23",
                "modifiedAt": "2017-11-19 23:23:23"
            }
        }
        ```

+ Response 404 (application/json)

    + Headers
    
        Location: /users
        
    + Body
    
        ```json
        {
            "status": "NOT FOUND"
        }
        ```