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
[<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>เว็บไซต์ตัวอย่าง</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>

    <header>
        <nav class="navbar">
            <ul class="menu">
                <li><a href="#" class="menu-item">หน้าแรก</a></li>
                <li><a href="#" class="menu-item active">สินค้า</a></li>
                <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
                <li><a href="#" class="menu-item">ติดต่อ</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section class="content">
            <h1>สินค้า</h1>
            <p>นี่คือหน้าสินค้าของเว็บไซต์ตัวอย่าง</p>
        </section>
    </main>

</body>
</html>
]
```
[![alt text](<Screenshot 2026-02-19 152022.png>)]


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
[<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>เว็บไซต์ตัวอย่าง</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>

<header>
    <nav class="navbar">
        <ul class="menu">
            <li><a href="#" class="menu-item">หน้าแรก</a></li>
            <li><a href="#" class="menu-item active">สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>
</header>

<main>
    <section class="content">
        <h1>สินค้า</h1>

        <div class="product-container">

            <div class="product-card">
                <img src="images/Screenshot 2026-02-19 152546.png" alt="สินค้า 1">
                <div class="product-info">
                    <h2>CSM คาบูโตธ</h2>
                    <p class="price">฿8,999</p>
                    <p>เอาไว้แปลงร่าง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

            <div class="product-card">
                <img src="images/csm-henshin-belt-typhoon-shin-kamen-rider-version-v0-xqouuylo34rb1.jpg" alt="สินค้า 2">
                <div class="product-info">
                    <h2>V 2</h2>
                    <p class="price">฿2,499</p>
                    <p>สินค้าที่มีคุณภาพสูง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

            <div class="product-card">
                <img src="images/Screenshot 2026-02-19 153726.png" alt="สินค้า 3">
                <div class="product-info">
                    <h2>๕</h2>
                    <p class="price">฿12,199</p>
                    <p>หากการต่อสู้ถือเป็นปาบฉันจะปกป้องเอง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

            <div class="product-card">
                <img src="images/Screenshot 2026-02-19 154005.png" alt="สินค้า 4">
                <div class="product-info">
                    <h2> V 1</h2>
                    <p class="price">฿8,599</p>
                    <p>แปลงร่างที่มีคุณภาพสูง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

        </div>
    </section>
</main>

</body>
</html>
]
```
[![alt text](image.png)]

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
[<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>เว็บไซต์ตัวอย่าง</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>

<header>
    <nav class="navbar">
        <ul class="menu">
            <li><a href="#" class="menu-item">หน้าแรก</a></li>
            <li><a href="#" class="menu-item active">สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>
</header>

<main>

    <!-- Section สินค้า -->
    <section class="content">
        <h1 class="section-title">สินค้า</h1>

        <div class="product-container">

            <div class="product-card">
                <img src="images/Screenshot 2026-02-19 152546.png" alt="สินค้า 1">
                <div class="product-info">
                    <h2>CSM คาบูโตะ</h2>
                    <div class="stat-number">฿8,999</div>
                    <p>เอาไว้แปลงร่าง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

            <div class="product-card">
                <img src="images/csm-henshin-belt-typhoon-shin-kamen-rider-version-v0-xqouuylo34rb1.jpg" alt="สินค้า 2">
                <div class="product-info">
                    <h2>V2</h2>
                    <div class="stat-number">฿2,499</div>
                    <p>สินค้าที่มีคุณภาพสูง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

            <div class="product-card">
                <img src="images/Screenshot 2026-02-19 153726.png" alt="สินค้า 3">
                <div class="product-info">
                    <h2>หมายเลข 5</h2>
                    <p class="price">฿12,199</p>
                    <p>หากการต่อสู้ถือเป็นบาป ฉันจะปกป้องเอง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

            <div class="product-card">
                <img src="images/Screenshot 2026-02-19 154005.png" alt="สินค้า 4">
                <div class="product-info">
                    <h2>V1</h2>
                    <p class="price">฿8,599</p>
                    <p>แปลงร่างที่มีคุณภาพสูง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

        </div>
    </section>

    <!-- Section สถิติ -->
    <section class="stats-container">
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
    </section>

</main>

</body>
</html>
]
```
```css
[/* ===== Global Reset & Font ===== */
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: "Segoe UI", Arial, sans-serif;
    background-color: #f4f6f9;
    color: #333;
}

