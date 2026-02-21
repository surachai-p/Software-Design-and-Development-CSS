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
<html>
<head>
    <meta charset="UTF-8">
    <title>My Website</title>
    <link rel="stylesheet" href="lab css 2.css">
</head>
<body>
    <nav>
        <ul>
            <li><a href="#" class="menu-item">หน้าแรก</a></li>
            <li><a href="#" class="menu-item" id="active">สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>
</body>
</html>
```

```css
/* style.css */

/* การใช้ Element Selector */
nav {
    background-color: #2b8eff;
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
    background-color: #ff4ba5;
    border-radius: 3px;
}
```

[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]

<img width="1913" height="1080" alt="pic lab2" src="https://github.com/user-attachments/assets/875fca13-fa03-4402-b0a7-9631654deecb" />



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
<html lang="th">
<head>
    <meta charset="UTF-8">
    <title>Product Page</title>
    <link rel="stylesheet" href="lab css 3.css">
</head>
<body>

    <div class="product-container">
        
        <div class="product-card">
            <div class="product-image" style="background-image: url('images/seafood.png');"></div>
            <div class="product-info">
                <h2 class="product-title">น้ำจิ้มซีฟู้ด</h2>
                <p class="product-price">฿100</p>
                <p class="product-description">รายละเอียดสินค้าชิ้นที่ 1 ที่มีความน่าสนใจและน่าใช้งาน</p>
                <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
            </div>
        </div>

        <div class="product-card">
            <div class="product-image" style="background-image: url('images/jeaw.png');"></div>
            <div class="product-info">
                <h2 class="product-title">น้ำจิ้มแจ่ว</h2>
                <p class="product-price">฿105</p>
                <p class="product-description">รายละเอียดสินค้าชิ้นที่ 2 ที่มีความน่าสนใจและน่าใช้งาน</p>
                <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
            </div>
        </div>

        <div class="product-card">
            <div class="product-image" style="background-image: url('images/sukiyaki.png');"></div>
            <div class="product-info">
                <h2 class="product-title">น้ำจิ้มสุกี้</h2>
                <p class="product-price">฿120</p>
                <p class="product-description">รายละเอียดสินค้าชิ้นที่ 3 ที่มีความน่าสนใจและน่าใช้งาน</p>
                <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
            </div>
        </div>

        <div class="product-card">
            <div class="product-image" style="background-image: url('images/chicken.png');"></div>
            <div class="product-info">
                <h2 class="product-title">น้ำจิ้มไก่</h2>
                <p class="product-price">฿110</p>
                <p class="product-description">รายละเอียดสินค้าชิ้นที่ 4 ที่มีความน่าสนใจและน่าใช้งาน</p>
                <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
            </div>
        </div>

    </div>

</body>
</html>
```

