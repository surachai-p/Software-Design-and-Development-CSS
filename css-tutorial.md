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
    <title>Menu</title>
    <link rel="stylesheet" href="style.css">
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
]
```
[![alt text](การทดลองที่2.png)]


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
<html>
<head>
    <title>Product Card</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

<div class="product-container">

    <div class="product-card">
        <img src="รูปที่1.png" class="product-image">
        <div class="product-info">
            <h2 class="product-title">สินค้า1</h2>
            <p class="product-price">฿80</p>
            <p class="product-description">อร่อย หอม มัน</p>
            <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
    </div>

    <div class="product-card">
        <img src="รูปที่2.png" class="product-image">
        <div class="product-info">
            <h2 class="product-title">สินค้า2</h2>
            <p class="product-price">฿85</p>
            <p class="product-description">หอม อร่อย ถูกใจ</p>
            <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
    </div>

    <div class="product-card">
        <img src="รูปที่3.png" class="product-image">
        <div class="product-info">
            <h2 class="product-title">สินค้า3</h2>
            <p class="product-price">฿80</p>
            <p class="product-description">ราคาประหยัด คุ้มค่า</p>
            <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
    </div>

    <div class="product-card">
        <img src="รูปที่4.png" class="product-image">
        <div class="product-info">
            <h2 class="product-title">สินค้า4</h2>
            <p class="product-price">฿85</p>
            <p class="product-description">อร่อย</p>
            <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
    </div>

</div>

</body>
</html>
]
```
[![alt text](การทดลองที่3-1.png)]

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
<html>
<head>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="stats-container">
        <div class="stat-box">
            <div class="stat-number">2,889</div>
            <div class="stat-label">ผู้ใช้งาน</div>
        </div>
        <div class="stat-box">
            <div class="stat-number">8.6K</div>
            <div class="stat-label">ยอดขาย</div>
        </div>
        <div class="stat-box">
            <div class="stat-number">99%</div>
            <div class="stat-label">ความพึงพอใจ</div>
        </div>
    </div>
</body>
</html>
]
```
```css
[body{
    background:#eaf3ff; /* เพิ่มพื้นหลังทั้งหน้า */
    font-family: "Segoe UI", sans-serif;
}

.stats-container {
    display: flex;
    justify-content: space-around;
    max-width: 900px; /* เปลี่ยนขนาด container */
    margin: 4rem auto;
    padding: 20px;
}

.stat-box {
    flex: 1;
    margin: 0 15px;
    padding: 40px 20px; /* padding ใหญ่ขึ้นชัด */
    text-align: center;
    background-color: #ffffff;
    border-radius: 15px; /* โค้งมากขึ้น */
    border: 2px solid #ff5aa7; /* เพิ่ม border */
}

.stat-number {
    font-size: 3.5rem; /* ใหญ่ขึ้นชัด */
    font-weight: bold;
    color: #ff5722; /* เปลี่ยนสีชัด */
    margin-bottom: 10px;
}

.stat-label {
    font-size: 1.2rem;
    color: #646161;
    text-transform: uppercase;
    letter-spacing: 3px; /* เพิ่ม spacing */
}

/* Responsive */
@media (max-width: 768px) {
    .stats-container {
        flex-direction: column;
    }

    .stat-box {
        margin: 15px 0;
    }
}
]
```
[![alt text](การทดลองที่4-1.png)]

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
<html>
<head>
    <link rel="stylesheet" href="style.css">
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
]
```
```css
[body{
    margin:0;
    background:#f6f8fb;
    font-family:'Sarabun', sans-serif;
}

/* กล่องบทความ */
.blog-post {
    max-width: 780px;
    margin: 60px auto;
    padding: 40px;
    background:#ffffff;
    border-radius: 16px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.08);
}

/* header */
.post-header {
    text-align:center;
    margin-bottom:35px;
}

.post-title {
    font-size: 2.6rem;
    color:#1e293b;
    margin-bottom:10px;
}

.post-meta {
    color:#64748b;
    font-size:0.95rem;
    letter-spacing:1px;
}

/* เนื้อหา */
.post-content{
    font-size:1.15rem;
    line-height:1.9;
    color:#334155;
}

/* ย่อหน้า */
.post-content p{
    margin-bottom:1.6rem;
}

/* หัวข้อย่อย */
.post-content h2{
    font-size:1.9rem;
    margin:2.5rem 0 1rem;
    color:#ff5aa7;
}

/* ตัวอักษรตัวแรกใหญ่ */
.post-content p:first-of-type::first-letter{
    font-size:3rem;
    font-weight:bold;
    color:#ff5aa7;
    float:left;
    margin-right:8px;
}

/* quote */
blockquote{
    background:#f1f5f9;
    border-left:5px solid #ff5aa7;
    padding:18px 20px;
    margin:2rem 0;
    border-radius:10px;
    font-style:italic;
    color:#334155;
}

/* responsive */
@media (max-width:768px){
    .blog-post{
        margin:30px 15px;
        padding:25px;
    }

    .post-title{
        font-size:2.1rem;
    }
}]
```
[![alt text](การทดลองที่5-1.png)]

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
<title>Shop</title>
<link rel="stylesheet" href="style.css">
</head>
<body>

