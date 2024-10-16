<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meesho Scrollable Page</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        .header {
            background-color: white;
            padding: 10px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            border-bottom: 1px solid #ddd;
        }
        .header img {
            height: 40px;
        }
        .header input[type="text"] {
            width: 400px;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        .header a {
            text-decoration: none;
            color: black;
            padding: 0 10px;
            font-weight: bold;
        }
        .header .sign-up-btn, .header .cart-btn {
            padding: 10px 15px;
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
            font-size: 14px;
            border-radius: 5px;
        }
        .banner {
            display: flex;
            justify-content: space-between;
            padding: 20px;
            background-color: white;
        }
        .banner-left {
            width: 60%;
        }
        .banner-left h1 {
            font-size: 30px;
            margin-bottom: 20px;
        }
        .banner-left ul {
            list-style: none;
            padding: 0;
        }
        .banner-left ul li {
            display: inline-block;
            margin-right: 15px;
            font-size: 14px;
        }
        .banner-right {
            width: 35%;
            background-color: #831067;
            color: white;
            border-radius: 10px;
            padding: 20px;
            text-align: center;
        }
        .banner-right img {
            width: 80px;
            height: 80px;
            margin-bottom: 10px;
        }
        .banner-right h2 {
            font-size: 20px;
            margin-bottom: 15px;
        }
        .banner-right .items {
            display: flex;
            justify-content: space-between;
        }
        .item {
            text-align: center;
        }
        .item img {
            width: 60px;
            height: 60px;
            border-radius: 5px;
        }
        .item p {
            margin: 5px 0;
            font-size: 14px;
            color: #ddd;
        }
        .download-btn {
            margin-top: 20px;
        }
        .download-btn a {
            text-decoration: none;
            color: white;
            background-color: #831067;
            padding: 10px 15px;
            border-radius: 5px;
        }
        .section {
            padding: 20px;
        }
        .section h2 {
            text-align: center;
            margin-bottom: 20px;
            font-size: 24px;
            color: #333;
        }
        .category-container, .product-container {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
        }
        .category-box, .product-box {
            background-color: white;
            width: 22%;
            margin: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            border-radius: 10px;
            text-align: center;
        }
        .category-box img, .product-box img {
            width: 100%;
            border-radius: 10px 10px 0 0;
        }
        .category-box h3, .product-box h3 {
            padding: 10px;
            font-size: 18px;
            color: #555;
        }
        .product-box p {
            color: #666;
            padding: 10px;
        }
        .view-all {
            background-color: #831067;
            color: white;
            padding: 10px;
            border-radius: 5px;
            text-align: center;
            text-decoration: none;
            display: block;
            width: 120px;
            margin: 20px auto;
            cursor: pointer;
        }
        .supplier-section {
            background-color: #f0f0f0;
            padding: 20px;
            text-align: center;
        }
        .supplier-section h3 {
            margin-bottom: 10px;
            font-size: 22px;
            color: #333;
        }
        .supplier-section button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }
        .download-section {
            text-align: center;
            padding: 20px;
        }
        .download-section h3 {
            font-size: 20px;
            color: #333;
            margin-bottom: 20px;
        }
        .download-btn {
            display: inline-block;
            padding: 10px 15px;
            margin-bottom: 20px;
            color: #831067;
            font-weight: bold;
            text-decoration: none;
            cursor: pointer;
        }
        .download-icons {
            display: flex;
            justify-content: center;
            gap: 20px;
        }
        .download-icons img {
            width: 150px;
            height: auto;
        }
        .hidden {
            display: none;
        }
        /* Sign Up Form Styles */
        #signUpForm, #cartPopup {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            z-index: 1000;
        }
        #signUpForm h2, #cartPopup h2 {
            margin-bottom: 15px;
        }
        #signUpForm label {
            display: block;
            margin: 10px 0 5px;
        }
        #signUpForm input {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        #signUpForm button[type="submit"], #closeCartBtn {
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
            padding: 10px;
            border-radius: 5px;
            margin-top: 10px;
        }
        #closeBtn, #closeCartBtn {
            background-color: #f44336;
            color: white;
            border: none;
            cursor: pointer;
            padding: 5px 10px;
            margin-top: 10px;
            border-radius: 5px;
        }
    </style>