```css
/* style.css */
body {
    font-family: Arial, sans-serif;
    background-color: #f5f5f5;
    display: flex;
    justify-content: center;
    padding: 20px;
}

/* Container สำหรับคลุม Card ทั้งหมดให้เรียงกัน */
.product-container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: center;
}

.product-card {
    width: 280px;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    background-color: white;
    transition: transform 0.2s;
}

.product-card:hover {
    transform: translateY(-5px);
}

.product-image {
    width: 100%;
    height: 200px;
    /* ข้อ 2: แก้ไขให้เรียกรูปจากโฟลเดอร์ images */
    background-size: cover;
    background-position: center;
}

.product-info {
    padding: 15px;
}

.product-title {
    color: #333;
    font-size: 18px;
    margin: 0 0 10px 0;
}

.product-price {
    color: #007bff;
    font-size: 24px;
    font-weight: bold;
    margin: 0 0 10px 0;
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
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]

<img width="1920" height="1080" alt="pic lab3" src="https://github.com/user-attachments/assets/a9d3fbe8-35c0-422a-b695-6204172f6f30" />


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
    <meta charset="UTF-8">
    <title>Product Page</title>
    <link rel="stylesheet" href="lab css 4.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Mali:ital,wght@0,200;0,300;0,400;0,500;0,600;0,700;1,200;1,300;1,400;1,500;1,600;1,700&display=swap" rel="stylesheet">
</head>
<body class="mali-medium">

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
 .stats-container {
            display: flex;
            justify-content: space-around;
            max-width: 800px;
            margin: 2rem auto;
            padding: 0 1rem;
        }

        .stat-box {
            flex: 1;
            margin: 0 15px;
            padding: 1rem;
            text-align: center;
            background-color: rgb(255, 184, 223);
            border-radius: 100px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: bold;
            color: #580078e8;
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
        .mali-extralight {
  font-family: "Mali", cursive;
  font-weight: 200;
  font-style: normal;
}

.mali-light {
  font-family: "Mali", cursive;
  font-weight: 300;
  font-style: normal;
}

.mali-regular {
  font-family: "Mali", cursive;
  font-weight: 400;
  font-style: normal;
}

.mali-medium {
  font-family: "Mali", cursive;
  font-weight: 500;
  font-style: normal;
}

.mali-semibold {
  font-family: "Mali", cursive;
  font-weight: 600;
  font-style: normal;
}

.mali-bold {
  font-family: "Mali", cursive;
  font-weight: 700;
  font-style: normal;
}

.mali-extralight-italic {
  font-family: "Mali", cursive;
  font-weight: 200;
  font-style: italic;
}

.mali-light-italic {
  font-family: "Mali", cursive;
  font-weight: 300;
  font-style: italic;
}

.mali-regular-italic {
  font-family: "Mali", cursive;
  font-weight: 400;
  font-style: italic;
}

.mali-medium-italic {
  font-family: "Mali", cursive;
  font-weight: 500;
  font-style: italic;
}

.mali-semibold-italic {
  font-family: "Mali", cursive;
  font-weight: 600;
  font-style: italic;
}

.mali-bold-italic {
  font-family: "Mali", cursive;
  font-weight: 700;
  font-style: italic;
}

```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]

<img width="1911" height="1080" alt="pic lab4" src="https://github.com/user-attachments/assets/cfcd207d-875e-45de-a178-321069bb4411" />

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
<html>
<head>
    <meta charset="UTF-8">
    <title>Blog Post</title>
    <link rel="stylesheet" href="style.css">
    <link href="https://fonts.googleapis.com/css2?family=Sarabun:wght@300;400;700&display=swap" rel="stylesheet">
</head>
<body>
    <article class="blog-post">
        <header class="post-header">
            <h1 class="post-title">วิธีการเขียนบทความที่น่าสนใจ</h1>
            <div class="post-meta">โพสต์เมื่อ 21 กุมภาพันธ์ 2026 | โดย ปทิตญา ภูกิจคุณาเดชากร</div>
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
/* style.css */
body {
    background-color: #f8f9fa; /* เพิ่มสีพื้นหลังหน้าเว็บ */
}

.blog-post {
    max-width: 800px;
    margin: 3rem auto;
    padding: 2rem;
    background-color: #ffffff; /* ให้เนื้อหาดูเด่นขึ้น */
    box-shadow: 0 4px 15px rgba(0,0,0,0.05); /* เพิ่มเงาให้นุ่มนวล */
    border-radius: 8px;
    font-family: 'Sarabun', sans-serif;
}

.post-header {
    text-align: center;
    margin-bottom: 3rem;
    border-bottom: 2px solid #eee;
    padding-bottom: 1.5rem;
}

.post-title {
    font-size: 2.8rem; /* ปรับขนาดใหญ่ขึ้น */
    color: #2c3e50;    /* เปลี่ยนเป็นสีน้ำเงินเข้ม */
    margin-bottom: 0.7rem;
    line-height: 1.3;
}

.post-meta {
    color: #888;
    font-size: 0.85rem;
    text-transform: uppercase;
    letter-spacing: 2px; /* เพิ่มระยะห่างตัวอักษร */
}

.post-content {
    font-size: 1.15rem; /* ปรับขนาดเนื้อหาให้อ่านง่ายขึ้น */
    line-height: 1.9;
    color: #34495e;
}

