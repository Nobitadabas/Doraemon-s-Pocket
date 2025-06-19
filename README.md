<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Doraemon's Pocket - Magical Gadgets Store</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
           .testimonials {
       text-align: center;
   }

   .testimonial {
       opacity: 0;
       transform: translateY(20px);
       animation: fadeInSlide 0.5s forwards;
   }

   @keyframes fadeInSlide {
       from {
           opacity: 0;
           transform: translateY(10px);
       }
       to {
           opacity: 1;
           transform: translateY(0);
       }
   }

   .testimonial:hover {
       background-color: #f0f0f0; /* Highlight effect */
       transition: background-color 0.3s ease;
   }
   
        :root {
            --primary: #3b82f6;
            --secondary: #f59e0b;
            --dark: #93aeda;
            --light: #f8fafc;
        }
        
        .dark {
            --primary: #76e9f4;
            --secondary: #fbbf24;
            --dark: #f8fafc;
            --light: #031912;
        }
        
        body {
            background-color: var(--light);
            color: var(--dark);
            transition: all 0.3s ease;
        }
        
        .bg-primary {
            background-color: var(--primary);
        }
        
        .text-primary {
            color: var(--primary);
        }
        
        .border-primary {
            border-color: var(--primary);
        }
        
        .bg-secondary {
            background-color: var(--secondary);
        }
        
        .text-secondary {
            color: var(--secondary);
        }
        
        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
        }
        
        .cart-item {
            animation: slideIn 0.3s forwards;
        }
        
        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateX(20px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }
        
        .carousel-item {
            transition: transform 0.5s ease;
        }
        
        .scroll-animation {
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.5s ease;
        }
        
        .animate {
            opacity: 1;
            transform: translateY(0);
        }
        .product-card {
  background: #0f0; /* neon green background */
  box-shadow: 0 0 15px #0f0, 0 0 30px #0f0, 0 0 45px #0f0;
  border-radius: 12px;
  padding: 20px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}


.product-card:hover {
  transform: scale(1.03) !important ;
  box-shadow: 0 0 20px #0ff, 0 0 40px #0ff, 0 0 60px #0ff  !important;
}

