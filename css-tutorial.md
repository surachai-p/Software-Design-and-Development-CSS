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
    <link rel="stylesheet" type="text/css" href="styles.css">
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
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
<img width="1440" alt="2" src="https://github.com/user-attachments/assets/edef63b1-a230-4004-8eb8-dab41a44f04c" />



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
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
    <div class="product-card">
        <div class="product-image" style="background-image: url('images/p1.jpg');"></div>
        <div class="product-info">
            <h2 class="product-title">Chocolate Brownies</h2>
            <p class="product-price">ชิ้นละ 15 บาท</p>
            <p class="product-description">รายละเอียดขนม</p>
            <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
    </div>
    <div class="product-card">
        <div class="product-image" style="background-image: url('images/p2.jpg');"></div>
        <div class="product-info">
            <h2 class="product-title">Chocolate Chip Cookies</h2>
            <p class="product-price">ชิ้นละ 15 บาทท</p>
            <p class="product-description">รายละเอียดขนม</p>
            <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
    </div>
    <div class="product-card">
        <div class="product-image" style="background-image: url('images/p3.jpg');"></div>
        <div class="product-info">
            <h2 class="product-title">Strawberry Shortcake</h2>
            <p class="product-price">ชิ้นละ 45 บาท</p>
            <p class="product-description">รายละเอียดขนม</p>
            <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
    </div>
    <div class="product-card">
        <div class="product-image" style="background-image: url('images/p4.jpg');"></div>
        <div class="product-info">
            <h2 class="product-title">Pancakes</h2>
            <p class="product-price">ชิ้นละ 25 บาท</p>
            <p class="product-description">รายละเอียดขนม</p>
            <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
    </div>
</body>
</html>
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
<img width="1440" alt="3 1" src="https://github.com/user-attachments/assets/a50efb3c-f665-4882-990d-5021f7ab5b59" />
<img width="1440" alt="3 2" src="https://github.com/user-attachments/assets/a2eedb9c-fad8-49ac-b900-16c041f9f49a" />



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
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>สถิติผู้ใช้งาน</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="stats-container">
        <div class="stat-box">
            <div class="stat-number">1270</div>
            <div class="stat-label">ผู้ใช้งาน</div>
        </div>
        <div class="stat-box">
            <div class="stat-number">12.7k</div>
            <div class="stat-label">ยอดขาย</div>
        </div>
        <div class="stat-box">
            <div class="stat-number">97%</div>
            <div class="stat-label">ความพึงพอใจ</div>
        </div>
    </div>
</body>
</html>
```
```css
[วางโค้ด CSS ที่นี่]
/* ตั้งค่าฟอนต์และพื้นหลัง */
body {
    font-family: 'Arial', sans-serif;
    background-color: #f4f4f9;
    margin: 0;
    padding: 0;
}

/* คอนเทนเนอร์หลัก */
.stats-container {
    display: flex;
    justify-content: space-around;
    max-width: 1100px;
    margin: 3rem auto;
    padding: 1rem;
}

/* กล่องสถิติ */
.stat-box {
    flex: 1;
    margin: 0 20px;
    padding: 2.5rem;
    text-align: center;
    background-color: #ffffff;
    border-radius: 12px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
    transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
}

/* ขนาดตัวเลข */
.stat-number {
    font-size: 3rem;
    font-weight: bold;
    color: #947cfe;
    margin-bottom: 0.75rem;
}

/* ป้ายกำกับ */
.stat-label {
    font-size: 1.2rem;
    color: #444;
    text-transform: uppercase;
    letter-spacing: 1.5px;
}

/* เอฟเฟกต์เมื่อ hover */
.stat-box:hover {
    transform: translateY(-5px);
    box-shadow: 0 6px 15px rgba(0, 0, 0, 0.2);
}

/* Responsive Design สำหรับมือถือ */
@media (max-width: 768px) {
    .stats-container {
        flex-direction: column;
        align-items: center;
    }

    .stat-box 
        width: 80%;
        margin: 1rem 0;
    }
}

