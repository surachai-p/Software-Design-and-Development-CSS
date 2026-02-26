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
```
[![alt text](<Screenshot 2026-02-24 224345.png>)]


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
    <link rel="stylesheet" href="style.css">
    <title>รายการสินค้า</title>
</head>
<body>

    <div class="product-container">
        
        <div class="product-card">
            <div class="product-image img-1"></div>
            <div class="product-info">
                <h2 class="product-title">Winsor & Newton Professional</h2>
                <p class="product-price">฿2,450</p>
                <p class="product-description">ชุดสีน้ำเกรดศิลปินจากอังกฤษ เม็ดสีบริสุทธิ์ ให้ความโปร่งแสงและความทนทานต่อแสงสูงสุด</p>
                <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
            </div>
        </div>

        <div class="product-card">
            <div class="product-image img-2"></div>
            <div class="product-info">
                <h2 class="product-title">Raphaël Kolinsky Sable</h2>
                <p class="product-price">฿1,200</p>
                <p class="product-description">พู่กันขนสัตว์แท้ (Kolinsky) เบอร์ 6 งานทำมือจากฝรั่งเศส สปริงตัวดีเยี่ยมและอุ้มสีได้ดีที่สุด</p>
                <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
            </div>
        </div>

        <div class="product-card">
            <div class="product-image img-3"></div>
            <div class="product-info">
                <h2 class="product-title">Arches Aquarelle Paper</h2>
                <p class="product-price">฿1,850</p>
                <p class="product-description">กระดาษสีน้ำ Cotton 100% หนา 300 แกรม แบบ Rough ทำด้วยแม่พิมพ์โบราณ คุณภาพสูงสุด</p>
                <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
            </div>
        </div>

        <div class="product-card">
            <div class="product-image img-4"></div>
            <div class="product-info">
                <h2 class="product-title">Faber-Castell Polychromos</h2>
                <p class="product-price">฿3,600</p>
                <p class="product-description">ชุดดินสอสีไม้ 60 สี ไส้สีสูตรน้ำมัน กันน้ำ ติดทน ระบายลื่น และสีไม่ซีดจางเมื่อเวลาผ่านไป</p>
                <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
            </div>
        </div>

    </div>
</body>
</html>]
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
    <link rel="stylesheet" href="stats-style.css">
</head>
<body>
    <div class="stats-container">
        <div class="stat-box">
            <div class="stat-number">120+</div>
            <div class="stat-label">สีน้ำ Winsor</div>
        </div>

        <div class="stat-box">
            <div class="stat-number">100%</div>
            <div class="stat-label">Cotton Arches</div>
        </div>

        <div class="stat-box">
            <div class="stat-number">60</div>
            <div class="stat-label">เฉดสี Faber</div>
        </div>
    </div>

</body>
</html>]
```
```css
[.stats-container {
    display: flex;
    gap: 40px;            
    max-width: 1200px;
    margin: 50px auto;    
}

.stat-box {
    flex: 1;
    margin: 10px; 
    padding: 50px 20px;            
    background-color: #ffffff;
    border-radius: 12px;
    box-shadow: 0 4px 15px rgba(121, 110, 110, 0.05);
    text-align: center;
}

.stat-number {
    font-size: 3.5rem;    
    font-weight: 800;
    color: #4985c5;       
    margin-bottom: 10px;
    font-family: 'Arial', sans-serif;
}

.stat-label {
    font-size: 1.1rem;    
    color: #9f6868;          
    font-weight: 600;
    letter-spacing: 1px;
}

/* Responsive: สำหรับมือถือ */
@media (max-width: 768px) {
    .stats-container {
        flex-direction: column;
    }
    
    .stat-box {
        width: 80%;
    }
}]
```
[![alt text](image-1.png)]

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
    <link rel="stylesheet" href="lab5.css">
</head>
<body>
    <article class="blog-post">
        <header class="post-header">
            <h1 class="post-title">เจาะลึกความลับของสีน้ำ Winsor & Newton</h1>
        </header>
        
        <div class="post-content">
            <p>หากพูดถึงสีน้ำระดับโลกที่ศิลปินเลือกใช้ ชื่อของ Winsor & Newton มักจะขึ้นมาเป็นอันดับต้นๆ เสมอ ด้วยประวัติศาสตร์ที่ยาวนานและความเข้มข้นของเม็ดสีที่ไม่เหมือนใคร</p>

            <h2>ทำไมต้องเกรด Professional?</h2>
            <p>ความแตกต่างที่ชัดเจนที่สุดคือความทนทานต่อแสง (Lightfastness) ซึ่งหมายความว่าผลงานของคุณจะยังคงสีสันสดใสไปอีกนับร้อยปีโดยไม่ซีดจาง</p>

            <blockquote>
                "หัวใจสำคัญของภาพวาดสีน้ำ คือการปล่อยให้เม็ดสีทำงานร่วมกับน้ำและกระดาษอย่างเป็นอิสระ"
            </blockquote>

            <h2>การเลือกใช้พู่กันที่เหมาะสม</h2>
            <p>การใช้สีระดับพรีเมียมคู่กับพู่กันขนสัตว์แท้ เช่น Raphael จะช่วยให้การควบคุมน้ำหนักมือและการกระจายตัวของสีทำได้สมบูรณ์แบบที่สุด</p>
        </div>
    </article>
