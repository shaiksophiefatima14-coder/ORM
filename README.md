# Ex01 Django ORM Web Application

# AIM
To develop a Django application to manage an online food delivery platform like Zomato/Swiggy using Object Relational Mapping (ORM).

# DESIGN STEPS
## STEP 1:
Clone the problem from GitHub

## STEP 2:
Create a new app in Django project

## STEP 3:
Enter the code for admin.py and models.py

## STEP 4:
Execute Django admin and create details for 10 cars

# PROGRAM

admin.py
```
from django.contrib import admin
from .models import Resturant, FoodItem, Cart, Order
admin.site.register(Resturant)
admin.site.register(FoodItem)  
admin.site.register(Cart)
admin.site.register(Order)
```

models.py
```
from django.db import models
from django.contrib.auth.models import User
class Resturant(models.Model):
    name = models.CharField(max_length=100)
    address = models.TextField()
    phone_number = models.CharField(max_length=20)

    def __str__(self):
        return self.name

class FoodItem(models.Model):
    restaurant = models.ForeignKey(Resturant, on_delete=models.CASCADE)
    name = models.CharField(max_length=100)
    price=models.FloatField()
    description = models.TextField()
    def __str__(self):
        return self.name
    

class Cart(models.Model):
    user = models.ForeignKey(User, on_delete=models.CASCADE)
    food_item = models.ForeignKey(FoodItem, on_delete=models.CASCADE)
    quantity = models.PositiveIntegerField(default=1)

    def __str__(self):
        return self.user.username

class Order(models.Model):
    user = models.ForeignKey(User, on_delete=models.CASCADE)
    food_item = models.ForeignKey(FoodItem, on_delete=models.CASCADE)
    quantity = models.PositiveIntegerField(default=1)
    order_date = models.DateTimeField(auto_now_add=True)

    def __str__(self):
        return self.user.username
```
# OUTPUT
<img width="1916" height="527" alt="image" src="https://github.com/user-attachments/assets/aed5f80c-6637-49ab-81de-b24f08dba1f0" />




# RESULT
Thus the program for creating a database using ORM hass been executed successfully
