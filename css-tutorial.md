# ใบงานการทดลอง: พื้นฐานการจัดการรูปแบบเว็บไซต์ด้วย CSS
[](#การทดลองที่-1-ทำความรู้จักกับ-css)
## การทดลองที่ 1: ทำความรู้จักกับ CSS

### 1.1 วิธีการใช้งาน CSS
CSS สามารถใช้งานได้ 3 วิธี:

1. **Inline CSS**:
```html
<p style="color: blue; font-size: 16px;">ข้อความสีน้ำเงิน</p>
```

2. **Internal CSS**:
```html
<head>
    <style>
        p {
            color: blue;
            font-size: 16px;
        }
    </style>
</head>
```

3. **External CSS**:
```html
<head>
    <link rel="stylesheet" href="style.css">
</head>
```

### ตัวอย่างการใช้งาน: การสร้างปุ่มสไตล์ต่างๆ

```html
<!-- ไฟล์ index.html -->
<!DOCTYPE html>
<html>
<head>
    <title>ตัวอย่างปุ่ม CSS</title>
    <!-- Internal CSS -->
    <style>
        .btn-primary {
            background-color: #007bff;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
    <!-- External CSS -->
    <link rel="stylesheet" href="css/buttons.css">
</head>
<body>
    <!-- Inline CSS -->
    <button style="background-color: #dc3545; color: white; padding: 10px 20px;">ปุ่มแบบ Inline</button>
    
    <!-- Internal CSS -->
    <button class="btn-primary">ปุ่มแบบ Internal</button>
    
    <!-- External CSS -->
    <button class="btn-success">ปุ่มแบบ External</button>
</body>
</html>
```

```css
/* สร้างไฟล์ buttons.css ในโฟลเดอร์ css */
.btn-success {
    background-color: #28a745;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}
```
[](#การทดลองที่-2-selectors-ใน-CSS)
## การทดลองที่ 2: Selectors ใน CSS
CSS Selector คือวิธีการระบุหรือเลือกองค์ประกอบ (elements) ที่เราต้องการจัดรูปแบบใน HTML โดยมีประเภทหลัก ๆ ดังนี้:

1. **Element Selector** - เลือกโดยใช้ชื่อ element
```css
p { color: red; }  /* เลือกทุก <p> elements */
h1 { color: blue; }  /* เลือกทุก <h1> elements */
```

2. **Class Selector** - เลือกโดยใช้ชื่อ class (ขึ้นต้นด้วย .)
```css
.menu { color: green; }  /* เลือก elements ที่มี class="menu" */
.highlight { background: yellow; }
```

3. **ID Selector** - เลือกโดยใช้ ID (ขึ้นต้นด้วย #)
```css
#header { background: black; }  /* เลือก element ที่มี id="header" */
#logo { width: 100px; }
```

4. **Descendant Selector** - เลือก elements ที่เป็นลูกหลาน
```css
div p { color: blue; }  /* เลือก <p> ที่อยู่ภายใน <div> */
```

5. **Child Selector** - เลือก elements ที่เป็นลูกโดยตรง (>)
```css
div > p { color: red; }  /* เลือก <p> ที่เป็นลูกโดยตรงของ <div> */
```

6. **Pseudo-class** - เลือกสถานะพิเศษ
```css
a:hover { color: red; }  /* เมื่อเมาส์ชี้ */
input:focus { border: blue; }  /* เมื่อได้รับการโฟกัส */
```

7. **Multiple Selector** - เลือกหลายอย่างพร้อมกัน
```css
h1, h2, h3 { color: purple; }
```

8. **Universal Selector** - เลือกทุก elements (*)
```css
* { margin: 0; padding: 0; }
```

9. **Attribute Selector** - เลือกตาม attribute
```css
input[type="text"] { border: 1px solid gray; }
```

10. **Adjacent Sibling Selector** - เลือกธาตุที่อยู่ถัดไป (+)
```css
h1 + p { margin-top: 20px; }
```

ความสำคัญของ Selector:
- ช่วยให้เราสามารถกำหนดสไตล์ให้กับ elements ที่ต้องการได้อย่างเฉพาะเจาะจง
- ช่วยในการจัดการและบำรุงรักษาโค้ด CSS
- ทำให้สามารถสร้างรูปแบบที่ซับซ้อนได้
- ช่วยลดการเขียนโค้ดซ้ำซ้อน
  
### 2.1 ประเภทของ Selectors
```css
/* Element Selector */
p {
    color: blue;
}

/* Class Selector */
.highlight {
    background-color: yellow;
}

/* ID Selector */
#header {
    font-size: 24px;
}

/* Descendant Selector */
div p {
    margin: 10px;
}

/* Child Selector */
div > p {
    padding: 5px;
}
```

### ตัวอย่างการใช้งาน: การสร้างเมนูนำทาง

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        /* การใช้ Element Selector */
        nav {
            background-color: #333;
            padding: 15px;
        }

        /* การใช้ Descendant Selector */
        nav ul {
            list-style: none;
            margin: 0;
            padding: 0;
            display: flex;
        }

        /* การใช้ Child Selector */
        nav > ul > li {
            margin: 0 10px;
        }

        /* การใช้ Class Selector */
        .menu-item {
            color: white;
            text-decoration: none;
            padding: 5px 10px;
        }

        /* การใช้ Pseudo-class */
        .menu-item:hover {
            background-color: #555;
            border-radius: 3px;
        }

        /* การใช้ ID Selector */
        #active {
            background-color: #007bff;
            border-radius: 3px;
        }
    </style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="#" class="menu-item" id="active">หน้าแรก</a></li>
            <li><a href="#" class="menu-item">สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>
</body>
</html>
```
### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. แก้ไขให้เมนูถูกเลือกที่ สินค้า
3. เปลี่ยนสีพื้นหลังของเมนู

### ผลการทดลอง
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Camera</title>
</head>
<body>
    <nav id="nav">
        <img src="./images/logo.jpg" alt="logo" width="50" height="50">
        <a href="index.html">หน้าหลัก</a>
        <a href="pages/about.html">เกี่ยวกับเรา</a>
        <a href="pages/contact.html">ติดต่อเรา</a>
        <link rel="stylesheet" href="styles.css">
    </nav>
    <hr>
    <section>
        <h1>Gallery</h1>
        <figure>
            <a href="images/gallery/product1.webp">
                <img src="images/gallery/product1.webp" alt="product1" width="200"> 
            </a>
            <figcaption>
                <p>
                    <strong>Brand:</strong>
                    Canon
                </p>
                <p>
                    <strong>Model:</strong>
                    Canon Eos R1
                </p>
                <p>
                   
                    <strong>PRICE:</strong>
                    235,900 THB
                </p>
            </figcaption>
        </figure>
        <hr>
        <figure>
            <a href="images/gallery/product2.jpg">
                <img src="images/gallery/product2.jpg" alt="product2" width="200"> 
            </a>
            <figcaption>
                <p>
                    <strong>Brand:</strong>
                    Sony
                </p>
                <p>
                    <strong>Model:</strong>
                    Sony a7 iv
                </p>
                <p>
                   
                    <strong>PRICE:</strong>
                    82,990 THB
                </p>
            </figcaption>
        </figure>
        <hr>
        <figure>
            <a href="images/gallery/product3.webp">
                <img src="images/gallery/product3.webp" alt="product3" width="200"> 
            </a>
            <figcaption>
                <p>
                    <strong>Brand:</strong>
                    Nikon
                </p>
                <p>
                    <strong>Model:</strong>
                    Nikon D850
                </p>
                <p>
                   
                    <strong>PRICE:</strong>
                    111,000 THB
                </p>
            </figcaption>
        </figure>
        <hr>
        <figure>
            <a href="images/gallery/product4.jpg">
                <img src="images/gallery/product4.jpg" alt="product4" width="200"> 
            </a>
            <figcaption>
                <p>
                    <strong>Brand:</strong>
                    Fujifilm
                </p>
                <p>
                    <strong>Model:</strong>
                    Fujifilm GFX 100S II
                </p>
                <p>
                   
                    <strong>PRICE:</strong>
                    184,990 THB
                </p>
            </figcaption>
        </figure>
        <hr>
        <figure>
        <hr>
    </section>
    
    <a href="#nav">กลับด้านบน</a>
</body>
</html>
[วางโค้ดที่นี่]
css
:root {
    --color-1: linear-gradient(to right, #a3a6da, #c81e84, #ade727); 
    --roboto-font: "Roboto", serif;
    --montserrat-font: "Montserrat", serif;
}

* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}

nav {
    display: flex;
    background: var(--color-1);
    height: 80px;
    font-family: var(--montserrat-font);
    font-weight: 600;
    position: sticky;
    top: 0;
}

nav .logo {
    border-radius: 9999px;
    padding: 15px;
    margin-left: 30px;
    width: 80px;
    height: 80px;
}

nav .button {
    text-decoration: none;
    font-size: 24px;
    margin: 10px 20px;
    padding: 15px;
    color: white;
}

nav .button:hover {
    border-radius: 9999px;
    padding: 15px;
    background: white;
    color: #eb3b6a;
    cursor: pointer;
    transition: .3s;
}
```

[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]

![image](https://github.com/user-attachments/assets/7ca32e96-f911-4f3c-9b9c-46f8f2f748bc)


[](#การทดลองที่-3-การจัดการสีและพื้นหลัง)
## การทดลองที่ 3: การจัดการสีและพื้นหลัง

### 3.1 การกำหนดสีและพื้นหลัง
```css
/* สีพื้นฐาน */
color: red;
color: #FF0000;
color: rgb(255, 0, 0);
color: rgba(255, 0, 0, 0.5);

/* พื้นหลัง */
background-color: #f0f0f0;
background-image: url('image.jpg');
background-size: cover;
```

### ตัวอย่างการใช้งาน: การสร้างการ์ดสินค้า

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .product-card {
            width: 300px;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            background-color: white;
        }

        .product-image {
            width: 100%;
            height: 200px;
            background-image: url('product.jpg');
            background-size: cover;
            background-position: center;
        }

        .product-info {
            padding: 15px;
        }

        .product-title {
            color: #333;
            font-size: 18px;
            margin-bottom: 10px;
        }

        .product-price {
            color: #007bff;
            font-size: 24px;
            font-weight: bold;
        }

        .product-description {
            color: #666;
            font-size: 14px;
            line-height: 1.5;
        }

        .product-button {
            display: block;
            background: linear-gradient(to right, #007bff, #0056b3);
            color: white;
            text-align: center;
            padding: 10px;
            text-decoration: none;
            margin-top: 15px;
            border-radius: 4px;
        }

        .product-button:hover {
            background: linear-gradient(to right, #0056b3, #003980);
        }
    </style>
</head>
<body>
    <div class="product-card">
        <div class="product-image"></div>
        <div class="product-info">
            <h2 class="product-title">สินค้าตัวอย่าง</h2>
            <p class="product-price">฿1,999</p>
            <p class="product-description">
                รายละเอียดสินค้าตัวอย่าง ที่มีความน่าสนใจและน่าใช้งาน
            </p>
            <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
    </div>
</body>
</html>
```

### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. แก้ไขให้แสดงรูปสินค้า โดยให้รูปสินค้าเก็บอยู่ในโฟลเดอร์ images
3. เพิ่มเติมให้มี card แสดงข้อมูลสินค้า 4 รูป

### ผลการทดลอง
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Camera Gallery</title>
    <link rel="stylesheet" href="styles.css">
    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(to right, #ff7e5f, #feb47b);
            margin: 0;
            padding: 0;
            text-align: center;
            color: #fff;
        }
        nav {
            background: #222;
            padding: 15px;
        }
        nav a {
            color: white;
            margin: 0 15px;
            text-decoration: none;
            font-weight: bold;
        }
        .gallery-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            padding: 20px;
            max-width: 1000px;
            margin: 0 auto;
        }
        .card {
            background: rgba(255, 255, 255, 0.9);
            color: #333;
            border-radius: 10px;
            padding: 10px;
            width: 250px;
            text-align: center;
            transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
            position: relative;
            overflow: hidden;
        }
        .card:hover {
            transform: scale(1.1);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
        }
        .card img {
            width: 100%;
            border-radius: 10px;
        }
        .card-content {
            margin-top: 10px;
            opacity: 0;
            transform: translateY(10px);
            transition: opacity 0.3s ease-in-out, transform 0.3s ease-in-out;
        }
        .card:hover .card-content {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <nav id="nav">
        <img src="images/logo.jpg" alt="logo" width="50" height="50">
        <a href="index.html">หน้าหลัก</a>
        <a href="pages/about.html">เกี่ยวกับเรา</a>
        <a href="pages/contact.html">ติดต่อเรา</a>
    </nav>
    <hr>
    <section>
        <h1>Gallery</h1>
        <div class="gallery-container">
            <div class="card">
                <a href="images/product1.webp">
                    <img src="images/product1.webp" alt="Canon Eos R1">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Canon</p>
                    <p><strong>Model:</strong> Canon Eos R1</p>
                    <p><strong>PRICE:</strong> 235,900 THB</p>
                </div>
            </div>
            <div class="card">
                <a href="images/product2.jpg">
                    <img src="images/product2.jpg" alt="Sony a7 iv">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Sony</p>
                    <p><strong>Model:</strong> Sony a7 iv</p>
                    <p><strong>PRICE:</strong> 82,990 THB</p>
                </div>
            </div>
            <div class="card">
                <a href="images/product3.webp">
                    <img src="images/product3.webp" alt="Nikon D850">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Nikon</p>
                    <p><strong>Model:</strong> Nikon D850</p>
                    <p><strong>PRICE:</strong> 111,000 THB</p>
                </div>
            </div>
            <div class="card">
                <a href="images/product4.jpg">
                    <img src="images/product4.jpg" alt="Fujifilm GFX 100S II">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Fujifilm</p>
                    <p><strong>Model:</strong> Fujifilm GFX 100S II</p>
                    <p><strong>PRICE:</strong> 184,990 THB</p>
                </div>
            </div>
        </div>
    </section>
    
    <a href="#nav" style="color: #fff; font-weight: bold;">กลับด้านบน</a>
</body>
</html>
```
[วางโค้ดที่นี่]
css
/* สไตล์พื้นฐานของหน้า */
body {
    font-family: Arial, sans-serif;
    background: linear-gradient(to right, #ff7e5f, #feb47b);
    margin: 0;
    padding: 0;
    text-align: center;
    color: #fff;
}

/* สไตล์ของเมนูนำทาง */
nav {
    background: #222;
    padding: 15px;
}

nav a {
    color: white;
    margin: 0 15px;
    text-decoration: none;
    font-weight: bold;
}

/* ตั้งค่ากล่องแสดงสินค้า */
.gallery-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    gap: 20px;
    padding: 20px;
    max-width: 1000px;
    margin: 0 auto;
}

/* สไตล์ของการ์ดสินค้า */
.card {
    background: rgba(238, 142, 142, 0.9);
    color: #333;
    border-radius: 10px;
    padding: 10px;
    width: 250px;
    text-align: center;
    transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
    position: relat

[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]

![image](https://github.com/user-attachments/assets/0e5e49c2-ad76-41e9-a1c4-10138133195d).



[](#การทดลองที่-4-การจัดการขนาดและระยะห่าง)
## การทดลองที่ 4: การจัดการขนาดและระยะห่าง

### 4.1 หน่วยวัดและ Box Model
```css
/* หน่วยวัด */
width: 100px;
width: 50%;
font-size: 1.2rem;
height: 100vh;

/* Box Model */
padding: 10px;
margin: 15px;
border: 1px solid black;
```

### ตัวอย่างการใช้งาน: การสร้างส่วนแสดงสถิติ

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .stats-container {
            display: flex;
            justify-content: space-around;
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 1rem;
        }

        .stat-box {
            flex: 1;
            margin: 0 15px;
            padding: 2rem;
            text-align: center;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: bold;
            color: #007bff;
            margin-bottom: 0.5rem;
        }

        .stat-label {
            font-size: 1rem;
            color: #666;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .stats-container {
                flex-direction: column;
            }

            .stat-box {
                margin: 1rem 0;
            }
        }
    </style>
</head>
<body>
    <div class="stats-container">
        <div class="stat-box">
            <div class="stat-number">1,234</div>
            <div class="stat-label">ผู้ใช้งาน</div>
        </div>
        <div class="stat-box">
            <div class="stat-number">5.6K</div>
            <div class="stat-label">ยอดขาย</div>
        </div>
        <div class="stat-box">
            <div class="stat-number">98%</div>
            <div class="stat-label">ความพึงพอใจ</div>
        </div>
    </div>
</body>
</html>
```

### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. ปรับแต่ง ขนาดต่าง ๆ ของ Box model, ขนาดและฟอนต์ตัวหนังสือ, สี


### ผลการทดลอง
```html
[วางโค้ด HTML ที่นี่]
```<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Camera Gallery</title>
    <link rel="stylesheet" href="styles.css">
    <style>
        
    </style>
</head>
<body>
    <nav id="nav">
        <img src="images/logo.jpg" alt="logo" width="50" height="50">
        <a href="index.html">หน้าหลัก</a>
        <a href="pages/about.html">เกี่ยวกับเรา</a>
        <a href="pages/contact.html">ติดต่อเรา</a>
    </nav>
    <hr>
    <section>
        <h1>Gallery</h1>
        <div class="gallery-container">
            <div class="card">
                <a href="images/product1.webp">
                    <img src="images/product1.webp" alt="Canon Eos R1">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Canon</p>
                    <p><strong>Model:</strong> Canon Eos R1</p>
                    <p><strong>PRICE:</strong> 235,900 THB</p>
                </div>
            </div>
            <div class="card">
                <a href="images/product2.jpg">
                    <img src="images/product2.jpg" alt="Sony a7 iv">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Sony</p>
                    <p><strong>Model:</strong> Sony a7 iv</p>
                    <p><strong>PRICE:</strong> 82,990 THB</p>
                </div>
            </div>
            <div class="card">
                <a href="images/product3.webp">
                    <img src="images/product3.webp" alt="Nikon D850">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Nikon</p>
                    <p><strong>Model:</strong> Nikon D850</p>
                    <p><strong>PRICE:</strong> 111,000 THB</p>
                </div>
            </div>
            <div class="card">
                <a href="images/product4.jpg">
                    <img src="images/product4.jpg" alt="Fujifilm GFX 100S II">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Fujifilm</p>
                    <p><strong>Model:</strong> Fujifilm GFX 100S II</p>
                    <p><strong>PRICE:</strong> 184,990 THB</p>
                </div>
            </div>
        </div>
    </section>
    
    <a href="#nav" style="color: #fff; font-weight: bold;">กลับด้านบน</a>
</body>
</html>

```css
[วางโค้ด CSS ที่นี่]
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&family=Roboto:ital,wght@0,100..900;1,100..900&display=swap');

:root {
    --color-gradient-1: linear-gradient(to right, #e01249, #c81e84, #7c26f5); 
    --color-gradient-2: linear-gradient(to right, #f52095, #ea4cff, #984fff);
    --color-gradient-3: linear-gradient(to right, #20f5d9, #4c7cff, #d455d8);
    --color-pinkish-red: #d10c41;
    --color-white: #fff;
    --color-card: #f4f4f4;
    --color-tr: #b6b6b6;
    --color-th: #7a7a7a;
    --color-shadow: #8a8a8a;
    --roboto-font: "Roboto", serif;
    --montserrat-font: "Montserrat", serif;
    --h1-size: 64px;
    --a-size: 24px;
    --p-size: 18px;
    --price-size: 40px;
}

* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    background: var(--color-white);
    height: auto;
}

/* nav */
nav {
    display: flex;
    background: var(--color-gradient-1);
    height: 80px;
    font-family: var(--montserrat-font);
    font-weight: 600;
    position: sticky;
    top: 0;
}

nav .logo {
    border-radius: 9999px;
    padding: 15px;
    margin-left: 30px;
    width: 80px;
    height: 80px;
}

nav .button {
    text-decoration: none;
    font-size: var(--a-size);
    margin: 10px 20px;
    padding: 15px;
    color: var(--color-white);
}

nav .button:hover {
    border-radius: 9999px;
    padding: 15px;
    background: var(--color-white);
    color: var(--color-pinkish-red);
    cursor: pointer;
    transition: .4s;
}

/* section */
section .hero {
    text-align: center;
    margin-bottom: 60px;
}

section .title {
    margin: 20px 40px;
    font-family: var(--roboto-font);
    font-size: var(--h1-size);
    background: var(--color-gradient-1);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

section .subtitle {
    margin: 20px 40px;
    font-family: var(--roboto-font);
    font-size: var(--p-size);
    background: var(--color-gradient-2);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

hr {
    border: none;
    border-radius: 9999px;
    height: 6px ;
    margin-left: 70px;
    width: 90%;
    background: var(--color-gradient-2);
}

/* main */
/* card */
.card {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    border-radius: 20px;
    padding: 40px 25px;
    margin-left: 650px;
    margin-top: 60px;
    width: 260px;
    height: 360px;
    gap: 10px;
    box-shadow: 10px 10px 20px 0 var(--color-shadow);
    background: var(--color-card);
    text-align: start;
    overflow: hidden;
    cursor: pointer;
}

.card:hover {
    margin: 60px 110px;
    padding-left: 50px;
    gap: 30px;
    width: 85%;
    transition: margin-left .5s ease, width .5s ease;
}

/* card left */
.card-left .img {
    display: flex;
    text-align: center;
    margin-bottom: 30px;
}

/* card center */
.card-center .passage {
    display: grid;
    grid-template-rows: auto;
    width: 500px;
    margin: 10px 40px;
    padding-left: 100px;
    font-size: var(--p-size);
    font-family: var(--roboto-font);
    gap: 10px;
}

.card-center .passage p {
    margin-bottom: 40px;
}

/* card right */
.card-right {
    font-family: var(--roboto-font);
    font-size: var(--p-size);
}

.card-right .cart p {
    margin-top: 50px;
    margin-bottom: 40px;
    margin-left: 75px;
    font-family: var(--montserrat-font);
    font-size: var(--price-size);
    font-weight: 800;
}

.card-right img {
    height: 40px;
    width: 40px;
}

.card-right .cart-button {
    display: flex;
    flex-direction: row;
    border-radius: 25px;
    height: 50px;
    width: 180px;
    padding-left: 50px;
    padding-top: 4px;
    margin-left: 70px;
    background: var(--color-blue);
    background: var(--color-gradient-3);
    color: var(--color-white);
}

.card-right .cart-button:hover {
    transform: scale(1.2);
    cursor: pointer;
}

.card-right .cart-button h2 {
    padding-top: 5px;
}

/* footer */
footer {
    text-align: end;
    position: sticky;
    bottom: 0;
    z-index: 10;
}

.footer-button img {
    border-radius: 9999px;
    background: var(--color-card);
    box-shadow: 10px 10px 30px 0 var(--color-shadow);
    margin-bottom: 30px;
    margin-right: 30px;
    width: 60px;
    height: 60px;
}

/* scrollbar */
::-webkit-scrollbar {
    width: 8px;
}

::-webkit-scrollbar-thumb {
    background-color: var(--color-th);
    border-radius: 4px;
}

::-webkit-scrollbar-track {
    background-color: var(--color-tr);
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![image](https://github.com/user-attachments/assets/3d67afcc-b885-40e2-98aa-112b756ea6b7)

[](#การทดลองที่-5-การจัดการข้อความและฟอนต์)
## การทดลองที่ 5: การจัดการข้อความและฟอนต์

### 5.1 การจัดการข้อความและฟอนต์
```css
/* การจัดการข้อความ */
text-align: center;
text-decoration: none;
text-transform: uppercase;
line-height: 1.5;

/* การจัดการฟอนต์ */
font-family: 'Arial', sans-serif;
font-size: 16px;
font-weight: bold;
```

### ตัวอย่างการใช้งาน: การสร้างบทความบล็อก

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .blog-post {
            max-width: 800px;
            margin: 2rem auto;
            padding: 0 1rem;
            font-family: 'Sarabun', sans-serif;
        }

        .post-header {
            text-align: center;
            margin-bottom: 2rem;
        }

        .post-title {
            font-size: 2.5rem;
            color: #333;
            margin-bottom: 0.5rem;
            line-height: 1.2;
        }

        .post-meta {
            color: #666;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .post-content {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #444;
        }

        .post-content p {
            margin-bottom: 1.5rem;
        }

        .post-content h2 {
            font-size: 1.8rem;
            color: #333;
            margin: 2rem 0 1rem;
        }

        blockquote {
            font-style: italic;
            border-left: 4px solid #007bff;
            margin: 1.5rem 0;
            padding-left: 1rem;
            color: #555;
        }

        @media (max-width: 768px) {
            .post-title {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <article class="blog-post">
        <header class="post-header">
            <h1 class="post-title">วิธีการเขียนบทความที่น่าสนใจ</h1>
            <div class="post-meta">โพสต์เมื่อ 1 มกราคม 2025 | โดย ผู้เขียน</div>
        </header>
        
        <div class="post-content">
            <p>เนื้อหาบทความที่ดีควรมีความน่าสนใจและเป็นประโยชน์ต่อผู้อ่าน การเขียนบทความให้น่าอ่านนั้นมีหลักการสำคัญหลายประการ</p>

            <h2>1. การเลือกหัวข้อที่น่าสนใจ</h2>
            <p>หัวข้อที่ดีควรตรงกับความสนใจของกลุ่มเป้าหมาย และมีประโยชน์ต่อผู้อ่าน</p>

            <blockquote>
                "การเขียนที่ดีไม่ได้เกิดจากพรสวรรค์เพียงอย่างเดียว แต่เกิดจากการฝึกฝนอย่างสม่ำเสมอ"
            </blockquote>

            <h2>2. การจัดโครงสร้างเนื้อหา</h2>
            <p>เนื้อหาที่ดีควรมีการจัดลำดับที่เป็นระบบ เข้าใจง่าย และมีความต่อเนื่อง</p>
        </div>
    </article>
</body>
</html>
```
### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. ปรับแต่งรูปแบบ สีและขนาด font

### ผลการทดลอง
```html
[วางโค้ด HTML ที่นี่]
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Camera Gallery</title>
    <link rel="stylesheet" href="styles.css">
    <style>
        
    </style>
</head>
<body>
    <nav id="nav">
        <img src="images/logo.jpg" alt="logo" width="50" height="50">
        <a href="index.html">หน้าหลัก</a>
        <a href="pages/about.html">เกี่ยวกับเรา</a>
        <a href="pages/contact.html">ติดต่อเรา</a>
    </nav>
    <hr>
    <section>
        <h1>Gallery</h1>
        <div class="gallery-container">
            <div class="card">
                <a href="images/product1.webp">
                    <img src="images/product1.webp" alt="Canon Eos R1">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Canon</p>
                    <p><strong>Model:</strong> Canon Eos R1</p>
                    <p><strong>PRICE:</strong> 235,900 THB</p>
                </div>
            </div>
            <div class="card">
                <a href="images/product2.jpg">
                    <img src="images/product2.jpg" alt="Sony a7 iv">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Sony</p>
                    <p><strong>Model:</strong> Sony a7 iv</p>
                    <p><strong>PRICE:</strong> 82,990 THB</p>
                </div>
            </div>
            <div class="card">
                <a href="images/product3.webp">
                    <img src="images/product3.webp" alt="Nikon D850">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Nikon</p>
                    <p><strong>Model:</strong> Nikon D850</p>
                    <p><strong>PRICE:</strong> 111,000 THB</p>
                </div>
            </div>
            <div class="card">
                <a href="images/product4.jpg">
                    <img src="images/product4.jpg" alt="Fujifilm GFX 100S II">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Fujifilm</p>
                    <p><strong>Model:</strong> Fujifilm GFX 100S II</p>
                    <p><strong>PRICE:</strong> 184,990 THB</p>
                </div>
            </div>
        </div>
    </section>
    
    <a href="#nav" style="color: #fff; font-weight: bold;">กลับด้านบน</a>
</body>
</html>

```
```css
[วางโค้ด CSS ที่นี่]
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&family=Roboto:ital,wght@0,100..900;1,100..900&display=swap');

:root {
    --color-gradient-1: linear-gradient(to right, #ad697b, #cc92b5, #6b09f3, #988fb1); 
    --color-gradient-2: linear-gradient(to right, #550330, #5d0768, #340774);
    --color-gradient-3: linear-gradient(to right, #20f5d9, #4c7cff, #d455d8);
    --color-gradient-4: linear-gradient(to right, #0e54a3, #d72aee);
    --color-pinkish-red: #d10c41;
    --color-white: #fff;
    --color-card: #f4f4f4;
    --color-tr: #b6b6b6;
    --color-th: #7a7a7a;
    --color-shadow: #8a8a8a;
    --roboto-font: "Roboto", serif;
    --montserrat-font: "Montserrat", serif;
    --h1-size: 64px;
    --a-size: 24px;
    --p-size: 18px;
    --price-size: 40px;
}

* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    background: var(--color-white);
    height: auto;
}

/* nav */
nav {
    display: flex;
    background: var(--color-gradient-1);
    height: 80px;
    font-family: var(--montserrat-font);
    font-weight: 600;
    position: sticky;
    top: 0;
}

nav .logo {
    border-radius: 9999px;
    padding: 15px;
    margin-left: 30px;
    width: 80px;
    height: 80px;
}

nav .button {
    text-decoration: none;
    font-size: var(--a-size);
    margin: 10px 20px;
    padding: 15px;
    color: var(--color-white);
}

nav .button:hover {
    border-radius: 9999px;
    padding: 15px;
    background: var(--color-white);
    color: var(--color-pinkish-red);
    cursor: pointer;
    transition: .4s;
}

/* section */
section .hero {
    text-align: center;
    margin-bottom: 60px;
}

section .title {
    margin: 20px 40px;
    font-family: var(--roboto-font);
    font-size: var(--h1-size);
    background: var(--color-gradient-1);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

section .subtitle {
    margin: 20px 40px;
    font-family: var(--roboto-font);
    font-size: var(--p-size);
    background: var(--color-gradient-2);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

hr {
    border: none;
    border-radius: 9999px;
    height: 6px ;
    margin-left: 70px;
    width: 90%;
    background: var(--color-gradient-3);
}

/* main */
/* card */
.card {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    border-radius: 20px;
    padding: 40px 25px;
    margin-left: 650px;
    margin-top: 60px;
    width: 260px;
    height: 360px;
    gap: 10px;
    box-shadow: 10px 10px 20px 0 var(--color-shadow);
    background: var(--color-card);
    text-align: start;
    overflow: hidden;
    cursor: pointer;
}

.card:hover {
    margin: 60px 110px;
    padding-left: 50px;
    gap: 30px;
    width: 85%;
    transition: margin-left .5s ease, width .5s ease;
}

/* card left */
.card-left .img {
    display: flex;
    text-align: center;
    margin-bottom: 30px;
}

/* card center */
.card-center .passage {
    display: grid;
    grid-template-rows: auto;
    width: 500px;
    margin: 10px 40px;
    padding-left: 100px;
    font-size: var(--p-size);
    font-family: var(--roboto-font);
    gap: 10px;
}

.card-center .passage p {
    margin-bottom: 40px;
}

.card-center .passage p:hover {
    transform: scale(1.05);
    background: var(--color-gradient-4);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    transition: .4s;
}

/* card right */
.card-right {
    font-family: var(--roboto-font);
    font-size: var(--p-size);
}

.card-right .cart p {
    margin-top: 50px;
    margin-bottom: 40px;
    margin-left: 75px;
    font-family: var(--montserrat-font);
    font-size: var(--price-size);
    font-weight: 800;
}

.card-right .cart p:hover {
    transform: scale(1.05);
    background: var(--color-gradient-1);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    transition: .4s;
}

.card-right img {
    height: 40px;
    width: 40px;
}

.card-right .cart-button {
    display: flex;
    flex-direction: row;
    border-radius: 25px;
    height: 50px;
    width: 180px;
    padding-left: 50px;
    padding-top: 4px;
    margin-left: 70px;
    background: var(--color-blue);
    background: var(--color-gradient-3);
    color: var(--color-white);
}

.card-right .cart-button:hover {
    transform: scale(1.2);
    cursor: pointer;
}

.card-right .cart-button h2 {
    padding-top: 5px;
}

/* footer */
footer {
    text-align: end;
    position: sticky;
    bottom: 0;
    z-index: 10;
}

.footer-button img {
    border-radius: 9999px;
    background: var(--color-card);
    box-shadow: 10px 10px 30px 0 var(--color-shadow);
    margin-bottom: 30px;
    margin-right: 30px;
    width: 60px;
    height: 60px;
}

/* scrollbar */
::-webkit-scrollbar {
    width: 8px;
}

::-webkit-scrollbar-thumb {
    background-color: var(--color-th);
    border-radius: 4px;
}

::-webkit-scrollbar-track {
    background-color: var(--color-tr);
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![image](https://github.com/user-attachments/assets/936a39d3-bc29-475e-be47-4afb835bf2e7)


[](#การทดลองที่-6-Layout-และการจัดวางอิลิเมนต์)
## การทดลองที่ 6: Layout และการจัดวางอิลิเมนต์

### 6.1 การจัดวางด้วย Flexbox และ Grid

```css
/* Flexbox */
.container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

/* Grid */
.grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

### ตัวอย่างการใช้งาน: การสร้างหน้าแสดงสินค้าแบบ Grid

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .product-card {
            background: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }

        .product-card:hover {
            transform: translateY(-5px);
        }

        .product-image {
            width: 100%;
            height: 200px;
            background-color: #f5f5f5;
            background-size: cover;
            background-position: center;
        }

        .product-details {
            padding: 15px;
        }

        .product-title {
            font-size: 1.1rem;
            margin: 0 0 10px 0;
            color: #333;
        }

        .product-price {
            font-size: 1.2rem;
            color: #007bff;
            font-weight: bold;
        }

        .product-action {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 15px;
        }

        .add-to-cart {
            background-color: #007bff;
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 4px;
            cursor: pointer;
        }

        .add-to-cart:hover {
            background-color: #0056b3;
        }

        @media (max-width: 768px) {
            .product-grid {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            }
        }
    </style>
</head>
<body>
    <div class="product-grid">
        <!-- สินค้าชิ้นที่ 1 -->
        <div class="product-card">
            <div class="product-image" style="background-image: url('product1.jpg')"></div>
            <div class="product-details">
                <h3 class="product-title">สินค้าตัวอย่างที่ 1</h3>
                <div class="product-price">฿1,299</div>
                <div class="product-action">
                    <button class="add-to-cart">เพิ่มลงตะกร้า</button>
                </div>
            </div>
        </div>

        <!-- สินค้าชิ้นที่ 2 -->
        <div class="product-card">
            <div class="product-image" style="background-image: url('product2.jpg')"></div>
            <div class="product-details">
                <h3 class="product-title">สินค้าตัวอย่างที่ 2</h3>
                <div class="product-price">฿1,499</div>
                <div class="product-action">
                    <button class="add-to-cart">เพิ่มลงตะกร้า</button>
                </div>
            </div>
        </div>

        <!-- เพิ่มสินค้าอื่นๆ ตามต้องการ -->
    </div>
</body>
</html>
```

### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. ปรับแต่งขนาดแสดงผลสินค้าให้เล็กลง
3. เพ่ิมรูปภาพของสินค้า


### ผลการทดลอง
```html
[วางโค้ด HTML ที่นี่]
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Camera Gallery</title>
    <link rel="stylesheet" href="styles.css">
    <style>
        
    </style>
</head>
<body>
    <nav id="nav">
        <img src="images/logo.jpg" alt="logo" width="50" height="50">
        <a href="index.html">หน้าหลัก</a>
        <a href="pages/about.html">เกี่ยวกับเรา</a>
        <a href="pages/contact.html">ติดต่อเรา</a>
    </nav>
    <hr>
    <section>
        <h1>Gallery</h1>
        <div class="gallery-container">
            <div class="card">
                <a href="images/product1.webp">
                    <img src="images/product1.webp" alt="Canon Eos R1">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Canon</p>
                    <p><strong>Model:</strong> Canon Eos R1</p>
                    <p><strong>PRICE:</strong> 235,900 THB</p>
                </div>
            </div>
            <div class="card">
                <a href="images/product2.jpg">
                    <img src="images/product2.jpg" alt="Sony a7 iv">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Sony</p>
                    <p><strong>Model:</strong> Sony a7 iv</p>
                    <p><strong>PRICE:</strong> 82,990 THB</p>
                </div>
            </div>
            <div class="card">
                <a href="images/product3.webp">
                    <img src="images/product3.webp" alt="Nikon D850">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Nikon</p>
                    <p><strong>Model:</strong> Nikon D850</p>
                    <p><strong>PRICE:</strong> 111,000 THB</p>
                </div>
            </div>
            <div class="card">
                <a href="images/product4.jpg">
                    <img src="images/product4.jpg" alt="Fujifilm GFX 100S II">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Fujifilm</p>
                    <p><strong>Model:</strong> Fujifilm GFX 100S II</p>
                    <p><strong>PRICE:</strong> 184,990 THB</p>
                </div>
            </div>
        </div>
    </section>
    
    <a href="#nav" style="color: #fff; font-weight: bold;">กลับด้านบน</a>
</body>
</html>
```

```css
[วางโค้ด CSS ที่นี่]
body {
    font-family: Arial, sans-serif;
}

nav {
    background-color: #333;
    padding: 1rem;
    text-align: center;
}

nav img {
    vertical-align: middle;
}

nav a {
    color: #fff;
    text-decoration: none;
    margin: 0 1rem;
    font-weight: bold;
}

hr {
    margin: 2rem 0;
}

section {
    text-align: center;
    padding: 2rem;
}

.gallery-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}

.card {
    border: 1px solid #ddd;
    border-radius: 5px;
    margin: 1rem;
    width: 200px;
    overflow: hidden;
}

.card img {
    width: 100%;
    height: auto;
}

.card-content {
    padding: 1rem;
}

.card-content p {
    margin: 0.5rem 0;
}

a[href="#nav"] {
    display: inline-block;
    margin-top: 2rem;
}

```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![image](https://github.com/user-attachments/assets/c4aaf1a1-e506-4f15-af3b-dac34310756f)


### ตัวอย่างการใช้งาน: การสร้างเลย์เอาต์ Modern Dashboard

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .dashboard {
            display: grid;
            grid-template-areas: 
                "sidebar header"
                "sidebar main";
            grid-template-columns: 250px 1fr;
            grid-template-rows: auto 1fr;
            min-height: 100vh;
        }

        .header {
            grid-area: header;
            background: white;
            padding: 1rem;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .sidebar {
            grid-area: sidebar;
            background: #2c3e50;
            color: white;
            padding: 1rem;
        }

        .main-content {
            grid-area: main;
            padding: 1rem;
            background: #f5f7fa;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .stat-card {
            background: white;
            padding: 1.5rem;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .chart-container {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 1rem;
        }

        .chart {
            background: white;
            padding: 1.5rem;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        @media (max-width: 768px) {
            .dashboard {
                grid-template-areas: 
                    "header"
                    "main";
                grid-template-columns: 1fr;
            }

            .sidebar {
                display: none;
            }

            .chart-container {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="dashboard">
        <header class="header">
            <h1>แดชบอร์ด</h1>
            <nav>
                <button>โปรไฟล์</button>
                <button>ออกจากระบบ</button>
            </nav>
        </header>

        <aside class="sidebar">
            <nav>
                <ul>
                    <li>หน้าแรก</li>
                    <li>รายงาน</li>
                    <li>การตั้งค่า</li>
                </ul>
            </nav>
        </aside>

        <main class="main-content">
            <div class="stats-grid">
                <div class="stat-card">
                    <h3>ยอดขายรวม</h3>
                    <p>฿150,000</p>
                </div>
                <div class="stat-card">
                    <h3>จำนวนออเดอร์</h3>
                    <p>1,234</p>
                </div>
                <div class="stat-card">
                    <h3>ลูกค้าใหม่</h3>
                    <p>45</p>
                </div>
            </div>

            <div class="chart-container">
                <div class="chart">
                    <h3>กราฟแสดงยอดขาย</h3>
                    <!-- เพิ่มกราฟตามต้องการ -->
                </div>
                <div class="chart">
                    <h3>สัดส่วนสินค้าขายดี</h3>
                    <!-- เพิ่มกราฟตามต้องการ -->
                </div>
            </div>
        </main>
    </div>
</body>
</html>
```

### แบบฝึกหัด
1. แก้ไขโค้ดโปรแกรมเดิม ให้ใช้งาน CSS แบบ External CSS
2. ปรับแต่งการแสดงผลต่าง ๆ ให้สวยงาม



### ผลการทดลอง
```html
[วางโค้ด HTML ที่นี่]
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Camera Gallery</title>
    <link rel="stylesheet" href="styles.css">
    <style>
        
    </style>
</head>
<body>
    <nav id="nav">
        <img src="images/logo.jpg" alt="logo" width="50" height="50">
        <a href="index.html">หน้าหลัก</a>
        <a href="pages/about.html">เกี่ยวกับเรา</a>
        <a href="pages/contact.html">ติดต่อเรา</a>
    </nav>
    <hr>
    <section>
        <h1>Gallery</h1>
        <div class="gallery-container">
            <div class="card">
                <a href="images/product1.webp">
                    <img src="images/product1.webp" alt="Canon Eos R1">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Canon</p>
                    <p><strong>Model:</strong> Canon Eos R1</p>
                    <p><strong>PRICE:</strong> 235,900 THB</p>
                </div>
            </div>
            <div class="card">
                <a href="images/product2.jpg">
                    <img src="images/product2.jpg" alt="Sony a7 iv">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Sony</p>
                    <p><strong>Model:</strong> Sony a7 iv</p>
                    <p><strong>PRICE:</strong> 82,990 THB</p>
                </div>
            </div>
            <div class="card">
                <a href="images/product3.webp">
                    <img src="images/product3.webp" alt="Nikon D850">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Nikon</p>
                    <p><strong>Model:</strong> Nikon D850</p>
                    <p><strong>PRICE:</strong> 111,000 THB</p>
                </div>
            </div>
            <div class="card">
                <a href="images/product4.jpg">
                    <img src="images/product4.jpg" alt="Fujifilm GFX 100S II">
                </a>
                <div class="card-content">
                    <p><strong>Brand:</strong> Fujifilm</p>
                    <p><strong>Model:</strong> Fujifilm GFX 100S II</p>
                    <p><strong>PRICE:</strong> 184,990 THB</p>
                </div>
            </div>
        </div>
    </section>
    
    <a href="#nav" style="color: #fff; font-weight: bold;">กลับด้านบน</a>
</body>
</html>

```
css
[วางโค้ด CSS ที่นี่]
body {
    font-family: Arial, sans-serif;
}

nav {
    background-color: #e0adad;
    padding: 1rem;
    text-align: center;
}

nav img {
    vertical-align: middle;
}

nav a {
    color: #1467c5;
    text-decoration: none;
    margin: 0 1rem;
    font-weight: bold;
}

hr {
    margin: 2rem 0;
}

section {
    text-align: center;
    padding: 2rem;
}

.gallery-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}

.card {
    border: 1px solid #db8383;
    border-radius: 5px;
    margin: 1rem;
    width: 200px;
    overflow: hidden;
}

.card img {
    width: 100%;
    height: auto;
}

.card-content {
    padding: 1rem;
}

.card-content p {
    margin: 0.5rem 0;
}

a[href="#nav"] {
    display: inline-block;
    margin-top: 2rem;
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
```
![image](https://github.com/user-attachments/assets/eed83160-2581-4f97-8e48-25e6c7cd356f)
