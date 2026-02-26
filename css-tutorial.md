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
[วางโค้ดที่นี่]
<!DOCTYPE html>
<html>
<head>

    <title>เมนูนำทาง</title>

    <link rel="stylesheet" href="css/style.css">

</head>
<body>

<nav>

    <ul>

        <li>
            <a href="#" class="menu-item">หน้าแรก</a>
        </li>

        <li>
            <a href="#" class="menu-item" id="active">สินค้า</a>
        </li>

        <li>
            <a href="#" class="menu-item">เกี่ยวกับเรา</a>
        </li>

        <li>
            <a href="#" class="menu-item">ติดต่อ</a>
        </li>

    </ul>

</nav>

</body>
</html>

```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
<img width="1431" height="251" alt="image" src="https://github.com/user-attachments/assets/81f9d336-fb23-402e-9da1-eca53e13d2f2" />


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
[วางโค้ดที่นี่]
```
<!DOCTYPE html>
<html>
<head>

    <title>Product Card</title>

    <link rel="stylesheet" href="css/style.css">

</head>
<body>

<div class="container">

    <!-- product 1 -->
    <div class="product-card">

        <div class="product-image"
        style="background-image: url('image/product1.jpg');">
        </div>

        <div class="product-info">

            <h2 class="product-title">น้ำพีช</h2>

            <p class="product-price">฿69</p>

            <p class="product-description">
                รายละเอียดสินค้า 
            </p>

            <a href="#" class="product-button">
                เพิ่มลงตะกร้า
            </a>

        </div>

    </div>

    <!-- product 2 -->
    <div class="product-card">

        <div class="product-image"
        style="background-image: url('image/product2.jpg');">
        </div>

        <div class="product-info">

            <h2 class="product-title">สับปะรดกวน</h2>

            <p class="product-price">฿29</p>

            <p class="product-description">
                รายละเอียดสินค้า
            </p>

            <a href="#" class="product-button">
                เพิ่มลงตะกร้า
            </a>

        </div>

    </div>

    <!-- product 3 -->
    <div class="product-card">

        <div class="product-image"
        style="background-image: url('image/product3.jpg');">
        </div>

        <div class="product-info">

            <h2 class="product-title">ซอส</h2>

            <p class="product-price">฿69</p>

            <p class="product-description">
                รายละเอียดสินค้า 
            </p>

            <a href="#" class="product-button">
                เพิ่มลงตะกร้า
            </a>

        </div>

    </div>

    <!-- product 4 -->
    <div class="product-card">

        <div class="product-image"
        style="background-image: url('image/product4.jpg');">
        </div>

        <div class="product-info">

            <h2 class="product-title">ขนมไก่ย่างถูกเผา</h2>

            <p class="product-price">฿20</p>

            <p class="product-description">
                รายละเอียดสินค้า 
            </p>

            <a href="#" class="product-button">
                เพิ่มลงตะกร้า
            </a>

        </div>

    </div>


</div>


</body>
</html>


