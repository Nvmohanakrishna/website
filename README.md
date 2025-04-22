# Ex.07 Restaurant Website
# Date:
# AIM:
To develop a static Restaurant website to display the food items and services provided by them.

# DESIGN STEPS:
## Step 1:
Requirement collection.

## Step 2:
Creating the layout using HTML and CSS.

## Step 3:
Updating the sample content.

## Step 4:
Choose the appropriate style and color scheme.

## Step 5:
Validate the layout in various browsers.

## Step 6:
Validate the HTML code.

## Step 7:
Publish the website in the given URL.

# PROGRAM:

## index.html :

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[Restaurant Name] - Home</title>
    <link href="https://fonts.googleapis.com/css2?family=Merriweather:wght@700&family=Open+Sans&display=swap" rel="stylesheet">
    <style>
        /* Global Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        html {
            scroll-behavior: smooth;
        }
        body {
            font-family: 'Open Sans', sans-serif;
            color: #e0e0e0;
            line-height: 1.6;
            background: #1a1a1a;
        }
        h1, h2, h3 {
            font-family: 'Merriweather', serif;
            color: #8A2BE2;
            text-shadow: 0 0 10px #8A2BE2, 0 0 20px #8A2BE2;
        }
        a, button {
            transition: all 0.3s ease;
        }

        /* Header */
        header {
            background-color: rgba(51, 51, 51, 0.9);
            color: #fff;
            padding: 15px 0;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
        }
        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
        }
        nav ul li {
            margin: 0 20px;
        }
        nav ul li a {
            color: #00FFFF;
            text-decoration: none;
            font-weight: 600;
            padding: 10px 15px;
            text-shadow: 0 0 5px #00FFFF;
        }
        nav ul li a:hover {
            color: #39FF14;
            background-color: #222;
            border-radius: 5px;
            text-shadow: 0 0 10px #39FF14;
        }
        nav ul li a.active {
            color: #39FF14;
            font-weight: 700;
            text-shadow: 0 0 15px #39FF14;
        }

        /* Hero Section */
        .hero {
            position: relative;
            overflow: hidden;
            height: 500px;
            background: url('https://png.pngtree.com/thumb_back/fh260/background/20230705/pngtree-sophisticated-bar-and-restaurant-boasting-luxurious-modern-design-featuring-elegant-furnishings-image_3720689.jpg') no-repeat center center;
            background-size: cover;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
        }
        .hero::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.3);
            z-index: 1;
        }
        .hero h1, .hero p, .hero button {
            position: relative;
            z-index: 2;
        }
        .hero h1 {
            font-size: 3.5em;
            margin-bottom: 15px;
        }
        .hero p {
            font-size: 1.3em;
            margin-bottom: 25px;
            color: #e0e0e0;
        }
        .hero button {
            background: linear-gradient(90deg, #8A2BE2, #00FFFF);
            color: #fff;
            padding: 15px 30px;
            border: none;
            cursor: pointer;
            font-size: 1.1em;
            border-radius: 10px;
            box-shadow: 0 0 10px #00FFFF;
        }
        .hero button:hover {
            transform: scale(1.1);
            box-shadow: 0 0 20px #39FF14;
        }

        /* Featured Dishes */
        .featured {
            padding: 50px 20px;
            text-align: center;
            background: rgba(34, 34, 34, 0.7);
        }
        .featured h2 {
            margin-bottom: 30px;
            font-size: 2.5em;
        }
        .grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
            max-width: 1200px;
            margin: 0 auto;
        }
        .dish {
            background: rgba(26, 26, 26, 0.8);
            padding: 20px;
            border: 2px solid #00FFFF;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 255, 255, 0.2);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .dish:hover {
            transform: translateY(-10px);
            box-shadow: 0 0 20px rgba(57, 255, 20, 0.3);
        }
        .dish img {
            width: 100%;
            height: 180px;
            object-fit: cover;
            border-radius: 5px;
            border: 1px solid #39FF14;
        }
        .dish h3 {
            margin: 15px 0;
            font-size: 1.4em;
            color: #8A2BE2;
        }
        .dish p {
            color: #e0e0e0;
            font-size: 1em;
        }

        /* Masters Section */
        .masters {
            padding: 50px 20px;
            background: rgba(26, 26, 26, 0.9);
            text-align: center;
        }
        .masters h2 {
            margin-bottom: 30px;
            font-size: 2.5em;
        }
        .masters-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
            max-width: 1200px;
            margin: 0 auto;
        }
        .master {
            background: rgba(34, 34, 34, 0.9);
            padding: 20px;
            border: 2px solid #8A2BE2;
            border-radius: 10px;
            box-shadow: 0 0 15px rgba(138, 43, 226, 0.3);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .master:hover {
            transform: translateY(-10px);
            box-shadow: 0 0 25px rgba(57, 255, 20, 0.5);
        }
        .master img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 5px;
            border: 1px solid #00FFFF;
        }
        .master h3 {
            margin: 15px 0;
            font-size: 1.4em;
        }
        .master p {
            color: #e0e0e0;
            font-size: 1em;
        }

        /* About and Contact Section */
        .info-section {
            padding: 50px 20px;
            background: url('https://t3.ftcdn.net/jpg/02/05/87/60/360_F_205876015_hYYs7ugqoU8QAobSS3TbnGQ92qyS5gEc.jpg') no-repeat center center;
            background-size: cover;
        }
        .info-section::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.6);
            z-index: 1;
        }
        .about, .contact {
            position: relative;
            z-index: 2;
            text-align: center;
        }
        .about h2, .contact h2 {
            margin-bottom: 20px;
            font-size: 2.5em;
        }
        .row {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
        }
        .column {
            width: 48%;
        }
        .column img {
            width: 100%;
            height: auto;
            border-radius: 10px;
            border: 2px solid #8A2BE2;
            box-shadow: 0 0 10px #8A2BE2;
        }
        .about p {
            font-size: 1.2em;
            color: #e0e0e0;
            margin-bottom: 20px;
        }
        .contact p {
            margin-bottom: 15px;
            font-size: 1.1em;
            color: #e0e0e0;
        }
        form {
            display: flex;
            flex-direction: column;
            align-items: center;
            max-width: 500px;
            margin: 20px auto;
        }
        input, textarea {
            width: 100%;
            padding: 12px;
            margin-bottom: 15px;
            border: 2px solid #00FFFF;
            border-radius: 10px;
            background: rgba(26, 26, 26, 0.9);
            color: #e0e0e0;
            transition: border-color 0.3s ease, box-shadow 0.3s ease;
        }
        input:focus, textarea:focus {
            border-color: #39FF14;
            box-shadow: 0 0 10px #39FF14;
            outline: none;
        }
        button {
            background: linear-gradient(90deg, #8A2BE2, #00FFFF);
            color: #fff;
            padding: 15px 30px;
            border: none;
            cursor: pointer;
            border-radius: 10px;
            font-size: 1.1em;
            box-shadow: 0 0 10px #00FFFF;
        }
        button:hover {
            transform: scale(1.05);
            box-shadow: 0 0 20px #39FF14;
        }

        /* Footer */
        footer {
            background-color: rgba(51, 51, 51, 0.9);
            color: #fff;
            text-align: center;
            padding: 15px 0;
            margin-top: 20px;
            border-top: 2px solid #00FFFF;
        }

        /* Animation */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        main > section {
            animation: fadeIn 1s ease-out;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            nav ul {
                flex-direction: column;
                align-items: center;
            }
            nav ul li {
                margin: 10px 0;
            }
            .hero {
                height: 350px;
            }
            .hero h1 {
                font-size: 2.2em;
            }
            .hero p {
                font-size: 1.1em;
            }
            .grid, .masters-grid {
                grid-template-columns: 1fr;
            }
            .row {
                flex-direction: column;
            }
            .column {
                width: 100%;
                margin-bottom: 20px;
            }
        }

        @media (min-width: 1200px) {
            .grid, .masters-grid {
                grid-template-columns: repeat(3, 1fr);
            }
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <ul>
                <li><a href="index.html" class="active">Home</a></li>
                <li><a href="menu.html">Menu</a></li>
                <li><a href="masters.html">Masters</a></li>
                <li><a href="contact.html">Contact</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <section class="hero">
            <h1>Welcome to REMOSUJ</h1>
            <p>Experience a culinary journey like never before</p>
            <button onclick="location.href='menu.html'">Explore Menu</button>
        </section>
        <section class="featured">
            <h2>Featured Dishes</h2>
            <div class="grid">
                <div class="dish">
                    <img src="images (1).jpg" alt="Grilled Salmon">
                    <h3>Grilled Salmon</h3>
                    <p>Freshly grilled with a zesty glaze</p>
                </div>
                <div class="dish">
                    <img src="images (2).jpg" alt="Pasta Primavera">
                    <h3>Pasta Primavera</h3>
                    <p>Seasonal veggies in a creamy sauce</p>
                </div>
                <div class="dish">
                    <img src="images (3).jpg" alt="Chocolate Cake">
                    <h3>Chocolate Cake</h3>
                    <p>Decadent and rich dessert</p>
                </div>
                <div class="dish">
                    <img src="images (4).jpg" alt="Beef Steak">
                    <h3>Beef Steak</h3>
                    <p>Juicy steak with herb butter</p>
                </div>
                <div class="dish">
                    <img src="image_1.jpg" alt="Caesar Salad">
                    <h3>Caesar Salad</h3>
                    <p>Crisp romaine with dressing</p>
                </div>
                <div class="dish">
                    <img src="download.jpg" alt="Seafood Pasta">
                    <h3>Seafood Pasta</h3>
                    <p>Shrimp and clams in garlic sauce</p>
                </div>
            </div>
        </section>
        <section class="masters">
            <h2>Our Masters</h2>
            <div class="masters-grid">
                <div class="master">
                    <img src="images.jpg" alt="Chef">
                    <h3>Chef</h3>
                    <p>Master of culinary arts</p>
                </div>
                <div class="master">
                    <img src="Screenshot 2025-04-22 235616.png" alt="Manager">
                    <h3>Manager</h3>
                    <p>Oversees operations</p>
                </div>
                <div class="master">
                    <img src="Iron-Chef-Ming-Tsai.jpg" alt="Accountant">
                    <h3>Accountant</h3>
                    <p>Handles finances</p>
                </div>
                <div class="master">
                    <img src="MHM-banner-1.webp" alt="Professional Cook">
                    <h3>Professional Cook</h3>
                    <p>Expert in dish preparation</p>
                </div>
                <div class="master">
                    <img src="Executive-Chef-The-Pathway-from-Culinary-Student-to-Master-Chef-870x600.jpg" alt="Cook Master">
                    <h3>Cook Master</h3>
                    <p>Head of kitchen mastery</p>
                </div>
                <div class="master">
                    <img src="OIP.jpg" alt="Receptionist">
                    <h3>Receptionist</h3>
                    <p>Welcomes and assists guests</p>
                </div>
            </div>
        </section>
        <section class="info-section">
            <section class="about">
                <h2>About Us</h2>
                <div class="row">
                    <div class="column">
                        <p>REMOSUJ has been delighting taste buds since 2006. Our commitment to quality ingredients and exceptional service sets us apart in the culinary world.</p>
                    </div>
                </div>
            </section>
            <section class="contact">
                <h2>Contact Us</h2>
                <p>Address: 123 Main St, City, State</p>
                <p>Phone: (123) 456-7890</p>
                <p>Email: info@REMOSUJ.com</p>
                <form action="https://formspree.io/your-email" method="POST">
                    <input type="text" name="name" placeholder="Your Name" required>
                    <input type="email" name="email" placeholder="Your Email" required>
                    <textarea name="message" placeholder="Your Message" required></textarea>
                    <button type="submit">Send Message</button>
                </form>
            </section>
        </section>
    </main>
    <footer>
        <p>© 2025 REMOSUJ</p>
    </footer>
</body>
</html>
```


## menu.html :

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[Restaurant Name] - Menu</title>
    <link href="https://fonts.googleapis.com/css2?family=Merriweather:wght@700&family=Open+Sans&display=swap" rel="stylesheet">
    <style>
        /* Global Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        html {
            scroll-behavior: smooth;
        }
        body {
            font-family: 'Open Sans', sans-serif;
            color: #e0e0e0;
            line-height: 1.6;
            background: #1a1a1a;
        }
        h1, h2, h3 {
            font-family: 'Merriweather', serif;
            color: #8A2BE2;
            text-shadow: 0 0 10px #8A2BE2, 0 0 20px #8A2BE2;
        }
        a, button {
            transition: all 0.3s ease;
        }

        /* Header */
        header {
            background-color: rgba(51, 51, 51, 0.9);
            color: #fff;
            padding: 15px 0;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
        }
        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
        }
        nav ul li {
            margin: 0 20px;
        }
        nav ul li a {
            color: #00FFFF;
            text-decoration: none;
            font-weight: 600;
            padding: 10px 15px;
            text-shadow: 0 0 5px #00FFFF;
        }
        nav ul li a:hover {
            color: #39FF14;
            background-color: #222;
            border-radius: 5px;
            text-shadow: 0 0 10px #39FF14;
        }
        nav ul li a.active {
            color: #39FF14;
            font-weight: 700;
            text-shadow: 0 0 15px #39FF14;
        }

        /* Hero Section */
        .hero {
            position: relative;
            overflow: hidden;
            height: 400px;
            background: url('https://png.pngtree.com/thumb_back/fh260/background/20230705/pngtree-sophisticated-bar-and-restaurant-boasting-luxurious-modern-design-featuring-elegant-furnishings-image_3720689.jpg') no-repeat center center;
            background-size: cover;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
        }
        .hero::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.3);
            z-index: 1;
        }
        .hero h1, .hero p, .hero button {
            position: relative;
            z-index: 2;
        }
        .hero h1 {
            font-size: 3em;
            margin-bottom: 15px;
        }
        .hero p {
            font-size: 1.2em;
            margin-bottom: 25px;
            color: #e0e0e0;
        }
        .hero button {
            background: linear-gradient(90deg, #8A2BE2, #00FFFF);
            color: #fff;
            padding: 12px 25px;
            border: none;
            cursor: pointer;
            font-size: 1.1em;
            border-radius: 10px;
            box-shadow: 0 0 10px #00FFFF;
        }
        .hero button:hover {
            transform: scale(1.1);
            box-shadow: 0 0 20px #39FF14;
        }

        /* Menu Section */
        .menu {
            padding: 50px 20px;
            background: rgba(34, 34, 34, 0.7);
            text-align: center;
        }
        .menu h2 {
            margin-bottom: 30px;
            font-size: 2.5em;
        }
        .menu-category {
            margin-bottom: 40px;
        }
        .menu-category h3 {
            font-size: 2em;
            margin-bottom: 20px;
        }
        .menu-item {
            display: inline-block;
            width: 45%;
            background: rgba(26, 26, 26, 0.8);
            padding: 15px;
            margin: 10px;
            border: 2px solid #00FFFF;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 255, 255, 0.2);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .menu-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 0 20px rgba(57, 255, 20, 0.3);
        }
        .menu-item h4 {
            font-size: 1.3em;
            color: #8A2BE2;
            margin-bottom: 5px;
        }
        .menu-item p {
            font-size: 1em;
            color: #e0e0e0;
            margin-bottom: 5px;
        }
        .menu-item span {
            color: #39FF14;
            font-weight: bold;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            nav ul {
                flex-direction: column;
                align-items: center;
            }
            nav ul li {
                margin: 10px 0;
            }
            .hero {
                height: 300px;
            }
            .hero h1 {
                font-size: 2.2em;
            }
            .hero p {
                font-size: 1.1em;
            }
            .menu-item {
                width: 100%;
                margin: 10px 0;
            }
        }

        @media (min-width: 1200px) {
            .menu-item {
                width: 45%;
            }
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <ul>
                <li><a href="index.html">Home</a></li>
                <li><a href="menu.html" class="active">Menu</a></li>
                <li><a href="masters.html">Masters</a></li>
                <li><a href="contact.html">Contact</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <section class="hero">
            <h1>REMOSUJ Menu</h1>
            <p>Explore our exquisite selection of dishes</p>
            <button onclick="location.href='#menu'">View Menu</button>
        </section>
        <section class="menu" id="menu">
            <h2>Our Menu</h2>

            <div class="menu-category">
                <h3>Appetizers</h3>
                <div class="menu-item">
                    <h4>Garlic Bread</h4>
                    <p>Crispy bread with garlic butter</p>
                    <span>$5.99</span>
                </div>
                <div class="menu-item">
                    <h4>Bruschetta</h4>
                    <p>Tomato and basil on toasted bread</p>
                    <span>$6.49</span>
                </div>
            </div>

            <div class="menu-category">
                <h3>Main Courses</h3>
                <div class="menu-item">
                    <h4>Grilled Salmon</h4>
                    <p>Freshly grilled with a zesty glaze</p>
                    <span>$18.99</span>
                </div>
                <div class="menu-item">
                    <h4>Pasta Primavera</h4>
                    <p>Seasonal veggies in a creamy sauce</p>
                    <span>$14.99</span>
                </div>
                <div class="menu-item">
                    <h4>Beef Steak</h4>
                    <p>Juicy steak with herb butter</p>
                    <span>$22.99</span>
                </div>
            </div>

            <div class="menu-category">
                <h3>Desserts</h3>
                <div class="menu-item">
                    <h4>Chocolate Cake</h4>
                    <p>Decadent and rich dessert</p>
                    <span>$7.99</span>
                </div>
                <div class="menu-item">
                    <h4>Tiramisu</h4>
                    <p>Classic Italian coffee-flavored dessert</p>
                    <span>$8.49</span>
                </div>
            </div>

            <div class="menu-category">
                <h3>Beverages</h3>
                <div class="menu-item">
                    <h4>House Wine</h4>
                    <p>Red or white, served by the glass</p>
                    <span>$9.99</span>
                </div>
                <div class="menu-item">
                    <h4>Fresh Lemonade</h4>
                    <p>Homemade with real lemons</p>
                    <span>$4.99</span>
                </div>
            </div>
        </section>
    </main>
    <footer>
        <p>© 2025 REMOSUJ</p>
    </footer>
</body>
</html>
```
# OUTPUT:

![image](https://github.com/user-attachments/assets/a3a27379-ea0f-4444-94c8-1634c972d0a5)

<br>
<br>

![image](https://github.com/user-attachments/assets/f0fd6d18-3eba-4497-9d23-3971d363e22b)

<br>
<br>

![image](https://github.com/user-attachments/assets/52eabf94-aa47-404f-8448-f9bf00e62b21)

## OUTPUT ;

![image](https://github.com/user-attachments/assets/181ae605-ce7a-45ba-8ab4-ad576b96a372)


<br>
<br>

![image](https://github.com/user-attachments/assets/2f80cac6-a267-4acb-bc45-a00a4230cc1f)

<br>
<br>


# RESULT:
The program for designing software company website using HTML and CSS is completed successfully.