.post-content h2 {
    font-size: 1.6rem;
    color: #e67e22; /* เปลี่ยนหัวข้อย่อยเป็นสีส้มอิฐ */
    margin: 2.5rem 0 1rem;
}

blockquote {
    font-style: italic;
    border-left: 5px solid #e67e22; /* เปลี่ยนสีเส้นขอบ quote */
    margin: 2rem 0;
    padding: 1rem 1.5rem;
    background-color: #fffaf5;
    color: #666;
}

@media (max-width: 768px) {
    .post-title {
        font-size: 2rem;
    }
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]

<img width="1918" height="1078" alt="pic lab5" src="https://github.com/user-attachments/assets/cd70079f-59bc-4269-b447-66f0e4f0f033" />

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
    <title>หน้าร้านค้าออนไลน์</title>
    <link rel="stylesheet" href="lab css 6.1.css">
</head>
<body>

    <div class="product-grid">
        <div class="product-card">
            <div class="product-image" style="background-image: url('images/seafood.png')"></div>
            <div class="product-details">
                <h3 class="product-title">น้ำจิ้มซีฟู้ด</h3>
                <div class="product-price">฿100</div>
                <button class="add-to-cart">หยิบใส่ตะกร้า</button>
            </div>
        </div>

        <div class="product-card">
            <div class="product-image" style="background-image: url('images/jeaw.png')"></div>
            <div class="product-details">
                <h3 class="product-title">น้ำจิ้มแจ่ว</h3>
                <div class="product-price">฿105</div>
                <button class="add-to-cart">หยิบใส่ตะกร้า</button>
            </div>
        </div>

        <div class="product-card">
            <div class="product-image" style="background-image: url('images/sukiyaki.png')"></div>
            <div class="product-details">
                <h3 class="product-title">น้ำจิ้มสุกี้</h3>
                <div class="product-price">฿120</div>
                <button class="add-to-cart">หยิบใส่ตะกร้า</button>
            </div>
        </div>

        <div class="product-card">
            <div class="product-image" style="background-image: url('images/chicken.png')"></div>
            <div class="product-details">
                <h3 class="product-title">น้ำจิ้มไก่</h3>
                <div class="product-price">฿110</div>
                <button class="add-to-cart">หยิบใส่ตะกร้า</button>
            </div>
        </div>
    </div>

</body>
</html>
```
```css
/* style.css */
body {
    background-color: #f4f7f6;
    margin: 0;
    font-family: 'Sarabun', sans-serif;
}

/* ตั้งค่าระบบ Grid */
.product-grid {
    display: grid; /* เปิดใช้งาน CSS Grid */
    
    /* ข้อ 2: ปรับขนาดสินค้าให้เล็กลง (180px) และจัดเรียงอัตโนมัติ */
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    
    gap: 20px;       /* ระยะห่างระหว่างช่อง Grid */
    padding: 30px;
    max-width: 1200px;
    margin: 0 auto;
}

.product-card {
    background: white;
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 4px 10px rgba(0,0,0,0.08);
    transition: all 0.3s ease;
    display: flex;
    flex-direction: column; /* จัดองค์ประกอบภายในการ์ดเป็นแนวตั้ง */
}

.product-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 15px rgba(0,0,0,0.15);
}

.product-image {
    width: 100%;
    height: 160px; /* ปรับความสูงรูปให้พอดีกับการ์ดที่เล็กลง */
    background-color: #eee;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
}

.product-details {
    padding: 15px;
    text-align: center;
}

.product-title {
    font-size: 0.95rem;
    color: #333;
    margin-bottom: 8px;
}

.product-price {
    font-size: 1.1rem;
    color: #007bff;
    font-weight: bold;
    margin-bottom: 12px;
}

.add-to-cart {
    background-color: #007bff;
    color: white;
    border: none;
    padding: 8px 15px;
    border-radius: 6px;
    cursor: pointer;
    width: 100%;
    font-size: 0.85rem;
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]