[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
<img width="2874" height="714" alt="image" src="https://github.com/user-attachments/assets/760682af-c6de-499d-8abf-a340f8a2b356" />

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
<!DOCTYPE html>
<html lang="th">
<head>

<meta charset="UTF-8">

<title>สถิติผู้ใช้งาน</title>

<!-- แก้ path ให้ถูกต้อง -->
<link rel="stylesheet" href="css/stats.css">

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
```css
[วางโค้ด CSS ที่นี่]
/* พื้นหลัง */

body{

background-color:#f0f4f8;

font-family:Arial, sans-serif;

}



/* กล่องหลัก */

.stats-container{

display:flex;

justify-content:center;

gap:20px;

margin-top:50px;

}



/* กล่องสถิติ */

.stat-box{

width:200px;

padding:30px;

background-color:white;

border:2px solid rgb(23, 23, 65);

border-radius:10px;

text-align:center;

box-shadow:0 0 10px rgba(248, 0, 0, 0.1);

}

/* ตัวเลข */
.stat-number{

font-size:40px;

font-weight:bold;

color:rgb(137, 26, 26);

margin-bottom:10px;

}



/* ข้อความ */
.stat-label{
font-size:18px;
color:rgb(94, 92, 92);

}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![Uploading Screenshot 2026-02-25 001936.png…]()
<img width="1654" height="383" alt="image" src="https://github.com/user-attachments/assets/293727e0-1fc5-43ac-95cf-106c549974d9" />

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
<html>

<head>

<meta charset="UTF-8">

<title>Blog</title>

<link rel="stylesheet" href="css/blog.css">

</head>
<body>

<article class="blog-post">

<header class="post-header">

<h1 class="post-title">

วิธีการเขียนบทความที่น่าสนใจ

</h1>

<div class="post-meta">

โพสต์เมื่อ 19 กุมภาพันธ์ 2026 | โดย ผู้เขียน

</div>

</header>

<div class="post-content">

<p>

เนื้อหาบทความที่ดีควรมีความน่าสนใจและเป็นประโยชน์ต่อผู้อ่าน

</p>

<h2>

1. การเลือกหัวข้อที่ดี

</h2>

<blockquote>

หัวข้อที่ดีควรตรงกับความสนใจของกลุ่มเป้าหมายและควรเป็นเรื่องที่มีประโยชน์

</blockquote>

<h2>

2. การเขียนที่ดีเกิดจากการฝึกฝน

</h2>


<blockquote>

การเขียนที่ดีเกิดจากการฝึกฝนและการอ่านมากๆ

</blockquote>
<h2>
3. การจัดโครงสร้าง
</h2>

<blockquote>

ควรจัดเรียงให้อ่านง่าย

</blockquote>

</div>

</article>

</body>

</html>
```
```css
[วางโค้ด CSS ที่นี่]
body {

    background-color: #f0f2f5;
    font-family: Arial, sans-serif;

}

.stats-container {

    display: flex;
    justify-content: space-around;

    max-width: 1000px;

    margin: 50px auto;

}

.stat-box {

    flex: 1;

    margin: 20px;

    padding: 30px;

    background-color: white;

    border-radius: 10px;

    border: 2px solid #5b2f75;

}

.stat-number {

    font-size: 40px;

    color: rgb(145, 44, 95);

    margin-bottom: 10px;

}

.stat-label {

    font-size: 18px;

    color: gray;

}

body{

background-color:#e6e6e6;

font-family: Arial, sans-serif;

}

.blog-post{

background:white;


max-width:900px;


margin:50px auto;


padding:40px;

border-radius:15px;


/* เงา */

box-shadow:0 0 10px rgba(0,0,0,0.2);

}

.post-header{

text-align:center;

}

.post-title{

font-size:42px;

color:#142157;

margin-bottom:10px;

}

.post-meta{

color:#999;

font-size:16px;

margin-bottom:30px;

}

.post-content{

font-size:18px;
color:#1a397b;

line-height:1.8;

}

.post-content h2{


color:#4da9ff;


font-size:28px;


margin-top:30px;


}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
<img width="1876" height="1306" alt="image" src="https://github.com/user-attachments/assets/48a510b5-1956-4bbb-9232-7911dfe1a5fa" />


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
<html lang="th">

<head>

<meta charset="UTF-8">

<title>Product Grid</title>

<link rel="stylesheet" href="css/grid.css">

</head>


<body>


<div class="product-grid">


<!-- สินค้า 1 -->

<div class="product-card">

<div class="product-image"
style="background-image: url('image/product1.jpg');">
</div>

<div class="product-details">

<h3 class="product-title">น้ำพีช</h3>

<div class="product-price">฿69</div>

<button class="add-to-cart">
เพิ่มลงตะกร้า
</button>

</div>

</div>


<!-- สินค้า 2 -->

<div class="product-card">

<div class="product-image"
style="background-image: url('image/product2.jpg');">
</div>

<div class="product-details">

<h3 class="product-title">สับปะรดกวน</h3>

<div class="product-price">฿29</div>

<button class="add-to-cart">
เพิ่มลงตะกร้า
</button>

</div>

</div>


<!-- สินค้า 3 -->

<div class="product-card">

<div class="product-image"
style="background-image: url('image/product3.jpg');">
</div>

<div class="product-details">

<h3 class="product-title">ซอส</h3>

<div class="product-price">฿69</div>

<button class="add-to-cart">
เพิ่มลงตะกร้า
</button>

</div>

</div>


<!-- สินค้า 4 -->

<div class="product-card">

<div class="product-image"
style="background-image: url('image/product4.jpg');">
</div>

<div class="product-details">

<h3 class="product-title">ขนมไก่ย่าง</h3>

<div class="product-price">฿20</div>

<button class="add-to-cart">
เพิ่มลงตะกร้า
</button>

</div>

</div>


</div>


</body>

</html>
```
```css
[วางโค้ด CSS ที่นี่]
body{

background-color:#f4f6f8;

font-family: Arial, sans-serif;

}

/* Grid layout */

.product-grid{

display:grid;

grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));

gap:20px;

max-width:900px;

margin:50px auto;

}


/* การ์ด */

.product-card{

background:white;

border-radius:10px;

overflow:hidden;

box-shadow:0 2px 5px rgba(0,0,0,0.2);

transition:0.3s;

}

/* hover */

.product-card:hover{

transform:translateY(-5px);

}


/* รูป */

.product-image{

width:100%;

height:150px;

background-size:cover;

background-position:center;

}


/* รายละเอียด */

.product-details{

padding:10px;

}

/* ชื่อ */

.product-title{

font-size:16px;

color:#333;

}


/* ราคา */

.product-price{

font-size:18px;

color:#6e6667;

margin-top:5px;

}

/* ปุ่ม */

.add-to-cart{

margin-top:10px;

width:100%;

padding:8px;

border:none;

background:#fcce00;

color:white;

border-radius:5px;

cursor:pointer;

}


/* hover ปุ่ม */

.add-to-cart:hover{

background:#b21e3e;

}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
<img width="1875" height="695" alt="image" src="https://github.com/user-attachments/assets/e5e29736-0fe0-4126-8c45-3ad2c6707bb3" />


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
<html lang="th">

<head>

<meta charset="UTF-8">

<title>Modern Dashboard</title>

<link rel="stylesheet" href="css/dashboard.css">

</head>


<body>


<div class="dashboard">


<header class="header">

<h1>Dashboard</h1>

<div>

<button class="btn">โปรไฟล์</button>

<button class="btn logout">ออกจากระบบ</button>

</div>

</header>



<aside class="sidebar">

<h2>เมนู</h2>

<ul>

<li>หน้าแรก</li>

<li>รายงาน</li>

<li>การตั้งค่า</li>

</ul>

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

<h3>กราฟยอดขาย</h3>

<p>แสดงข้อมูลยอดขาย</p>

</div>


<div class="chart">

<h3>สินค้าขายดี</h3>

<p>อันดับสินค้า</p>

</div>


</div>


</main>


</div>


</body>
</html>
```
```css
[วางโค้ด CSS ที่นี่]
body{

margin:0;

font-family: Arial, sans-serif;

background:#eef1f5;

}


/* Layout */

.dashboard{

display:grid;

grid-template-areas:

"sidebar header"

"sidebar main";

grid-template-columns:250px 1fr;

min-height:100vh;

}



/* Header */

.header{

grid-area:header;

background:rgb(181, 138, 255);

padding:15px 30px;

display:flex;

justify-content:space-between;

align-items:center;

box-shadow:0 2px 5px rgba(0,0,0,0.1);

}



/* Sidebar */

.sidebar{

grid-area:sidebar;

background:rgb(30, 16, 65);

color:white;

padding:20px;

}


.sidebar ul{

list-style:none;

padding:0;

}


.sidebar li{

padding:10px;

margin-top:10px;

background:#8b55c9;

border-radius:5px;

}



/* Main */

.main-content{

grid-area:main;

padding:30px;

}



/* Cards */

.stats-grid{

display:grid;

grid-template-columns:repeat(auto-fit,minmax(200px,1fr));

gap:20px;

margin-bottom:30px;

}


.stat-card{

background:white;

padding:20px;

border-radius:10px;

box-shadow:0 2px 5px rgba(0,0,0,0.2);

text-align:center;

}


.stat-card p{

font-size:24px;

color:#1c8d89;

}



/* Chart */

.chart-container{

display:grid;

grid-template-columns:2fr 1fr;

gap:20px;

}


.chart{

background:white;

padding:20px;

border-radius:10px;

box-shadow:0 2px 5px rgba(0,0,0,0.2);

}



/* Buttons */

.btn{

padding:8px 15px;

border:none;

background:#f0d806;

color:white;

border-radius:5px;

cursor:pointer;

}


.logout{

background:rgb(207, 26, 26);

}



/* Responsive */

@media(max-width:768px){

.dashboard{

grid-template-areas:

"header"

"main";

grid-template-columns:1fr;

}


.sidebar{

display:none;

}


.chart-container{

grid-template-columns:1fr;

}

}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
<img width="2879" height="1304" alt="image" src="https://github.com/user-attachments/assets/78ca7b0f-9fd0-40b2-b26c-37aa542cba50" />