/* Rainbow Border Animation */
.rainbow-border {
  position: relative !important;
  z-index: 0 !important;
  overflow: hidden !important;
}

  .rainbow-border::before {
    content: '' !important;
    position: absolute !important;
    top: -2px !important;
    left: -2px !important;
    right: -2px !important;
    bottom: -2px !important;
    z-index: -1 !important;
    background: linear-gradient(
      45deg,
      #ff0000,
      #ffa500,
      #ffff00,
      #00ff00,
      #00ffff,
      #0000ff,
      #ff00ff,
      #ff0000
    )!important;
    background-size: 400% 400% !important;
    animation: borderRainbow 6s linear infinite !important;
    border-radius: 1rem !important;
  }

  @keyframes borderRainbow {
    0% { background-position: 0% 50%; }
    100% { background-position: 100% 50%; }
  }

  /* Starfield Effect */
  .twinkling::after {
    content: '' !important;
    position: absolute  !important;
    top: -50% !important;
    left: -50% !important;
    width: 200% !important;
    height: 200% !important;
    background-image: radial-gradient(#ffffff 1px, transparent 1px) !important;
    background-size: 10px 10px !important;
    opacity: 0.06 !important;
    animation: twinkle 3s linear infinite !important;
    z-index: 0 !important;
    pointer-events: none;
  }

  @keyframes twinkle {
    0% { transform: translate(0, 0) !important; }
    100% { transform: translate(10px, 10px) !important; }
  }

  /* Icon Pulse on Hover */
  .feature-icon:hover {
    animation: pulse 1.2s infinite alternate !important ;
  }

  @keyframes pulse {
    from { transform: scale(1); }
    to { transform: scale(1.2) rotate(3deg); }
  }

  /* Card Tilt Hover */
  .feature-card {
    transition: transform 0.6s ease;
    transform-style: preserve-3d;
  }

  .feature-card:hover {
    transform: rotateY(5deg) rotateX(5deg) !important;
  }
</style>

<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@600&display=swap" rel="stylesheet">
</head>
    <!-- Dark/Light Mode Toggle -->
    <button id="theme-toggle" class="fixed top-4 right-4 z-50 p-2 rounded-full bg-gray-200 dark:bg-gray-700 shadow-lg">
        <i class="fas fa-moon dark:hidden"></i>
        <i class="fas fa-sun hidden dark:block"></i>
    </button>

    <!-- Navigation Bar -->
    <nav class="bg-white dark:bg-gray-800 shadow-md sticky top-0 z-40 transition-all duration-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between h-16">
                <div class="flex items-center">
                    <div class="flex-shrink-0 flex items-center">
                        <img class="h-8 w-auto" src="https://japancitytour.com/wp-content/uploads/2021/03/doraemon.jpg" alt="Doraemon's Pocket Logo">
                        <span class="ml-2 text-xl font-bold text-gray-900 dark:text-white">Doraemon's Pocket</span>
                    </div>
                    <div class="hidden sm:ml-6 sm:flex sm:space-x-8">
                        <a href="#home" class="border-primary text-gray-900 dark:text-white inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium scroll-smooth">Home</a>
                        <a href="#products" class="border-transparent text-gray-500 dark:text-gray-300 hover:border-gray-300 hover:text-gray-700 dark:hover:text-white inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium scroll-smooth">Products</a>
                        <a href="#features" class="border-transparent text-gray-500 dark:text-gray-300 hover:border-gray-300 hover:text-gray-700 dark:hover:text-white inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium scroll-smooth">Features</a>
                        <a href="#about" class="border-transparent text-gray-500 dark:text-gray-300 hover:border-gray-300 hover:text-gray-700 dark:hover:text-white inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium scroll-smooth">About</a>
                        <a href="#contact" class="border-transparent text-gray-500 dark:text-gray-300 hover:border-gray-300 hover:text-gray-700 dark:hover:text-white inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium scroll-smooth">Contact</a>
                    </div>
                </div>
                <div class="flex items-center">
                    <div class="relative mx-4">
                        <input type="text" id="search" placeholder="Search gadgets..." class="pl-10 pr-4 py-2 rounded-full border border-gray-300 dark:border-gray-600 dark:bg-gray-700 dark:text-white focus:outline-none focus:ring-2 focus:ring-primary focus:border-transparent w-64">
                        <i class="fas fa-search absolute left-3 top-3 text-gray-400"></i>
                    </div>
                    <div class="relative">
                        <button id="cart-btn" class="p-2 rounded-full text-gray-600 dark:text-gray-300 hover:text-gray-900 dark:hover:text-white relative">
                            <i class="fas fa-shopping-cart text-xl"></i>
                            <span id="cart-count" class="absolute -top-1 -right-1 bg-primary text-white text-xs font-bold rounded-full h-5 w-5 flex items-center justify-center">0</span>
                        </button>
                        <div id="cart-dropdown" class="hidden absolute right-0 mt-2 w-80 bg-white dark:bg-gray-800 rounded-md shadow-lg overflow-hidden z-50 border border-gray-200 dark:border-gray-700">
                            <div class="p-4 border-b border-gray-200 dark:border-gray-700">
                                <h3 class="text-lg font-medium text-gray-900 dark:text-white">Your Cart</h3>
                            </div>
                            <div id="cart-items" class="max-h-96 overflow-y-auto p-2">
                                <!-- Cart items will be added here -->
                                <p class="text-center text-gray-500 dark:text-gray-400 py-4">Your cart is empty</p>
                            </div>
                            <div class="p-4 border-t border-gray-200 dark:border-gray-700">
                                <div class="flex justify-between mb-2">
                                    <span class="text-gray-600 dark:text-gray-300">Total:</span>
                                    <span id="cart-total" class="font-bold text-gray-900 dark:text-white">$0.00</span>
                                </div>
                                <button id="checkout-btn" class="w-full bg-primary hover:bg-blue-600 text-white py-2 rounded-md transition duration-300">Checkout</button>
                            </div>
                        </div>
                    </div>
                    <div class="ml-4 relative">
                        <button id="user-btn" class="p-2 rounded-full text-gray-600 dark:text-gray-300 hover:text-gray-900 dark:hover:text-white">
                            <i class="fas fa-user text-xl"></i>
                        </button>
                        <div id="user-dropdown" class="hidden absolute right-0 mt-2 w-48 bg-white dark:bg-gray-800 rounded-md shadow-lg overflow-hidden z-50 border border-gray-200 dark:border-gray-700">
                            <a href="#" class="block px-4 py-2 text-sm text-gray-700 dark:text-gray-300 hover:bg-gray-100 dark:hover:bg-gray-700">Profile</a>
                            <a href="#" class="block px-4 py-2 text-sm text-gray-700 dark:text-gray-300 hover:bg-gray-100 dark:hover:bg-gray-700">Orders</a>
                            <a href="#" class="block px-4 py-2 text-sm text-gray-700 dark:text-gray-300 hover:bg-gray-100 dark:hover:bg-gray-700">Settings</a>
                            <div class="border-t border-gray-200 dark:border-gray-700">
                                <a href="#" class="block px-4 py-2 text-sm text-gray-700 dark:text-gray-300 hover:bg-gray-100 dark:hover:bg-gray-700">Sign out</a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="relative overflow-hidden scroll-animation">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-20">
            <div class="lg:grid lg:grid-cols-2 lg:gap-8 items-center">
                <div class="mb-12 lg:mb-0">
                    <h1 class="text-4xl font-extrabold tracking-tight text-gray-900 dark:text-white sm:text-5xl md:text-6xl">
                        <span class="block text-primary">Doraemon's Pocket</span>
                        <span class="block">Magical Gadgets Store</span>
                    </h1>
                    <p class="mt-3 text-base text-gray-500 dark:text-gray-300 sm:mt-5 sm:text-lg sm:max-w-xl sm:mx-auto md:mt-5 md:text-xl lg:mx-0">
                        Discover amazing gadgets straight from the 22nd century! Our collection features time-traveling tools, futuristic devices, and magical items that will make your life easier and more fun.
                    </p>
                    <div class="mt-8 sm:flex sm:justify-center lg:justify-start">
                        <div class="rounded-md shadow">
                            <a href="#products" class="w-full flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-md text-white bg-primary hover:bg-blue-600 md:py-4 md:text-lg md:px-10 scroll-smooth">
                                Shop Now
                            </a>
                        </div>
                        <div class="mt-3 sm:mt-0 sm:ml-3">
                            <a href="#features" class="w-full flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-md text-primary bg-white dark:bg-gray-800 hover:bg-gray-50 dark:hover:bg-gray-700 md:py-4 md:text-lg md:px-10 scroll-smooth">
                                Learn More
                            </a>
                        </div>
                    </div>
                </div>
                <div class="relative">
                    <img class="w-full h-auto max-w-md mx-auto lg:max-w-none" src="https://japancitytour.com/wp-content/uploads/2021/03/doraemon.jpg" alt="Doraemon with gadgets">
                    <div class="absolute -bottom-8 -right-8 bg-secondary w-32 h-32 rounded-full opacity-20"></div>
                    <div class="absolute -top-8 -left-8 bg-primary w-32 h-32 rounded-full opacity-20"></div>
                </div>
            </div>
        </div>
    </section>

    <!-- Featured Products Carousel -->
    <section class="bg-gray-50 dark:bg-gray-900 py-12 scroll-animation">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-extrabold text-gray-900 dark:text-white sm:text-4xl">
                    <span class="block">Featured Gadgets</span>
                </h2>
                <p class="mt-3 max-w-2xl mx-auto text-gray-500 dark:text-gray-300 sm:mt-4">
                    Check out our most popular items from Doraemon's magical pocket
                </p>
            </div>
            
            <div class="relative overflow-hidden">
                <div id="carousel" class="flex transition-transform duration-500">
                    <!-- Carousel items will be added dynamically -->
                </div>
                <button id="carousel-prev" class="absolute left-0 top-1/2 transform -translate-y-1/2 bg-white dark:bg-gray-800 p-2 rounded-full shadow-md hover:bg-gray-100 dark:hover:bg-gray-700 z-10">
                    <i class="fas fa-chevron-left text-gray-700 dark:text-gray-300"></i>
                </button>
                <button id="carousel-next" class="absolute right-0 top-1/2 transform -translate-y-1/2 bg-white dark:bg-gray-800 p-2 rounded-full shadow-md hover:bg-gray-100 dark:hover:bg-gray-700 z-10">
                    <i class="fas fa-chevron-right text-gray-700 dark:text-gray-300"></i>
                </button>
            </div>
        </div>
    </section>

    <!-- Products Section with Filtering -->
    <section id="products" class="py-12 scroll-animation">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-extrabold text-gray-900 dark:text-white sm:text-4xl">
                    <span class="block">Magical Gadgets Collection</span>
                </h2>
                <p class="mt-3 max-w-2xl mx-auto text-gray-500 dark:text-gray-300 sm:mt-4">
                    Browse through our extensive collection of futuristic gadgets
                </p>
            </div>
            
            <div class="flex flex-col md:flex-row gap-8">
                <!-- Filters -->
                <div class="w-full md:w-1/4 bg-white dark:bg-gray-800 p-6 rounded-lg shadow-md h-fit sticky top-20">
                    <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-4">Filters</h3>
                    
                    <div class="mb-6">
                        <h4 class="text-sm font-medium text-gray-900 dark:text-white mb-2">Categories</h4>
                        <div class="space-y-2">
                            <label class="flex items-center">
                                <input type="checkbox" class="category-filter h-4 w-4 text-primary focus:ring-primary border-gray-300 rounded" value="Time Travel">
                                <span class="ml-2 text-sm text-gray-700 dark:text-gray-300">Time Travel</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="category-filter h-4 w-4 text-primary focus:ring-primary border-gray-300 rounded" value="Transportation">
                                <span class="ml-2 text-sm text-gray-700 dark:text-gray-300">Transportation</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="category-filter h-4 w-4 text-primary focus:ring-primary border-gray-300 rounded" value="Food">
                                <span class="ml-2 text-sm text-gray-700 dark:text-gray-300">Food</span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="category-filter h-4 w-4 text-primary focus:ring-primary border-gray-300 rounded" value="Daily Life">
                                <span class="ml-2 text-sm text-gray-700 dark:text-gray-300">Daily Life</span>
                            </label>
                        </div>
                    </div>
                    
                    <div class="mb-6">
                        <h4 class="text-sm font-medium text-gray-900 dark:text-white mb-2">Price Range</h4>
                        <div class="flex items-center justify-between mb-2">
                            <span class="text-sm text-gray-500 dark:text-gray-400">$0</span>
                            <span class="text-sm text-gray-500 dark:text-gray-400">$10000</span>
                        </div>
                        <input type="range" id="price-range" min="0" max="1000" value="1000" class="w-full h-2 bg-gray-200 rounded-lg appearance-none cursor-pointer dark:bg-gray-700">
                        <div class="flex justify-between mt-2">
                            <span id="min-price" class="text-sm text-gray-700 dark:text-gray-300">$0</span>
                            <span id="max-price" class="text-sm text-gray-700 dark:text-gray-300">$10000</span>
                        </div>
                    </div>
                    
                    <div class="mb-6">
                        <h4 class="text-sm font-medium text-gray-900 dark:text-white mb-2">Rating</h4>
                        <div class="space-y-2">
                            <label class="flex items-center">
                                <input type="checkbox" class="rating-filter h-4 w-4 text-primary focus:ring-primary border-gray-300 rounded" value="5">
                                <span class="ml-2 text-sm text-gray-700 dark:text-gray-300">
                                    <i class="fas fa-star text-yellow-400"></i>
                                    <i class="fas fa-star text-yellow-400"></i>
                                    <i class="fas fa-star text-yellow-400"></i>
                                    <i class="fas fa-star text-yellow-400"></i>
                                    <i class="fas fa-star text-yellow-400"></i>
                                </span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="rating-filter h-4 w-4 text-primary focus:ring-primary border-gray-300 rounded" value="4">
                                <span class="ml-2 text-sm text-gray-700 dark:text-gray-300">
                                    <i class="fas fa-star text-yellow-400"></i>
                                    <i class="fas fa-star text-yellow-400"></i>
                                    <i class="fas fa-star text-yellow-400"></i>
                                    <i class="fas fa-star text-yellow-400"></i>
                                    <i class="fas fa-star text-gray-300"></i>
                                </span>
                            </label>
                            <label class="flex items-center">
                                <input type="checkbox" class="rating-filter h-4 w-4 text-primary focus:ring-primary border-gray-300 rounded" value="3">
                                <span class="ml-2 text-sm text-gray-700 dark:text-gray-300">
                                    <i class="fas fa-star text-yellow-400"></i>
                                    <i class="fas fa-star text-yellow-400"></i>
                                    <i class="fas fa-star text-yellow-400"></i>
                                    <i class="fas fa-star text-gray-300"></i>
                                    <i class="fas fa-star text-gray-300"></i>
                                </span>
                            </label>
                        </div>
                    </div>
                    
                    <button id="reset-filters" class="w-full bg-gray-200 dark:bg-gray-700 hover:bg-gray-300 dark:hover:bg-gray-600 text-gray-800 dark:text-gray-200 py-2 rounded-md transition duration-300">
                        Reset Filters
                    </button>
                </div>
                
                <!-- Products Grid -->
                <div class="w-full md:w-3/4">
                    <div class="flex justify-between items-center mb-6">
                        <div>
                            <span id="product-count" class="text-sm text-gray-500 dark:text-gray-400">Showing all products</span>
                        </div>
                        <div>
                            <select id="sort-by" class="block w-full pl-3 pr-10 py-2 text-base border-gray-300 dark:border-gray-600 dark:bg-gray-700 dark:text-white focus:outline-none focus:ring-primary focus:border-primary sm:text-sm rounded-md">
                                <option value="default">Sort by</option>
                                <option value="price-low">Price: Low to High</option>
                                <option value="price-high">Price: High to Low</option>
                                <option value="rating">Rating</option>
                                <option value="popular">Popularity</option>
                            </select>
                        </div>
                    </div>
                    
                    <div id="products-grid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
                        <!-- Products will be added dynamically -->
                    </div>
                    
                    <div id="no-products" class="hidden text-center py-12">
                        <i class="fas fa-search text-4xl text-gray-400 mb-4"></i>
                        <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-2">No products found</h3>
                        <p class="text-gray-500 dark:text-gray-400">Try adjusting your filters or search for something else</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <!-- Features Section -->
    <section id="features" class="py-12 bg-gray-50 dark:bg-gray-900 scroll-animation">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-extrabold text-gray-900 dark:text-white sm:text-4xl">
                    <span class="block">Why Choose Doraemon's Pocket?</span>
                </h2>
                <p class="mt-3 max-w-2xl mx-auto text-gray-500 dark:text-gray-300 sm:mt-4">
                    We bring the future to your doorstep with these amazing benefits and it is designed by NOBITA !!!
                </p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <div class="bg-white dark:bg-gray-800 p-6 rounded-lg shadow-md hover:shadow-lg transition duration-300">
                    <div class="flex items-center justify-center h-12 w-12 rounded-md bg-primary text-white mb-4">
                        <i class="fas fa-shipping-fast text-xl"></i>
                    </div>
                    <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-2">Instant Delivery</h3>
                    <p class="text-gray-500 dark:text-gray-400">
                        Our gadgets arrive instantly using time-travel technology. No waiting required!
                    </p>
                </div>
                
                <div class="bg-white dark:bg-gray-800 p-6 rounded-lg shadow-md hover:shadow-lg transition duration-300">
                    <div class="flex items-center justify-center h-12 w-12 rounded-md bg-primary text-white mb-4">
                        <i class="fas fa-check-circle text-xl"></i>
                    </div>
                    <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-2">Quality Guaranteed</h3>
                    <p class="text-gray-500 dark:text-gray-400">
                        All our gadgets are tested in the 22nd century before being sent to you.
                    </p>
                </div>
                
                <div class="bg-white dark:bg-gray-800 p-6 rounded-lg shadow-md hover:shadow-lg transition duration-300">
                    <div class="flex items-center justify-center h-12 w-12 rounded-md bg-primary text-white mb-4">
                        <i class="fas fa-headset text-xl"></i>
                    </div>
                    <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-2">24/7 Support</h3>
                    <p class="text-gray-500 dark:text-gray-400">
                        Our support team is available across all time periods to assist you.
                    </p>
                </div>
                
                <div class="bg-white dark:bg-gray-800 p-6 rounded-lg shadow-md hover:shadow-lg transition duration-300">
                    <div class="flex items-center justify-center h-12 w-12 rounded-md bg-primary text-white mb-4">
                        <i class="fas fa-exchange-alt text-xl"></i>
                    </div>
                    <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-2">Easy Returns</h3>
                    <p class="text-gray-500 dark:text-gray-400">
                        Not satisfied? Return any gadget within 30 days with our time-reversal policy.
                    </p>
                </div>
                
                <div class="bg-white dark:bg-gray-800 p-6 rounded-lg shadow-md hover:shadow-lg transition duration-300">
                    <div class="flex items-center justify-center h-12 w-12 rounded-md bg-primary text-white mb-4">
                        <i class="fas fa-gift text-xl"></i>
                    </div>
                    <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-2">Special Rewards</h3>
                    <p class="text-gray-500 dark:text-gray-400">
                        Earn points with every purchase that can be redeemed for exclusive gadgets.
                    </p>
                </div>
                
                <div class="bg-white dark:bg-gray-800 p-6 rounded-lg shadow-md hover:shadow-lg transition duration-300">
                    <div class="flex items-center justify-center h-12 w-12 rounded-md bg-primary text-white mb-4">
                        <i class="fas fa-lock text-xl"></i>
                    </div>
                    <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-2">Secure Payments</h3>
                    <p class="text-gray-500 dark:text-gray-400">
                        Your payments are protected with futuristic encryption technology.
                    </p>
                </div>
            </div>
        </section>

    <!-- Newsletter Section -->
    <section class="py-12 bg-primary text-white scroll-animation">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="md:flex md:items-center md:justify-between">
                <div class="md:w-1/2 mb-6 md:mb-0">
                    <h2 class="text-2xl font-bold mb-2">Stay Updated</h2>
                    <p class="opacity-90">Subscribe to our newsletter for exclusive gadget releases and special offers !</p>
                </div>
                <div class="md:w-1/2">
                    <form id="newsletter-form" class="flex">
                        <input type="email" id="newsletter-email" placeholder="Your email address" class="flex-grow px-4 py-3 rounded-l-md focus:outline-none text-gray-900" required>
                        <button type="submit" class="bg-secondary hover:bg-yellow-500 text-gray-900 font-bold px-6 py-3 rounded-r-md transition duration-300">
                            Subscribe
                        </button>
                    </form>
                    <p id="newsletter-message" class="mt-2 text-sm opacity-80 hidden"></p>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-12 scroll-animation">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="lg:grid lg:grid-cols-2 lg:gap-12 items-center">
                <div class="mb-8 lg:mb-0">
                    <img src="https://i.redd.it/q4jq5d2rojod1.png" alt="About Doraemon's Pocket" class="w-full h-auto rounded-lg shadow-lg">
                </div>
                <div>
                    <h2 class="text-3xl font-extrabold text-gray-900 dark:text-white mb-6">About Doraemon's Pocket</h2>
                    <p class="text-gray-600 dark:text-gray-300 mb-4">
                        Founded in the 22nd century by Doraemon himself, our mission is to bring futuristic convenience to the present day. We carefully select gadgets that can improve your daily life without disrupting the space-time continuum.
                    </p>
                    <p class="text-gray-600 dark:text-gray-300 mb-4">
                        All our products undergo rigorous testing in our future labs to ensure they're safe, effective, and easy to use. We work closely with scientists from multiple time periods to develop innovative solutions for modern problems.
                    </p>
                    <div class="mt-8">
                        <a href="#contact" class="inline-flex items-center px-6 py-3 border border-transparent text-base font-medium rounded-md text-white bg-primary hover:bg-blue-600 scroll-smooth">
                            Contact Us
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section class="py-12 bg-gray-50 dark:bg-gray-900 scroll-animation">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-12">
                <h2 class="text-3xl font-extrabold text-gray-900 dark:text-white sm:text-4xl">
                    <span class="block">What Our Customers Say</span>
                </h2>
                <p class="mt-3 max-w-2xl mx-auto text-gray-500 dark:text-gray-300 sm:mt-4">
                    Hear from people across different time periods about their experiences
                </p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="bg-white dark:bg-gray-800 p-6 rounded-lg shadow-md">
                    <div class="flex items-center mb-4">
                        <div class="flex-shrink-0">
                            <img class="h-10 w-10 rounded-full" src="https://i.pinimg.com/736x/bf/eb/a8/bfeba832a872fef7b0426e3c314041d9.jpg" alt="Nobita">
                        </div>
                        <div class="ml-3">
                            <h3 class="text-sm font-medium text-gray-900 dark:text-white">Nobita Nobi</h3>
                            <div class="flex text-yellow-400">
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                            </div>
                        </div>
                    </div>
                    <p class="text-gray-600 dark:text-gray-300">
                        "The Anywhere Door has completely changed my life! No more being late for school. I can visit my friends instantly. Best purchase ever!"
                    </p>
                </div>
                
                <div class="bg-white dark:bg-gray-800 p-6 rounded-lg shadow-md">
                    <div class="flex items-center mb-4">
                        <div class="flex-shrink-0">
                            <img class="h-10 w-10 rounded-full" src="https://photosnow.org/wp-content/uploads/2024/02/shizuka-photo38.jpg" alt="Shizuka">
                        </div>
                        <div class="ml-3">
                            <h3 class="text-sm font-medium text-gray-900 dark:text-white">Shizuka Minamoto</h3>
                            <div class="flex text-yellow-400">
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                            </div>
                        </div>
                    </div>
                    <p class="text-gray-600 dark:text-gray-300">
                        "The Time Furoshiki is amazing! I can wrap up anything and take it with me anywhere. Perfect for picnics and travel. Highly recommend!"
                    </p>
                </div>
                
                <div class="bg-white dark:bg-gray-800 p-6 rounded-lg shadow-md">
                    <div class="flex items-center mb-4">
                        <div class="flex-shrink-0">
                            <img class="h-10 w-10 rounded-full" src="https://static.wikia.nocookie.net/doraemon/images/b/b7/1979_remake_Suneo.png/revision/latest?cb=20230708140959&path-prefix=en" alt="Suneo">
                        </div>
                        <div class="ml-3">
                            <h3 class="text-sm font-medium text-gray-900 dark:text-white">Suneo Honekawa</h3>
                            <div class="flex text-yellow-400">
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star"></i>
                                <i class="fas fa-star-half-alt"></i>
                            </div>
                        </div>
                    </div>
                    <p class="text-gray-600 dark:text-gray-300">
                        "The Small Light is worth every penny! I can shrink all my expensive toys to carry them easily. Though I wish it came with a remote control..."
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-12 scroll-animation">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="lg:grid lg:grid-cols-2 lg:gap-12">
                <div class="mb-8 lg:mb-0">
                    <h2 class="text-3xl font-extrabold text-gray-900 dark:text-white mb-6">Contact Us</h2>
                    <p class="text-gray-600 dark:text-gray-300 mb-6">
                        Have questions about our gadgets? Want to suggest a new product? We'd love to hear from you across any time period!
                    </p>
                    
                    <div class="space-y-4">
                        <div class="flex items-start">
                            <div class="flex-shrink-0">
                                <i class="fas fa-map-marker-alt text-primary text-xl mt-1"></i>
                            </div>
                            <div class="ml-3">
                                <h3 class="text-sm font-medium text-gray-900 dark:text-white">Address</h3>
                                <p class="text-sm text-gray-500 dark:text-gray-400">22nd Century, Tokyo, Japan (Anywhere Door required)</p>
                            </div>
                        </div>
                        
                        <div class="flex items-start">
                            <div class="flex-shrink-0">
                                <i class="fas fa-phone-alt text-primary text-xl mt-1"></i>
                            </div>
                            <div class="ml-3">
                                <h3 class="text-sm font-medium text-gray-900 dark:text-white">Phone</h3>
                                <p class="text-sm text-gray-500 dark:text-gray-400">+91 XXXXXXXXXX</p>
                            </div>
                        </div>
                        
                        <div class="flex items-start">
                            <div class="flex-shrink-0">
                                <i class="fas fa-envelope text-primary text-xl mt-1"></i>
                            </div>
                            <div class="ml-3">
                                <h3 class="text-sm font-medium text-gray-900 dark:text-white">Email</h3>
                                <p class="text-sm text-gray-500 dark:text-gray-400">contact@doraemons__pocket.com</p>
                            </div>
                        </div>
                        
                        <div class="flex items-start">
                            <div class="flex-shrink-0">
                                <i class="fas fa-clock text-primary text-xl mt-1"></i>
                            </div>
                            <div class="ml-3">
                                <h3 class="text-sm font-medium text-gray-900 dark:text-white">Hours</h3>
                                <p class="text-sm text-gray-500 dark:text-gray-400">24/7 across all time periods</p>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div>
                    <form id="contact-form" class="space-y-6">
                        <div>
                            <label for="name" class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-1">Your Name</label>
                            <input type="text" id="name" name="name" class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 dark:bg-gray-700 dark:text-white rounded-md focus:outline-none focus:ring-primary focus:border-primary" required>
                        </div>
                        
                        <div>
                            <label for="email" class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-1">Email Address</label>
                            <input type="email" id="email" name="email" class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 dark:bg-gray-700 dark:text-white rounded-md focus:outline-none focus:ring-primary focus:border-primary" required>
                        </div>
                        
                        <div>
                            <label for="time-period" class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-1">Time Period</label>
                            <select id="time-period" name="time-period" class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 dark:bg-gray-700 dark:text-white rounded-md focus:outline-none focus:ring-primary focus:border-primary">
                                <option value="present">Present (21st Century)</option>
                                <option value="past">Past</option>
                                <option value="future">Future (22nd Century+)</option>
                                <option value="other">Other</option>
                            </select>
                        </div>
                        
                        <div>
                            <label for="message" class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-1">Message</label>
                            <textarea id="message" name="message" rows="4" class="w-full px-4 py-2 border border-gray-300 dark:border-gray-600 dark:bg-gray-700 dark:text-white rounded-md focus:outline-none focus:ring-primary focus:border-primary" required></textarea>
                        </div>
                        
                        <div>
                            <button type="submit" class="w-full bg-primary hover:bg-blue-600 text-white py-2 px-4 rounded-md transition duration-300">
                                Send Message
                            </button>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-800 text-white pt-12 pb-6">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-8 mb-8">
                <div>
                    <h3 class="text-lg font-semibold mb-4">Doraemon's Pocket</h3>
                    <p class="text-gray-400">
                        Bringing futuristic convenience to your present since ever.
                    </p>
                </div>
                
                <div>
                    <h3 class="text-lg font-semibold mb-4">Quick Links</h3>
                    <ul class="space-y-2">
                        <li><a href="#home" class="text-gray-400 hover:text-white transition duration-300 scroll-smooth">Home</a></li>
                        <li><a href="#products" class="text-gray-400 hover:text-white transition duration-300 scroll-smooth">Products</a></li>
                        <li><a href="#features" class="text-gray-400 hover:text-white transition duration-300 scroll-smooth">Features</a></li>
                        <li><a href="#about" class="text-gray-400 hover:text-white transition duration-300 scroll-smooth">About</a></li>
                        <li><a href="#contact" class="text-gray-400 hover:text-white transition duration-300 scroll-smooth">Contact</a></li>
                    </ul>
                </div>
                
                <div>
                    <h3 class="text-lg font-semibold mb-4">Categories</h3>
                    <ul class="space-y-2">
                        <li><a href="#" class="text-gray-400 hover:text-white transition duration-300">Time Travel</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition duration-300">Transportation</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition duration-300">Food</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition duration-300">Daily Life</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition duration-300">New Arrivals</a></li>
                    </ul>
                </div>
                
                <div>
                    <h3 class="text-lg font-semibold mb-4">Connect With Us</h3>
                    <div class="flex space-x-4 mb-4">
                        <a href="#" class="text-gray-400 hover:text-white transition duration-300">
                            <i class="fab fa-facebook-f"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white transition duration-300">
                            <i class="fab fa-twitter"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white transition duration-300">
                            <i class="fab fa-instagram"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white transition duration-300">
                            <i class="fab fa-youtube"></i>
                        </a>
                    </div>
                    <p class="text-gray-400 mb-2">Subscribe to our newsletter</p>
                    <form class="flex">
                        <input type="email" placeholder="Your email" class="px-3 py-2 text-gray-900 rounded-l-md focus:outline-none w-full">
                        <button class="bg-primary hover:bg-blue-600 px-4 rounded-r-md transition duration-300">
                            <i class="fas fa-paper-plane"></i>
                        </button>
                    </form>
                </div>
            </div>
            
            <div class="border-t border-gray-700 pt-6 flex flex-col md:flex-row justify-between items-center">
                <p class="text-gray-400 text-sm mb-4 md:mb-0">
                    &copy; 2112-∞ Doraemon's Pocket. All rights reserved across all time periods with nobita , so don't underestimate .
                </p>
                <div class="flex space-x-6">
                    <a href="#" class="text-gray-400 hover:text-white text-sm transition duration-300">Privacy Policy</a>
                    <a href="#" class="text-gray-400 hover:text-white text-sm transition duration-300">Terms of Service</a>
                    <a href="#" class="text-gray-400 hover:text-white text-sm transition duration-300">Shipping Policy</a>
                </div>
            </div>
        </div>
    </footer>

    <!-- Product Modal -->
    <div id="product-modal" class="hidden fixed inset-0 bg-black bg-opacity-50 z-50 flex items-center justify-center p-4">
        <div class="bg-white dark:bg-gray-800 rounded-lg shadow-xl max-w-4xl w-full max-h-[90vh] overflow-y-auto">
            <div class="relative">
                <button id="close-modal" class="absolute top-4 right-4 text-gray-500 dark:text-gray-300 hover:text-gray-700 dark:hover:text-white">
                    <i class="fas fa-times text-2xl"></i>
                </button>
                
                <div class="p-6">
                    <div class="lg:flex lg:space-x-8">
                        <div class="lg:w-1/2 mb-6 lg:mb-0">
                            <img id="modal-image" src="" alt="" class="w-full h-auto rounded-lg">
                        </div>
                        <div class="lg:w-1/2">
                            <h2 id="modal-title" class="text-2xl font-bold text-gray-900 dark:text-white mb-2"></h2>
                            <div class="flex items-center mb-4">
                                <div id="modal-rating" class="flex text-yellow-400 mr-2"></div>
                                <span id="modal-review-count" class="text-sm text-gray-500 dark:text-gray-400"></span>
                            </div>
                            <p id="modal-price" class="text-3xl font-bold text-primary mb-4"></p>
                            <p id="modal-description" class="text-gray-600 dark:text-gray-300 mb-6"></p>
                            
                            <div class="flex items-center mb-6">
                                <button id="decrease-quantity" class="p-2 border border-gray-300 dark:border-gray-600 rounded-l-md">
                                    <i class="fas fa-minus"></i>
                                </button>
                                <input id="product-quantity" type="number" value="1" min="1" class="w-16 text-center border-t border-b border-gray-300 dark:border-gray-600 dark:bg-gray-700 dark:text-white py-2">
                                <button id="increase-quantity" class="p-2 border border-gray-300 dark:border-gray-600 rounded-r-md">
                                    <i class="fas fa-plus"></i>
                                </button>
                            </div>
                            
                            <button id="add-to-cart-modal" class="w-full bg-primary hover:bg-blue-600 text-white py-3 px-4 rounded-md transition duration-300 mb-4">
                                Add to Cart
                            </button>
                            
                            <div class="flex space-x-4">
                                <button class="flex-1 border border-gray-300 dark:border-gray-600 text-gray-700 dark:text-gray-300 py-2 px-4 rounded-md hover:bg-gray-100 dark:hover:bg-gray-700 transition duration-300">
                                    <i class="far fa-heart mr-2"></i> Wishlist
                                </button>
                                <button class="flex-1 border border-gray-300 dark:border-gray-600 text-gray-700 dark:text-gray-300 py-2 px-4 rounded-md hover:bg-gray-100 dark:hover:bg-gray-700 transition duration-300">
                                    <i class="fas fa-share-alt mr-2"></i> Share
                                </button>
                            </div>
                        </div>
                    </div>
                    
                    <div class="mt-8 pt-6 border-t border-gray-200 dark:border-gray-700">
                        <h3 class="text-lg font-medium text-gray-900 dark:text-white mb-4">Product Details</h3>
                        <div id="modal-details" class="text-gray-600 dark:text-gray-300"></div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Sample product data
        const products = [
            {
                id: 1,
                name: "Anywhere Door",
                price: 499.99,
                category: "Transportation",
                rating: 5,
                reviews: 128,
                image: "https://static.wikia.nocookie.net/doraemon/images/6/6c/Anywhere_Door_CGI.png/revision/latest?cb=20201027180628&path-prefix=en",
                description: "Go anywhere instantly with this magical door! Just say the destination and walk through.",
                details: "<p>The Anywhere Door allows you to travel to any location instantly. Simply input your desired destination (coordinates, address, or even just a description) and the door will create a portal to that place.</p><ul class='list-disc pl-5 mt-2 space-y-1'><li>Works across all time periods</li><li>No size restrictions</li><li>Voice recognition system included</li><li>Safety protocols prevent dangerous destinations</li></ul>"
            },
            {
                id: 2,
                name: "Time Furoshiki a.k.a Time Cloth",
                price: 199.99,
                category: "Daily Life",
                rating: 4.5,
                reviews: 87,
                image: "https://static.wikia.nocookie.net/doraemon/images/1/12/Time_Cloth.jpg/revision/latest?cb=20190630110321&path-prefix=en",
                description: "Wrap up anything and carry it effortlessly. Perfect for travel and daily chores.",
                details: "<p>The Time Furoshiki is a magical cloth that can wrap any object, regardless of size or weight, making it easy to carry. The wrapped object becomes lightweight and compact.</p><ul class='list-disc pl-5 mt-2 space-y-1'><li>Adjustable size from handkerchief to blanket</li><li>Waterproof and tear-resistant</li><li>Automatically folds itself when not in use</li><li>Comes in various colors and patterns</li></ul>"
            },
            {
                id: 3,
                name: "Small Light",
                price: 349.99,
                category: "Daily Life",
                rating: 4,
                reviews: 64,
                image: "https://static.wikia.nocookie.net/doraemon/images/e/e5/Small_Light.jpg/revision/latest?cb=20190630111918&path-prefix=en",
                description: "Shrink any object to pocket size with this handy flashlight-like device.",
                details: "<p>The Small Light emits a special beam that can shrink objects to miniature size. The effect is temporary and wears off after a set time (adjustable from 1 hour to 1 week).</p><ul class='list-disc pl-5 mt-2 space-y-1'><li>Adjustable shrinking intensity</li><li>Safety lock prevents accidental shrinking</li><li>Rechargeable battery lasts for 1000 uses</li><li>Includes anti-loss tracking for shrunken items</li></ul>"
            },
            {
                id: 4,
                name: "Take-copter",
                price: 299.99,
                category: "Transportation",
                rating: 4,
                reviews: 56,
                image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQLt4CwYk9Yl1aKCImVqTjednDhzJ3HUXk0bw&s",
                description: "Fly anywhere with this propeller that sticks to your head! No batteries needed.",
                details: "<p>The Take-copter is a small propeller that attaches to your head (or any surface) and allows flight. It responds to thought commands for direction and speed.</p><ul class='list-disc pl-5 mt-2 space-y-1'><li>Weight capacity: 100kg</li><li>Maximum speed: 50km/h</li><li>Built-in collision avoidance</li><li>Works in all weather conditions</li></ul>"
            },
            {
                id: 5,
                name: "Memory Bread",
                price: 79.99,
                category: "Food",
                rating: 3.5,
                reviews: 42,
                image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRDRfrVBrGGOGAH7GGnxAxOqZKSF1P88hNP8g&s",
                description: "Print any information on this special bread and eat it to memorize instantly!",
                details: "<p>Memory Bread allows you to transfer information directly to your brain by eating. Simply print text or images onto the bread and consume it to gain the knowledge.</p><ul class='list-disc pl-5 mt-2 space-y-1'><li>Various flavors available</li><li>Retention lasts 1 month per slice</li><li>Gluten-free option available</li><li>Includes printable stickers for non-edible information</li></ul>"
            },
            {
                id: 6,
                name: "Time Machine",
                price: 999.99,
                category: "Time Travel",
                rating: 5,
                reviews: 32,
                image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS3Z7JvfKxywpSrHlnZRbG37K6bwYdgHYUsDA&s",
                description: "Travel through time with this compact, easy-to-use time machine.",
                details: "<p>The Time Machine allows safe travel to any point in history or the future. It includes safety features to prevent paradoxes and timeline disruptions.</p><ul class='list-disc pl-5 mt-2 space-y-1'><li>Pre-programmed historical events</li><li>Automatic return function</li><li>Language translation built-in</li><li>Currency and clothing adaptation</li></ul>"
            },
            {
                id: 7,
                name: "Translation Jelly",
                price: 59.99,
                category: "Daily Life",
                rating: 4,
                reviews: 38,
                image: "https://i.redd.it/phd3g7xc830f1.jpeg",
                description: "Understand and speak any language after consuming this tasty jelly!",
                details: "<p>Translation Jelly temporarily gives you the ability to understand and speak any language. Effects last for 24 hours per serving.</p><ul class='list-disc pl-5 mt-2 space-y-1'><li>Over 7000 languages included</li><li>Also translates animal communication</li><li>Various fruit flavors</li><li>No artificial preservatives</li></ul>"
            },
            {
                id: 8,
                name: "Pass Loop",
                price: 149.99,
                category: "Daily Life",
                rating: 4.5,
                reviews: 45,
                image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQA9PsK8CSQTa7cWXCo6JEdkxxR11zpi93O4g&s",
                description: "Walk through walls with this magical loop! Great for emergencies.",
                details: "<p>The Pass Loop creates a temporary passage through solid objects when placed against them. Simply hold the loop against a wall or other surface and walk through.</p><ul class='list-disc pl-5 mt-2 space-y-1'><li>Works on most materials</li><li>Duration: 30 seconds per use</li><li>Rechargeable with sunlight</li><li>Compact folding design</li></ul>"
            }
        ];

        // Shopping cart
        let cart = [];
        
        // DOM elements
        const themeToggle = document.getElementById('theme-toggle');
        const cartBtn = document.getElementById('cart-btn');
        const cartDropdown = document.getElementById('cart-dropdown');
        const cartCount = document.getElementById('cart-count');
        const cartItems = document.getElementById('cart-items');
        const cartTotal = document.getElementById('cart-total');
        const checkoutBtn = document.getElementById('checkout-btn');
        const userBtn = document.getElementById('user-btn');
        const userDropdown = document.getElementById('user-dropdown');
        const searchInput = document.getElementById('search');
        const productsGrid = document.getElementById('products-grid');
        const noProducts = document.getElementById('no-products');
        const productCount = document.getElementById('product-count');
        const sortBy = document.getElementById('sort-by');
        const priceRange = document.getElementById('price-range');
        const minPrice = document.getElementById('min-price');
        const maxPrice = document.getElementById('max-price');
        const resetFilters = document.getElementById('reset-filters');
        const carousel = document.getElementById('carousel');
        const carouselPrev = document.getElementById('carousel-prev');
        const carouselNext = document.getElementById('carousel-next');
        const newsletterForm = document.getElementById('newsletter-form');
        const newsletterMessage = document.getElementById('newsletter-message');
        const contactForm = document.getElementById('contact-form');
        const productModal = document.getElementById('product-modal');
        const closeModal = document.getElementById('close-modal');
        const modalImage = document.getElementById('modal-image');
        const modalTitle = document.getElementById('modal-title');
        const modalRating = document.getElementById('modal-rating');
        const modalReviewCount = document.getElementById('modal-review-count');
        const modalPrice = document.getElementById('modal-price');
        const modalDescription = document.getElementById('modal-description');
        const modalDetails = document.getElementById('modal-details');
        const decreaseQuantity = document.getElementById('decrease-quantity');
        const increaseQuantity = document.getElementById('increase-quantity');
        const productQuantity = document.getElementById('product-quantity');
        const addToCartModal = document.getElementById('add-to-cart-modal');
        const scrollAnimations = document.querySelectorAll('.scroll-animation');
        
        // Current product in modal
        let currentProduct = null;

        // Initialize the page
        document.addEventListener('DOMContentLoaded', function() {
            if (localStorage.getItem('theme') === 'dark' || (!localStorage.getItem('theme') && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
                document.documentElement.classList.add('dark');
            }
            
            // Render products
            renderProducts(products);
            renderCarousel();
            
            setupEventListeners();
            
            // Initialize scroll animations
            checkScroll();
            window.addEventListener('scroll', checkScroll);
        });

        // Set up event listeners
        function setupEventListeners() {
            // Theme toggle
            themeToggle.addEventListener('click', toggleTheme);
            
            // Cart dropdown
            cartBtn.addEventListener('click', toggleCartDropdown);
            
            userBtn.addEventListener('click', toggleUserDropdown);
            
            // Close dropdowns when clicking outside
            document.addEventListener('click', function(e) {
                if (!cartBtn.contains(e.target) && !cartDropdown.contains(e.target)) {
                    cartDropdown.classList.add('hidden');
                }
                if (!userBtn.contains(e.target) && !userDropdown.contains(e.target)) {
                    userDropdown.classList.add('hidden');
                }
            });
            
            // Search functionality
            searchInput.addEventListener('input', filterProducts);
            
            // Filter functionality
            document.querySelectorAll('.category-filter').forEach(filter => {
                filter.addEventListener('change', filterProducts);
            });
            
            document.querySelectorAll('.rating-filter').forEach(filter => {
                filter.addEventListener('change', filterProducts);
            });
            
            priceRange.addEventListener('input', function() {
                maxPrice.textContent = '$' + this.value;
                filterProducts();
            });
            
            resetFilters.addEventListener('click', function() {
                document.querySelectorAll('.category-filter').forEach(filter => {
                    filter.checked = false;
                });
                
                document.querySelectorAll('.rating-filter').forEach(filter => {
                    filter.checked = false;
                });
                
                priceRange.value = 1000;
                maxPrice.textContent = '$1000';
                sortBy.value = 'default';
                
                filterProducts();
            });
            
            // Sort functionality
            sortBy.addEventListener('change', filterProducts);
            
            // Carousel navigation
            carouselPrev.addEventListener('click', function() {
                const firstItem = carousel.firstElementChild;
                carousel.style.transition = 'transform 0.5s ease';
                carousel.style.transform = 'translateX(0)';
                setTimeout(() => {
                    carousel.style.transition = 'none';
                    carousel.appendChild(firstItem);
                    carousel.style.transform = 'translateX(-100%)';
                }, 500);
            });
            
            carouselNext.addEventListener('click', function() {
                const lastItem = carousel.lastElementChild;
                carousel.style.transition = 'none';
                carousel.insertBefore(lastItem, carousel.firstChild);
                carousel.style.transform = 'translateX(-100%)';
                setTimeout(() => {
                    carousel.style.transition = 'transform 0.5s ease';
                    carousel.style.transform = 'translateX(0)';
                }, 20);
            });
            
            // Newsletter form
            newsletterForm.addEventListener('submit', function(e) {
                e.preventDefault();
                const email = document.getElementById('newsletter-email').value;
                newsletterMessage.textContent = 'Thank you for subscribing! You will receive our latest updates soon.';
                newsletterMessage.classList.remove('hidden');
                newsletterForm.reset();
                setTimeout(() => {
                    newsletterMessage.classList.add('hidden');
                }, 5000);
            });
            
            // Contact form
            contactForm.addEventListener('submit', function(e) {
                e.preventDefault();
                alert('Thank you for your message! We will get back to you soon.');
                contactForm.reset();
            });
            
            // Product modal
            closeModal.addEventListener('click', function() {
                productModal.classList.add('hidden');
            });
            
            decreaseQuantity.addEventListener('click', function() {
                if (productQuantity.value > 1) {
                    productQuantity.value--;
                }
            });
            
            increaseQuantity.addEventListener('click', function() {
                productQuantity.value++;
            });
            
            addToCartModal.addEventListener('click', function() {
                if (currentProduct) {
                    addToCart(currentProduct, parseInt(productQuantity.value));
                    productModal.classList.add('hidden');
                }
            });
            
            // Checkout button
            checkoutBtn.addEventListener('click', function() {
                if (cart.length > 0) {
                    alert('Thank you for your purchase! Your order has been placed.');
                    cart = [];
                    updateCart();
                    cartDropdown.classList.add('hidden');
                } else {
                    alert('Your cart is empty. Please add some items before checking out.');
                }
            });
        }
        
        // Toggle dark/light mode
        function toggleTheme() {
            if (document.documentElement.classList.contains('dark')) {
                document.documentElement.classList.remove('dark');
                localStorage.setItem('theme', 'light');
            } else {
                document.documentElement.classList.add('dark');
                localStorage.setItem('theme', 'dark');
            }
        }
        
        // Toggle cart dropdown
        function toggleCartDropdown() {
            cartDropdown.classList.toggle('hidden');
            if (!cartDropdown.classList.contains('hidden')) {
                userDropdown.classList.add('hidden');
            }
        }
        
        // Toggle user dropdown
        function toggleUserDropdown() {
            userDropdown.classList.toggle('hidden');
            if (!userDropdown.classList.contains('hidden')) {
                cartDropdown.classList.add('hidden');
            }
        }
        
        // Render products
        function renderProducts(productsToRender) {
            productsGrid.innerHTML = '';
            
            if (productsToRender.length === 0) {
                noProducts.classList.remove('hidden');
                productCount.textContent = 'No products found';
                return;
            }
            
            noProducts.classList.add('hidden');
            productCount.textContent = `Showing ${productsToRender.length} of ${products.length} products`;
            
            productsToRender.forEach(product => {
                const productCard = document.createElement('div');
                productCard.className = 'bg-white dark:bg-gray-800 rounded-lg shadow-md overflow-hidden product-card transition duration-300';
                productCard.innerHTML = `
                    <div class="relative pb-2/3 h-48">
                        <img src="${product.image}" alt="${product.name}" class="w-full h-full object-cover">
                    </div>
                    <div class="p-4">
                        <div class="flex justify-between items-start mb-2">
                            <h3 class="text-lg font-medium text-gray-900 dark:text-white">${product.name}</h3>
                            <span class="text-lg font-bold text-primary">$${product.price.toFixed(2)}</span>
                        </div>
                        <div class="flex items-center mb-3">
                            ${renderRatingStars(product.rating)}
                            <span class="ml-2 text-sm text-gray-500 dark:text-gray-400">(${product.reviews})</span>
                        </div>
                        <p class="text-gray-600 dark:text-gray-300 text-sm mb-4 line-clamp-2">${product.description}</p>
                        <div class="flex justify-between items-center">
                            <span class="text-xs px-2 py-1 bg-gray-100 dark:bg-gray-700 text-gray-600 dark:text-gray-300 rounded">${product.category}</span>
                            <button class="add-to-cart bg-primary hover:bg-blue-600 text-white py-2 px-4 rounded-md transition duration-300" data-id="${product.id}">
                                Add to Cart
                            </button>
                        </div>
                    </div>
                `;
                
                productCard.querySelector('.add-to-cart').addEventListener('click', function() {
                    addToCart(product, 1);
                });
                
                productCard.addEventListener('click', function(e) {
                    if (!e.target.classList.contains('add-to-cart')) {
                        openProductModal(product);
                    }
                });
                
                productsGrid.appendChild(productCard);
            });
        }
        
        // Render rating stars
        function renderRatingStars(rating) {
            let stars = '';
            const fullStars = Math.floor(rating);
            const hasHalfStar = rating % 1 >= 0.5;
            
            for (let i = 0; i < fullStars; i++) {
                stars += '<i class="fas fa-star text-yellow-400"></i>';
            }
            
            if (hasHalfStar) {
                stars += '<i class="fas fa-star-half-alt text-yellow-400"></i>';
            }
            
            for (let i = 0; i < 5 - Math.ceil(rating); i++) {
                stars += '<i class="far fa-star text-yellow-400"></i>';
            }
            
            return stars;
        }
        
        // Render carousel
        function renderCarousel() {
            const featuredProducts = products.slice(0, 3); // Get first 3 products as featured
            
            featuredProducts.forEach(product => {
                const carouselItem = document.createElement('div');
                carouselItem.className = 'flex-shrink-0 w-full';
                carouselItem.innerHTML = `
                    <div class="bg-white dark:bg-gray-800 rounded-lg shadow-md overflow-hidden mx-4">
                        <div class="md:flex">
                            <div class="md:w-1/2">
                                <img src="${product.image}" alt="${product.name}" class="w-full h-full object-cover">
                            </div>
                            <div class="p-8 md:w-1/2">
                                <h3 class="text-2xl font-bold text-gray-900 dark:text-white mb-2">${product.name}</h3>
                                <div class="flex items-center mb-4">
                                    ${renderRatingStars(product.rating)}
                                    <span class="ml-2 text-sm text-gray-500 dark:text-gray-400">${product.reviews} reviews</span>
                                </div>
                                <p class="text-gray-600 dark:text-gray-300 mb-6">${product.description}</p>
                                <div class="flex items-center justify-between">
                                    <span class="text-3xl font-bold text-primary">$${product.price.toFixed(2)}</span>
                                    <button class="add-to-cart bg-primary hover:bg-blue-600 text-white py-2 px-6 rounded-md transition duration-300" data-id="${product.id}">
                                        Add to Cart
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>
                `;
                
                carouselItem.querySelector('.add-to-cart').addEventListener('click', function() {
                    addToCart(product, 1);
                });
                
                carousel.appendChild(carouselItem);
            });
        }
        
        // Filter products
        function filterProducts() {
            const searchTerm = searchInput.value.toLowerCase();
            const selectedCategories = Array.from(document.querySelectorAll('.category-filter:checked')).map(el => el.value);
            const selectedRatings = Array.from(document.querySelectorAll('.rating-filter:checked')).map(el => parseInt(el.value));
            const maxPrice = parseInt(priceRange.value);
            const sortByValue = sortBy.value;
            
            let filteredProducts = products.filter(product => {
                // Search filter
                const matchesSearch = product.name.toLowerCase().includes(searchTerm) || 
                                     product.description.toLowerCase().includes(searchTerm) ||
                                     product.category.toLowerCase().includes(searchTerm);
                
                // Category filter
                const matchesCategory = selectedCategories.length === 0 || 
                                       selectedCategories.includes(product.category);
                
                // Rating filter
                const matchesRating = selectedRatings.length === 0 || 
                                     selectedRatings.some(rating => Math.floor(product.rating) === rating);
                
                // Price filter
                const matchesPrice = product.price <= maxPrice;
                
                return matchesSearch && matchesCategory && matchesRating && matchesPrice;
            });
            
            // Sort products
            switch (sortByValue) {
                case 'price-low':
                    filteredProducts.sort((a, b) => a.price - b.price);
                    break;
                case 'price-high':
                    filteredProducts.sort((a, b) => b.price - a.price);
                    break;
                case 'rating':
                    filteredProducts.sort((a, b) => b.rating - a.rating);
                    break;
                case 'popular':
                    filteredProducts.sort((a, b) => b.reviews - a.reviews);
                    break;
                default:
                    // Default sorting (by ID or original order)
                    break;
            }
            
            renderProducts(filteredProducts);
        }
        
        // Add to cart
        function addToCart(product, quantity) {
            const existingItem = cart.find(item => item.id === product.id);
            
            if (existingItem) {
                existingItem.quantity += quantity;
            } else {
                cart.push({
                    id: product.id,
                    name: product.name,
                    price: product.price,
                    image: product.image,
                    quantity: quantity
                });
            }
            
            updateCart();
            
            // Show notification
            const notification = document.createElement('div');
            notification.className = 'fixed top-20 right-4 bg-green-500 text-white px-4 py-2 rounded-md shadow-lg z-50 animate-bounce';
            notification.textContent = `${quantity} ${product.name} added to cart!`;
            document.body.appendChild(notification);
            
            setTimeout(() => {
                notification.classList.remove('animate-bounce');
                notification.classList.add('opacity-0', 'transition-opacity', 'duration-300');
                setTimeout(() => notification.remove(), 300);
            }, 2000);
        }
        
        // Update cart
        function updateCart() {
            cartCount.textContent = cart.reduce((total, item) => total + item.quantity, 0);
            
            cartItems.innerHTML = '';
            
            if (cart.length === 0) {
                cartItems.innerHTML = '<p class="text-center text-gray-500 dark:text-gray-400 py-4">Your cart is empty</p>';
                cartTotal.textContent = '$0.00';
                return;
            }
            
            let total = 0;
            
            cart.forEach(item => {
                const cartItem = document.createElement('div');
                cartItem.className = 'cart-item flex items-center p-3 border-b border-gray-200 dark:border-gray-700';
                cartItem.innerHTML = `
                    <img src="${item.image}" alt="${item.name}" class="w-12 h-12 object-cover rounded-md">
                    <div class="ml-3 flex-grow">
                        <h4 class="text-sm font-medium text-gray-900 dark:text-white">${item.name}</h4>
                        <p class="text-sm text-gray-500 dark:text-gray-400">$${item.price.toFixed(2)} x ${item.quantity}</p>
                    </div>
                    <div class="flex items-center">
                        <span class="text-sm font-medium text-gray-900 dark:text-white mr-2">$${(item.price * item.quantity).toFixed(2)}</span>
                        <button class="remove-from-cart text-red-500 hover:text-red-700" data-id="${item.id}">
                            <i class="fas fa-times"></i>
                        </button>
                    </div>
                `;
                
                cartItem.querySelector('.remove-from-cart').addEventListener('click', function() {
                    removeFromCart(item.id);
                });
                
                cartItems.appendChild(cartItem);
                total += item.price * item.quantity;
            });
            
            cartTotal.textContent = '$' + total.toFixed(2);
        }
        
        // Remove from cart
        function removeFromCart(productId) {
            cart = cart.filter(item => item.id !== productId);
            updateCart();
        }
        
        // Open product modal
        function openProductModal(product) {
            currentProduct = product;
            modalImage.src = product.image;
            modalImage.alt = product.name;
            modalTitle.textContent = product.name;
            modalRating.innerHTML = renderRatingStars(product.rating);
            modalReviewCount.textContent = `${product.reviews} reviews`;
            modalPrice.textContent = '$' + product.price.toFixed(2);
            modalDescription.textContent = product.description;
            modalDetails.innerHTML = product.details;
            productQuantity.value = 1;
            
            productModal.classList.remove('hidden');
        }
        
        // Scroll animations
        function checkScroll() {
            scrollAnimations.forEach(element => {
                const elementTop = element.getBoundingClientRect().top;
                const windowHeight = window.innerHeight;
                
                if (elementTop < windowHeight - 100) {
                    element.classList.add('animate');
                }
                
            });
        }
    
   
        
        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
    </script>
</body>
</html>