</body>
</html>]
```
```css
[.blog-post {
    max-width: 800px;
    margin: 3rem auto;
    padding: 0 1.5rem;
    font-family: 'Sarabun'
}

.post-header {
    text-align: center;
    margin-bottom: 3rem;
}

.post-title {
    font-size: 2.8rem;
    color: #004a99; 
    margin-bottom: 1rem;
    line-height: 1.3;
    font-weight: bold;
}

.post-meta {
    color: #888;
    font-size: 0.85rem;
    text-transform: uppercase;
    letter-spacing: 2px;
}

.post-content {
    font-size: 1.25rem; 
    line-height: 1.8;
    color: #333;
}

.post-content h2 {
    font-size: 1.8rem;
    color: #0056b3;
    margin: 2.5rem 0 1rem;
    border-bottom: 2px solid #f0f4f8;
    padding-bottom: 10px;
}

blockquote {
    font-style: italic;
    border-left: 5px solid #0056b3;
    margin: 2rem 0;
    padding: 1rem 1.5rem;
    background-color: #f9fbff;
    color: #444;
}

/* Responsive: สำหรับหน้าจอมือถือ */
@media (max-width: 768px) {
    .post-title {
        font-size: 2rem;
    }
    .post-content {
        font-size: 1.1rem;
    }
}]
```
[![alt text](image-2.png)]

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
    <link rel="stylesheet" href="lab6.css">
</head>
<body>

    <div class="product-grid">
        <div class="product-card">
            <div class="product-image" style="background-image: url('images/winsor.jpg.jpg')"></div>
            <div class="product-details">
                <h3 class="product-title">สีน้ำ Winsor & Newton</h3>
                <div class="product-price">฿2,450</div>
                <div class="product-action">
                    <button class="add-to-cart">ซื้อเลย</button>
                </div>
            </div>
        </div>

        <div class="product-card">
            <div class="product-image" style="background-image: url('images/brush.jpg.jpg')"></div>
            <div class="product-details">
                <h3 class="product-title">พู่กัน Raphael</h3>
                <div class="product-price">฿1,200</div>
                <div class="product-action">
                    <button class="add-to-cart">ซื้อเลย</button>
                </div>
            </div>
        </div>

        <div class="product-card">
            <div class="product-image" style="background-image: url('images/paper.jpg.jpg')"></div>
            <div class="product-details">
                <h3 class="product-title">กระดาษ Arches</h3>
                <div class="product-price">฿1,850</div>
                <div class="product-action">
                    <button class="add-to-cart">ซื้อเลย</button>
                </div>
            </div>
        </div>

        <div class="product-card">
            <div class="product-image" style="background-image: url('images/woodcolor.jpg.jpg')"></div>
            <div class="product-details">
                <h3 class="product-title">Faber-Castell</h3>
                <div class="product-price">฿3,600</div>
                <div class="product-action">
                    <button class="add-to-cart">ซื้อเลย</button>
                </div>
            </div>
        </div>
    </div>

</body>
</html>]
```
```css
[.product-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    gap: 15px;
    padding: 30px;
    max-width: 1200px;
    margin: 0 auto;
}

/* ปรับแต่ง Card สินค้า */
.product-card {
    background: white;
    border-radius: 6px;
    overflow: hidden;
    box-shadow: 0 2px 8px rgba(0,0,0,0.06);
    transition: transform 0.2s ease;
}

.product-card:hover {
    transform: translateY(-3px);
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.product-image {
    width: 100%;
    height: 150px;
    background-color: #f5f5f5;
    background-size: cover;
    background-position: center;
}

.product-details {
    padding: 12px;
}

.product-title {
    font-size: 0.95rem; 
    margin: 0 0 8px 0;
    color: #333;
    display: -webkit-box;
    -webkit-box-orient: vertical;
    overflow: hidden;
}

.product-price {
    font-size: 1.1rem;
    color: #0056b3; 
    font-weight: bold;
}

.product-action {
    display: flex;
    justify-content: center; 
}

.add-to-cart {
    background-color: #0056b3;
    color: white;
    border: none;
    padding: 6px 12px;
    border-radius: 4px;
    font-size: 0.85rem;
    cursor: pointer;
    width: 100%;
}

.add-to-cart:hover {
    background-color: #003d7a;
}

@media (max-width: 768px) {
    .product-grid {
        grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    }
}]
```
[![alt text](image-3.png)]


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
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="lab6.2.css">
</head>
<body>
    <div class="dashboard">
        <header class="header">
            <h1>แดชบอร์ด</h1>
            <nav class="nav-buttons">
                <button>โปรไฟล์</button>
                <button>ออกจากระบบ</button>
            </nav>
        </header>

        <aside class="sidebar">
            <h2>เมนูหลัก</h2>
            <nav>
                <ul>
                    <li> ภาพรวมสถิติ</li>
                    <li> จัดการสินค้าอุปกรณ์</li>
                    <li> ออเดอร์ลูกค้า</li>
                    <li> การตั้งค่าระบบ</li>
                </ul>
            </nav>
        </aside>

        <main class="main-content">
            <div class="stats-grid">
                <div class="stat-card" style="border-left-color: #3498db;">
                    <h3>ยอดจำหน่ายอุปกรณ์ศิลปะ</h3>
                    <p>฿150,000</p>
                </div>
                <div class="stat-card" style="border-left-color: #3498db;">
                    <h3>คำสั่งอุปกรณ์ศิลปะ</h3>
                    <p>1,234</p>
                </div>
                <div class="stat-card" style="border-left-color: #3498db;">
                    <h3>ลูกค้าใหม่</h3>
                    <p>45</p>
                </div>
            </div>

            <div class="chart-container">
                <div class="chart">
                    <h3>แนวโน้มยอดขาย</h3>
                    <div style="height: 200px; background: #f9f9f9; border: 2px dashed #eee; display: flex; align-items: center; justify-content: center; color: #ccc; margin-top: 1rem;">
                        พื้นที่แสดงกราฟเส้น
                    </div>
                </div>
                <div class="chart">
                    <h3>สินค้าที่เติมสต็อกบ่อย</h3>
                    <div style="height: 200px; background: #f9f9f9; border: 2px dashed #eee; display: flex; align-items: center; justify-content: center; color: #ccc; margin-top: 1rem;">
                        พื้นที่แสดงกราฟวงกลม
                    </div>
                </div>
            </div>
        </main>
    </div>
