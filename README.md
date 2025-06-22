<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FOMTIME - Premium Fashion & Lifestyle</title>
    <meta name="description" content="Discover premium fashion and lifestyle products at FOMTIME. Shop the latest trends with fast shipping and secure payment options.">
    <meta name="keywords" content="fashion, lifestyle, premium, shopping, online store">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
            background-color: #f8f9fa;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header Styles */
        header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 1rem 0;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .logo {
            font-size: 2rem;
            font-weight: bold;
            text-decoration: none;
            color: white;
            background: linear-gradient(45deg, #fff, #f0f0f0);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-menu a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            padding: 0.5rem 1rem;
            border-radius: 25px;
        }

        .nav-menu a:hover {
            background: rgba(255,255,255,0.2);
            transform: translateY(-2px);
        }

        .header-actions {
            display: flex;
            gap: 1rem;
            align-items: center;
        }

        .search-bar {
            position: relative;
        }

        .search-bar input {
            padding: 0.5rem 2.5rem 0.5rem 1rem;
            border: none;
            border-radius: 25px;
            width: 250px;
            outline: none;
        }

        .search-btn {
            position: absolute;
            right: 5px;
            top: 50%;
            transform: translateY(-50%);
            background: none;
            border: none;
            cursor: pointer;
            padding: 0.5rem;
        }

        .cart-icon, .user-icon {
            background: rgba(255,255,255,0.2);
            padding: 0.7rem;
            border-radius: 50%;
            cursor: pointer;
            transition: all 0.3s ease;
            position: relative;
        }

        .cart-icon:hover, .user-icon:hover {
            background: rgba(255,255,255,0.3);
            transform: scale(1.1);
        }

        .cart-count {
            position: absolute;
            top: -5px;
            right: -5px;
            background: #ff4757;
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.8rem;
            font-weight: bold;
        }

        /* Page Sections */
        .page-section {
            display: none;
            min-height: calc(100vh - 200px);
            padding: 2rem 0;
        }

        .page-section.active {
            display: block;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 4rem 0;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grain" width="100" height="100" patternUnits="userSpaceOnUse"><circle cx="25" cy="25" r="1" fill="%23ffffff" opacity="0.1"/><circle cx="75" cy="75" r="1" fill="%23ffffff" opacity="0.1"/></pattern></defs><rect width="100" height="100" fill="url(%23grain)"/></svg>');
            opacity: 0.3;
        }

        .hero-content {
            position: relative;
            z-index: 1;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .cta-button {
            background: linear-gradient(45deg, #ff6b6b, #ee5a24);
            color: white;
            padding: 1rem 2rem;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            display: inline-block;
            box-shadow: 0 4px 15px rgba(255,107,107,0.3);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(255,107,107,0.4);
        }

        /* Categories Grid */
        .categories-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .category-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .category-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.2);
        }

        .category-image {
            height: 200px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: white;
        }

        .category-content {
            padding: 1.5rem;
            text-align: center;
        }

        .category-content h3 {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            color: #333;
        }

        /* Products Grid */
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
            margin: 2rem 0;
        }

        .product-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.15);
        }

        .product-image {
            height: 250px;
            background: linear-gradient(45deg, #f093fb, #f5576c);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            color: white;
            position: relative;
        }

        .product-badge {
            position: absolute;
            top: 10px;
            left: 10px;
            background: #ff4757;
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 15px;
            font-size: 0.8rem;
            font-weight: bold;
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-info h3 {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
            color: #333;
        }

        .product-price {
            font-size: 1.3rem;
            font-weight: bold;
            color: #667eea;
            margin-bottom: 1rem;
        }

        .add-to-cart {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            border: none;
            padding: 0.8rem 1.5rem;
            border-radius: 25px;
            cursor: pointer;
            font-weight: bold;
            width: 100%;
            transition: all 0.3s ease;
        }

        .add-to-cart:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(102,126,234,0.3);
        }

        /* Product Detail Styles */
        .product-detail {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            margin: 2rem 0;
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
        }

        .product-detail-image {
            height: 400px;
            background: linear-gradient(45deg, #f093fb, #f5576c);
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: white;
        }

        .product-detail-info h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: #333;
        }

        .product-detail-price {
            font-size: 2rem;
            font-weight: bold;
            color: #667eea;
            margin-bottom: 1rem;
        }

        .product-description {
            margin-bottom: 2rem;
            line-height: 1.8;
            color: #666;
        }

        .quantity-selector {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .quantity-btn {
            background: #667eea;
            color: white;
            border: none;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 1.2rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .quantity-input {
            width: 60px;
            text-align: center;
            padding: 0.5rem;
            border: 2px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
        }

        /* Checkout Styles */
        .checkout-container {
            display: grid;
            grid-template-columns: 1fr 400px;
            gap: 3rem;
            margin: 2rem 0;
        }

        .checkout-form {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: bold;
            color: #333;
        }

        .form-group input, .form-group select {
            width: 100%;
            padding: 0.8rem;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus, .form-group select:focus {
            outline: none;
            border-color: #667eea;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
        }

        .order-summary {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            height: fit-content;
        }

        .summary-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 1rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid #eee;
        }

        .summary-total {
            display: flex;
            justify-content: space-between;
            font-size: 1.3rem;
            font-weight: bold;
            color: #333;
            margin-top: 1rem;
            padding-top: 1rem;
            border-top: 2px solid #667eea;
        }

        .place-order-btn {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            border: none;
            padding: 1rem 2rem;
            border-radius: 25px;
            cursor: pointer;
            font-weight: bold;
            width: 100%;
            font-size: 1.1rem;
            margin-top: 1rem;
            transition: all 0.3s ease;
        }

        .place-order-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(102,126,234,0.3);
        }

        /* Mobile Menu */
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 1rem;
            }

            .nav-menu {
                display: none;
                width: 100%;
                flex-direction: column;
                gap: 0;
            }

            .nav-menu.active {
                display: flex;
            }

            .mobile-menu-btn {
                display: block;
            }

            .search-bar input {
                width: 200px;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .categories-grid {
                grid-template-columns: 1fr;
            }

            .products-grid {
                grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            }

            .product-detail {
                grid-template-columns: 1fr;
                gap: 2rem;
            }

            .checkout-container {
                grid-template-columns: 1fr;
            }

            .form-row {
                grid-template-columns: 1fr;
            }
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .fade-in-up {
            animation: fadeInUp 0.6s ease-out;
        }

        /* Loading Animation */
        .loading {
            display: inline-block;
            width: 20px;
            height: 20px;
            border: 3px solid rgba(255,255,255,.3);
            border-radius: 50%;
            border-top-color: #fff;
            animation: spin 1s ease-in-out infinite;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        /* Success Message */
        .success-message {
            background: linear-gradient(45deg, #00b894, #00a085);
            color: white;
            padding: 1rem;
            border-radius: 8px;
            margin: 1rem 0;
            text-align: center;
            display: none;
        }

        .success-message.show {
            display: block;
            animation: fadeInUp 0.5s ease-out;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-content">
                <a href="#" class="logo" onclick="showPage('home')">FOMTIME</a>
                
                <nav>
                    <ul class="nav-menu" id="navMenu">
                        <li><a href="#" onclick="showPage('home')">Home</a></li>
                        <li><a href="#" onclick="showPage('categories')">Categories</a></li>
                        <li><a href="#" onclick="showPage('products')">Products</a></li>
                        <li><a href="#" onclick="showPage('about')">About</a></li>
                        <li><a href="#" onclick="showPage('contact')">Contact</a></li>
                    </ul>
                </nav>

                <div class="header-actions">
                    <div class="search-bar">
                        <input type="text" placeholder="Search products..." id="searchInput">
                        <button class="search-btn" onclick="searchProducts()">🔍</button>
                    </div>
                    
                    <div class="user-icon" onclick="showPage('login')">👤</div>
                    
                    <div class="cart-icon" onclick="showPage('cart')">
                        🛒
                        <span class="cart-count" id="cartCount">0</span>
                    </div>
                </div>

                <button class="mobile-menu-btn" onclick="toggleMobileMenu()">☰</button>
            </div>
        </div>
    </header>

    <!-- Home Page -->
    <section id="home" class="page-section active">
        <div class="hero">
            <div class="container">
                <div class="hero-content fade-in-up">
                    <h1>Welcome to FOMTIME</h1>
                    <p>Discover Premium Fashion & Lifestyle Products</p>
                    <a href="#" class="cta-button" onclick="showPage('products')">Shop Now</a>
                </div>
            </div>
        </div>

        <div class="container">
            <h2 style="text-align: center; margin: 3rem 0 2rem; font-size: 2.5rem; color: #333;">Featured Categories</h2>
            <div class="categories-grid">
                <div class="category-card fade-in-up" onclick="showCategoryProducts('fashion')">
                    <div class="category-image">👗</div>
                    <div class="category-content">
                        <h3>Fashion</h3>
                        <p>Latest trends in clothing and accessories</p>
                    </div>
                </div>
                <div class="category-card fade-in-up" onclick="showCategoryProducts('electronics')">
                    <div class="category-image">📱</div>
                    <div class="category-content">
                        <h3>Electronics</h3>
                        <p>Cutting-edge technology and gadgets</p>
                    </div>
                </div>
                <div class="category-card fade-in-up" onclick="showCategoryProducts('lifestyle')">
                    <div class="category-image">🏠</div>
                    <div class="category-content">
                        <h3>Lifestyle</h3>
                        <p>Home decor and lifestyle products</p>
                    </div>
                </div>
                <div class="category-card fade-in-up" onclick="showCategoryProducts('sports')">
                    <div class="category-image">⚽</div>
                    <div class="category-content">
                        <h3>Sports</h3>
                        <p>Sports equipment and fitness gear</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Categories Page -->
    <section id="categories" class="page-section">
        <div class="container">
            <h1 style="text-align: center; margin: 2rem 0; font-size: 2.5rem; color: #333;">All Categories</h1>
            <div class="categories-grid">
                <div class="category-card" onclick="showCategoryProducts('fashion')">
                    <div class="category-image">👗</div>
                    <div class="category-content">
                        <h3>Fashion & Apparel</h3>
                        <p>Clothing, shoes, and accessories for all styles</p>
                    </div>
                </div>
                <div class="category-card" onclick="showCategoryProducts('electronics')">
                    <div class="category-image">📱</div>
                    <div class="category-content">
                        <h3>Electronics</h3>
                        <p>Smartphones, laptops, and tech accessories</p>
                    </div>
                </div>
                <div class="category-card" onclick="showCategoryProducts('lifestyle')">
                    <div class="category-image">🏠</div>
                    <div class="category-content">
                        <h3>Home & Lifestyle</h3>
                        <p>Furniture, decor, and home essentials</p>
                    </div>
                </div>
                <div class="category-card" onclick="showCategoryProducts('sports')">
                    <div class="category-image">⚽</div>
                    <div class="category-content">
                        <h3>Sports & Fitness</h3>
                        <p>Exercise equipment and sporting goods</p>
                    </div>
                </div>
                <div class="category-card" onclick="showCategoryProducts('beauty')">
                    <div class="category-image">💄</div>
                    <div class="category-content">
                        <h3>Beauty & Health</h3>
                        <p>Skincare, makeup, and wellness products</p>
                    </div>
                </div>
                <div class="category-card" onclick="showCategoryProducts('books')">
                    <div class="category-image">📚</div>
                    <div class="category-content">
                        <h3>Books & Media</h3>
                        <p>Books, magazines, and entertainment</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Products Page -->
    <section id="products" class="page-section">
        <div class="container">
            <h1 style="text-align: center; margin: 2rem 0; font-size: 2.5rem; color: #333;">Our Products</h1>
            <div class="products-grid" id="productsGrid">
                <!-- Products will be dynamically loaded here -->
            </div>
        </div>
    </section>

    <!-- Product Detail Page -->
    <section id="product-detail" class="page-section">
        <div class="container">
            <div class="product-detail" id="productDetailContent">
                <!-- Product detail content will be loaded here -->
            </div>
        </div>
    </section>

    <!-- Cart Page -->
    <section id="cart" class="page-section">
        <div class="container">
            <h1 style="text-align: center; margin: 2rem 0; font-size: 2.5rem; color: #333;">Shopping Cart</h1>
            <div id="cartContent">
                <div style="text-align: center; padding: 3rem; background: white; border-radius: 15px; box-shadow: 0 5px 20px rgba(0,0,0,0.1);">
                    <h3>Your cart is empty</h3>
                    <p style="margin: 1rem 0; color: #666;">Add some products to get started!</p>
                    <a href="#" class="cta-button" onclick="showPage('products')">Continue Shopping</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Checkout Page -->
    <section id="checkout" class="page-section">
        <div class="container">
            <h1 style="text-align: center; margin: 2rem 0; font-size: 2.5rem; color: #333;">Checkout</h1>
            <div class="checkout-container">
                <div class="checkout-form">
                    <h2 style="margin-bottom: 2rem;">Shipping Information</h2>
                    <form id="checkoutForm">
                        <div class="form-row">
                            <div class="form-group">
                                <label for="firstName">First Name</label>
                                <input type="text" id="firstName" name="firstName" required>
                            </div>
                            <div class="form-group">
                                <label for="lastName">Last Name</label>
                                <input type="text" id="lastName" name="lastName" required>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label for="email">Email Address</label>
                            <input type="email" id="email" name="email" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="address">Street Address</label>
                            <input type="text" id="address" name="address" required>
                        </div>
                        
                        <div class="form-row">
                            <div class="form-group">
                                <label for="city">City</label>
                                <input type="text" id="city" name="city" required>
                            </div>
                            <div class="form-group">
                                <label for="zipCode">Zip Code</label>
                                <input type="text" id="zipCode" name="zipCode" required>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label for="country">Country</label>
                            <select id="country" name="country" required>
                                <option value="">Select Country</option>
                                <option value="US">United States</option>
                                <option value="CA">Canada</option>
                                <option value="UK">United Kingdom</option>
                                <option value="DE">Germany</option>
                                <option value="FR">France</option>
                                <option value="TR">Turkey</option>
                                <option value="AU">Australia</option>
                                <option value="JP">Japan</option>
                            </select>
                        </div>

                        <h2 style="margin: 2rem 0 1rem;">Payment Information</h2>
                        
                        <div class="form-group">
                            <label for="cardNumber">Card Number</label>
                            <input type="text" id="cardNumber" name="cardNumber" placeholder="1234 5678 9012 3456" required>
                        </div>
                        
                        <div class="form-row">
                            <div class="form-group">
                                <label for="expiryDate">Expiry Date</label>
                                <input type="text" id="expiryDate" name="expiryDate" placeholder="MM/YY" required>
                            </div>
                            <div class="form-group">
                                <label for="cvv">CVV</label>
                                <input type="text" id="cvv" name="cvv" placeholder="123" required>
                            </div>
                        </div>
                    </form>
                </div>

                <div class="order-summary">
                    <h2 style="margin-bottom: 2rem;">Order Summary</h2>
                    <div class="summary-item">
                        <span>Subtotal:</span>
                        <span>$299.97</span>
                    </div>
                    <div class="summary-item">
                        <span>Shipping:</span>
                        <span>$9.99</span>
                    </div>
                    <div class="summary-item">
                        <span>Tax:</span>
                        <span>$24.00</span>
                    </div>
                    <div class="summary-total">
                        <span>Total:</span>
                        <span>$333.96</span>
                    </div>
                    <button class="place-order-btn" onclick="placeOrder()">
                        <span id="orderBtnText">Place Order</span>
                        <span id="orderBtnLoader" class="loading" style="display: none;"></span>
                    </button>
                    <div class="success-message" id="orderSuccess">
                        Order placed successfully! 🎉
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Page -->
    <section id="about" class="page-section">
        <div class="container">
            <div style="background: white; padding: 3rem; border-radius: 15px; box-shadow: 0 5px 20px rgba(0,0,0,0.1); margin: 2rem 0;">
                <h1 style="text-align: center; margin-bottom: 2rem; font-size: 2.5rem; color: #333;">About FOMTIME</h1>
                <p style="font-size: 1.2rem; line-height: 1.8; margin-bottom: 2rem; color: #666;">
                    FOMTIME is your premier destination for premium fashion and lifestyle products. We curate the finest selection of items from around the world, bringing you quality, style, and innovation in every purchase.
                </p>
                <p style="font-size: 1.1rem; line-height: 1.8; margin-bottom: 2rem; color: #666;">
                    Founded with a passion for excellence, we believe that everyone deserves access to high-quality products that enhance their lifestyle. Our team works tirelessly to source unique items and deliver exceptional customer service.
                </p>
                <div style="text-align: center; margin-top: 3rem;">
                    <h2 style="color: #333; margin-bottom: 1rem;">Why Choose FOMTIME?</h2>
                    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 2rem; margin-top: 2rem;">
                        <div style="text-align: center;">
                            <div style="font-size: 2rem; margin-bottom: 1rem;">🚚</div>
                            <h3>Fast Shipping</h3>
                            <p>Free worldwide shipping on orders over $50</p>
                        </div>
                        <div style="text-align: center;">
                            <div style="font-size: 2rem; margin-bottom: 1rem;">🔒</div>
                            <h3>Secure Payment</h3>
                            <p>Your payment information is always safe</p>
                        </div>
                        <div style="text-align: center;">
                            <div style="font-size: 2rem; margin-bottom: 1rem;">↩️</div>
                            <h3>Easy Returns</h3>
                            <p>30-day return policy for your peace of mind</p>
                        </div>
                        <div style="text-align: center;">
                            <div style="font-size: 2rem; margin-bottom: 1rem;">💬</div>
                            <h3>24/7 Support</h3>
                            <p>Customer service available around the clock</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Page -->
    <section id="contact" class="page-section">
        <div class="container">
            <div style="background: white; padding: 3rem; border-radius: 15px; box-shadow: 0 5px 20px rgba(0,0,0,0.1); margin: 2rem 0;">
                <h1 style="text-align: center; margin-bottom: 2rem; font-size: 2.5rem; color: #333;">Contact Us</h1>
                <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 3rem;">
                    <div>
                        <h2 style="color: #333; margin-bottom: 1rem;">Get in Touch</h2>
                        <form id="contactForm">
                            <div class="form-group">
                                <label for="contactName">Name</label>
                                <input type="text" id="contactName" name="contactName" required>
                            </div>
                            <div class="form-group">
                                <label for="contactEmail">Email</label>
                                <input type="email" id="contactEmail" name="contactEmail" required>
                            </div>
                            <div class="form-group">
                                <label for="contactSubject">Subject</label>
                                <input type="text" id="contactSubject" name="contactSubject" required>
                            </div>
                            <div class="form-group">
                                <label for="contactMessage">Message</label>
                                <textarea id="contactMessage" name="contactMessage" rows="5" style="width: 100%; padding: 0.8rem; border: 2px solid #ddd; border-radius: 8px; font-size: 1rem; resize: vertical;" required></textarea>
                            </div>
                            <button type="submit" class="cta-button">Send Message</button>
                        </form>
                    </div>
                    <div>
                        <h2 style="color: #333; margin-bottom: 1rem;">Contact Information</h2>
                        <div style="margin-bottom: 2rem;">
                            <h3 style="color: #667eea; margin-bottom: 0.5rem;">📍 Address</h3>
                            <p>123 Fashion Street<br>New York, NY 10001<br>United States</p>
                        </div>
                        <div style="margin-bottom: 2rem;">
                            <h3 style="color: #667eea; margin-bottom: 0.5rem;">📞 Phone</h3>
                            <p>+1 (555) 123-4567</p>
                        </div>
                        <div style="margin-bottom: 2rem;">
                            <h3 style="color: #667eea; margin-bottom: 0.5rem;">✉️ Email</h3>
                            <p>support@fomtime.com</p>
                        </div>
                        <div>
                            <h3 style="color: #667eea; margin-bottom: 0.5rem;">🕒 Business Hours</h3>
                            <p>Monday - Friday: 9:00 AM - 6:00 PM<br>Saturday: 10:00 AM - 4:00 PM<br>Sunday: Closed</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Login Page -->
    <section id="login" class="page-section">
        <div class="container">
            <div style="max-width: 400px; margin: 2rem auto; background: white; padding: 3rem; border-radius: 15px; box-shadow: 0 5px 20px rgba(0,0,0,0.1);">
                <h1 style="text-align: center; margin-bottom: 2rem; font-size: 2rem; color: #333;">Welcome Back</h1>
                <form id="loginForm">
                    <div class="form-group">
                        <label for="loginEmail">Email Address</label>
                        <input type="email" id="loginEmail" name="loginEmail" required>
                    </div>
                    <div class="form-group">
                        <label for="loginPassword">Password</label>
                        <input type="password" id="loginPassword" name="loginPassword" required>
                    </div>
                    <button type="submit" class="cta-button" style="width: 100%; margin-bottom: 1rem;">Sign In</button>
                </form>
                <div style="text-align: center;">
                    <p style="margin-bottom: 1rem; color: #666;">Don't have an account?</p>
                    <button onclick="showRegister()" style="background: none; border: 2px solid #667eea; color: #667eea; padding: 0.8rem 2rem; border-radius: 25px; cursor: pointer; font-weight: bold;">Create Account</button>
                </div>
            </div>
        </div>
    </section>

    <script>
        // Sample product data
        const products = [
            { id: 1, name: "Premium T-Shirt", price: 49.99, category: "fashion", image: "👕", badge: "New" },
            { id: 2, name: "Wireless Headphones", price: 129.99, category: "electronics", image: "🎧", badge: "Sale" },
            { id: 3, name: "Designer Lamp", price: 89.99, category: "lifestyle", image: "💡", badge: "" },
            { id: 4, name: "Running Shoes", price: 79.99, category: "sports", image: "👟", badge: "Popular" },
            { id: 5, name: "Smartphone Case", price: 24.99, category: "electronics", image: "📱", badge: "" },
            { id: 6, name: "Yoga Mat", price: 39.99, category: "sports", image: "🧘", badge: "Eco" },
            { id: 7, name: "Skincare Set", price: 69.99, category: "beauty", image: "🧴", badge: "Bundle" },
            { id: 8, name: "Coffee Mug", price: 19.99, category: "lifestyle", image: "☕", badge: "" },
        ];

        let cart = [];
        let currentCategory = 'all';

        // Page navigation
        function showPage(pageId) {
            document.querySelectorAll('.page-section').forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById(pageId).classList.add('active');

            if (pageId === 'products') {
                loadProducts();
            } else if (pageId === 'cart') {
                updateCartDisplay();
            }
        }

        // Toggle mobile menu
        function toggleMobileMenu() {
            const menu = document.getElementById('navMenu');
            menu.classList.toggle('active');
        }

        // Load products
        function loadProducts(category = 'all') {
            const grid = document.getElementById('productsGrid');
            const filteredProducts = category === 'all' ? products : products.filter(p => p.category === category);
            
            grid.innerHTML = filteredProducts.map(product => `
                <div class="product-card fade-in-up" onclick="showProductDetail(${product.id})">
                    <div class="product-image">
                        ${product.image}
                        ${product.badge ? `<div class="product-badge">${product.badge}</div>` : ''}
                    </div>
                    <div class="product-info">
                        <h3>${product.name}</h3>
                        <div class="product-price">${product.price}</div>
                        <button class="add-to-cart" onclick="event.stopPropagation(); addToCart(${product.id})">
                            Add to Cart
                        </button>
                    </div>
                </div>
            `).join('');
        }

        // Show category products
        function showCategoryProducts(category) {
            currentCategory = category;
            showPage('products');
            loadProducts(category);
        }

        // Show product detail
        function showProductDetail(productId) {
            const product = products.find(p => p.id === productId);
            if (!product) return;

            const detailContent = document.getElementById('productDetailContent');
            detailContent.innerHTML = `
                <div class="product-detail-image">${product.image}</div>
                <div class="product-detail-info">
                    <h1>${product.name}</h1>
                    <div class="product-detail-price">${product.price}</div>
                    <div class="product-description">
                        This is a high-quality ${product.name.toLowerCase()} that combines style, comfort, and functionality. 
                        Made with premium materials and attention to detail, this product is perfect for those who appreciate quality.
                        <br><br>
                        Features:
                        <ul style="margin: 1rem 0; padding-left: 2rem;">
                            <li>Premium quality materials</li>
                            <li>Durable construction</li>
                            <li>Modern design</li>
                            <li>Satisfaction guaranteed</li>
                        </ul>
                    </div>
                    <div class="quantity-selector">
                        <button class="quantity-btn" onclick="changeQuantity(-1)">-</button>
                        <input type="number" class="quantity-input" value="1" min="1" id="productQuantity">
                        <button class="quantity-btn" onclick="changeQuantity(1)">+</button>
                    </div>
                    <button class="add-to-cart" style="font-size: 1.1rem; padding: 1rem 2rem;" onclick="addToCart(${product.id}, getQuantity())">
                        Add to Cart - ${product.price}
                    </button>
                </div>
            `;
            showPage('product-detail');
        }

        // Change quantity
        function changeQuantity(change) {
            const input = document.getElementById('productQuantity');
            const newValue = parseInt(input.value) + change;
            if (newValue >= 1) {
                input.value = newValue;
            }
        }

        // Get quantity
        function getQuantity() {
            const input = document.getElementById('productQuantity');
            return parseInt(input.value) || 1;
        }

        // Add to cart
        function addToCart(productId, quantity = 1) {
            const product = products.find(p => p.id === productId);
            if (!product) return;

            const existingItem = cart.find(item => item.id === productId);
            if (existingItem) {
                existingItem.quantity += quantity;
            } else {
                cart.push({ ...product, quantity });
            }

            updateCartCount();
            showSuccessMessage('Product added to cart!');
        }

        // Update cart count
        function updateCartCount() {
            const count = cart.reduce((total, item) => total + item.quantity, 0);
            document.getElementById('cartCount').textContent = count;
        }

        // Update cart display
        function updateCartDisplay() {
            const cartContent = document.getElementById('cartContent');
            
            if (cart.length === 0) {
                cartContent.innerHTML = `
                    <div style="text-align: center; padding: 3rem; background: white; border-radius: 15px; box-shadow: 0 5px 20px rgba(0,0,0,0.1);">
                        <h3>Your cart is empty</h3>
                        <p style="margin: 1rem 0; color: #666;">Add some products to get started!</p>
                        <a href="#" class="cta-button" onclick="showPage('products')">Continue Shopping</a>
                    </div>
                `;
                return;
            }

            const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            
            cartContent.innerHTML = `
                <div style="background: white; border-radius: 15px; box-shadow: 0 5px 20px rgba(0,0,0,0.1); padding: 2rem;">
                    <div class="cart-items">
                        ${cart.map(item => `
                            <div style="display: flex; align-items: center; padding: 1rem; border-bottom: 1px solid #eee; gap: 1rem;">
                                <div style="font-size: 2rem;">${item.image}</div>
                                <div style="flex: 1;">
                                    <h3>${item.name}</h3>
                                    <p style="color: #666;">${item.price} each</p>
                                </div>
                                <div style="display: flex; align-items: center; gap: 1rem;">
                                    <button onclick="updateCartItem(${item.id}, -1)" style="background: #ff4757; color: white; border: none; width: 30px; height: 30px; border-radius: 50%; cursor: pointer;">-</button>
                                    <span style="font-weight: bold;">${item.quantity}</span>
                                    <button onclick="updateCartItem(${item.id}, 1)" style="background: #667eea; color: white; border: none; width: 30px; height: 30px; border-radius: 50%; cursor: pointer;">+</button>
                                </div>
                                <div style="font-weight: bold; color: #667eea;">${(item.price * item.quantity).toFixed(2)}</div>
                                <button onclick="removeFromCart(${item.id})" style="background: #ff4757; color: white; border: none; padding: 0.5rem; border-radius: 5px; cursor: pointer;">Remove</button>
                            </div>
                        `).join('')}
                    </div>
                    <div style="margin-top: 2rem; text-align: right;">
                        <h2 style="color: #333; margin-bottom: 1rem;">Total: ${total.toFixed(2)}</h2>
                        <button onclick="showPage('checkout')" class="cta-button" style="margin-left: 1rem;">Proceed to Checkout</button>
                    </div>
                </div>
            `;
        }

        // Update cart item quantity
        function updateCartItem(productId, change) {
            const item = cart.find(item => item.id === productId);
            if (!item) return;

            item.quantity += change;
            if (item.quantity <= 0) {
                removeFromCart(productId);
            } else {
                updateCartCount();
                updateCartDisplay();
            }
        }

        // Remove from cart
        function removeFromCart(productId) {
            cart = cart.filter(item => item.id !== productId);
            updateCartCount();
            updateCartDisplay();
            showSuccessMessage('Product removed from cart');
        }

        // Search products
        function searchProducts() {
            const query = document.getElementById('searchInput').value.toLowerCase();
            if (!query) return;

            const filteredProducts = products.filter(product => 
                product.name.toLowerCase().includes(query)
            );

            const grid = document.getElementById('productsGrid');
            grid.innerHTML = filteredProducts.map(product => `
                <div class="product-card fade-in-up" onclick="showProductDetail(${product.id})">
                    <div class="product-image">
                        ${product.image}
                        ${product.badge ? `<div class="product-badge">${product.badge}</div>` : ''}
                    </div>
                    <div class="product-info">
                        <h3>${product.name}</h3>
                        <div class="product-price">${product.price}</div>
                        <button class="add-to-cart" onclick="event.stopPropagation(); addToCart(${product.id})">
                            Add to Cart
                        </button>
                    </div>
                </div>
            `).join('');

            showPage('products');
        }

        // Place order
        function placeOrder() {
            const btnText = document.getElementById('orderBtnText');
            const btnLoader = document.getElementById('orderBtnLoader');
            const successMsg = document.getElementById('orderSuccess');

            btnText.style.display = 'none';
            btnLoader.style.display = 'inline-block';

            // Simulate order processing
            setTimeout(() => {
                btnText.style.display = 'inline';
                btnLoader.style.display = 'none';
                successMsg.classList.add('show');
                
                // Clear cart
                cart = [];
                updateCartCount();

                // Redirect to home after 3 seconds
                setTimeout(() => {
                    showPage('home');
                    successMsg.classList.remove('show');
                }, 3000);
            }, 2000);
        }

        // Show success message
        function showSuccessMessage(message) {
            const msgDiv = document.createElement('div');
            msgDiv.className = 'success-message show';
            msgDiv.textContent = message;
            msgDiv.style.position = 'fixed';
            msgDiv.style.top = '100px';
            msgDiv.style.right = '20px';
            msgDiv.style.zIndex = '9999';
            msgDiv.style.minWidth = '250px';
            
            document.body.appendChild(msgDiv);
            
            setTimeout(() => {
                msgDiv.remove();
            }, 3000);
        }

        // Show register form
        function showRegister() {
            const loginSection = document.getElementById('login');
            loginSection.innerHTML = `
                <div class="container">
                    <div style="max-width: 400px; margin: 2rem auto; background: white; padding: 3rem; border-radius: 15px; box-shadow: 0 5px 20px rgba(0,0,0,0.1);">
                        <h1 style="text-align: center; margin-bottom: 2rem; font-size: 2rem; color: #333;">Create Account</h1>
                        <form id="registerForm">
                            <div class="form-group">
                                <label for="registerName">Full Name</label>
                                <input type="text" id="registerName" name="registerName" required>
                            </div>
                            <div class="form-group">
                                <label for="registerEmail">Email Address</label>
                                <input type="email" id="registerEmail" name="registerEmail" required>
                            </div>
                            <div class="form-group">
                                <label for="registerPassword">Password</label>
                                <input type="password" id="registerPassword" name="registerPassword" required>
                            </div>
                            <div class="form-group">
                                <label for="confirmPassword">Confirm Password</label>
                                <input type="password" id="confirmPassword" name="confirmPassword" required>
                            </div>
                            <button type="submit" class="cta-button" style="width: 100%; margin-bottom: 1rem;">Create Account</button>
                        </form>
                        <div style="text-align: center;">
                            <p style="margin-bottom: 1rem; color: #666;">Already have an account?</p>
                            <button onclick="showPage('login')" style="background: none; border: 2px solid #667eea; color: #667eea; padding: 0.8rem 2rem; border-radius: 25px; cursor: pointer; font-weight: bold;">Sign In</button>
                        </div>
                    </div>
                </div>
            `;
        }

        // Initialize the page
        document.addEventListener('DOMContentLoaded', function() {
            loadProducts();
        });

        // Handle search on Enter key
        document.addEventListener('DOMContentLoaded', function() {
            const searchInput = document.getElementById('searchInput');
            searchInput.addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    searchProducts();
                }
            });
        });
    </script>
</body>
</html>