```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
<img width="1440" alt="4" src="https://github.com/user-attachments/assets/d9377f67-16eb-4f39-9ab7-a3d95290f3f4" />


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
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>บทความที่น่าสนใจ</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <article class="blog-post">
        <header class="post-header">
            <h1 class="post-title">เเนะนำตัวเอง</h1>
            <div class="post-meta">โพสต์เมื่อ 14 กุมภาพันธ์ 2025 | โดยผู้เขียน นางสาววิชญาพร เนียมเที่ยง 67030211 </div>
        </header>
        
        <div class="post-content">
            <p>เนื้อหาของเพจนี้เป็นการเเนะนำตัวเอง</p>

            <h2>1. การเเนะนำตัวเอง</h2>
            <p>สวัสดีค่ะ ดิฉันชื่อ นางสาววิชญาพร เนียมเที่ยง ชื่อเล่น หญิง หรือที่เพื่อน ๆ ของดิฉันเรียกกันว่า หงิง ม หงิงหงิง ปัจจุบันฉันมีอายุ 19 ปี
            <br>  เรียนอยู่ในชั้นปีที่ 1 สาขาเทคโนโลยีคอมพิวเตอร์ คณะครุศาสตร์อุตสาหกรรมและเทคโนโลยี สถาบันเทคโนโลยีพระจอมเกล้าเจ้าคุณทหารลาดกระบัง
            </p>

            <blockquote>
                "การที่ดิฉันเลือกเรียนในสาขาวิชานี้ เพราะว่าดิฉันมีความสนใจในคอมพิวเตอร์ การออกแบบกราฟิก และที่ดิฉันเลือกเรียนในคณะนี้ เป็นเพราะว่า ในอนาคตฉันเองอยากเป็นครูที่ดีให้กับนักเรียนที่ฉันสอน"
            </blockquote>

            <h2>2. ความฝันในอนาคต</h2>
            <p>อยากเป็นครูที่ดี เด็ก ๆ ชื่นชอบ มีอาชีพมั่นคง เป็นที่พึ่งของครอบครัวได้</p>
        </div>
    </article>
</body>
</html>
```
```css
[วางโค้ด CSS ที่นี่]
body {
    font-family: 'Sarabun', sans-serif;
    background-color: #f8f9fa;
    margin: 0;
    padding: 0;
    color: #333;
}

/* คอนเทนเนอร์ของบทความ */
.blog-post {
    max-width: 850px;
    margin: 3rem auto;
    padding: 2rem;
    background: #ffffff;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
}

/* ส่วนหัวของบทความ */
.post-header {
    text-align: center;
    margin-bottom: 2rem;
}

/* หัวข้อหลัก */
.post-title {
    font-size: 2.8rem;
    color: #ff6ec4;
    margin-bottom: 0.5rem;
    font-weight: bold;
    line-height: 1.3;
}

/* ข้อมูลเมตาของโพสต์ */
.post-meta {
    color: #84d9ff;
    font-size: 1rem;
    text-transform: uppercase;
    letter-spacing: 1px;
}

/* เนื้อหาของบทความ */
.post-content {
    font-size: 1.2rem;
    line-height: 1.8;
    color: #000000;
}

/* การตั้งค่าข้อความในเนื้อหา */
.post-content p {
    margin-bottom: 1.5rem;
}

/* หัวข้อย่อย */
.post-content h2 {
    font-size: 2rem;
    color: #c686fc;
    margin: 2rem 0 1rem;
}

/* Blockquote (คำพูด) */
blockquote {
    font-style: italic;
    border-left: 5px solid #fff453;
    margin: 1.5rem 0;
    padding-left: 1rem;
    color: #555;
    background: #f1f1f1;
    padding: 1rem;
    border-radius: 5px;
}

/* เพิ่มเอฟเฟกต์เมื่อ hover หัวข้อ */
.post-title:hover {
    color: #ff33ac;
    text-decoration: underline;
    cursor: pointer;
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
<img width="1440" alt="5" src="https://github.com/user-attachments/assets/3e29fe89-5b65-43ad-bb74-6185b0ebafd2" />


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
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>หน้าร้านค้า - Grid Layout</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>

    <div class="product-grid">
        <!-- สินค้าชิ้นที่ 1 -->
        <div class="product-card">
            <div class="product-image-wrapper">
                <img src="images/p1.jpg" alt="ขนมอย่างที่ 1" class="product-image">
            </div>
            <div class="product-details">
                <h3 class="product-title">ขนมอย่างที่ 1</h3>
                <div class="product-price">ชิ้นละ 15 บาท</div>
                <div class="product-action">
                    <button class="add-to-cart">เพิ่มลงตะกร้า</button>
                </div>
            </div>
        </div>

        <div class="product-card">
            <div class="product-image-wrapper">
                <img src="images/p2.jpg" alt="ขนมอย่างที่ 2" class="product-image">
            </div>
            <div class="product-details">
                <h3 class="product-title">ขนมอย่างที่ 2</h3>
                <div class="product-price">ชิ้นละ 15 บาท</div>
                <div class="product-action">
                    <button class="add-to-cart">เพิ่มลงตะกร้า</button>
                </div>
            </div>
        </div>

        <div class="product-card">
            <div class="product-image-wrapper">
                <img src="images/p3.jpg" alt="ขนมอย่างที่ 3" class="product-image">
            </div>
            <div class="product-details">
                <h3 class="product-title">ขนมอย่างที่ 3</h3>
                <div class="product-price">ชิ้นละ 45 บาท</div>
                <div class="product-action">
                    <button class="add-to-cart">เพิ่มลงตะกร้า</button>
                </div>
            </div>
        </div>

        <div class="product-card">
            <div class="product-image-wrapper">
                <img src="images/p4.jpg" alt="ขนมอย่างที่ 4" class="product-image">
            </div>
            <div class="product-details">
                <h3 class="product-title">ขนมอย่างที่ 4</h3>
                <div class="product-price">ชิ้นละ 25 บาท</div>
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
[วางโค้ด CSS ที่นี่]
/* รีเซ็ตค่าพื้นฐาน */
body {
    font-family: 'Arial', sans-serif;
    background-color: #f8f9fa;
    margin: 0;
    padding: 0;
}

/* กำหนด Layout แบบ Grid */
.product-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); /* แก้ไข */
    gap: 15px;
    padding: 20px;
    max-width: 1000px;
    margin: 0 auto;
}

/* กล่องสินค้า */
.product-card {
    background: white;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    transition: transform 0.2s ease, box-shadow 0.2s ease;
    text-align: center;
    padding: 10px;
}

.product-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 5px 10px rgba(0,0,0,0.15);
}

/* กรอบรูปภาพสินค้า */
.product-image-wrapper {
    border: 5px solid #c686fc; /* หรือสีที่ต้องการ */
    border-radius: 10px; /* มุมมน */
    overflow: hidden; /* ซ่อนส่วนเกิน */
}

/* รูปภาพสินค้า */
.product-image {
    width: 100%;  /* กำหนดความกว้างของรูปภาพ */
    height: auto; /* กำหนดความสูงของรูปภาพ */
    object-fit: cover; /* ให้ภาพพอดีกับขนาดที่กำหนด */
    object-position: center; /* จัดให้อยู่ตรงกลาง */
    background-color: #f5f5f5; /* สีพื้นหลังถ้าภาพโปร่งใส */
}

/* รายละเอียดสินค้า */
.product-details {
    padding: 10px;
}

.product-title {
    font-size: 0.95rem; /* ปรับขนาดให้เล็กลง */
    font-weight: bold;
    margin-bottom: 5px;
    color: #333;
}

.product-price {
    font-size: 1.1rem;
    color: #ff48b6;
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
<img width="1440" alt="6" src="https://github.com/user-attachments/assets/c3d2367d-c633-4624-833f-394331fc2a64" />



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
<html>
<head>
    <link rel="stylesheet" type="text/css" href="styles.css">
    <title>แดชบอร์ด</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
</head>
<body>
    <div class="dashboard">
        <header class="header">
            <h1>My Dashboard</h1>
            <nav>
                <button>โปรไฟล์</button>
                <button
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
                    <p>127.77k</p>
                </div>
                <div class="stat-card">
                    <h3>จำนวนออเดอร์</h3>
                    <p>7,210</p>
                </div>
                <div class="stat-card">
                    <h3>ลูกค้าใหม่</h3>
                    <p>127</p>
                </div>
            </div>

            <div class="chart-container">
                <div class="chart">
                    <h3>กราฟแสดงยอดขาย</h3>
                    <canvas id="salesChart"></canvas>
                </div>
                <div class="chart">
                    <h3>สัดส่วนสินค้าขายดี</h3>
                    <canvas id="productChart"></canvas>
                </div>
            </div>
        </main>
    </div>

    <script>
        // กราฟแสดงยอดขาย
        const ctxSales = document.getElementById('salesChart').getContext('2d');
        const salesChart = new Chart(ctxSales, {
            type: 'line',
            data: {
                labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul'],
                datasets: [{
                    label: 'ยอดขาย',
                    data: [110000, 130000, 150000, 170000, 150000, 200000, 230000],
                    borderColor: 'rgba(75, 192, 192, 1)',
                    backgroundColor: 'rgba(75, 192, 192, 0.2)',
                    borderWidth: 2,
                    fill: true
                }]
            },
            options: {
                responsive: true,
                plugins: {
                    legend: {
                        position: 'top',
                    },
                    title: {
                        display: true,
                        text: 'กราฟแสดงยอดขายรายเดือน'
                    }
                }
            }
        });

        // กราฟสัดส่วนสินค้าขายดี
        const ctxProduct = document.getElementById('productChart').getContext('2d');
        const productChart = new Chart(ctxProduct, {
            type: 'pie',
            data: {
                labels: ['สินค้า A', 'สินค้า B', 'สินค้า C', 'สินค้า D'],
                datasets: [{
                    label: 'สัดส่วนสินค้าขายดี',
                    data: [300, 50, 100, 150],
                    backgroundColor: [
                        'rgba(255, 99, 132, 0.2)',
                        'rgba(54, 162, 235, 0.2)',
                        'rgba(255, 206, 86, 0.2)',
                        'rgba(75, 192, 192, 0.2)',
                    ],
                    borderColor: [
                        'rgba(255, 99, 132, 1)',
                        'rgba(54, 162, 235, 1)',
                        'rgba(255, 206, 86, 1)',
                        'rgba(75, 192, 192, 1)',
                    ],
                    borderWidth: 1
                }]
            },
            options: {
                responsive: true,
                plugins: {
                    legend: {
                        position: 'top',
                    },
                    title: {
                        display: true,
                        text: 'สัดส่วนสินค้าขายดี'
                    }
                }
            }
        });
    </script>
</body>
</html>
```
```css
[วางโค้ด CSS ที่นี่]
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background-color: #6fcdf9;
}

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
    background: rgb(132, 217, 255);
    padding: 1rem;
    box-shadow: 0 2px 4px rgb(254, 253, 253);
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.header nav button {
    background-color: #ff6ec4; /* สีพื้นหลัง */
    color: white; /* สีข้อความ */
    border: none; /* ไม่มีขอบ */
    border-radius: 20px; /* ทำให้มุมโค้งมน */
    padding: 10px 20px; /* ขนาดของปุ่ม */
    font-size: 16px; /* ขนาดของข้อความ */
    cursor: pointer; /* เปลี่ยนรูปแบบของลูกศรเมื่อชี้ไปที่ปุ่ม */
    transition: background-color 0.3s, transform 0.3s; /* เอฟเฟกต์เคลื่อนไหว */
}

.header nav button:hover {
    background-color: #ff1fa6; /* เปลี่ยนสีเมื่อเลื่อนเมาส์ไปที่ปุ่ม */
    transform: scale(1.05); /* ขยายเล็กน้อยเมื่อเลื่อนเมาส์ไปที่ปุ่ม */
}

.sidebar {
    grid-area: sidebar;
    background: #032649a2;
    color: white;
    padding: 1rem;
    border-right: 2px solid #07213b;
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
    background: rgba(255, 244, 83, 1);
    padding: 1.5rem;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    transition: transform 0.3s;
}

.stat-card h3 {
    color: #000000; /* เปลี่ยนสีของหัวข้อ */
}

.stat-card p {
    color: #fe5827; /* เปลี่ยนสีของข้อความในพารากราฟ */
    font-weight: bold; /* ทำให้ข้อความมีน้ำหนักเข้มขึ้น */
}

.stat-card:hover {
    transform: scale(1.05);
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
    box-shadow: 0 2px 4px rgba(224, 221, 221, 0.1);
}
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
<img width="1440" alt="6 1" src="https://github.com/user-attachments/assets/07fa22f2-85fb-485c-a938-bbf1d141a286" />


