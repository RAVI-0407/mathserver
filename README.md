# Ex.05 Design a Website for Server Side Processing
# Date:25/10/2024
# AIM:
To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side.

# FORMULA:
V=L*W*H
V - Volume
L - Length
W - Width
H - Height
# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Create python programs for views and urls to perform server side processing.

## Step 5:
Create a HTML file to implement form based input and output.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
 # views.py
  ~~~
from django.shortcuts import render

def calculate_volume(request):
    result = None
    if request.method == 'POST':
        try:
            length = float(request.POST.get('length', 0))
            width = float(request.POST.get('width', 0))
            height = float(request.POST.get('height', 0))
            result = length * width * height
        except ValueError:
            result = "Invalid input. Please enter valid numbers."
    
    return render(request, 'cuboid_volume/index.html', {'result': result}) 
 ~~~
 # urls.py
 ~~~
from django.urls import path
from . import views

urlpatterns = [
    path('', views.calculate_volume, name='calculate_volume'),
]
~~~
 # Html File(index.html)
 ~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cuboid Volume Calculator</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #1a1a1a;
            color: #f4f4f4;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .container {
            max-width: 400px;
            padding: 30px;
            background: linear-gradient(145deg, #2a2a2a, #1e1e1e);
            box-shadow: 0 10px 15px rgba(0, 0, 0, 0.3);
            border-radius: 12px;
            text-align: center;
        }
        h1 {
            font-size: 24px;
            color: #ff9800;
            margin-bottom: 20px;
        }
        form {
            display: flex;
            flex-direction: column;
        }
        input {
            margin-bottom: 15px;
            padding: 12px;
            font-size: 16px;
            border: none;
            border-radius: 8px;
            background: #333;
            color: #f4f4f4;
            outline: none;
            transition: all 0.3s ease;
        }
        input:focus {
            background: #444;
            box-shadow: 0 0 5px #ff9800;
        }
        button {
            padding: 12px;
            font-size: 18px;
            font-weight: bold;
            color: #fff;
            background: #ff9800;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        button:hover {
            background: #e68900;
            box-shadow: 0 5px 10px rgba(255, 152, 0, 0.3);
        }
        .result {
            margin-top: 20px;
            font-size: 20px;
            color: #76ff03;
            animation: fadeIn 1s ease-in-out;
        }
        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Cuboid Volume Calculator</h1>
        <form method="post">
            {% csrf_token %}
            <input type="number" name="length" placeholder="Enter length (cm)" required>
            <input type="number" name="width" placeholder="Enter width (cm)" required>
            <input type="number" name="height" placeholder="Enter height (cm)" required>
            <button type="submit">Calculate Volume</button>
        </form>
        <div class="result">
            <strong>Volume of Cuboid: {{ result }}</strong>
        </div>
    </div>
</body>
</html>
~~~
# SERVER SIDE PROCESSING:

![Screenshot 2024-12-04 142828](https://github.com/user-attachments/assets/d11004b2-7c4e-45b5-9470-505f3d4e6d65)

# HOMEPAGE:

![Screenshot 2024-12-04 142654](https://github.com/user-attachments/assets/3aeac902-0ef7-4cdc-bae5-22cf340f0dec)

![Screenshot 2024-12-07 084620](https://github.com/user-attachments/assets/df981ceb-c85c-47c6-bbcd-483da02d9d97)

![Screenshot 2024-12-07 084641](https://github.com/user-attachments/assets/7c65e7ed-3d29-444c-9168-f8306735f7e6)


# RESULT:
The program for performing server side processing is completed successfully.
