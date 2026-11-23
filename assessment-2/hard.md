Design a backend system similar to Swiggy.

- Has multiple Restaurants
- Each restaurant has a fixed percentage of GST that will be considered while bill preparation. `example`: restaurant x can have a GST of 10%
- Each restaurant has food items and their costs
- Each restaurant has location stored in the form of coordinates (x, y)

Build an API `/checkout` that computes the cost

Sample request:
```json
{
    "x":10,
    "y":15,
    "restaurantId":21,
    "foodItems": [
        {
            "foodId":10,
            "quantity": 1
        },
        {
            "foodId":18,
            "quantity": 2
        }
    ],
    "tip":50,
    "time":"2026-11-23T10:30:00.000Z"
}
```

- `x` - x coordinate
- `y` - y coordinate
- `restaurantId` - primary key of the restaurant
- `foodItems` - An array of all the food items
- `foodId` - primary key of the food
- `quantity`: Quantity of the provided food item
- `tip`: tip amount for the delivery partner
- `time`: The time of placing an order (ISO)

Sample response:
```json
{
    "distance": 10.2,
    "itemTotal":250,
    "gst": 42.5,
    "deliveryFee": 61.2,
    "lateNightFee":0,
    "toPay": 353.7
}
```

- `distance` - Total distance between the user and the restaurant
- `itemTotal`: The cost of the food items
- `gst`: GST amount
- `deliveryFee`: calculated as `distance * 6`.
- `lateNightFee`: if the `time` is between 1 am - 6 am, then a fixed fee of 25 rupees is charged.
- `toPay`: The total amount payable