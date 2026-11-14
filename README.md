# Ex.03 Design a Website for Server Side Processing
## Date:14-11-26

## AIM:
To create a web page to calculate Churn Rate using server-side scripts.

## FORMULA:
Churn Rate = (CustLost / InitCust) * 100
<br> InitCust --> Initial Customers Count
<br> CustLost --> Customers Lost Count

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create a HTML file to implement form based input and output.

### Step 5:
Create python programs for views and urls to perform server side processing.

### Step 6:
Receive input values from the form using request.POST.get().

### Step 7:
Calculate the Result using the given formula.

### Step 8:
Display the calculated result in the server console.

### Step 9:
Render the result to the HTML template.

### Step 10:
Publish the website in Localhost.

## PROGRAM:
``` 
math.html
<html>
    <head>
        <title>samplepage</title>
        </head>
        <body>
            <h1>Narmatha(26018962)</h1>
            <h2>Churn Rate</h2>
            <form method="POST">
                {%csrf_token%}<br></br>
                <label>Customerslost</label>
                <input type = "number" name="lost" value="{{1}}"><br></br>
                <label>InitialCustomer:</label>
                <input type="number" name="initial" value="{{i}}"><br></br>
                <input type="submit"  value="{{churnrate}}"><br></br>
                <label>ChurnRate:</label>
                <input type="number" value="{{churnrate}}"><br></br>
            </form>

        </body>

</html>
views.py
from django.shortcuts import render
def churn_rate(request):
    l = float(request.POST.get('lost', '0'))
    i = float(request.POST.get('initial', '0'))

    churnrate = (l/i)*100 if request.method == 'POST' else 0

    print("Customerslost =", l)
    print("InitialCustomers =", i)
    print("ChurnRate =", churnrate)

    return render(
        request,
        'myapp/math.html',
        {'l': l, 'i': i, 'churnrate': churnrate}
    )
urls.py
from django.contrib import admin
from django.urls import path
from myapp import views

urlpatterns = [
    path('', views.churn_rate, name='churn_rate'),
]
```

## OUTPUT - SERVER SIDE:
![alt text](<Screenshot 2026-11-14 105500.png>)

c:\Users\acer\Pictures\Screenshots\Screenshot 2026-11-14 110201.png
## RESULT:
The the web page to calculate Churn Rate using server-side scripts is created successfully.
