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
<html>
<head>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <nav>
        <ul>
            <li><a href="#" class="menu-item">หน้าแรก</a></li>
            <li><a href="#" class="menu-item selected">สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>
</body>
</html>]
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![alt text](<สกรีนช็อต 2026-02-24 094000.png>)

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
[วางโค้ดที่นี่  <!DOCTYPE html>
    <html lang="th">
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <title>รายการสินค้า</title>
        <link rel="stylesheet" href="styles.css">
    </head>
    <body>
        <main>
            <h1 style="text-align:center; margin-top:20px;">สินค้า</h1>
            <div class="product-grid">

                <div class="product-card">
                    <img class="product-image" src="product/ปืนเล็ก%20M4.png" alt="ปืนเล็ก M4">
                    <div class="product-info">
                        <h2 class="product-title">ปืนเล็ก M4</h2>
                        <p class="product-price">฿1,599</p>
                        <p class="product-description">ปืนเล็กสมรรถนะสูง น้ำหนักเบา เหมาะสำหรับผู้เริ่มต้น</p>
                        <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
                    </div>
                </div>

                <div class="product-card">
                    <img class="product-image" src="product/ปืนเล็กล%2088.png" alt="ปืนเล็กล 88">
                    <div class="product-info">
                        <h2 class="product-title">ปืนเล็กล 88</h2>
                        <p class="product-price">฿1,899</p>
                        <p class="product-description">ดีไซน์เรียบหรู ระบบแม่นยำ เหมาะสำหรับสะสม</p>
                        <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
                    </div>
                </div>

                <div class="product-card">
                    <img class="product-image" src="product/ปืนพก%2080.png" alt="ปืนพก 80">
                    <div class="product-info">
                        <h2 class="product-title">ปืนพก 80</h2>
                        <p class="product-price">฿2,299</p>
                        <p class="product-description">ขนาดกะทัดรัด จับกระชับ เหมาะสำหรับการใช้งานทั่วไป</p>
                        <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
                    </div>
                </div>

                <div class="product-card">
                    <img class="product-image" src="product/ปืนกลมือ%2086.png" alt="ปืนกลมือ 86">
                    <div class="product-info">
                        <h2 class="product-title">ปืนกลมือ 86</h2>
                        <p class="product-price">฿3,499</p>
                        <p class="product-description">ประสิทธิภาพสูง เหมาะสำหรับการยิงต่อเนื่อง</p>
                        <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
                    </div>
                </div>

            </div>
        </main>
    </body>
    </html>]
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![alt text](<สกรีนช็อต 2026-02-24 122136.png>)
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
    <!DOCTYPE html>
    <html lang="th">
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <title>รายการสินค้า</title>
        <link rel="stylesheet" href="styles.css">
    </head>
    <body>
        <main>
            <h1 style="text-align:center; margin-top:20px;">สินค้า</h1>
            <div class="product-grid">

                <div class="product-card">
                    <img class="product-image" src="product/ปืนเล็ก%20M4.png" alt="ปืนเล็ก M4">
                    <div class="product-info">
                        <h2 class="product-title">ปืนเล็ก M4</h2>
                        <p class="product-price">฿1,599</p>
                        <p class="product-description">ปืนเล็กสมรรถนะสูง น้ำหนักเบา เหมาะสำหรับผู้เริ่มต้น</p>
                        <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
                    </div>
                </div>

                <div class="product-card">
                    <img class="product-image" src="product/ปืนเล็กล%2088.png" alt="ปืนเล็กล 88">
                    <div class="product-info">
                        <h2 class="product-title">ปืนเล็กล 88</h2>
                        <p class="product-price">฿1,899</p>
                        <p class="product-description">ดีไซน์เรียบหรู ระบบแม่นยำ เหมาะสำหรับสะสม</p>
                        <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
                    </div>
                </div>

                <div class="product-card">
                    <img class="product-image" src="product/ปืนพก%2080.png" alt="ปืนพก 80">
                    <div class="product-info">
                        <h2 class="product-title">ปืนพก 80</h2>
                        <p class="product-price">฿2,299</p>
                        <p class="product-description">ขนาดกะทัดรัด จับกระชับ เหมาะสำหรับการใช้งานทั่วไป</p>
                        <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
                    </div>
                </div>

                <div class="product-card">
                    <img class="product-image" src="product/ปืนกลมือ%2086.png" alt="ปืนกลมือ 86">
                    <div class="product-info">
                        <h2 class="product-title">ปืนกลมือ 86</h2>
                        <p class="product-price">฿3,499</p>
                        <p class="product-description">ประสิทธิภาพสูง เหมาะสำหรับการยิงต่อเนื่อง</p>
                        <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
                    </div>
                </div>

            </div>
        </main>
    </body>
    </html>
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
```css
[วางโค้ด CSS ที่นี่]
```/* External stylesheet moved from lab1.html */
nav {
    background-color: #2a9d8f; /* เปลี่ยนสีพื้นหลังของเมนู */
    padding: 15px;
}

nav ul {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
}

nav > ul > li {
    margin: 0 10px;
}

:root {
    --card-min-width: 240px;
    --card-radius: 10px;
    --image-height: 200px;
    --gutter: 20px;
    --font-base: 16px;
    --font-heading: 20px;
    --primary: #007bff;
    --accent: #114B5F;
    --muted: #666666;
    --bg-start: #f4f7fb;
    --bg-mid: #eef2f7;
}

/* Box model reset */
*, *::before, *::after { box-sizing: border-box; }

/* External stylesheet moved from lab1.html */
nav {
    background-color: var(--accent); /* เปลี่ยนสีพื้นหลังของเมนู */
    padding: 15px;
}