<header class="navbar">
    <h1 class="logo">MyShop</h1>
    <nav>
        <a href="#">หน้าแรก</a>
        <a href="#" class="active">สินค้า</a>
        <a href="#">เกี่ยวกับเรา</a>
        <a href="#">ติดต่อ</a>
    </nav>
</header>

<section class="product-grid">

    <!-- card 1 -->
    <div class="card">
        <img src="images/product1.jpg">
        <div class="info">
            <h3>กาแฟดำ</h3>
            <p class="price">฿80</p>
            <p class="desc">หอม เข้ม เต็มรส</p>
            <button>เพิ่มลงตะกร้า</button>
        </div>
    </div>

    <!-- card 2 -->
    <div class="card">
        <img src="images/product2.jpg">
        <div class="info">
            <h3>คาปูชิโน่</h3>
            <p class="price">฿85</p>
            <p class="desc">นุ่ม ละมุน</p>
            <button>เพิ่มลงตะกร้า</button>
        </div>
    </div>

    <!-- card 3 -->
    <div class="card">
        <img src="images/product3.jpg">
        <div class="info">
            <h3>ช็อกโก้ปั่น</h3>
            <p class="price">฿90</p>
            <p class="desc">หวาน อร่อย</p>
            <button>เพิ่มลงตะกร้า</button>
        </div>
    </div>

    <!-- card 4 -->
    <div class="card">
        <img src="images/product4.jpg">
        <div class="info">
            <h3>ลาเต้</h3>
            <p class="price">฿85</p>
            <p class="desc">กลมกล่อม</p>
            <button>เพิ่มลงตะกร้า</button>
        </div>
    </div>

</section>

</body>
</html>
]
```
```css
[*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:sans-serif;
}

body{
    background:#f6f7fb;
}

/* navbar */
.navbar{
    display:flex;
    justify-content:space-between;
    align-items:center;
    padding:15px 40px;
    background:white;
    box-shadow:0 2px 10px rgba(0,0,0,0.05);
}

.logo{
    color:#e91e63;
}

nav a{
    margin-left:15px;
    text-decoration:none;
    color:#555;
    font-weight:500;
    padding:8px 14px;
    border-radius:6px;
}

nav a.active,
nav a:hover{
    background:#e91e63;
    color:white;
}

/* grid */
.product-grid{
    max-width:1100px;
    margin:40px auto;
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
    gap:25px;
    padding:0 20px;
}

/* card */
.card{
    background:white;
    border-radius:15px;
    overflow:hidden;
    box-shadow:0 5px 20px rgba(0,0,0,0.08);
    transition:.3s;
}

.card:hover{
    transform:translateY(-8px);
}

/* image */
.card img{
    width:100%;
    height:160px;
    object-fit:cover;
}

/* content */
.info{
    padding:15px;
}

.price{
    color:#e91e63;
    font-weight:bold;
    margin:5px 0;
}

.desc{
    font-size:14px;
    color:#777;
}

