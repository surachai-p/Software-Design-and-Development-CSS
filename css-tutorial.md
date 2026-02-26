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
<html lang="th">
<head>
    <meta charset="UTF-8">
    <title>เมนูเว็บไซต์</title>

    <!-- เรียกใช้ External CSS -->
    <link rel="stylesheet" href="/css/buttom.css">
</head>

<body>

    <nav>
        <ul>
            <li><a href="#" class="menu-item">หน้าแรก</a></li>
            <li><a href="#" class="menu-item active">สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>

</body>
</html>
CSS
/* พื้นหลังแถบเมนู */
nav{
    background-color: #222;
    padding: 15px;
}

/* เอาจุดหน้าลิสต์ออก + เรียงแนวนอน */
nav ul{
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
}

/* ระยะห่างเมนู */
nav ul li{
    margin: 0 10px;
}

/* ปุ่มเมนู */
.menu-item{
    color: white;
    text-decoration: none;
    padding: 10px 18px;
    border-radius: 6px;
    font-family: Tahoma;
}

/* เอาเมาส์ชี้ */
.menu-item:hover{
    background-color: orange;
}

/* เมนูที่ถูกเลือก = สินค้า */
.menu-item.active{
    background-color: #007bff;
}
#active {
    background-color: red;
}

```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
<img width="1919" height="873" alt="image" src="https://github.com/user-attachments/assets/c3427169-a5ab-47d3-8793-19fdedbf2680" />


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
product.html
<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <title>สินค้า</title>

    <!-- External CSS -->
    <link rel="stylesheet" href="../css/product.css">
</head>

<body>

<div class="container">

    <!-- สินค้า 1 -->
    <div class="product-card">
        <img src="../images/p1.jpg" class="product-image">
        <div class="product-info">
            <h2 class="product-title">สินค้าตัวอย่าง 1</h2>
            <p class="product-price">฿1,999</p>
            <p class="product-description">รายละเอียดสินค้าน่าใช้งาน</p>
            <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
    </div>

    <!-- สินค้า 2 -->
    <div class="product-card">
        <img src="../images/p2.jpg" class="product-image">
        <div class="product-info">
            <h2 class="product-title">สินค้าตัวอย่าง 2</h2>
            <p class="product-price">฿2,490</p>
            <p class="product-description">คุณภาพดี คุ้มราคา</p>
            <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
    </div>

    <!-- สินค้า 3 -->
    <div class="product-card">
        <img src="../images/p3.jpg" class="product-image">
        <div class="product-info">
            <h2 class="product-title">สินค้าตัวอย่าง 3</h2>
            <p class="product-price">฿3,290</p>
            <p class="product-description">เหมาะสำหรับใช้งานทุกวัน</p>
            <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
    </div>

    <!-- สินค้า 4 -->
    <div class="product-card">
        <img src="../images/p4.jpg" class="product-image">
        <div class="product-info">
            <h2 class="product-title">สินค้าตัวอย่าง 4</h2>
            <p class="product-price">฿990</p>
            <p class="product-description">ราคาประหยัด น่าใช้</p>
            <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
    </div>

</div>

</body>
</html>
product.css
/* พื้นหลังหน้าเว็บ */
body{
    background-color: #f4f6f9;
    font-family: Tahoma;
}

/* จัดการ์ดให้เรียง 4 อัน */
.container{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 25px;
    padding: 40px;
}

/* กล่องสินค้า */
.product-card{
    width: 260px;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 4px 10px rgba(0,0,0,0.15);
    background-color: white;
    transition: 0.3s;
}

/* hover ลอยขึ้น */
.product-card:hover{
    transform: translateY(-5px);
}

/* รูปสินค้า */
.product-image{
    width: 100%;
    height: 180px;
    object-fit: cover;
}

/* ข้อมูลสินค้า */
.product-info{
    padding: 15px;
}

.product-title{
    color: #333;
    font-size: 18px;
    margin-bottom: 10px;
}

.product-price{
    color: #007bff;
    font-size: 22px;
    font-weight: bold;
}

.product-description{
    color: #666;
    font-size: 14px;
}

/* ปุ่ม */
.product-button{
    display: block;
    background: linear-gradient(to right, #007bff, #004a99);
    color: white;
    text-align: center;
    padding: 10px;
    text-decoration: none;
    margin-top: 15px;
    border-radius: 5px;
}

.product-button:hover{
    background: linear-gradient(to right, #004a99, #002f66);
}

```
<img width="1918" height="866" alt="image" src="https://github.com/user-attachments/assets/0b3acf03-2f5a-4d8e-a5b1-12f0f28173c0" />


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
<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Stats Cards</title>

  <!-- External CSS -->
  <link rel="stylesheet" href="style.css" />
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
/* ===== Page Base ===== */
body {
  margin: 0;
  padding: 0;
  font-family: "Sarabun", Arial, sans-serif;
  background: #f3f6fb;
  color: #222;
}