nav ul {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
}

nav > ul > li {
    margin: 0 10px;
}

.menu-item {
    color: white;
    text-decoration: none;
    padding: 6px 12px;
    font-size: 0.95rem;
}

.menu-item:hover {
    background-color: rgba(0,0,0,0.12);
    border-radius: 4px;
}

.menu-item.selected {
    background-color: #0b2b3a; /* สีสำหรับรายการที่ถูกเลือก */
    border-radius: 4px;
}

/* Product grid and cards */
.product-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(var(--card-min-width), 1fr));
    gap: var(--gutter);
    padding: calc(var(--gutter) * 1);
    max-width: 1100px;
    margin: 22px auto;
}

.product-card {
    background: #fff;
    border-radius: var(--card-radius);
    overflow: hidden;
    box-shadow: 0 2px 10px rgba(0,0,0,0.06);
    display: flex;
    flex-direction: column;
    min-height: 380px;
}

.product-image {
    width: 100%;
    height: var(--image-height);
    object-fit: cover;
    display: block;
}

.product-info {
    padding: 18px;
    flex: 1 1 auto;
}

.product-title {
    color: #0b2b3a;
    font-size: calc(var(--font-heading) - 2px);
    :root {
        --card-min-width: 260px;
        --card-radius: 12px;
        --image-height: 240px;
        --gutter: 28px;
        --font-base: 18px;
        --font-heading: 24px;
        --primary: #007bff;
        --accent: #114B5F;
        --muted: #666666;
        --bg-start: #f4f7fb;
        --bg-mid: #eef2f7;
    }
    margin: 0 0 8px;
}

.product-price {
    color: var(--primary);
    font-size: 1.15rem;
    font-weight: 800;
        font-size: var(--font-base);
        line-height: 1.6;
    margin: 0 0 10px;
}

.product-description {
    color: var(--muted);
    font-size: 0.95rem;
    margin: 0 0 14px;
    line-height: 1.45;
}
    .product-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(var(--card-min-width), 1fr));
        gap: var(--gutter);
        padding: calc(var(--gutter) * 1.2);
        max-width: 1200px;
        margin: 28px auto;
    }

