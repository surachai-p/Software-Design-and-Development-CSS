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
    <link rel="stylesheet" href="css/buttons.css">
</head>
<body>
    <nav>
        <ul>
            <li><a href="#" class="menu-item" >หน้าแรก</a></li>
            <li><a href="#" class="menu-item"id="active" >สินค้า</a></li>
            <li><a href="#" class="menu-item">เกี่ยวกับเรา</a></li>
            <li><a href="#" class="menu-item">ติดต่อ</a></li>
        </ul>
    </nav>
</body>
</html>
css
nav {
    background-color: rgb(62, 189, 115);
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
```

[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![selector](https://github.com/user-attachments/assets/2fd0ad4f-129a-4591-9c1a-5bce5a923267)


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
<html>
<head>
    <link rel="stylesheet" href="css/ground.css">
</head>
<body>
    
    <div class="product-card">
        <div class="product-image" style="background-image: url('images/love1.gif');"></div>
        <div class="product-info">
            <h2 class="product-title">กลิ่นหอมความรัก</h2>
            <p class="product-price">549 บาท</p>
            <p class="product-description">
                จอมเป็นสถาปนิกผู้รับผิดชอบการรีโนเวตเรือนโบราณริมแม่น้ำปิง
ที่นั่นเขาพบหีบไม้อัดแน่นไปด้วยรูปวาดเก่าๆ ซึ่งดูคุ้นตาอย่างน่าประหลาด
ถึงจะนึกสงสัยแต่จอมก็ไม่มีเวลากับเรื่องพวกนั้นมากนัก
เขาต้องกลับกรุงเทพฯ ชั่วคราวเพื่อไปรับคนรักซึ่งเพิ่งเรียนจบกลับมา
จอมเฝ้านับวันที่จะได้พบกับแฟนหนุ่มมาตลอดหลังต้องห่างกันนานหลายปี
เพื่อจะพบว่าอีกฝ่ายกำลังจะแต่งงานกับผู้หญิงคนหนึ่งที่ดูเหมาะสมกันดี...
แม้ลึกๆ ในใจอยากได้คำอธิบาย แต่ในเมื่ออีกฝ่ายเลือกแล้ว จอมก็จะรับมันไว้
เขาเดินทางกลับเชียงใหม่ทันที แต่ความเสียใจกลับนำไปสู่เหตุการณ์ไม่คาดคิด
ขณะที่รถของเขากำลังจมดิ่งลงสู่ก้นแม่น้ำ ท่ามกลางความมืดมิดอันเย็นเยียบ
จอมได้กลิ่นดอกลั่นทมหอมจรุงมากับสายน้ำ
และแว่วเสียงทุ้มเจือความอ่อนหวานที่เอ่ยคำหนักแน่น
‘พ่อจอม...’
            </p>
            <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
    </div>

    <div class="product-card">
        <div class="product-image" style="background-image: url('images/love2.gif');"></div>
        <div class="product-info">
            <h2 class="product-title">ปลาบนฟ้า</h2>
            <p class="product-price">399 บาท</p>
            <p class="product-description">
                สำหรับผม เมืองน่านคนนั้นก็เหมือน ‘ปลาบนฟ้า’
                อยู่ไกลเกินเอื้อมเสียจนควรจะตัดใจซะถ้าไม่อยากเจ็บ
                เพราะผู้ชายอย่างไอ้ปีคนนี้มันดันฉลาดแต่เรื่องวิชาการ สอบตกเรื่องความรัก
                ผมเลยทำได้แค่แอบมองเขาอยู่ห่างๆ มาเป็นปี
                
                ทว่าทันทีที่ผมตัดสินใจเป็นไงเป็นกันจะจีบเมืองน่านให้ได้
                กลับมีผู้ชายคนหนึ่งมาตามเกาะปลาบนฟ้าของผมราวกับปลิง
                ซึ่งคนคนนั้นก็แค่หล่อ เท่ ฉลาด แฟนคลับเพียบ... เท่านั้นเอ๊งงง
                แต่ไอ้ปีคนนี้ไม่ยอมแพ้หรอก!
                ก่อนอื่นก็แค่ต้องกำจัดศัตรูหัวใจนี่ไปให้ไกลๆ
                แต่ไหงกำจัดไปกำจัดมา... กลายเป็นมีคนมาสารภาพรักกับผมไปได้!
            </p>
            <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
    </div>
    <div class="product-card">
        <div class="product-image" style="background-image: url('images/love3.gif');"></div>
        <div class="product-info">
            <h2 class="product-title">หลวงตาบอกแล้วอย่าออกแว้นตอนตีสาม...เปรตมัน</h2>
            <p class="product-price">549 บาท</p>
            <p class="product-description">
                'พารัก' เด็กหนุ่มเลือดร้อนผู้สดใสที่ใครๆ ต่างรู้จักเขากันดีในฐานะเด็กแว้นประจำซอย แม้พื้นเพนิสัยจะเป็นเด็กดีไม่น้อย แต่อีกด้านหนึ่งก็เป็นภาระสังคมอยู่พอสมควร แว้นรถเสียงดังจนใครๆ ก็ส่ายหน้า
จนกระทั่งวันหนึ่งเพื่อนในแก๊งดันแหกโค้งดับคาที่ งานซิ่งรอบเมรุส่งท้ายให้เพื่อนผู้ล่วงลับจึงต้องมา เบิ้ลเครื่องกันตึงๆ ตอนตีสาม ทว่าคราวนี้ขากลับดันมีคนซ้อนท้ายกลับบ้านไปด้วย แต่ไอ้คนซ้อนท้ายมันดันไม่ใช่มนุษย์เนี่ยสิ...

หลวงตาบอกแล้วอย่าออกแว้นตอนตีสาม ถ้ามันไม่ฟัง ให้เจอผีสักทีก็ดีเหมือนกัน!

---
หนังสือเล่มเดียวจบ
---
            </p>
            <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
        </div>
    </div>
</div>
<div class="product-card">
    <div class="product-image" style="background-image: url('images/love4.gif');"></div>
    <div class="product-info">
        <h2 class="product-title">บทกวีของปีแสง</h2>
        <p class="product-price">299 บาท</p>
        <p class="product-description">
            มีใครคนหนึ่งถามผมว่าหากย้อนเวลาได้ อยากกลับไปแก้ไขอะไรมากที่สุด
คำตอบก็คือ... ผมอยากกลับไปเรียนมหา’ลัยอีกครั้ง
และรวบรวมความกล้าเข้าไปทำความรู้จักกับเธอ
แต่ใครจะคิดดดดด ว่าพอย้อนเวลากลับไปจริงๆ แล้ว
ไอ้ที่หวังว่าจะได้พูดคุยกับรักแรกอย่างแพรไหมก็เป็นจริงอยู่แหละ
แต่ที่แถมมาแบบไม่ต้องการก็คือมารหัวใจที่ชื่อปีแสง!
ให้ตายเถอะ ปัจจุบันมันได้แต่งงานกับไหม
พอมีปาฏิหาริย์ย้อนเวลา มันยังจะมาขัดขวางทางรักของผมอีกเหรอ
คงจะจริงอย่างที่เขาว่ากันแหละครับ
กับคนบางคน ต่อให้ย้อนเวลากลับไปแก้ไขอีกสักกี่ครั้ง
เขาก็ไม่มีทางเป็นของเราอยู่วันยังค่ำ
        </p>
        <a href="#" class="product-button">เพิ่มลงตะกร้า</a>
    </div>
</div>

</body>
</html>

css

body {
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: bisque;
}
.container{
    display: flex;
    flex-direction: row;
    overflow: auto;
    justify-content: center;
    gap: 20px;
    padding: 20px;
    width: 100%;
    box-sizing: border-box;
}
.product-card {
    width: 300px;
    border-radius: 15px;
    overflow: hidden;
    box-shadow: 0 2px 4px rgba(39, 27, 146, 0.1);
    background-color: rgb(58, 50, 50);
    display: flex;
    flex-direction: column;
    align-items: center;
    
}

.product-image {
    width: 100%;
    height: 500px;
    background-image: url('product.jpg');
    background-size: cover;
    background-position: center;
   
}

.product-info {
    padding: 15px;
}

.product-title {
    color: #f3eded;
    font-size: 24px;
    margin-bottom: 10px;
}

.product-price {
    color: #db7500;
    font-size: 24px;
    font-weight: bold;
}

.product-description {
    color: #8dbd41;
    font-size: 20px;
    line-height: 1.5;
}

.product-button {
    display: block;
    background: linear-gradient(to right, #1860ad, #0056b3);
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
![g2](https://github.com/user-attachments/assets/d6c18981-378d-4025-ab05-f03ceeece21d)
![g1](https://github.com/user-attachments/assets/d0520aaf-e595-4c28-8cc4-a32fef57de4b)

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
    
    <link rel="stylesheet" href="css/box.css">

</head>
<body>
    <div class="stats-container">
        <div class="stat-box">
            <div class="stat-number">1,234</div>
            <div class="stat-label">ผู้ใช้งาน</div>
        </div>
        <div class="stat-box">
            <div class="stat-number">100K</div>
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
body {
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgb(226, 185, 219);
}
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
    padding: 5rem;
    text-align: center;
    background-color: white;
    border-radius: 15px;
    box-shadow: 0 2px 4px rgba(252, 3, 3, 0.1);
}

.stat-number {
    font-size: 3rem;
    font-weight: bold;
    color: #ff009d;
    margin-bottom: 0.5rem;
}

.stat-label {
    font-size: 1.5rem;
    color: #110808;
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
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![b1](https://github.com/user-attachments/assets/58b5d78e-beff-43cc-85f0-d6cb90501bd6)

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
    <link rel="stylesheet" href="css/text.css">
</head>
<body>
    <article class="blog-post">
        <header class="post-header">
            <h1 class="post-title">ระบบสุริยะ</h1>
            <div class="post-meta">โพสต์เมื่อ 7 กุมภาพันธ์ 2025 | โดย นาย รัฐภูมิ สอนเขียว</div>
        </header>
        
        <div class="post-content">
            <p>ระบบสุริยะ (Solar System) เป็นระบบดาวที่ประกอบไปด้วยดวงอาทิตย์เป็นศูนย์กลาง และมีวัตถุต่าง ๆ โคจรรอบ รวมถึงดาวเคราะห์ ดาวเคราะห์แคระ ดวงจันทร์ ดาวเคราะห์น้อย ดาวหาง และฝุ่นละอองในอวกาศ ระบบสุริยะเป็นส่วนหนึ่งของกาแล็กซีทางช้างเผือกและมีอายุประมาณ 4.6 พันล้านปี</p>

            <h2>องค์ประกอบของระบบสุริยะ</h2>
            <p>1. ดวงอาทิตย์

                ดวงอาทิตย์เป็นศูนย์กลางของระบบสุริยะ มีมวลมากถึง 99.86% ของมวลรวมทั้งหมดของระบบสุริยะ ทำให้มีแรงโน้มถ่วงสูงพอที่จะยึดดาวเคราะห์และวัตถุอื่น ๆ ให้อยู่ในวงโคจรของมัน ดวงอาทิตย์เป็นดาวฤกษ์ประเภท G-type main-sequence (G2V) และมีพลังงานมาจากปฏิกิริยานิวเคลียร์ฟิวชันที่เกิดขึ้นในแกนกลางของมัน
                
                2. ดาวเคราะห์
                
                ระบบสุริยะประกอบด้วยดาวเคราะห์หลัก 8 ดวง แบ่งออกเป็นสองกลุ่มหลัก ได้แก่:
                
                ดาวเคราะห์ชั้นใน (Terrestrial Planets) ประกอบด้วย ดาวพุธ ดาวศุกร์ โลก และดาวอังคาร มีลักษณะเป็นดาวเคราะห์หินที่มีพื้นผิวแข็ง
                
                ดาวเคราะห์ชั้นนอก (Gas Giants & Ice Giants) ประกอบด้วย ดาวพฤหัสบดี ดาวเสาร์ ดาวยูเรนัส และดาวเนปจูน ซึ่งมีองค์ประกอบหลักเป็นก๊าซและน้ำแข็ง
                
                3. ดาวเคราะห์แคระ
                
                ดาวเคราะห์แคระ (Dwarf Planets) คือวัตถุที่มีลักษณะคล้ายดาวเคราะห์แต่ไม่สามารถเคลียร์วงโคจรของตนเองจากเศษซากวัตถุอื่น ๆ ได้ ตัวอย่างเช่น พลูโต, อีริส, เฮาเมอา และเซเรส
                
                4. วัตถุขนาดเล็กในระบบสุริยะ
                
                นอกจากดาวเคราะห์และดาวเคราะห์แคระแล้ว ระบบสุริยะยังมีวัตถุขนาดเล็กมากมาย เช่น:
                
                ดาวเคราะห์น้อย (Asteroids): พบมากในแถบดาวเคราะห์น้อยระหว่างดาวอังคารและดาวพฤหัสบดี
                
                ดาวหาง (Comets): ประกอบด้วยน้ำแข็งและฝุ่น พบมากในแถบไคเปอร์ (Kuiper Belt) และกลุ่มเมฆออร์ต (Oort Cloud)
                
                อุกกาบาต (Meteoroids): วัตถุขนาดเล็กที่สามารถตกลงสู่พื้นผิวดาวเคราะห์และกลายเป็นอุกกาบาต (Meteorites)</p>

            

            <h2>วงโคจรและแรงโน้มถ่วง</h2>
            <p>แรงโน้มถ่วงของดวงอาทิตย์เป็นปัจจัยหลักที่ควบคุมการโคจรของวัตถุต่าง ๆ ในระบบสุริยะ ดาวเคราะห์แต่ละดวงโคจรเป็นวงรีรอบดวงอาทิตย์ตามกฎของเคปเลอร์ โดยมีระยะเวลาการโคจรแตกต่างกันขึ้นอยู่กับระยะห่างจากดวงอาทิตย์</p>
            <h2>การสำรวจระบบสุริยะ</h2>
            <p>มนุษย์ได้ส่งยานอวกาศหลายลำเพื่อสำรวจระบบสุริยะ เช่น:

                Voyager 1 และ 2: เดินทางออกจากระบบสุริยะและยังคงส่งข้อมูลกลับมา
                
                New Horizons: สำรวจพลูโตและแถบไคเปอร์
                
                Mars Rovers (เช่น Curiosity และ Perseverance): สำรวจดาวอังคารเพื่อค้นหาหลักฐานของสิ่งมีชีวิตในอดีต</p>
            <blockquote>
                "ระบบสุริยะเป็นระบบที่ซับซ้อนและเต็มไปด้วยวัตถุหลากหลายประเภท ตั้งแต่ดวงอาทิตย์ ดาวเคราะห์ ดาวเคราะห์แคระ ไปจนถึงดาวหางและฝุ่นละอองในอวกาศ การสำรวจระบบสุริยะช่วยให้เราเข้าใจต้นกำเนิดของโลกและเอกภพได้มากขึ้น รวมถึงความเป็นไปได้ของสิ่งมีชีวิตนอกโลก"
            </blockquote>
        </div>
    </article>
</body>
</html>
```
```css
body {
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgb(110, 4, 105);
}
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
            font-size: 3.5rem;
            color: #ffffff;
            margin-bottom: 0.5rem;
            line-height: 1.2;
        }

        .post-meta {
            color: #7cf79a;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .post-content {
            font-size: 1.5rem;
            line-height: 1.8;
            color: #ffffff;
        }

        .post-content p {
            margin-bottom: 2.0rem;
        }

        .post-content h2 {
            font-size: 1.8rem;
            color: #ffffff;
            margin: 2rem 0 1rem;
        }

        blockquote {
            font-style: italic;
            border-left: 4px solid #376392;
            margin: 1.5rem 0;
            padding-left: 1rem;
            color: #fffdfd;
        }

        @media (max-width: 768px) {
            .post-title {
                font-size: 2rem;
            }
        }
  
```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]
![t1](https://github.com/user-attachments/assets/1da38f25-f5d6-4a83-a57f-48319411df16)

![t2](https://github.com/user-attachments/assets/27ed40fc-601d-4050-b847-13539757929c)

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
<html>
<head>
    <link rel="stylesheet" href="css/flexbox.css">
    
</head>
<body>
    <div class="product-grid">
        <!-- สินค้าชิ้นที่ 1 -->
        <div class="product-card">
            <div class="product-image" style="background-image: url('images/love1.gif')"></div>
            <div class="product-details">
                <h3 class="product-title">กลิ่นหอมความรัก</h3>
                <div class="product-price">฿549</div>
                <div class="product-action">
                    <button class="add-to-cart">เพิ่มลงตะกร้า</button>
                </div>
            </div>
        </div>

        <!-- สินค้าชิ้นที่ 2 -->
        <div class="product-card">
            <div class="product-image" style="background-image: url('images/love2.gif')"></div>
            <div class="product-details">
                <h3 class="product-title">ปลาบนฟ้า</h3>
                <div class="product-price">฿499</div>
                <div class="product-action">
                    <button class="add-to-cart">เพิ่มลงตะกร้า</button>
                </div>
            </div>
        </div>

        <div class="product-card">
            <div class="product-image" style="background-image: url('images/love3.gif')"></div>
            <div class="product-details">
                <h3 class="product-title">หลวงตาบอกแล้วอย่าออกแว้นตอนตีสาม...เปรตมันดุ</h3>
                <div class="product-price">฿499</div>
                <div class="product-action">
                    <button class="add-to-cart">เพิ่มลงตะกร้า</button>
                </div>
            </div>
        </div>
        <div class="product-card">
            <div class="product-image" style="background-image: url('images/love4.gif')"></div>
            <div class="product-details">
                <h3 class="product-title">บทกวีของปีแสง</h3>
                <div class="product-price">฿599</div>
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
```css
body {
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgb(203, 185, 238);
}
.product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 20px;
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .product-card {
            background: rgb(255, 255, 255);
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
            height: 250px;
            background-color: #f5f5f5;
            background-size: cover;
            background-position: center;
        }

        .product-details {
            padding: 15px;
        }

        .product-title {
            font-size: 1.8rem;
            margin: 0 0 10px 0;
            color: #0f0d0d;
        }

        .product-price {
            font-size: 1.5rem;
            color: #1e630a;
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
            color: rgb(10, 10, 10);
            border: none;
            padding: 8px 15px;
            border-radius: 4px;
            cursor: pointer;
        }

        .add-to-cart:hover {
            background-color: #607c99;
        }

        @media (max-width: 768px) {
            .product-grid {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            }
        }

```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]

![f1](https://github.com/user-attachments/assets/c08dbb81-6a74-4ebb-a861-61da5b2979d4)


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
<html>
<head>
    <link rel="stylesheet" href="css/layout.css">
</head>
<body>
    <div class="dashboard">
        <header class="header">
            <h1>Cafe cake</h1>
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
                    <p>฿500,000</p>
                </div>
                <div class="stat-card">
                    <h3>จำนวนออเดอร์</h3>
                    <p>12,340</p>
                </div>
                <div class="stat-card">
                    <h3>ลูกค้าใหม่</h3>
                    <p>105</p>
                </div>
            </div>

            <div class="chart-container">
                <div class="chart">
                    <h3>กราฟแสดงยอดขาย</h3>
                    <div class="product-image" style="background-image: url('images/L1.png')"></div>
                    <!-- เพิ่มกราฟตามต้องการ -->
                </div>
                <div class="chart">
                    <h3>สัดส่วนสินค้าขายดี</h3>
                    <div class="product-image" style="background-image: url('images/L2.png')"></div>

                    <!-- เพิ่มกราฟตามต้องการ -->
                </div>
            </div>
        </main>
    </div>
</body>
</html>
```
```css
body {
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: rgb(247, 223, 243);
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
    background: rgb(245, 11, 139);
    padding: 1rem;
    box-shadow: 0 2px 4px rgba(255, 234, 234, 0.973);
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.sidebar {
    grid-area: sidebar;
    background: #e98fc7;
    color: rgb(14, 10, 10);
    padding: 1rem;
}
.product-image {
    width: 100%;
    height: 250px;
    background-color: #f5f5f5;
    background-size: cover;
    background-position: center;
}
.main-content {
    grid-area: main;
    padding: 1rem;
    background: #ce5ba2;
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
    box-shadow: 0 2px 4px rgba(223, 30, 120, 0.918);
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
    box-shadow: 0 2px 4px rgb(228, 27, 194);
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

```
[บันทึกภาพหน้าจอของผลลัพธ์การทดลอง]

![7](https://github.com/user-attachments/assets/a085f37a-15a9-45e6-80f2-13d2da6e6ca2)
