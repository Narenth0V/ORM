# Ex02 Django ORM Web Application
# Date:03/11/2026
# AIM
To develop a Django application to store and retrieve data from a bank loan database using Object Relational Mapping(ORM).

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
Views.py
```
from django.shortcuts import render

def Churn_rate(request):
    if request.method == "POST":
        cstart = int(request.POST.get('cstart'))
        clost = int(request.POST.get('clost'))

        if cstart != 0:
            churn_rate = (clost / cstart) * 100
        else:
            churn_rate = 0
        print("customers at start:", cstart)
        print("customers lost:", clost)
        print("customer churn rate:", churn_rate)
        return render(request, 'new.html', {"cstart": cstart, "clost": clost, "churn_rate": churn_rate})
    return render(request, 'new.html')
```
new.html
```<html>  
    <head>  
        <title>Customer Churn rate calculator</title>
    </head>
    <body>  
        <h1>Customer Churn rate calculator</h1>
        <form method="POST">
        {% csrf_token %}
        <label>Totle customers at the start</label>
        <input type="number" name="cstart"><br><br>
        <label>Number of customers Lost</label>
        <input type="number" name="clost"><br>
        <button type="submit">Calculate</button>
        </form>
        <h2>Customer at the start is : {{cstart}} %</h2>
        <h2>Customer lost is : {{clost}} %</h2>
        <h2>Customer churn rate is : {{churn_rate}} %</h2>
    </body>
</html>
```
urls.py
```
from django.contrib import admin
from django.urls import path
from app import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', views.Churn_rate ),
]
```


# OUTPUT



# RESULT
Thus the program for creating a database using ORM hass been executed successfully