/* ===== Layout ===== */
.stats-container {
  display: flex;
  justify-content: space-around;
  gap: 20px;
  max-width: 1100px;
  margin: 2.5rem auto;
  padding: 0 1rem;
}

/* ===== Box Model ===== */
.stat-box {
  flex: 1;
  padding: 28px;                 /* ปรับ padding ให้ชัด */
  text-align: center;
  background-color: #ffffff;
  border-radius: 14px;           /* มุมโค้งขึ้น */
  border: 1px solid #e8eef7;     /* เพิ่มเส้นขอบบาง ๆ */
  box-shadow: 0 6px 18px rgba(0, 0, 0, 0.08); /* เงานุ่มขึ้น */
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.stat-box:hover {
  transform: translateY(-4px);
  box-shadow: 0 10px 24px rgba(0, 0, 0, 0.12);
}

/* ===== Typography ===== */
.stat-number {
  font-size: 2.8rem;       /* ปรับขนาดตัวเลข */
  font-weight: 800;
  color: #1d4ed8;          /* ปรับโทนสี */
  margin-bottom: 10px;
  line-height: 1.1;
}

.stat-label {
  font-size: 0.95rem;      /* ปรับขนาด label */
  color: #64748b;
  letter-spacing: 1px;
  text-transform: uppercase;
}

/* ===== Responsive ===== */
@media (max-width: 768px) {
  .stats-container {
    flex-direction: column;
  }

  .stat-box {
    padding: 22px;
  }

  .stat-number {
    font-size: 2.2rem;
  }
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
<img width="1916" height="1014" alt="image" src="https://github.com/user-attachments/assets/ce48e28d-e941-4b3c-bb79-cf4865ad1afa" />

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
<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>บทความตัวอย่าง</title>

  <!-- External CSS -->
  <link rel="stylesheet" href="style.css" />
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
```css
/* ===== Base ===== */
body {
  margin: 0;
  padding: 0;
  font-family: "Sarabun", Arial, sans-serif;
  background: #f6f7fb;
  color: #1f2937;
}

/* ===== Blog Layout ===== */
.blog-post {
  max-width: 820px;
  margin: 2.5rem auto;
  padding: 0 1rem;
}

/* กล่องบทความให้ดูเป็น Card */
.blog-post {
  background: #ffffff;
  border: 1px solid #e5e7eb;
  border-radius: 14px;
  padding: 28px;
  box-shadow: 0 10px 26px rgba(0,0,0,0.06);
}

/* ===== Header ===== */
.post-header {
  text-align: center;
  margin-bottom: 2rem;
}

.post-title {
  font-size: 2.6rem;      /* ปรับขนาด title */
  color: #111827;         /* เข้มขึ้น */
  margin: 0 0 0.6rem;
  line-height: 1.2;
  letter-spacing: -0.5px;
}

.post-meta {
  color: #6b7280;         /* เทาอ่านง่าย */
  font-size: 0.9rem;
  text-transform: uppercase;
  letter-spacing: 1px;
}

/* ===== Content ===== */
.post-content {
  font-size: 1.1rem;      /* ปรับขนาดเนื้อหา */
  line-height: 1.9;       /* อ่านสบายตา */
  color: #374151;
}

.post-content p {
  margin: 0 0 1.2rem;
}

.post-content h2 {
  font-size: 1.7rem;      /* ปรับขนาดหัวข้อย่อย */
  color: #111827;
  margin: 2rem 0 1rem;
}

/* Quote */
blockquote {
  margin: 1.6rem 0;
  padding: 1rem 1.2rem;
  border-left: 5px solid #2563eb;
  background: #eff6ff;
  color: #1e3a8a;
  font-style: italic;
  border-radius: 10px;
}

/* ===== Responsive ===== */
@media (max-width: 768px) {
  .blog-post {
    padding: 18px;
    margin: 1.2rem auto;
  }

  .post-title {
    font-size: 2rem;
  }

  .post-content {
    font-size: 1rem;
  }

  .post-content h2 {
    font-size: 1.4rem;
  }
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
<img width="1919" height="1009" alt="image" src="https://github.com/user-attachments/assets/872f8767-662f-4f65-bd2d-9ac34da50d0e" />

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
<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>สินค้า</title>

    <!-- External CSS -->
    <link rel="stylesheet" href="style.css">
</head>

<body>

<div class="product-grid">

    <!-- สินค้าชิ้นที่ 1 -->
    <div class="product-card">
        <img src="product1.jpg" class="product-image">

        <div class="product-details">
            <h3 class="product-title">Iphone 17 Promax</h3>
            <div class="product-price">฿82,000</div>

            <div class="product-action">
                <button class="add-to-cart">เพิ่มลงตะกร้า</button>
            </div>
        </div>
    </div>

    <!-- สินค้าชิ้นที่ 2 -->
    <div class="product-card">
        <img src="product2.jpg" class="product-image">

        <div class="product-details">
            <h3 class="product-title">Samsung Galaxy S25</h3>
            <div class="product-price">฿14,990</div>

            <div class="product-action">
                <button class="add-to-cart">เพิ่มลงตะกร้า</button>
            </div>
        </div>
    </div>

</div>

</body>
</html>
```
```css
/* พื้นหลัง */
body{
    margin:0;
    font-family: Arial, sans-serif;
    background:#f3f5f9;
}

/* grid */
.product-grid{
    display:grid;
    grid-template-columns: repeat(auto-fill, minmax(200px,1fr)); /* เล็กลง */
    gap:15px;
    padding:15px;
    max-width:900px;  /* ลดขนาดหน้ากว้าง */
    margin:auto;
}

/* card */
.product-card{
    background:white;
    border-radius:10px;
    overflow:hidden;
    box-shadow:0 3px 10px rgba(0,0,0,0.1);
    transition:0.25s;
}

.product-card:hover{
    transform:translateY(-6px);
}

/* รูปสินค้า */
.product-image{
    width:100%;
    height:150px;          /* ลดความสูงรูป */
    object-fit:cover;      /* ไม่ยืดภาพ */
}

/* รายละเอียด */
.product-details{
    padding:12px;
}

.product-title{
    font-size:1rem;        /* ตัวหนังสือเล็กลง */
    margin-bottom:6px;
    color:#222;
}

.product-price{
    font-size:1.1rem;
    color:#0d6efd;
    font-weight:bold;
}

/* ปุ่ม */
.product-action{
    margin-top:10px;
}

.add-to-cart{
    width:100%;
    background:#0d6efd;
    color:white;
    border:none;
    padding:7px;
    border-radius:5px;
    cursor:pointer;
}

.add-to-cart:hover{
    background:#084cdf;
}

/* มือถือ */
@media(max-width:768px){
    .product-grid{
        grid-template-columns:repeat(auto-fill,minmax(160px,1fr));
    }

    .product-image{
        height:120px;
    }
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
<img width="1919" height="1015" alt="image" src="https://github.com/user-attachments/assets/042891f0-9cc0-4a04-b681-36b8f9b95081" />


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
<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>แดชบอร์ด</title>

  <!-- External CSS -->
  <link rel="stylesheet" href="style.css" />
</head>

<body>
  <div class="dashboard">
    <header class="header">
      <h1 class="title">แดชบอร์ด</h1>

      <nav class="top-nav">
        <button class="btn btn-outline">โปรไฟล์</button>
        <button class="btn btn-primary">ออกจากระบบ</button>
      </nav>
    </header>

    <aside class="sidebar">
      <div class="brand">MY DASH</div>

      <nav class="side-nav">
        <a class="menu-item active" href="#">หน้าแรก</a>
        <a class="menu-item" href="#">รายงาน</a>
        <a class="menu-item" href="#">การตั้งค่า</a>
      </nav>
    </aside>

    <main class="main-content">
      <div class="stats-grid">
        <div class="stat-card">
          <h3>ยอดขายรวม</h3>
          <p class="stat-value">฿150,000</p>
          <p class="stat-sub">+12% จากเดือนที่แล้ว</p>
        </div>

        <div class="stat-card">
          <h3>จำนวนออเดอร์</h3>
          <p class="stat-value">1,234</p>
          <p class="stat-sub">เฉลี่ย 41 ออเดอร์/วัน</p>
        </div>

        <div class="stat-card">
          <h3>ลูกค้าใหม่</h3>
          <p class="stat-value">45</p>
          <p class="stat-sub">เพิ่มขึ้นต่อเนื่อง</p>
        </div>
      </div>

      <div class="chart-container">
        <div class="chart">
          <h3>กราฟแสดงยอดขาย</h3>
          <div class="chart-placeholder">พื้นที่สำหรับกราฟ</div>
        </div>

        <div class="chart">
          <h3>สัดส่วนสินค้าขายดี</h3>
          <div class="chart-placeholder">พื้นที่สำหรับกราฟ</div>
        </div>
      </div>
    </main>
  </div>
</body>
</html>
```
```css
/* ===== Reset / Base ===== */
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: "Sarabun", Arial, sans-serif;
  background: #f5f7fa;
  color: #111827;
}

/* ===== Dashboard Grid ===== */
.dashboard {
  display: grid;
  grid-template-areas:
    "sidebar header"
    "sidebar main";
  grid-template-columns: 260px 1fr;
  grid-template-rows: auto 1fr;
  min-height: 100vh;
}

/* ===== Header ===== */
.header {
  grid-area: header;
  background: #ffffff;
  padding: 14px 18px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.06);
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.title {
  margin: 0;
  font-size: 1.35rem;
  letter-spacing: -0.2px;
}

.top-nav {
  display: flex;
  gap: 10px;
}

/* ===== Buttons ===== */
.btn {
  border: none;
  padding: 10px 14px;
  border-radius: 10px;
  cursor: pointer;
  font-size: 0.95rem;
  transition: 0.2s;
}

.btn-primary {
  background: #2563eb;
  color: #fff;
}

.btn-primary:hover {
  background: #1d4ed8;
  transform: translateY(-1px);
}

.btn-outline {
  background: #ffffff;
  border: 1px solid #dbe3f0;
  color: #111827;
}

.btn-outline:hover {
  background: #f3f6ff;
  transform: translateY(-1px);
}

/* ===== Sidebar ===== */
.sidebar {
  grid-area: sidebar;
  background: #0f172a;
  color: #ffffff;
  padding: 16px 14px;
}

.brand {
  font-weight: 800;
  letter-spacing: 2px;
  font-size: 1.05rem;
  padding: 10px 12px;
  border-radius: 10px;
  background: rgba(255,255,255,0.06);
  margin-bottom: 14px;
}

.side-nav {
  display: flex;
  flex-direction: column;
  gap: 6px;
}

.menu-item {
  text-decoration: none;
  color: rgba(255,255,255,0.85);
  padding: 10px 12px;
  border-radius: 10px;
  transition: 0.2s;
}

.menu-item:hover {
  background: rgba(255,255,255,0.10);
  color: #fff;
}

.menu-item.active {
  background: rgba(37, 99, 235, 0.35);
  color: #fff;
}

/* ===== Main ===== */
.main-content {
  grid-area: main;
  padding: 18px;
}

/* ===== Stats Cards ===== */
.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
  gap: 14px;
  margin-bottom: 18px;
}

.stat-card {
  background: #ffffff;
  padding: 16px;
  border-radius: 14px;
  border: 1px solid #e7eef8;
  box-shadow: 0 8px 20px rgba(0,0,0,0.06);
  transition: 0.2s;
}

.stat-card:hover {
  transform: translateY(-3px);
}

.stat-card h3 {
  margin: 0 0 6px;
  font-size: 1rem;
  color: #334155;
}

.stat-value {
  margin: 0;
  font-size: 1.6rem;
  font-weight: 800;
  color: #2563eb;
}

.stat-sub {
  margin: 6px 0 0;
  color: #64748b;
  font-size: 0.9rem;
}

/* ===== Charts ===== */
.chart-container {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 14px;
}

.chart {
  background: #ffffff;
  padding: 16px;
  border-radius: 14px;
  border: 1px solid #e7eef8;
  box-shadow: 0 8px 20px rgba(0,0,0,0.06);
}

.chart h3 {
  margin: 0 0 10px;
  color: #334155;
  font-size: 1rem;
}

.chart-placeholder {
  height: 220px;
  border-radius: 12px;
  background: repeating-linear-gradient(
    45deg,
    #f3f6fb,
    #f3f6fb 10px,
    #eef2ff 10px,
    #eef2ff 20px
  );
  display: flex;
  align-items: center;
  justify-content: center;
  color: #64748b;
  font-size: 0.95rem;
}

/* ===== Responsive ===== */
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
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
<img width="1911" height="1002" alt="image" src="https://github.com/user-attachments/assets/406d3102-9349-4177-b253-4b4689224ed5" />