.product-button {
    display: inline-block;
    background: linear-gradient(90deg, var(--primary), #0056b3);
    color: #fff;
    padding: 10px 14px;
    text-decoration: none;
    border-radius: 6px;
    font-weight: 600;
    .product-card {
        background: #fff;
        border-radius: var(--card-radius);
        overflow: hidden;
        box-shadow: 0 4px 18px rgba(0,0,0,0.08);
        display: flex;
        flex-direction: column;
        min-height: 420px;
        padding-bottom: 6px;
    }
}

.product-button:hover {
    opacity: 0.95;
}

    .product-image {
        width: 100%;
        height: var(--image-height);
        object-fit: cover;
        display: block;
    }
@media (max-width: 480px) {
    .product-image { height: 160px; }
}

    .product-info {
        padding: 22px;
        flex: 1 1 auto;
    }
/* Page-level styling */
html, body {
    height: 100%;
}
body {
    .product-title {
        color: #0b2b3a;
        font-size: var(--font-heading);
        margin: 0 0 10px;
    }
    font-family: 'Kanit', system-ui, -apple-system, 'Segoe UI', Roboto, 'Noto Sans Thai', sans-serif;
    background: linear-gradient(180deg, #f4f7fb 0%, #eef2f7 50%, #f8fafc 100%);
    color: #223;
    margin: 0;
    -webkit-font-smoothing:antialiased;
}
    .product-price {
        color: var(--primary);
        font-size: 1.3rem;
        font-weight: 800;
        margin: 0 0 12px;
    }

main {
    padding-bottom: 40px;
}

h1 {
    .product-description {
        color: var(--muted);
        font-size: 1rem;
        margin: 0 0 16px;
        line-height: 1.55;
    }
    font-weight: 600;
    color: #0b2b3a;
    letter-spacing: 0.4px;
}

/* Card decoration */
.product-card {
    position: relative;
    transition: transform 220ms ease, box-shadow 220ms ease;
    .product-button {
        display: inline-block;
        background: linear-gradient(90deg, var(--primary), #0056b3);
        color: #fff;
        padding: 12px 18px;
        text-decoration: none;
        border-radius: 8px;
        font-weight: 700;
        font-size: 1rem;
    }
}

.product-card:hover {
    transform: translateY(-6px) scale(1.01);
    box-shadow: 0 10px 30px rgba(12,35,55,0.12);
}

.price-badge {
    position: absolute;
    right: 12px;
    top: 12px;
    background: linear-gradient(90deg,#ff8a65,#ff6b6b);
    color: #fff;
    padding: 6px 10px;
    border-radius: 999px;
    font-weight: 700;
    font-size: 13px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.08);
}

.product-info {
    display: flex;
    flex-direction: column;
}

.product-info .product-button {
    margin-top: auto;
}

.product-button {
    box-shadow: 0 6px 18px rgba(3,87,255,0.08);
    transition: transform 160ms ease, box-shadow 160ms ease;
}

.product-button:active {
    transform: translateY(1px) scale(0.997);
}

.product-title { display:block; }

.product-image { background-color: #f0f0f0; }

/* Subtle captions */
.product-description { opacity: 0.95; }

/* small screens spacing */
@media (max-width: 720px) {
    .product-grid { padding: 12px; gap: 14px; }
}



[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
[](#การทดลองที่-5-การจัดการข้อความและฟอนต์)
![alt text](<สกรีนช็อต 2026-02-24 123436.png>)

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
```
    <section class="stats-container" aria-label="สถิติ">
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

    <article class="blog-post">
      <header class="post-header">
        <h2 class="post-title">การใช้อาวุธปืนอย่างปลอดภัย</h2>
        <div class="post-meta">โพสต์เมื่อ 24 กุมภาพันธ์ 2026 | โดย ผู้เชี่ยวชาญด้านความปลอดภัย</div>
      </header>
      <div class="post-content">
        <p>การใช้อาวุธปืนเป็นสิ่งที่ต้องการความรับผิดชอบสูงสุด และความรู้เกี่ยวกับความปลอดภัยเป็นพื้นฐานที่สำคัญที่สุด บทความนี้จะนำเสนอแนวทางและเคล็ดลับที่ช่วยให้ผู้ใช้อาวุธปืนสามารถใช้ได้อย่างปลอดภัยและรับผิดชอบต่อสังคม</p>
        
        <h3>1. แนวทางการเก็บรักษาปืนให้ถูกต้องตามกฎหมาย</h3>
        <p>การเก็บรักษาอาวุธปืนให้ถูกต้องตามกฎหมายเป็นข้อกำหนดที่ต้องปฏิบัติอย่างเคร่งครัด ประเทศไทยและประเทศอื่น ๆ มีกฎหมายเข้มงวดเกี่ยวกับการจัดเก็บปืน ดังนี้:</p>
        <ul style="margin-left: 20px;">
          <li>ต้องเก็บปืนในตู้เหล็กล็อกที่มั่นคง หรือที่ปลอดภัยตามข้อกำหนด</li>
          <li>เก็บลูกกระสุนแยกต่างหากจากอาวุธ และเก็บในสถานที่ที่ปลอดภัย</li>
          <li>ห้ามเก็บไว้ในที่สูงไม่เกินความสูงที่เด็กเข้าถึงได้</li>
          <li>ต้องมีใบอนุญาตและทะเบียนที่ถูกต้องตามกฎหมาย</li>
          <li>ต้องเก็บด้วยแม่กุญแจแยกต่างหากจากปืน</li>
        </ul>
        
        <h3>2. ความรู้พื้นฐานสำหรับผู้เริ่มต้นกีฬายิงปืน</h3>
        <p>ผู้เริ่มต้นต้องเรียนรู้พื้นฐานที่สำคัญเพื่อให้มีทักษะและความปลอดภัยสูงสุด:</p>
        <ul style="margin-left: 20px;">
          <li><strong>ท่าทางที่ถูกต้อง:</strong> การยืน การถือปืนพลาด และการจัดตำแหน่งรางเหลือบ</li>
          <li><strong>การหายใจ:</strong> เทคนิคการหายใจที่ถูกต้องในขณะยิง</li>
          <li><strong>การรักษาเสถียรภาพ:</strong> การควบคุมความสั่นไหว และการออกแรงที่สม่ำเสมอ</li>
          <li><strong>การกดไ트้เรียร์:</strong> เทคนิคการกดไทร์กเกอร์อย่างราบรื่นเพื่อความแม่นยำ</li>
          <li><strong>ความรู้เบื้องต้นเกี่ยวกับกลไก:</strong> การทำความสะอาด การบำรุงรักษา และการตรวจสอบ</li>
        </ul>
        
        <h3>3. การเตรียมตัวก่อนเข้าสนามยิงปืน</h3>
        <p>การเตรียมตัวที่เหมาะสมก่อนเข้าสนามยิงปืนเป็นตัวกำหนดความสำเร็จและความปลอดภัย:</p>
        <ul style="margin-left: 20px;">
          <li>ตรวจสอบอาวุธและหัวลูกกระสุนว่าอยู่ในสภาพที่ดี ไม่มีสนิม หรือความเสียหาย</li>
          <li>นำเสนอบัตรประจำตัว ใบอนุญาต และเอกสารที่เกี่ยวข้องอย่างครบถ้วน</li>
          <li>สวมใส่อุปกรณ์ป้องกัน เช่น แว่นตาป้องกัน หูฟังลดเสียง และเสื้อผ้าที่เหมาะสม</li>
          <li>ทำความคุ้นเคยกับสนามยิง และเรียนรู้กฎของสนามนั้น ๆ</li>
          <li>วางแผนการฝึกซ้อมและตั้งเป้าหมายที่มีความเป็นไปได้</li>
        </ul>
        
        <h3>4. ความสำคัญของการอบรมและใบอนุญาตอย่างถูกต้อง</h3>
        <p>การอบรมและการได้รับใบอนุญาตอย่างถูกต้องเป็นสิ่งที่ไม่สามารถละเลยได้:</p>
        <ul style="margin-left: 20px;">
          <li>ต้องผ่านหลักสูตรการอบรมที่ได้รับอนุมัติจากหน่วยงานที่เกี่ยวข้อง</li>
          <li>ต้องสอบผ่านการประเมินความรู้และทักษะ</li>
          <li>ต้องอบรมด้านกฎหมาย จริยธรรม และความปลอดภัย</li>
          <li>ต้องมีใบอนุญาตถูกต้องก่อนมีครอบครองหรือใช้อาวุธปืน</li>
          <li>ต้องต่ออายุใบอนุญาตตามกำหนดเวลา และเข้าอบรมเพิ่มเติมตามความจำเป็น</li>
        </ul>
        
        <h3>5. จรรยาบรรณของผู้ครอบครองอาวุธปืนที่ดี</h3>
        <p>ผู้ที่ครอบครองอาวุธปืนต้องปฏิบัติตามจรรยาบรรณเพื่อรักษาความปลอดภัยและความเชื่อถือจากสังคม:</p>
        <ul style="margin-left: 20px;">
          <li>ปฏิบัติตามกฎหมายและข้อบังคับทั้งหมด</li>
          <li>ใช้อาวุธปืนด้วยความหมั่นไตร่ตรวจสอบและมีความรับผิดชอบ</li>
          <li>เก็บอาวุธให้มั่นคง ห่างจากเด็กและผู้ที่ไม่มีสิทธิ์</li>
          <li>อบรมครอบครัวและผู้ใช้อาวุธเพื่อให้เข้าใจความปลอดภัย</li>
          <li>ไม่ใช้อาวุธในสถานการณ์ที่ไม่เหมาะสม หรือเพื่อการกระทำที่ผิดกฎหมาย</li>
          <li>ร่วมมือกับการบังคับใช้กฎหมายและหน่วยงานที่เกี่ยวข้อง</li>
          <li>ส่งเสริมวัฒนธรรมของความปลอดภัยและการใช้อาวุธที่ถูกต้อง</li>
        </ul>
        
        <p><strong>บทสรุป:</strong> การใช้อาวุธปืนอย่างปลอดภัยเป็นความรับผิดชอบที่ต้องถือว่าเป็นสิ่งสำคัญที่สุด ผู้ใช้อาวุธปืนต้องมีความรู้ ทักษะ และจริยธรรมที่ดี พร้อมทั้งปฏิบัติตามกฎหมายและข้อบังคับที่กำหนดไว้ การฝึกซ้อมอย่างสม่ำเสมอ การรักษาป้องกันตัวเอง และการมีจิตสำนึกเกี่ยวกับความปลอดภัยจะเป็นตัวช่วยที่สำคัญในการลดอุบัติเหตุและความเสียหาย</p>
      </div>
    </article>

```css
[วางโค้ด CSS ที่นี่]
```nav {
    background-color: #2a9d8f; /* เปลี่ยนสีพื้นหลังของเมนู */
    padding: 15px;
}

nav ul {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
}

nav > ul > li {
    margin: 0 10px;
}

:root {
    --card-min-width: 240px;
    --card-radius: 10px;
    --image-height: 200px;
    --gutter: 20px;
    --font-base: 16px;
    --font-heading: 20px;
    --primary: #007bff;
    --accent: #114B5F;
    --muted: #666666;
    --bg-start: #f4f7fb;
    --bg-mid: #eef2f7;
}

/* Box model reset */
*, *::before, *::after { box-sizing: border-box; }

/* External stylesheet moved from lab1.html */
nav {
    background-color: var(--accent); /* เปลี่ยนสีพื้นหลังของเมนู */
    padding: 15px;
}

nav ul {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
}

nav > ul > li {
    margin: 0 10px;
}

.menu-item {
    color: white;
    text-decoration: none;
    padding: 6px 12px;
    font-size: 0.95rem;
}

.menu-item:hover {
    background-color: rgba(0,0,0,0.12);
    border-radius: 4px;
}

.menu-item.selected {
    background-color: #0b2b3a; /* สีสำหรับรายการที่ถูกเลือก */
    border-radius: 4px;
}

/* Product grid and cards */
.product-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(var(--card-min-width), 1fr));
    gap: var(--gutter);
    padding: calc(var(--gutter) * 1);
    max-width: 1100px;
    margin: 22px auto;
}

.product-card {
    background: #fff;
    border-radius: var(--card-radius);
    overflow: hidden;
    box-shadow: 0 2px 10px rgba(0,0,0,0.06);
    display: flex;
    flex-direction: column;
    min-height: 380px;
}

.product-image {
    width: 100%;
    height: var(--image-height);
    object-fit: cover;
    display: block;
}

.product-info {
    padding: 18px;
    flex: 1 1 auto;
}

.product-title {
    color: #0b2b3a;
    font-size: calc(var(--font-heading) - 2px);
    :root {
        --card-min-width: 260px;
        --card-radius: 12px;
        --image-height: 240px;
        --gutter: 28px;
        --font-base: 18px;
        --font-heading: 24px;
        --primary: #007bff;
        --accent: #114B5F;
        --muted: #666666;
        --bg-start: #f4f7fb;
        --bg-mid: #eef2f7;
    }
    margin: 0 0 8px;
}

.product-price {
    color: var(--primary);
    font-size: 1.15rem;
    font-weight: 800;
        font-size: var(--font-base);
        line-height: 1.6;
    margin: 0 0 10px;
}

.product-description {
    color: var(--muted);
    font-size: 0.95rem;
    margin: 0 0 14px;
    line-height: 1.45;
}
    .product-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(var(--card-min-width), 1fr));
        gap: var(--gutter);
        padding: calc(var(--gutter) * 1.2);
        max-width: 1200px;
        margin: 28px auto;
    }

.product-button {
    display: inline-block;
    background: linear-gradient(90deg, var(--primary), #0056b3);
    color: #fff;
    padding: 10px 14px;
    text-decoration: none;
    border-radius: 6px;
    font-weight: 600;
    .product-card {
        background: #fff;
        border-radius: var(--card-radius);
        overflow: hidden;
        box-shadow: 0 4px 18px rgba(0,0,0,0.08);
        display: flex;
        flex-direction: column;
        min-height: 420px;
        padding-bottom: 6px;
    }
}

.product-button:hover {
    opacity: 0.95;
}

    .product-image {
        width: 100%;
        height: var(--image-height);
        object-fit: cover;
        display: block;
    }
@media (max-width: 480px) {
    .product-image { height: 160px; }
}

    .product-info {
        padding: 22px;
        flex: 1 1 auto;
    }
/* Page-level styling */
html, body {
    height: 100%;
}
body {
    .product-title {
        color: #0b2b3a;
        font-size: var(--font-heading);
        margin: 0 0 10px;
    }
    font-family: 'Kanit', system-ui, -apple-system, 'Segoe UI', Roboto, 'Noto Sans Thai', sans-serif;
    background: linear-gradient(180deg, #f4f7fb 0%, #eef2f7 50%, #f8fafc 100%);
    color: #223;
    margin: 0;
    -webkit-font-smoothing:antialiased;
}
    .product-price {
        color: var(--primary);
        font-size: 1.3rem;
        font-weight: 800;
        margin: 0 0 12px;
    }

main {
    padding-bottom: 40px;
}

h1 {
    .product-description {
        color: var(--muted);
        font-size: 1rem;
        margin: 0 0 16px;
        line-height: 1.55;
    }
    font-weight: 600;
    color: #0b2b3a;
    letter-spacing: 0.4px;
}

/* Card decoration */
.product-card {
    position: relative;
    transition: transform 220ms ease, box-shadow 220ms ease;
    .product-button {
        display: inline-block;
        background: linear-gradient(90deg, var(--primary), #0056b3);
        color: #fff;
        padding: 12px 18px;
        text-decoration: none;
        border-radius: 8px;
        font-weight: 700;
        font-size: 1rem;
    }
}

.product-card:hover {
    transform: translateY(-6px) scale(1.01);
    box-shadow: 0 10px 30px rgba(12,35,55,0.12);
}

.price-badge {
    position: absolute;
    right: 12px;
    top: 12px;
    background: linear-gradient(90deg,#ff8a65,#ff6b6b);
    color: #fff;
    padding: 6px 10px;
    border-radius: 999px;
    font-weight: 700;
    font-size: 13px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.08);
}

.product-info {
    display: flex;
    flex-direction: column;
}

.product-info .product-button {
    margin-top: auto;
}

.product-button {
    box-shadow: 0 6px 18px rgba(3,87,255,0.08);
    transition: transform 160ms ease, box-shadow 160ms ease;
}

.product-button:active {
    transform: translateY(1px) scale(0.997);
}

.product-title { display:block; }

.product-image { background-color: #f0f0f0; }

/* Subtle captions */
.product-description { opacity: 0.95; }

/* small screens spacing */
@media (max-width: 720px) {
    .product-grid { padding: 12px; gap: 14px; }
}

/* Stats boxes */
.stats-container {
    display: flex;
    justify-content: space-around;
    max-width: 1200px;
    margin: 2.4rem auto;
    padding: 0 1rem;
    gap: 18px;
}
.stat-box {
    flex: 1 1 240px;
    background: #fff;
    border-radius: 12px;
    padding: 1.6rem;
    text-align: center;
    box-shadow: 0 6px 20px rgba(10,30,60,0.06);
}
.stat-number {
    font-size: 2.2rem;
    font-weight: 800;
    color: var(--primary);
    margin-bottom: 0.4rem;
}
.stat-label {
    font-size: 0.95rem;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 1px;
}

/* Blog/article styles */
.blog-post {
    max-width: 1000px;
    margin: 2.2rem auto;
    padding: 0 1rem;
}
.post-header { text-align: center; margin-bottom: 1.6rem; }
.post-title { font-size: 2.4rem; color: #0b2b3a; margin-bottom: 0.4rem; line-height: 1.15; }
.post-meta { color: var(--muted); font-size: 0.95rem; text-transform: uppercase; letter-spacing: 1px; }
.post-content { font-size: 1.05rem; line-height: 1.8; color: #333; }
.post-content p { margin-bottom: 1.2rem; }
.post-content h2 { font-size: 1.6rem; color: #0b2b3a; margin: 1.6rem 0 0.8rem; }
blockquote { font-style: italic; border-left: 4px solid var(--primary); margin: 1rem 0; padding-left: 1rem; color: #556; }

@media (max-width: 768px) {
    .stat-number { font-size: 1.8rem; }
    .post-title { font-size: 1.8rem; }
}



[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
c:\Users\teeta\OneDrive\รูปภาพ\Screenshots\สกรีนช็อต 2026-02-24 130138.png
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
``` <div class="product-card">
        <div class="price-badge">แนะนำ</div>
        <img class="product-image" src="product/สินค้าตัวอย่าง/ปืนกลเบา%20แบบ%2083.png" alt="ปืนกลเบา 83">
        <div class="product-info">
          <h2 class="product-title">ปืนกลเบา 83</h2>
          <p class="product-price">฿2,799</p>
          <p class="product-description">น้ำหนักเบา สำหรับการแบกพกง่าย ประหยัดหลวงเพื่อนหนึ่งหมวก</p>
          <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
      </div>

      <div class="product-card">
        <div class="price-badge">ขายดี</div>
        <img class="product-image" src="product/สินค้าตัวอย่าง/ปืนเล็กกล%20เอฟ.เอ็น.มินิมิ.png" alt="ปืนเล็กกล เอฟ.เอ็น.มินิมิ">
        <div class="product-info">
          <h2 class="product-title">ปืนเล็กกล FN Minimi</h2>
          <p class="product-price">฿3,199</p>
          <p class="product-description">ระบบอัตโนมัติรุ่นใหม่ ความแม่นยำสูง เหมาะสำหรับหน่วยโจมตี</p>
          <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
      </div>

      <div class="product-card">
        <div class="price-badge">ใหม่</div>
        <img class="product-image" src="product/สินค้าตัวอย่าง/ปืนเล็กกล%20แบบ%2005.png" alt="ปืนเล็กกล 05">
        <div class="product-info">
          <h2 class="product-title">ปืนเล็กกล 05</h2>
          <p class="product-price">฿2,999</p>
          <p class="product-description">ดีไซน์ทันสมัย ควบคุมง่าย เหมาะสำหรับการฝึกซ้อม</p>
          <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
      </div>
    </div>
```css
[วางโค้ด CSS ที่นี่]
```:root {
    --card-min-width: 170px;
    --card-radius: 12px;
    --image-height: 120px;
    --gutter: 14px;
    --font-base: 13px;
    --font-heading: 16px;
    --primary: #007bff;
    --accent: #114B5F;
    --muted: #666666;
    --bg-start: #f4f7fb;
    --bg-mid: #eef2f7;
}

[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![alt text](<สกรีนช็อต 2026-02-24 132304.png>)

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
```!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>แดชบอร์ด</title>
  <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;600;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="dashboard.css">
</head>
<body>
  <div class="dashboard">
    <header class="header">
      <div class="header-left">
        <h1 class="header-title">📊 แดชบอร์ด</h1>
      </div>
      <nav class="header-nav">
        <button class="nav-button">👤 โปรไฟล์</button>
        <button class="nav-button logout-btn">🚪 ออกจากระบบ</button>
      </nav>
    </header>

    <aside class="sidebar">
      <div class="sidebar-logo">
        <h2>MyStore</h2>
      </div>
      <nav class="sidebar-nav">
        <ul>
          <li><a href="#" class="sidebar-link active">🏠 หน้าแรก</a></li>
          <li><a href="#" class="sidebar-link">📈 รายงาน</a></li>
          <li><a href="#" class="sidebar-link">⚙️ การตั้งค่า</a></li>
          <li><a href="#" class="sidebar-link">👥 ลูกค้า</a></li>
          <li><a href="#" class="sidebar-link">📦 สินค้า</a></li>
        </ul>
      </nav>
    </aside>

    <main class="main-content">
      <section class="stats-grid">
        <div class="stat-card">
          <div class="stat-icon">💰</div>
          <div class="stat-info">
            <h3 class="stat-title">ยอดขายรวม</h3>
            <p class="stat-value">฿150,000</p>
            <p class="stat-change">📈 +12% จากเดือนที่แล้ว</p>
          </div>
        </div>

        <div class="stat-card">
          <div class="stat-icon">📋</div>
          <div class="stat-info">
            <h3 class="stat-title">จำนวนออเดอร์</h3>
            <p class="stat-value">1,234</p>
            <p class="stat-change">📊 +8% จากเดือนที่แล้ว</p>
          </div>
        </div>

        <div class="stat-card">
          <div class="stat-icon">👤</div>
          <div class="stat-info">
            <h3 class="stat-title">ลูกค้าใหม่</h3>
            <p class="stat-value">45</p>
            <p class="stat-change">📍 สัปดาห์นี้</p>
          </div>
        </div>

        <div class="stat-card">
          <div class="stat-icon">⭐</div>
          <div class="stat-info">
            <h3 class="stat-title">ความพึงพอใจ</h3>
            <p class="stat-value">4.8/5</p>
            <p class="stat-change">⬆️ +0.3 จากเดือนที่แล้ว</p>
          </div>
        </div>
      </section>

      <section class="chart-section">
        <h2 class="section-title">วิเคราะห์ผลขาย</h2>
        
        <div class="chart-container">
          <div class="chart-card">
            <h3 class="chart-title">กราฟแสดงยอดขาย</h3>
            <div class="chart-placeholder">
              <div class="chart-bar" style="height: 60%; background: #007bff;"></div>
              <div class="chart-bar" style="height: 75%; background: #28a745;"></div>
              <div class="chart-bar" style="height: 55%; background: #ffc107;"></div>
              <div class="chart-bar" style="height: 80%; background: #17a2b8;"></div>
              <div class="chart-bar" style="height: 70%; background: #007bff;"></div>
              <div class="chart-bar" style="height: 85%; background: #28a745;"></div>
            </div>
            <p class="chart-footer">มกราคม - มิถุนายน 2026</p>
          </div>

          <div class="chart-card">
            <h3 class="chart-title">สัดส่วนสินค้าขายดี</h3>
            <div class="pie-chart">
              <div class="pie-segment" style="background: #007bff; width: 40%; border-radius: 999px 0 0 999px;">35%</div>
              <div class="pie-segment" style="background: #28a745;">30%</div>
              <div class="pie-segment" style="background: #ffc107;">20%</div>
              <div class="pie-segment" style="background: #ff6b6b; border-radius: 0 999px 999px 0;">15%</div>
            </div>
            <div class="pie-legend">
              <div class="legend-item"><span class="legend-color" style="background: #007bff;"></span>ปืนเล็ก (35%)</div>
              <div class="legend-item"><span class="legend-color" style="background: #28a745;"></span>ปืนกล (30%)</div>
              <div class="legend-item"><span class="legend-color" style="background: #ffc107;"></span>ปืนพก (20%)</div>
              <div class="legend-item"><span class="legend-color" style="background: #ff6b6b;"></span>อื่นๆ (15%)</div>
            </div>
          </div>
        </div>
      </section>

      <section class="recent-orders">
        <h2 class="section-title">ออเดอร์ล่าสุด</h2>
        <div class="orders-table">
          <div class="table-header">
            <div class="table-cell">สั่งซื้อ ID</div>
            <div class="table-cell">ลูกค้า</div>
            <div class="table-cell">ยอด</div>
            <div class="table-cell">สถานะ</div>
          </div>
          <div class="table-row">
            <div class="table-cell">#ORD-001</div>
            <div class="table-cell">สมชาย จันทร์</div>
            <div class="table-cell">฿3,500</div>
            <div class="table-cell"><span class="badge successful">✓ สำเร็จ</span></div>
          </div>
          <div class="table-row">
            <div class="table-cell">#ORD-002</div>
            <div class="table-cell">ศิริวรรณ ดำรงค์</div>
            <div class="table-cell">฿2,800</div>
            <div class="table-cell"><span class="badge pending">⏳ รอดำเนิน</span></div>
          </div>
          <div class="table-row">
            <div class="table-cell">#ORD-003</div>
            <div class="table-cell">อมร สุขสวัสดิ์</div>
            <div class="table-cell">฿4,200</div>
            <div class="table-cell"><span class="badge successful">✓ สำเร็จ</span></div>
          </div>
          <div class="table-row">
            <div class="table-cell">#ORD-004</div>
            <div class="table-cell">สาธิต บุญญะ</div>
            <div class="table-cell">฿1,950</div>
            <div class="table-cell"><span class="badge pending">⏳ รอดำเนิน</span></div>
          </div>
        </div>
      </section>
    </main>
  </div>
</body>
</html>

```css
[วางโค้ด CSS ที่นี่]
```:root {
    --primary: #007bff;
    --success: #28a745;
    --warning: #ffc107;
    --danger: #ff6b6b;
    --info: #17a2b8;
    --accent: #114B5F;
    --dark: #2c3e50;
    --light: #f5f7fa;
    --muted: #666666;
    --border: #e0e0e0;
    --shadow: 0 2px 8px rgba(0,0,0,0.08);
    --shadow-lg: 0 8px 24px rgba(0,0,0,0.12);
}

/* Reset & Base Styles */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html, body {
    height: 100%;
    width: 100%;
}

body {
    font-family: 'Kanit', system-ui, -apple-system, sans-serif;
    background: var(--light);
    color: #333;
    -webkit-font-smoothing: antialiased;
}

/* Dashboard Grid Layout */
.dashboard {
    display: grid;
    grid-template-areas: 
        "sidebar header"
        "sidebar main";
    grid-template-columns: 250px 1fr;
    grid-template-rows: auto 1fr;
    min-height: 100vh;
    gap: 0;
}

/* Header */
.header {
    grid-area: header;
    background: white;
    padding: 1.2rem 1.5rem;
    box-shadow: var(--shadow);
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 2px solid var(--light);
    position: sticky;
    top: 0;
    z-index: 100;
}

.header-left {
    display: flex;
    align-items: center;
}

.header-title {
    font-size: 1.8rem;
    color: var(--dark);
    font-weight: 700;
    letter-spacing: -0.5px;
}

.header-nav {
    display: flex;
    gap: 10px;
}

.nav-button {
    background: white;
    border: 1px solid var(--border);
    padding: 8px 16px;
    border-radius: 6px;
    cursor: pointer;
    font-family: 'Kanit', sans-serif;
    font-size: 0.9rem;
    color: #333;
    transition: all 200ms ease;
}

.nav-button:hover {
    background: var(--light);
    border-color: var(--primary);
    color: var(--primary);
    transform: translateY(-2px);
}

.logout-btn:hover {
    border-color: var(--danger);
    color: var(--danger);
}

/* Sidebar */
.sidebar {
    grid-area: sidebar;
    background: linear-gradient(180deg, var(--dark) 0%, #1a252f 100%);
    color: white;
    padding: 1.5rem 1rem;
    overflow-y: auto;
}

.sidebar-logo {
    margin-bottom: 2rem;
    padding-bottom: 1.5rem;
    border-bottom: 1px solid rgba(255,255,255,0.1);
}

.sidebar-logo h2 {
    font-size: 1.5rem;
    font-weight: 700;
    letter-spacing: 1px;
}

.sidebar-nav ul {
    list-style: none;
}

.sidebar-nav li {
    margin-bottom: 8px;
}

.sidebar-link {
    display: block;
    padding: 12px 14px;
    color: rgba(255,255,255,0.8);
    text-decoration: none;
    border-radius: 6px;
    transition: all 200ms ease;
    font-size: 0.95rem;
}

.sidebar-link:hover {
    background: rgba(255,255,255,0.1);
    color: white;
    padding-left: 18px;
}

.sidebar-link.active {
    background: var(--primary);
    color: white;
    font-weight: 600;
    box-shadow: 0 4px 12px rgba(0,123,255,0.3);
}

/* Main Content */
.main-content {
    grid-area: main;
    padding: 2rem;
    overflow-y: auto;
}

/* Stats Grid */
.stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 1.5rem;
    margin-bottom: 2.5rem;
}

.stat-card {
    background: white;
    padding: 1.5rem;
    border-radius: 12px;
    box-shadow: var(--shadow);
    display: flex;
    gap: 1.2rem;
    align-items: flex-start;
    transition: all 300ms ease;
    border: 1px solid rgba(0,0,0,0.05);
}

.stat-card:hover {
    transform: translateY(-4px);
    box-shadow: var(--shadow-lg);
    border-color: var(--primary);
}

.stat-icon {
    font-size: 2.5rem;
    flex-shrink: 0;
}

.stat-info {
    flex: 1;
}

.stat-title {
    font-size: 0.9rem;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 0.5px;
    margin-bottom: 0.5rem;
    font-weight: 500;
}

.stat-value {
    font-size: 1.8rem;
    font-weight: 700;
    color: var(--dark);
    margin-bottom: 0.5rem;
}

.stat-change {
    font-size: 0.85rem;
    color: var(--success);
    font-weight: 500;
}

/* Section Title */
.section-title {
    font-size: 1.4rem;
    color: var(--dark);
    margin-bottom: 1.5rem;
    font-weight: 700;
    padding-bottom: 10px;
    border-bottom: 2px solid var(--primary);
    display: inline-block;
}

/* Chart Section */
.chart-section {
    margin-bottom: 2.5rem;
}

.chart-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: 1.5rem;
}

.chart-card {
    background: white;
    padding: 1.8rem;
    border-radius: 12px;
    box-shadow: var(--shadow);
    border: 1px solid rgba(0,0,0,0.05);
    transition: all 300ms ease;
}

.chart-card:hover {
    box-shadow: var(--shadow-lg);
    border-color: var(--primary);
}

.chart-title {
    font-size: 1.1rem;
    color: var(--dark);
    margin-bottom: 1.5rem;
    font-weight: 600;
}

/* Chart Placeholder */
.chart-placeholder {
    display: flex;
    align-items: flex-end;
    justify-content: space-around;
    height: 200px;
    gap: 10px;
    margin-bottom: 1rem;
    padding: 1rem 0;
    border-radius: 8px;
    background: linear-gradient(180deg, rgba(0,123,255,0.05) 0%, transparent 100%);
}

.chart-bar {
    width: 12%;
    border-radius: 4px 4px 0 0;
    transition: all 300ms ease;
    cursor: pointer;
    opacity: 0.8;
}

.chart-bar:hover {
    opacity: 1;
    transform: scaleY(1.05);
}

.chart-footer {
    text-align: center;
    color: var(--muted);
    font-size: 0.85rem;
}

/* Pie Chart */
.pie-chart {
    display: flex;
    height: 120px;
    margin-bottom: 1.5rem;
    border-radius: 8px;
    overflow: hidden;
}

.pie-segment {
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-weight: 600;
    font-size: 0.9rem;
    transition: all 300ms ease;
    cursor: pointer;
}

.pie-segment:hover {
    filter: brightness(1.1);
    flex-grow: 0.2;
}

/* Pie Legend */
.pie-legend {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 0.8rem;
}

.legend-item {
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 0.9rem;
    color: var(--muted);
}

.legend-color {
    width: 12px;
    height: 12px;
    border-radius: 3px;
    flex-shrink: 0;
}

/* Recent Orders */
.recent-orders {
    margin-top: 2.5rem;
}

.orders-table {
    background: white;
    border-radius: 12px;
    box-shadow: var(--shadow);
    border: 1px solid rgba(0,0,0,0.05);
    overflow: hidden;
}

.table-header {
    display: grid;
    grid-template-columns: 1fr 1.5fr 1fr 1.2fr;
    background: linear-gradient(90deg, var(--primary) 0%, #0056b3 100%);
    color: white;
    padding: 1.2rem;
    font-weight: 600;
    border-bottom: 2px solid var(--border);
}

.table-row {
    display: grid;
    grid-template-columns: 1fr 1.5fr 1fr 1.2fr;
    padding: 1.2rem;
    border-bottom: 1px solid var(--border);
    align-items: center;
    transition: all 200ms ease;
}

.table-row:hover {
    background: rgba(0,123,255,0.02);
}

.table-row:last-child {
    border-bottom: none;
}

.table-cell {
    font-size: 0.95rem;
    color: #333;
}

.table-header .table-cell {
    color: white;
    font-size: 0.9rem;
    text-transform: uppercase;
    letter-spacing: 0.5px;
}

/* Status Badges */
.badge {
    display: inline-block;
    padding: 6px 12px;
    border-radius: 6px;
    font-size: 0.85rem;
    font-weight: 600;
    text-align: center;
}

.badge.successful {
    background: rgba(40,167,69,0.15);
    color: var(--success);
}

.badge.pending {
    background: rgba(255,193,7,0.15);
    color: #ff9800;
}

.badge.failed {
    background: rgba(255,107,107,0.15);
    color: var(--danger);
}

/* Responsive Design */
@media (max-width: 1024px) {
    .dashboard {
        grid-template-columns: 200px 1fr;
    }

    .sidebar {
        padding: 1rem 0.5rem;
    }

    .stat-title {
        font-size: 0.8rem;
    }

    .stat-value {
        font-size: 1.5rem;
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
        display: none;
    }

    .header {
        flex-direction: column;
        gap: 1rem;
    }

    .header-title {
        font-size: 1.5rem;
    }

    .header-nav {
        width: 100%;
    }

    .nav-button {
        flex: 1;
    }

    .stats-grid {
        grid-template-columns: 1fr;
    }

    .stat-card {
        flex-direction: row;
    }

    .chart-container {
        grid-template-columns: 1fr;
    }

    .table-header,
    .table-row {
        grid-template-columns: 1fr 1fr;
        gap: 1rem;
    }

    .table-cell:nth-child(3),
    .table-header .table-cell:nth-child(3) {
        display: none;
    }

    .main-content {
        padding: 1rem;
    }
}

@media (max-width: 480px) {
    .header-title {
        font-size: 1.2rem;
    }

    .nav-button {
        padding: 6px 12px;
        font-size: 0.8rem;
    }

    .stats-grid {
        gap: 1rem;
    }

    .stat-card {
        padding: 1rem;
    }

    .stat-icon {
        font-size: 2rem;
    }

    .stat-value {
        font-size: 1.3rem;
    }

    .chart-card {
        padding: 1rem;
    }

    .pie-legend {
        grid-template-columns: 1fr;
    }

    .main-content {
        padding: 0.8rem;
    }
}

/* Scrollbar Styling */
::-webkit-scrollbar {
    width: 8px;
    height: 8px;
}

::-webkit-scrollbar-track {
    background: var(--light);
}

::-webkit-scrollbar-thumb {
    background: var(--border);
    border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
    background: var(--muted);
}

[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]

![alt text](<สกรีนช็อต 2026-02-24 132717.png>)