</head>
<body>

    <!-- Header Section -->
    <div class="header">
        <img src="https://th.bing.com/th/id/OIP.rw994mz1-DGPDjY_rHC8kgAAAA?rs=1&pid=ImgDetMain" alt="Meesho Logo">
        <input type="text" placeholder="Try Saree, Kurti or Search by Product Code">
        <div>
            <a href="#">Download App</a>
            <a href="#">Become a Supplier</a>
            <a href="#">Newsroom</a>
            <button class="sign-up-btn" id="signUpBtn">Sign Up</button>
            <button class="cart-btn" id="cartBtn">Cart</button>
        </div>
    </div>

    <!-- Banner Section -->
    <div class="banner">
        <div class="banner-left">
            <h1>Lowest Prices, Best Quality Shopping</h1>
            <ul>
                <li>Free Delivery</li>
                <li>Cash on Delivery</li>
                <li>Easy Returns</li>
            </ul>
            <div class="download-btn">
                <a href="#">Download the Meesho App</a>
            </div>
        </div>
        <div class="banner-right">
            <h2>Get up to 25% off on first order</h2>
            <div class="items">
                <div class="item">
                    <img src="https://th.bing.com/th/id/OIP.8W6ApjeE-CT7v0oD7tfvCwHaGb?rs=1&pid=ImgDetMain/60" alt="Item 1">
                    <p>₹220</p>
                </div>
                <div class="item">
                    <img src="https://th.bing.com/th/id/OIP.CovBW2wagjUiy9niX9cooAHaL2?rs=1&pid=ImgDetMain/60" alt="Item 2">
                    <p>₹318</p>
                </div>
                <div class="item">
                    <img src="https://th.bing.com/th/id/OIP.KWivfOMFFd0xyreIWDxvlQAAAA?rs=1&pid=ImgDetMain/60" alt="Item 3">
                    <p>₹390</p>
                </div>
            </div>
        </div>
    </div>

    <!-- Categories Section -->
    <div class="section">
        <h2>Top Categories to choose from</h2>
        <div class="category-container">
            <div class="category-box">
                <img src="https://th.bing.com/th/id/OIP.jDh5BM_-hYKuBD0aHM7H0wAAAA?rs=1&pid=ImgDetMain/300x200" alt="Women's Store">
                <h3>Women's Store</h3>
            </div>
            <div class="category-box">
                <img src="https://th.bing.com/th/id/R.1f0c176740137c75e6bb809ae8561ca9?rik=XnQL7ddxNaG5Rg&riu=http%3a%2f%2fmenscraze.com%2fwp-content%2fuploads%2f2016%2f05%2fMens-Casual-Fashion-2.jpg&ehk=qth3iXPf8V9xoWdVbke4NqZGIAK61kFwxmVHPla4ChM%3d&risl=&pid=ImgRaw&r=0/300x200" alt="Men's Store">
                <h3>Men's Store</h3>
            </div>
            <div class="category-box">
                <img src="https://th.bing.com/th/id/OIP.XbA4gHd6ziXuvTsJrFO4HgAAAA?rs=1&pid=ImgDetMain/300x200" alt="Kid's Store">
                <h3>Kid's Store</h3>
            </div>
            <div class="category-box">
                <img src="https://th.bing.com/th/id/OIP.NfiLj5K6C7GGQfkIWLymEAHaHa?rs=1&pid=ImgDetMain/300x200" alt="Beauty and Health">
                <h3>Beauty & Health</h3>
            </div>
        </div>
        <a href="#" class="view-all">View All</a>
    </div>

    <!-- Essentials Section -->
    <div class="section">
        <h2>Essentials</h2>
        <div class="product-container">
            <div class="product-box">
                <img src="https://emailmarketing.deepfocus.in/oneeka/wp-content/uploads/2018/05/SkinEssentials.jpg" alt="Bath and Body">
                <h3>Bath and Body</h3>
                <p>From ₹299</p>
            </div>
            <div class="product-box">
                <img src="https://i1.wp.com/mdcreekmore.com/wp-content/uploads/2018/09/how-to-make-homemade-soap.jpg?resize=911,1000&ssl=1" alt="Soap bars">
                <h3>Soap bars</h3>
                <p>From ₹599</p>
            </div>
            <div class="product-box">
                <img src="https://i5.walmartimages.com/asr/58dcd01d-eb6f-4d5e-a5d7-aa8e08172c3a.c47cf8c76ed3e11b1d87ffd099de7407.png" alt="Supplements">
                <h3>Supplements</h3>
                <p>From ₹499</p>
            </div>
        </div>
        <a href="#" class="view-all">View All</a>
    </div>

    <!-- New Styles Section -->
    <div class="section">
        <h2>New Styles</h2>
        <div class="product-container">
            <div class="product-box">
                <img src="https://i.pinimg.com/originals/9d/92/1f/9d921fcc1a74cc4516d6cfbebfb26fb4.jpg" alt="Kurta Suit sets">
                <h3>Kurta Suit sets</h3>
                <p>From ₹999</p>
            </div>
            <div class="product-box">
                <img src="https://th.bing.com/th/id/OIP.rjdE8F2V48qWLcmLyoTEzgAAAA?rs=1&pid=ImgDetMain" alt="Lehengar">
                <h3>Lehengar</h3>
                <p>From ₹1,299</p>
            </div>
            <div class="product-box">
                <img src="https://i.pinimg.com/originals/6a/93/a4/6a93a40eb5bee60617b79c1c2dac6908.jpg" alt="Jumpsuits">
                <h3>Jumpsuits</h3>
                <p>From ₹899</p>
            </div>
        </div>
        <a href="#" class="view-all">View All</a>
    </div>

    <!-- Download App Section -->
    <div class="download-section">
        <h3>Download the Meesho App</h3>
        <div class="download-icons">
            <img src="https://th.bing.com/th/id/OIP.qVeTPJTsHmYVhkebFsL7JAHaHa?rs=1&pid=ImgDetMain/250x50" alt="Google Play">
            <img src="https://storage.googleapis.com/gweb-uniblog-publish-prod/images/Google_Play_Prism.max-2800x2800.png" alt="App Store">
        </div>
    </div>

    <!-- Sign Up Form -->
    <div id="signUpForm" class="hidden">
        <h2>Sign Up</h2>
        <form>
            <label for="username">Username:</label>
            <input type="text" id="username" name="username" required>
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>
            <label for="password">Password:</label>
            <input type="password" id="password" name="password" required>
            <button type="submit">Submit</button>
        </form>
        <button id="closeBtn">Close</button>
    </div>

    <script>
        // Toggle Sign Up Form
        document.getElementById('signUpBtn').addEventListener('click', function() {
            document.getElementById('signUpForm').classList.toggle('hidden');
        });
        document.getElementById('closeBtn').addEventListener('click', function() {
            document.getElementById('signUpForm').classList.add('hidden');
        });
    </script>
