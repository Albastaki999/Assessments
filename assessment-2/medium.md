# A Food-Rating app (backend)

The app contains:

- Users (just username, there won't be any security)
- Restaurants
- Each restaurant has ratings (on a scale of 5)
- Each restaurant has food items with their costs
- Each food item has ratings (on a scale of 5)

#### Design the following API's:\

### 1. `/rate-restaurant`

This API is responsible for giving a rating to any restaurant for a given user\
`note`: If a user has rated already, their existing rating is modified

**Sample request:**

```json
{
  "user": "john123",
  "restaurantId": 10,
  "rating": 4.5
}
```

**Response**:

```json
{
  "message": "Restaurant Rated successfully"
}
```

### 2. `/rate-food`

This API is responsible for giving a rating to any food for a given user\
`note`: If a user has rated already, their existing rating is modified
**Sample request:**

```json
{
  "user": "john123",
  "foodId": 25,
  "rating": 4.5
}
```

**Response**:

```json
{
  "message": "Food Rated successfully"
}
```

 ### 3. `/menu/:restaurantId`
 This API displays the menu of a restaurant just like Swiggy
 
 **Sample Response**:
 ```json
 {
    "restaurantId": 10,
    "restaurantName": "KFC",
    "rating": 4.2,
    "foodItems": [
        {
            "foodId": 1,
            "foodName": "Zinger Burger",
            "cost": 250,
            "rating": 4.3
        },
        {
            "foodId": 2,
            "foodName": "French Fries",
            "cost": 199,
            "rating": 3.6
        }
    ]
 }
 ```

