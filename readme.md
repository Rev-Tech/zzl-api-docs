# Login

Used to collect a Token for a registered User.

**URL** : `https://api-staging.zuckzuck.land/partners/sign_in`

**Method** : `POST`

**Auth required** : NO

**Data constraints**

```json
{
  "partner": {
    "email": "string",
    "password": "stringst"
  }
}

```

**Data example**

```json
{
    "email": "demo@zuckzuck.land",
    "password": "1234"
}
```

## Success Response

**Code** : `200 OK`

**Content example**

```json
{
  "data": {
    "token": "eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiIxIiwic2NwIjoicGFydG5lciIsImF1ZCI6bnVsbCwiaWF0IjoxNjYyNjU3MzQ5LCJleHAiOjE2NjI2NjA5NDksImp0aSI6IjBhOWQ4ZDhjLWI4NjctNDJiNC1iNzAzLWMwOGIwMGM5OTU4ZiJ9.7-9xFfFHaPa5_4tpWDYnAtY6oxOZOfGBnszkoJ03geY",
    "refresh_token": "68a4c6d353a6dbff9dad791a3d256be06c0dc6dbf02579de490d6d69048772d5.190ff8e11f28d5c0447126ed857cc2d0"
  }
}
```

## Error Response

**Condition** : If 'username' and 'password' combination is wrong.

**Code** : `400 BAD REQUEST`

**Content** :

```json
[
  {
    "errors": {
      "message": "Invalid Email or password."
    }
  }
]
```
# Payout Request
Used to send request withdraw to Epixel.
**URL** : `https://api-staging.zuckzuck.land/payout_requests`

**Method** : `POST`

**Auth required** : YES

**Headers**

**Authorization** : Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiIxIiwic2NwIjoicGFydG5lciIsImF1ZCI6bnVsbCwiaWF0IjoxNjYyNjU3MzQ5LCJleHAiOjE2NjI2NjA5NDksImp0aSI6IjBhOWQ4ZDhjLWI4NjctNDJiNC1iNzAzLWMwOGIwMGM5OTU4ZiJ9.7-9xFfFHaPa5_4tpWDYnAtY6oxOZOfGBnszkoJ03geY

###Token will be expried so please refresh / create new token when it expried

**Data constraints**

```json
{
  "payout_request": {
    "amount": "12345"
  }
}
```

## Success Response

**Code** : `200 OK`

# Payout Request
Used to cancel request withdraw to Epixel.
**URL** : `https://api-staging.zuckzuck.land/payout_requests/{id}/cancel`

**Method** : `POST`

**Auth required** : YES

**Headers**

**Authorization** : Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiIxIiwic2NwIjoicGFydG5lciIsImF1ZCI6bnVsbCwiaWF0IjoxNjYyNjU3MzQ5LCJleHAiOjE2NjI2NjA5NDksImp0aSI6IjBhOWQ4ZDhjLWI4NjctNDJiNC1iNzAzLWMwOGIwMGM5OTU4ZiJ9.7-9xFfFHaPa5_4tpWDYnAtY6oxOZOfGBnszkoJ03geY

###Token will be expried so please refresh / create new token when it expried

**Data constraints**

## Success Response

**Code** : `200 OK`


# Hook Payout 
Used to send callback to ZuckZuckLand.
**URL** : `https://api-staging.zuckzuck.land/payout_hooks`

**Method** : `POST`

**Auth required** : YES

**Headers**

**Authorization** : Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiIxIiwic2NwIjoicGFydG5lciIsImF1ZCI6bnVsbCwiaWF0IjoxNjYyNjU3MzQ5LCJleHAiOjE2NjI2NjA5NDksImp0aSI6IjBhOWQ4ZDhjLWI4NjctNDJiNC1iNzAzLWMwOGIwMGM5OTU4ZiJ9.7-9xFfFHaPa5_4tpWDYnAtY6oxOZOfGBnszkoJ03geY

###Token will be expried so please refresh / create new token when it expried

**Data constraints**

```json
{
  "payout_request": {
    "trans_id": "12345",
    "status": "paid" 
  }
}
```
***Status value: paid or cancel**

## Success Response

**Code** : `200 OK`