</body>
</html>]
```
```css
[.dashboard {
    display: grid;
    grid-template-areas: 
        "sidebar header"
        "sidebar main";
    grid-template-columns: 260px 1fr;
    grid-template-rows: 70px 1fr;
    min-height: 100vh;
}

.header {
    grid-area: header;
    background: #ffffff;
    padding: 0 2rem;
    box-shadow: 0 2px 10px rgba(0,0,0,0.05);
    display: flex;
    justify-content: space-between;
    align-items: center;
    z-index: 10;
}

.header h1 {
    font-size: 1.5rem;
    color: #2c3e50;
}

.nav-buttons button {
    background: #f8f9fa;
    border: 1px solid #2145b3;
    padding: 8px 16px;
    border-radius: 6px;
    cursor: pointer;
    margin-left: 10px;
    transition: 0.3s;
}

.nav-buttons button:hover {
    background: #9ecaf9;
    color: white;
}

.sidebar {
    grid-area: sidebar;
    background: #152d44; 
    color: #ecf0f1;
    padding: 2rem 1.5rem;
}

.sidebar h2 {
    font-size: 1.2rem;
    color: #7bafd7;
    margin-bottom: 2rem;
    text-align: center;
    text-transform: uppercase;
}

.sidebar ul {
    list-style: none;
    padding: 0;
}

.sidebar li {
    padding: 12px 15px;
    margin-bottom: 5px;
    border-radius: 8px;
    cursor: pointer;
    transition: 0.3s;
}

.sidebar li:hover {
    background: #34495e;
    color: #3498db;
}

.main-content {
    grid-area: main;
    padding: 2rem;
}

/* การ์ดสถิติ */
.stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 1.5rem;
    margin-bottom: 2rem;
}

.stat-card {
    background: white;
    padding: 1.5rem;
    border-radius: 12px;
    box-shadow: 0 4px 6px rgba(0,0,0,0.02);
    border-left: 5px solid #0056b3; 
}

.stat-card h3 {
    margin: 0;
    font-size: 0.9rem;
    color: #677b7c;
    text-transform: uppercase;
}

.stat-card p {
    margin: 10px 0 0;
    font-size: 1.8rem;
    font-weight: bold;
    color: #2c3e50;
}

/* ส่วนแสดงกราฟ/ตาราง */
.chart-container {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 1.5rem;
}

.chart {
    background: white;
    padding: 2rem;
    border-radius: 12px;
    min-height: 300px;
    box-shadow: 0 4px 6px rgba(0,0,0,0.02);
}

/* --- Responsive Design --- */
@media (max-width: 992px) {
    .dashboard {
        grid-template-areas: 
            "header"
            "main";
        grid-template-columns: 1fr;
    }
    .sidebar { display: none; }
    .chart-container { grid-template-columns: 1fr; }
}]
```
[![alt text](image-4.png)]