<img width="1900" height="1078" alt="pic lab6 1" src="https://github.com/user-attachments/assets/d977926c-6086-4214-92a9-5fe0f14bce98" />

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
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard</title>
    <link rel="stylesheet" href="lab css 6.2.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <div class="dashboard">
        <aside class="sidebar">
            <h2><i class="fas fa-chart-line"></i> MY DASH</h2>
            <nav>
                <ul>
                    <li class="active"><i class="fas fa-home"></i> หน้าแรก</li>
                    <li><i class="fas fa-chart-bar"></i> รายงานยอดขาย</li>
                    <li><i class="fas fa-cog"></i> การตั้งค่าระบบ</li>
                </ul>
            </nav>
        </aside>

        <header class="header">
            <h1>ภาพรวมธุรกิจ</h1>
            <nav>
                <button><i class="fas fa-user-circle"></i> โปรไฟล์</button>
                <button class="logout"><i class="fas fa-sign-out-alt"></i> ออกจากระบบ</button>
            </nav>
        </header>

        <main class="main-content">
            <div class="stats-grid">
                <div class="stat-card">
                    <h3><i class="fas fa-money-bill-wave"></i> ยอดขายรวม </h3>
                    <p>฿150,000</p>
                </div>
                <div class="stat-card" style="border-left-color: #28a745;"> <h3><i class="fas fa-shopping-cart"></i> จำนวนออเดอร์</h3>
                    <p>1,234</p>
                </div>
                <div class="stat-card" style="border-left-color: #ffc107;"> <h3><i class="fas fa-user-plus"></i> ลูกค้าใหม่</h3>
                    <p>45</p>
                </div>
            </div>

            <div class="chart-container">
                <div class="chart">
                    <h3>📈 กราฟแสดงยอดขาย</h3>
                    <div style="height: 250px; background: #fdfdfd; border: 1px dashed #e9ecef; display: flex; align-items: center; justify-content: center; color: #adb5bd; font-size: 1.1rem;">
                        <i class="fas fa-chart-line" style="margin-right: 10px;"></i> พื้นที่สำหรับแสดงกราฟเส้น (เช่น Chart.js)
                    </div>
                </div>
                <div class="chart">
                    <h3>📊 สัดส่วนสินค้าขายดี</h3>
                    <div style="height: 250px; background: #fdfdfd; border: 1px dashed #e9ecef; display: flex; align-items: center; justify-content: center; color: #adb5bd; font-size: 1.1rem;">
                        <i class="fas fa-chart-pie" style="margin-right: 10px;"></i> พื้นที่สำหรับแสดงกราฟวงกลม (เช่น Chart.js)
                    </div>
                </div>
            </div>
        </main>
    </div>
</body>
</html>
```
```css
/* style.css */
@import url('https://fonts.googleapis.com/css2?family=Sarabun:wght@300;400;500;600;700&display=swap');

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Sarabun', sans-serif;
    background-color: #f8f9fa; /* Light grey background for a clean look */
    line-height: 1.6;
    color: #343a40; /* Darker text for readability */
}

/* Overall Dashboard Layout */
.dashboard {
    display: grid;
    grid-template-areas: 
        "sidebar header"
        "sidebar main";
    grid-template-columns: 280px 1fr; /* Wider sidebar for more content */
    grid-template-rows: auto 1fr;
    min-height: 100vh;
}

/* --- Header Section --- */
.header {
    grid-area: header;
    background: #ffffff;
    padding: 1rem 2.5rem; /* More padding */
    box-shadow: 0 4px 15px rgba(0,0,0,0.05);
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 1px solid #e9ecef;
    z-index: 10;
}

.header h1 {
    font-size: 1.6rem; /* Slightly larger title */
    color: #212529;
    font-weight: 600;
}

.header nav button {
    padding: 10px 20px;
    margin-left: 15px;
    border-radius: 8px; /* Softer rounded corners */
    border: none; /* No border for a cleaner look */
    background: #e9ecef; /* Light grey button background */
    color: #495057;
    cursor: pointer;
    font-weight: 500;
    transition: all 0.3s ease;
}

.header nav button:hover {
    background: #dee2e6;
    color: #212529;
}

.header nav button.logout {
    background-color: #dc3545; /* Red for logout */
    color: white;
}