/* button */
button{
    width:100%;
    margin-top:12px;
    padding:10px;
    border:none;
    border-radius:8px;
    background:linear-gradient(45deg,#ff4d94,#e91e63);
    color:white;
    font-weight:bold;
    cursor:pointer;
    transition:.3s;
}

button:hover{
    transform:scale(1.05);
}
]
```
[![alt text](การทดลองที่6-1.png)]


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
[
<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <title>แดชบอร์ดร้านกาแฟ</title>
    <link rel="stylesheet" href="style.css">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
</head>
<body>

<div class="container">

    <!-- เมนูซ้าย -->
    <aside class="sidebar">
        <h2>เมนู</h2>
        <a class="active">หน้าแรก</a>
        <a>รายงาน</a>
        <a>การตั้งค่า</a>
    </aside>

    <!-- เนื้อหา -->
    <main class="main">

        <!-- header -->
        <div class="topbar">
            <h1>📊 แดชบอร์ด</h1>
            <div>
                <button class="btn">โปรไฟล์</button>
                <button class="btn logout">ออกจากระบบ</button>
            </div>
        </div>

        <!-- การ์ด -->
        <div class="cards">
            <div class="card">
                <p>ยอดขายรวม</p>
                <h2>฿150,000</h2>
            </div>

            <div class="card">
                <p>จำนวนออเดอร์</p>
                <h2>1,234</h2>
            </div>

            <div class="card">
                <p>ลูกค้าใหม่</p>
                <h2>45</h2>
            </div>
        </div>

        <!-- กราฟ -->
        <div class="charts">

            <div class="card">
                <h3>📈 กราฟยอดขาย</h3>
                <canvas id="salesChart"></canvas>
            </div>

            <div class="card">
                <h3>🏆 สินค้าขายดี</h3>
                <canvas id="productChart"></canvas>
            </div>

        </div>

    </main>
</div>

<script>
// กราฟเส้น
new Chart(document.getElementById('salesChart'), {
    type: 'line',
    data: {
        labels: ['ม.ค.', 'ก.พ.', 'มี.ค.', 'เม.ย.', 'พ.ค.', 'มิ.ย.'],
        datasets: [{
            label: 'ยอดขาย',
            data: [12000,19000,15000,22000,18000,25000],
            borderWidth: 3,
            tension: 0.4
        }]
    }
});

// กราฟแท่ง
new Chart(document.getElementById('productChart'), {
    type: 'bar',
    data: {
        labels: ['เอสเพรสโซ่','ลาเต้','คาปูชิโน','มอคค่า'],
        datasets: [{
            label: 'จำนวนขาย',
            data: [50,40,35,60],
            borderWidth: 2
        }]
    }
});
</script>

</body>
</html>
]
```
```css
[*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:sans-serif;
}

body{
    background:#eef2f7;
}

/* layout */
.dashboard{
    display:grid;
    grid-template-areas:
        "sidebar header"
        "sidebar main";
    grid-template-columns:240px 1fr;
    grid-template-rows:auto 1fr;
    min-height:100vh;
}

/* header */
.header{
    grid-area:header;
    background:white;
    padding:18px 25px;
    box-shadow:0 2px 10px rgba(0,0,0,0.08);
    display:flex;
    justify-content:space-between;
    align-items:center;
}

.header h1{
    color:#333;
}

/* sidebar */
.sidebar{
    grid-area:sidebar;
    background:linear-gradient(180deg,#2c3e50,#1a252f);
    color:white;
    padding:25px 20px;
}

.sidebar h2{
    margin-bottom:20px;
}

.sidebar ul{
    list-style:none;
}

.sidebar li{
    padding:12px;
    margin-bottom:10px;
    border-radius:8px;
    cursor:pointer;
    transition:.3s;
}

.sidebar li:hover{
    background:rgba(255,255,255,0.1);
}

.sidebar .active{
    background:#ff4d94;
}

/* main */
.main-content{
    grid-area:main;
    padding:30px;
}

/* stat cards */
.stats-grid{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
    gap:20px;
    margin-bottom:30px;
}

.stat-card{
    background:white;
    padding:25px;
    border-radius:15px;
    box-shadow:0 10px 25px rgba(0,0,0,0.08);
    transition:.3s;
}

.stat-card:hover{
    transform:translateY(-6px);
}

.stat-card h3{
    color:#777;
    margin-bottom:10px;
}

.stat-card p{
    font-size:28px;
    font-weight:bold;
    color:#ff4d94;
}

/* chart */
.chart-container{
    display:grid;
    grid-template-columns:2fr 1fr;
    gap:20px;
}

.chart{
    background:white;
    padding:25px;
    border-radius:15px;
    box-shadow:0 10px 25px rgba(0,0,0,0.08);
}

.placeholder{
    margin-top:20px;
    background:#f1f4f9;


    body{
    margin:0;
    font-family: 'Segoe UI', sans-serif;
    background:#f2f4f8;
}

.container{
    display:flex;
}

/* sidebar */
.sidebar{
    width:220px;
    height:100vh;
    background:linear-gradient(#1f2d3d,#0d1b2a);
    color:white;
    padding:20px;
}

.sidebar h2{
    margin-bottom:30px;
}

.sidebar a{
    display:block;
    padding:12px;
    margin:10px 0;
    border-radius:8px;
    cursor:pointer;
}

.sidebar a:hover,
.sidebar .active{
    background:#ff4f8b;
}

/* main */
.main{
    flex:1;
    padding:20px;
}

/* topbar */
.topbar{
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-bottom:20px;
}

.btn{
    padding:10px 18px;
    border:none;
    border-radius:8px;
    background:#ff4f8b;
    color:white;
    margin-left:10px;
    cursor:pointer;
}

.logout{
    background:#ff2e63;
}

/* cards */
.cards{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
    gap:20px;
}

.card{
    background:white;
    padding:20px;
    border-radius:15px;
    box-shadow:0 5px 15px rgba(0,0,0,0.1);
}

.card h2{
    color:#ff4f8b;
}

/* charts */
.charts{
    display:grid;
    grid-template-columns:2fr 1fr;
    gap:20px;
    margin-top:20px;
}

canvas{
    max-height:250px;
}

]
```
[![alt text](disbord-1.png)]