</body>
</html>

    <!-- Cart Popup -->
    <div id="cartPopup" class="hidden">
        <h2>Your Cart</h2>
        <p>Your cart is currently empty.</p>
        <button id="closeCartBtn">Close</button>
    </div>

    <!-- Sign Up Form -->
    <div id="signUpForm" class="hidden">
        <h2>Sign Up</h2>
        <form>
            <label for="username">Username:</label>
            <input type="text" id="username" name="username" required>
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>
            <label for="password">Password:</label>
            <input type="password" id="password" name="password" required>
            <button type="submit">Submit</button>
        </form>
        <button id="closeBtn">Close</button>
    </div>

    <script>
        // Sign Up Popup Logic
        document.getElementById('signUpBtn').addEventListener('click', function() {
            document.getElementById('signUpForm').classList.remove('hidden');
        });
        document.getElementById('closeBtn').addEventListener('click', function() {
            document.getElementById('signUpForm').classList.add('hidden');
        });

        // Cart Popup Logic
        document.getElementById('cartBtn').addEventListener('click', function() {
            document.getElementById('cartPopup').classList.remove('hidden');
        });
        document.getElementById('closeCartBtn').addEventListener('click', function() {
            document.getElementById('cartPopup').classList.add('hidden');
        });
    </script>
</body>