.header nav button.logout:hover {
    background-color: #c82333;
}

/* --- Sidebar Section --- */
.sidebar {
    grid-area: sidebar;
    background: linear-gradient(to bottom, #142b5f, #334c89); /* Dark gradient for depth */
    color: #e0e0e0; /* Lighter text for contrast */
    padding: 2.5rem 1.5rem; /* More vertical padding */
    box-shadow: 2px 0 10px rgba(0,0,0,0.1);
    position: sticky; /* Make sidebar sticky */
    top: 0;
    height: 100vh;
}

.sidebar h2 {
    color: #ffffff;
    margin-bottom: 3rem; /* More space below title */
    text-align: center;
    font-size: 1.8rem;
    font-weight: 700;
    letter-spacing: 1px;
}

.sidebar ul {
    list-style: none;
}

.sidebar li {
    padding: 15px 20px; /* More padding for menu items */
    margin-bottom: 8px;
    border-radius: 8px;
    cursor: pointer;
    transition: background 0.3s ease, color 0.3s ease;
    display: flex; /* For icon alignment */
    align-items: center;
    font-weight: 500;
}

.sidebar li i { /* Icon styling */
    margin-right: 10px;
    font-size: 1.1rem;
}

.sidebar li:hover {
    background: #3a4b60; /* Slightly lighter dark on hover */
    color: #ffffff;
}

.sidebar li.active { /* Active menu item */
    background: #007bff;
    color: white;
    box-shadow: 0 4px 10px rgba(0,123,255,0.3);
}

/* --- Main Content Section --- */
.main-content {
    grid-area: main;
    padding: 2.5rem; /* More padding */
    background: #f8f9fa;
}

.stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); /* Larger stat cards */
    gap: 2rem; /* More space between cards */
    margin-bottom: 3rem;
}

.stat-card {
    background: #ffffff;
    padding: 2rem; /* More internal padding */
    border-radius: 12px; /* Softer corners */
    box-shadow: 0 6px 20px rgba(0,0,0,0.08); /* More prominent shadow */
    border-left: 6px solid #007bff; /* Primary blue left border */
    transition: transform 0.3s ease;
}

.stat-card:hover {
    transform: translateY(-5px); /* Lift effect on hover */
}

.stat-card h3 {
    font-size: 1rem;
    color: #6c757d;
    margin-bottom: 12px;
    font-weight: 500;
}

.stat-card p {
    font-size: 2.2rem; /* Larger numbers */
    font-weight: 700;
    color: #212529;
}

/* Chart Section */
.chart-container {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 2rem;
}

.chart {
    background: #ffffff;
    padding: 2rem;
    border-radius: 12px;
    min-height: 350px; /* Taller charts */
    box-shadow: 0 6px 20px rgba(0,0,0,0.08);
}

.chart h3 {
    font-size: 1.3rem;
    color: #212529;
    margin-bottom: 1.5rem;
    border-bottom: 1px solid #e9ecef;
    padding-bottom: 1rem;
    font-weight: 600;
}

/* Responsive Design */
@media (max-width: 992px) {
    .dashboard {
        grid-template-columns: 200px 1fr; /* Slightly narrower sidebar on medium screens */
    }
    .chart-container {
        grid-template-columns: 1fr; /* Stack charts on smaller screens */
    }
}

@media (max-width: 768px) {
    .dashboard {
        grid-template-areas: 
            "header"
            "main";
        grid-template-columns: 1fr;
    }
    .sidebar {
        display: none; /* Hide sidebar on mobile */
    }
    .header {
        padding: 0.8rem 1.5rem;
    }
    .header h1 {
        font-size: 1.2rem;
    }
    .header nav button {
        padding: 6px 12px;
        font-size: 0.85rem;
    }
    .main-content {
        padding: 1.5rem;
    }
    .stats-grid {
        grid-template-columns: 1fr; /* Stack stat cards on mobile */
    }
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]

<img width="1913" height="1078" alt="pic lab6 2" src="https://github.com/user-attachments/assets/d1cba040-a145-493e-b5d0-e3ca37a941e9" />
