# 🎯 Django POS Management Application

A fully functional **Point of Sale (POS) Management System** built using
**Django**.\
This system helps businesses manage **products, categories,
subcategories, and POS transactions** smoothly and efficiently.

------------------------------------------------------------------------

## 🚀 Features

✔ Manage **Products**\
✔ Manage **Categories & Subcategories**\
✔ Manage **Sales Transactions**\
✔ Auto-Generated **Transaction Codes**\
✔ Dashboard showing **Today's Sales Summary**\
✔ Full **CRUD Operations**\
✔ Clean, professional UI\
✔ Screenshots included\
✔ Ready for deployment

------------------------------------------------------------------------

## 🛠️ Tech Stack

  Layer      Technology
  ---------- ---------------------------------------
  Backend    Django 3.2
  Frontend   HTML • CSS • JavaScript
  Database   SQLite
  Packages   Django CKEditor, Crispy Forms, Pillow

------------------------------------------------------------------------

## 📁 Project Setup Guide

### **1️⃣ Clone the Repository**

``` bash
git clone https://github.com/Navinrajput2712/django-pos-management.git
cd django-pos-management
```

### **2️⃣ Create Virtual Environment**

``` bash
python -m venv env
```

### **3️⃣ Activate Virtual Environment**

**Windows**

``` bash
env\Scriptsctivate
```

**Mac/Linux**

``` bash
source env/bin/activate
```

### **4️⃣ Install Requirements**

``` bash
pip install -r requirements.txt
```

### **5️⃣ Apply Migrations**

``` bash
python manage.py makemigrations
python manage.py migrate
```

### **6️⃣ Run the Server**

``` bash
python manage.py runserver
```

Server will start at:

    http://127.0.0.1:8000

------------------------------------------------------------------------

## 📘 Folder Structure

    django-pos-management/
    │── manage.py
    │── db.sqlite3
    │── requirements.txt
    │── README.md
    │
    ├── pos/                      
    │   ├── models.py             
    │   ├── views.py              
    │   ├── urls.py               
    │   ├── admin.py              
    │   └── templates/pos/        
    │
    ├── static/                  
    ├── media/                    
    └── screens/                  

------------------------------------------------------------------------

## 🧾 Code Snippets

### **Product Model**

``` python
class Product(models.Model):
    category = models.ForeignKey(Category, on_delete=models.CASCADE)
    name = models.CharField(max_length=100)
    price = models.FloatField()
    quantity = models.IntegerField()
    description = models.TextField(blank=True)
    image = models.ImageField(upload_to='products/', blank=True)

    def __str__(self):
        return self.name
```

### **POS Add Item Logic**

``` python
def add_to_pos(request, product_id):
    product = Product.objects.get(id=product_id)
    cart = request.session.get('cart', [])

    cart.append({
        "id": product.id,
        "name": product.name,
        "price": product.price,
        "quantity": 1
    })

    request.session['cart'] = cart
    return redirect("pos_page")
```

### **Dashboard View**

``` python
def dashboard(request):
    today = date.today()
    orders_today = Order.objects.filter(created_at__date=today)
    total_sales = sum(order.total_amount for order in orders_today)

    return render(request, "dashboard.html", {
        "orders_today": orders_today,
        "total_sales": total_sales
    })
```

------------------------------------------------------------------------

## 🖼️ Screenshots

### 🔐 Login Page

`<img src="https://github.com/Navinrajput2712/django-pos-management/blob/main/screens/screen1.png" height="400"/>`{=html}

### 📊 Dashboard

`<img src="https://github.com/Navinrajput2712/django-pos-management/blob/main/screens/screen01.png" height="400"/>`{=html}

### 🏷️ Category Page

`<img src="https://github.com/Navinrajput2712/django-pos-management/blob/main/screens/screen2.png" height="400"/>`{=html}

### 📂 Subcategory Page

`<img src="https://github.com/Navinrajput2712/django-pos-management/blob/main/screens/screen3.png" height="400"/>`{=html}

### 📦 Product Page

`<img src="https://github.com/Navinrajput2712/django-pos-management/blob/main/screens/screen4.png" height="400"/>`{=html}\
`<img src="https://github.com/Navinrajput2712/django-pos-management/blob/main/screens/screen8.png" height="400"/>`{=html}

### 🧾 POS Add Page

`<img src="https://github.com/Navinrajput2712/django-pos-management/blob/main/screens/screen7.png" height="400"/>`{=html}

### 📑 Order Page

`<img src="https://github.com/Navinrajput2712/django-pos-management/blob/main/screens/screen6.png" height="400"/>`{=html}