/* ===== Navbar ===== */
.navbar {
    background: linear-gradient(90deg, #1e1e1e, #333);
    padding: 15px 0;
}

.menu {
    list-style: none;
    display: flex;
    justify-content: center;
    padding: 0;
    margin: 0;
}

.menu > li {
    margin: 0 20px;
}

.menu-item {
    color: white;
    text-decoration: none;
    padding: 10px 18px;
    border-radius: 6px;
    font-size: 16px;
    transition: 0.3s;
}

.menu-item:hover {
    background-color: #555;
}

.menu-item.active {
    background-color: #ff6600;
    font-weight: bold;
}

/* ===== Section Title ===== */
.section-title {
    font-size: 32px;
    margin-bottom: 30px;
    color: #222;
}

/* ===== Product Grid ===== */
.content {
    padding: 50px 5%;
    text-align: center;
}

.product-container {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 25px;
}

/* ===== Product Card ===== */
.product-card {
    background: #edcccc;
    border-radius: 12px;
    padding-bottom: 20px;
    box-shadow: 0 6px 15px rgba(0,0,0,0.1);
    transition: transform 0.3s ease;
}

.product-card:hover {
    transform: translateY(-8px);
}

.product-card img {
    width: 100%;
    height: 220px;
    object-fit: cover;
}

.product-info {
    padding: 20px;
    text-align: left;
}

.product-info h2 {
    font-size: 20px;
    margin-bottom: 10px;
}

.price {
    font-size: 22px;
    font-weight: bold;
    color: #007bff;
    margin-bottom: 10px;
}

.btn {
    display: inline-block;
    padding: 10px 15px;
    background: #007bff;
    color: white;
    text-decoration: none;
    border-radius: 6px;
    font-size: 14px;
    margin-top: 10px;
}

.btn:hover {
    background: #0056b3;
}

/* ===== Stats Section ===== */
.stats-container {
    display: flex;
    justify-content: space-around;
    max-width: 1200px;
    margin: 60px auto;
    padding: 0 20px;
}

.stat-box {
    flex: 1;
    margin: 0 15px;
    padding: 40px 20px;
    background: white;
    border-radius: 12px;
    text-align: center;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.stat-number {
    font-size: 40px;
    font-weight: bold;
    color: #ff6600;
}

.stat-label {
    font-size: 14px;
    margin-top: 8px;
    letter-spacing: 1px;
    color: #666;
}

/* ===== Responsive ===== */
@media (max-width: 992px) {
    .product-container {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 768px) {
    .product-container {
        grid-template-columns: 1fr;
    }

    .stats-container {
        flex-direction: column;
    }

    .stat-box {
        margin: 15px 0;
    }
}
]
```
[![alt text](image.png)]

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
[<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>เว็บไซต์ตัวอย่าง</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>

<header>
    <nav class="navbar">
        <ul class="menu">
            <li><a href="#" class="menu-item">หน้าแรก</a></li>
            <li><a href="#" class="menu-item active">สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>
</header>

<main>

    <!-- Section สินค้า -->
    <section class="content">
        <h1 class="section-title">สินค้า</h1>

        <div class="product-container">

            <div class="product-card">
                <img src="images/Screenshot 2026-02-19 152546.png" alt="สินค้า 1">
                <div class="product-info">
                    <h2>CSM คาบูโตะ</h2>
                    <div class="stat-number">฿8,999</div>
                    <p>เอาไว้แปลงร่าง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

            <div class="product-card">
                <img src="images/csm-henshin-belt-typhoon-shin-kamen-rider-version-v0-xqouuylo34rb1.jpg" alt="สินค้า 2">
                <div class="product-info">
                    <h2>V2</h2>
                    <div class="stat-number">฿2,499</div>
                    <p>สินค้าที่มีคุณภาพสูง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

            <div class="product-card">
                <img src="images/Screenshot 2026-02-19 153726.png" alt="สินค้า 3">
                <div class="product-info">
                    <h2>หมายเลข 5</h2>
                    <p class="price">฿12,199</p>
                    <p>หากการต่อสู้ถือเป็นบาป ฉันจะปกป้องเอง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

            <div class="product-card">
                <img src="images/Screenshot 2026-02-19 154005.png" alt="สินค้า 4">
                <div class="product-info">
                    <h2>V1</h2>
                    <p class="price">฿8,599</p>
                    <p>แปลงร่างที่มีคุณภาพสูง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

        </div>
    </section>

    <!-- Section สถิติ -->
    <section class="stats-container">
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
    </section>

</main>

</body>
</html>
]
```
```css
[/* ===== Global Reset & Font ===== */
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: "Segoe UI", Arial, sans-serif;
    background-color: #f4f6f9;
    color: #333;
}

/* ===== Navbar ===== */
.navbar {
    background: linear-gradient(90deg, #1e1e1e, #333);
    padding: 15px 0;
}

.menu {
    list-style: none;
    display: flex;
    justify-content: center;
    padding: 0;
    margin: 0;
}

.menu > li {
    margin: 0 20px;
}

.menu-item {
    color: white;
    text-decoration: none;
    padding: 10px 18px;
    border-radius: 6px;
    font-size: 16px;
    transition: 0.3s;
}

.menu-item:hover {
    background-color: #555;
}

.menu-item.active {
    background-color: #ff6600;
    font-weight: bold;
}

/* ===== Section Title ===== */
.section-title {
    font-size: 32px;
    margin-bottom: 30px;
    color: #222;
}

/* ===== Product Grid ===== */
.content {
    padding: 50px 5%;
    text-align: center;
}

.product-container {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 25px;
}

/* ===== Product Card ===== */
.product-card {
    background: #edcccc;
    border-radius: 12px;
    padding-bottom: 20px;
    box-shadow: 0 6px 15px rgba(0,0,0,0.1);
    transition: transform 0.3s ease;
}

.product-card:hover {
    transform: translateY(-8px);
}

.product-card img {
    width: 100%;
    height: 220px;
    object-fit: cover;
}

.product-info {
    padding: 20px;
    text-align: left;
}

.product-info h2 {
    font-size: 20px;
    margin-bottom: 10px;
}

.price {
    font-size: 22px;
    font-weight: bold;
    color: #007bff;
    margin-bottom: 10px;
}

.btn {
    display: inline-block;
    padding: 10px 15px;
    background: #007bff;
    color: white;
    text-decoration: none;
    border-radius: 6px;
    font-size: 14px;
    margin-top: 10px;
}

.btn:hover {
    background: #0056b3;
}

/* ===== Stats Section ===== */
.stats-container {
    display: flex;
    justify-content: space-around;
    max-width: 1200px;
    margin: 60px auto;
    padding: 0 20px;
}

.stat-box {
    flex: 1;
    margin: 0 15px;
    padding: 40px 20px;
    background: white;
    border-radius: 12px;
    text-align: center;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.stat-number {
    font-size: 40px;
    font-weight: bold;
    color: #ff6600;
}

.stat-label {
    font-size: 14px;
    margin-top: 8px;
    letter-spacing: 1px;
    color: #666;
}

/* ===== Responsive ===== */
@media (max-width: 992px) {
    .product-container {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 768px) {
    .product-container {
        grid-template-columns: 1fr;
    }

    .stats-container {
        flex-direction: column;
    }

    .stat-box {
        margin: 15px 0;
    }
}

/* ===== Blog Post Style ===== */
.blog-post {
    max-width: 800px;
    margin: 60px auto;
    padding: 40px;
    background: #ffffff;
    border-radius: 12px;
    box-shadow: 0 8px 20px rgba(0,0,0,0.08);
}

/* ===== Header ===== */
.post-title {
    font-size: 36px;
    color: #222;
    margin-bottom: 10px;
    line-height: 1.3;
}

.post-meta {
    font-size: 14px;
    color: #888;
    margin-bottom: 30px;
}

/* ===== Content ===== */
.post-content p {
    font-size: 18px;
    line-height: 1.8;
    color: #444;
    margin-bottom: 20px;
}

.post-content h2 {
    font-size: 24px;
    color: #ff6600;
    margin-top: 30px;
    margin-bottom: 15px;
}

/* ===== Blockquote ===== */
.post-content blockquote {
    font-size: 18px;
    font-style: italic;
    background: #f9f9f9;
    border-left: 5px solid #ff6600;
    padding: 20px;
    margin: 30px 0;
    color: #555;
}

]

```
[![alt text](image.png)]


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
[<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>เว็บไซต์ตัวอย่าง</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>

<header>
    <nav class="navbar">
        <ul class="menu">
            <li><a href="#" class="menu-item">หน้าแรก</a></li>
            <li><a href="#" class="menu-item active">สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>
</header>

<main>

    <!-- Section สินค้า -->
    <section class="content">
        <h1 class="section-title">สินค้า</h1>

        <div class="product-container">

            <div class="product-card">
                <img src="images/Screenshot 2026-02-19 152546.png" alt="สินค้า 1">
                <div class="product-info">
                    <h2>CSM คาบูโตะ</h2>
                    <div class="stat-number">฿8,999</div>
                    <p>เอาไว้แปลงร่าง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

            <div class="product-card">
                <img src="images/csm-henshin-belt-typhoon-shin-kamen-rider-version-v0-xqouuylo34rb1.jpg" alt="สินค้า 2">
                <div class="product-info">
                    <h2>V2</h2>
                    <div class="stat-number">฿2,499</div>
                    <p>สินค้าที่มีคุณภาพสูง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

            <div class="product-card">
                <img src="images/Screenshot 2026-02-19 153726.png" alt="สินค้า 3">
                <div class="product-info">
                    <h2>หมายเลข 5</h2>
                    <p class="price">฿12,199</p>
                    <p>หากการต่อสู้ถือเป็นบาป ฉันจะปกป้องเอง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

            <div class="product-card">
                <img src="images/Screenshot 2026-02-19 154005.png" alt="สินค้า 4">
                <div class="product-info">
                    <h2>V1</h2>
                    <p class="price">฿8,599</p>
                    <p>แปลงร่างที่มีคุณภาพสูง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

            <div class="product-card">
                <img src="images/Screenshot 2026-02-19 161744.png" alt="สินค้า 1">
                <div class="product-info">
                    <h2>C M S</h2>
                    <div class="price">฿80,000</div>
                    <a href="#" class="btn">สั่งซื้อ</a>
        </div>
    </div>

        </div>
    </section>

    <!-- Section สถิติ -->
    <section class="stats-container">
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
    </section>

</main>

</body>
</html>
]
```
```css
[/* ===== Global Reset & Font ===== */
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: "Segoe UI", Arial, sans-serif;
    background-color: #f4f6f9;
    color: #333;
}

/* ===== Navbar ===== */
.navbar {
    background: linear-gradient(90deg, #1e1e1e, #333);
    padding: 15px 0;
}

.menu {
    list-style: none;
    display: flex;
    justify-content: center;
    padding: 0;
    margin: 0;
}

.menu > li {
    margin: 0 20px;
}

.menu-item {
    color: white;
    text-decoration: none;
    padding: 10px 18px;
    border-radius: 6px;
    font-size: 16px;
    transition: 0.3s;
}

.menu-item:hover {
    background-color: #555;
}

.menu-item.active {
    background-color: #ff6600;
    font-weight: bold;
}

/* ===== Section Title ===== */
.section-title {
    font-size: 28px;
    margin-bottom: 25px;
    color: #222;
}

/* ===== Content ===== */
.content {
    padding: 40px 5%;
    text-align: center;
}

/* ===== Product Grid (เล็กลงจริง) ===== */
.product-container {
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 18px;
}

/* ===== Product Card ===== */
.product-card {
    background: #ffffff;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 4px 10px rgba(0,0,0,0.08);
    transition: transform 0.2s ease;
}

.product-card:hover {
    transform: translateY(-5px);
}

.product-card img {
    width: 100%;
    height: 160px;
    object-fit: cover;
}

/* ===== Product Info ===== */
.product-info {
    padding: 15px;
    text-align: left;
}

.product-info h2 {
    font-size: 16px;
    margin-bottom: 8px;
}

.price {
    font-size: 18px;
    font-weight: bold;
    color: #007bff;
    margin-bottom: 8px;
}

.btn {
    display: inline-block;
    padding: 8px 12px;
    background: #007bff;
    color: white;
    text-decoration: none;
    border-radius: 6px;
    font-size: 13px;
}

.btn:hover {
    background: #0056b3;
}

/* ===== Stats Section ===== */
.stats-container {
    display: flex;
    justify-content: space-around;
    max-width: 1200px;
    margin: 60px auto;
    padding: 0 20px;
}

.stat-box {
    flex: 1;
    margin: 0 15px;
    padding: 40px 20px;
    background: white;
    border-radius: 12px;
    text-align: center;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.stat-number {
    font-size: 36px;
    font-weight: bold;
    color: #ff6600;
}

.stat-label {
    font-size: 14px;
    margin-top: 8px;
    letter-spacing: 1px;
    color: #666;
}

/* ===== Blog Post ===== */
.blog-post {
    max-width: 800px;
    margin: 60px auto;
    padding: 40px;
    background: #ffffff;
    border-radius: 12px;
    box-shadow: 0 8px 20px rgba(0,0,0,0.08);
}

.post-title {
    font-size: 34px;
    margin-bottom: 10px;
}

.post-meta {
    font-size: 14px;
    color: #888;
    margin-bottom: 30px;
}

.post-content p {
    font-size: 17px;
    line-height: 1.8;
    margin-bottom: 20px;
}

.post-content h2 {
    font-size: 22px;
    color: #ff6600;
    margin-top: 25px;
    margin-bottom: 15px;
}

.post-content blockquote {
    font-size: 17px;
    font-style: italic;
    background: #f9f9f9;
    border-left: 5px solid #ff6600;
    padding: 20px;
    margin: 30px 0;
}

/* ===== Responsive ===== */
@media (max-width: 1200px) {
    .product-container {
        grid-template-columns: repeat(4, 1fr);
    }
}

@media (max-width: 992px) {
    .product-container {
        grid-template-columns: repeat(3, 1fr);
    }
}

@media (max-width: 768px) {
    .product-container {
        grid-template-columns: repeat(2, 1fr);
    }

    .stats-container {
        flex-direction: column;
    }

    .stat-box {
        margin: 15px 0;
    }
}

@media (max-width: 480px) {
    .product-container {
        grid-template-columns: 1fr;
    }
}
]
```
[![alt text](image-1.png)]


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
[<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>เว็บไซต์ตัวอย่าง</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>

<header>
    <nav class="navbar">
        <ul class="menu">
            <li><a href="#" class="menu-item">หน้าแรก</a></li>
            <li><a href="#" class="menu-item active">สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>
</header>

<main>

    <!-- Section สินค้า -->
    <section class="content">
        <h1 class="section-title">สินค้า</h1>

        <div class="product-container">

            <div class="product-card">
                <img src="images/Screenshot 2026-02-19 152546.png" alt="สินค้า 1">
                <div class="product-info">
                    <h2>CSM คาบูโตะ</h2>
                    <div class="stat-number">฿8,999</div>
                    <p>เอาไว้แปลงร่าง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

            <div class="product-card">
                <img src="images/csm-henshin-belt-typhoon-shin-kamen-rider-version-v0-xqouuylo34rb1.jpg" alt="สินค้า 2">
                <div class="product-info">
                    <h2>V2</h2>
                    <div class="stat-number">฿2,499</div>
                    <p>สินค้าที่มีคุณภาพสูง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

            <div class="product-card">
                <img src="images/Screenshot 2026-02-19 153726.png" alt="สินค้า 3">
                <div class="product-info">
                    <h2>หมายเลข 5</h2>
                    <p class="price">฿12,199</p>
                    <p>หากการต่อสู้ถือเป็นบาป ฉันจะปกป้องเอง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

            <div class="product-card">
                <img src="images/Screenshot 2026-02-19 154005.png" alt="สินค้า 4">
                <div class="product-info">
                    <h2>V1</h2>
                    <p class="price">฿8,599</p>
                    <p>แปลงร่างที่มีคุณภาพสูง</p>
                    <a href="#" class="btn">เพิ่มลงตะกร้า</a>
                </div>
            </div>

            <div class="product-card">
                <img src="images/Screenshot 2026-02-19 161744.png" alt="สินค้า 1">
                <div class="product-info">
                    <h2>C M S</h2>
                    <div class="price">฿80,000</div>
                    <a href="#" class="btn">สั่งซื้อ</a>
        </div>
    </div>

        </div>
    </section>

    <!-- Section สถิติ -->
    <section class="stats-container">
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
    </section>

</main>

</body>
</html>
]
```
```css
[/* ===== Reset ===== */
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: "Segoe UI", Arial, sans-serif;
    background: #f9f9f9;
    color: #2c2c2c;
}

/* ===== Navbar ===== */
.navbar {
    background: white;
    padding: 18px 0;
    box-shadow: 0 2px 10px rgba(0,0,0,0.05);
}

.menu {
    list-style: none;
    display: flex;
    justify-content: center;
    padding: 0;
    margin: 0;
}

.menu > li {
    margin: 0 25px;
}

.menu-item {
    text-decoration: none;
    color: #444;
    font-size: 15px;
    font-weight: 500;
    transition: 0.3s;
}

.menu-item:hover {
    color: #b08d2f; /* ทองอ่อน */
}

.menu-item.active {
    color: #b08d2f;
    border-bottom: 2px solid #b08d2f;
    padding-bottom: 4px;
}

/* ===== Section Title ===== */
.section-title {
    font-size: 30px;
    margin-bottom: 40px;
    font-weight: 600;
}

/* ===== Content ===== */
.content {
    padding: 70px 8%;
    text-align: center;
}

/* ===== Product Grid ===== */
.product-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
    gap: 30px;
}

/* ===== Product Card ===== */
.product-card {
    background: white;
    border-radius: 14px;
    overflow: hidden;
    box-shadow: 0 8px 25px rgba(0,0,0,0.05);
    transition: 0.3s ease;
}

.product-card:hover {
    transform: translateY(-6px);
}

/* ===== Product Image ===== */
.product-card img {
    width: 100%;
    height: 210px;
    object-fit: cover;
}

/* ===== Product Info ===== */
.product-info {
    padding: 20px;
    text-align: left;
}

.product-info h2 {
    font-size: 17px;
    margin-bottom: 8px;
    font-weight: 600;
}

.price {
    font-size: 18px;
    font-weight: bold;
    color: #b08d2f; /* ทอง */
    margin-bottom: 12px;
}

/* ===== Button ===== */
.btn {
    display: inline-block;
    padding: 8px 14px;
    border: 1px solid #b08d2f;
    color: #b08d2f;
    text-decoration: none;
    border-radius: 25px;
    font-size: 13px;
    transition: 0.3s;
}

.btn:hover {
    background: #b08d2f;
    color: white;
}

/* ===== Stats Section ===== */
.stats-container {
    display: flex;
    justify-content: center;
    gap: 30px;
    margin: 90px auto;
    max-width: 1100px;
}

.stat-box {
    flex: 1;
    background: white;
    padding: 40px 25px;
    border-radius: 14px;
    text-align: center;
    box-shadow: 0 6px 18px rgba(0,0,0,0.05);
}

.stat-number {
    font-size: 36px;
    font-weight: bold;
    color: #b08d2f;
}

.stat-label {
    font-size: 14px;
    margin-top: 8px;
    color: #777;
}

/* ===== Blog Post ===== */
.blog-post {
    max-width: 850px;
    margin: 90px auto;
    padding: 50px;
    background: white;
    border-radius: 16px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.05);
}

.post-title {
    font-size: 32px;
    margin-bottom: 12px;
    font-weight: 600;
}

.post-meta {
    font-size: 14px;
    color: #999;
    margin-bottom: 30px;
}

.post-content p {
    font-size: 16px;
    line-height: 1.8;
    margin-bottom: 20px;
}

.post-content h2 {
    font-size: 20px;
    margin-top: 25px;
    margin-bottom: 10px;
    color: #b08d2f;
}

.post-content blockquote {
    font-size: 16px;
    background: #f5f5f5;
    border-left: 4px solid #b08d2f;
    padding: 20px;
    margin: 25px 0;
    border-radius: 6px;
}

/* ===== Responsive ===== */
@media (max-width: 768px) {
    .stats-container {
        flex-direction: column;
    }
}
]
```
[![alt text](image.png)]

