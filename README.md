<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KIDS TIME | Premium Wonder & Apparel Store for Kids</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        brand: {
                            pink: '#FF6B8B',
                            purple: '#8A4FFF',
                            yellow: '#FFC837',
                            blue: '#4A90E2',
                            mint: '#2ECC71',
                            softBg: '#F7F9FC',
                            text: '#2D3748',
                            muted: '#718096'
                        }
                    },
                    fontFamily: {
                        sans: ['Fredoka', 'Quicksand', 'sans-serif'],
                        heading: ['Fredoka', 'sans-serif']
                    },
                    borderRadius: {
                        '4xl': '2rem'
                    }
                }
            }
        }
    </script>
    <!-- Google Fonts & FontAwesome -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@400;500;600;700&family=Quicksand:wght@500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        body {
            font-family: 'Quicksand', sans-serif;
            background-color: #F7F9FC;
            color: #2D3748;
            overflow-x: hidden;
        }
        h1, h2, h3, h4, h5, h6, .brand-font {
            font-family: 'Fredoka', sans-serif;
        }

        /* Playful Floating Animations */
        @keyframes floatSlow {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-15px) rotate(3deg); }
        }
        @keyframes floatMedium {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-10px) rotate(-3deg); }
        }
        @keyframes pulseGlow {
            0%, 100% { opacity: 0.8; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.05); }
        }

        .animate-float-slow { animation: floatSlow 6s ease-in-out infinite; }
        .animate-float-medium { animation: floatMedium 4s ease-in-out infinite; }
        .animate-pulse-glow { animation: pulseGlow 3s ease-in-out infinite; }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 10px;
        }
        ::-webkit-scrollbar-track {
            background: #F7F9FC;
        }
        ::-webkit-scrollbar-thumb {
            background: #8A4FFF;
            border-radius: 10px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #FF6B8B;
        }

        .glass-card {
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(10px);
            border: 2px solid rgba(255, 255, 255, 0.8);
        }

        .product-card {
            transition: all 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
        }
        .product-card:hover {
            transform: translateY(-8px);
        }
    </style>
</head>
<body class="antialiased selection:bg-brand-pink selection:text-white">

    <!-- TOP ANNOUNCEMENT BAR -->
    <div class="bg-gradient-to-r from-brand-pink via-brand-purple to-brand-blue text-white text-xs font-bold py-2 px-4 text-center tracking-wide">
        <span class="inline-block animate-bounce mr-1">🎁</span> SPECIAL OFFER: Free Express Shipping on orders over $50! Use code <span class="underline decoration-wavy decoration-brand-yellow font-black">KIDSTIME20</span> for 20% OFF
    </div>

    <!-- MAIN NAVIGATION BAR -->
    <header class="sticky top-0 z-40 bg-white/90 backdrop-blur-md shadow-sm border-b border-gray-100">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                
                <!-- Logo -->
                <div class="flex-shrink-0 flex items-center cursor-pointer" onclick="navigateTo('home')">
                    <div class="w-12 h-12 rounded-2xl bg-gradient-to-tr from-brand-pink to-brand-yellow flex items-center justify-center text-white text-2xl shadow-md transform hover:rotate-6 transition-transform">
                        <i class="fa-solid fa-shapes"></i>
                    </div>
                    <div class="ml-3">
                        <span class="text-2xl font-black tracking-tight text-brand-purple">KIDS<span class="text-brand-pink">TIME</span></span>
                        <span class="block text-[10px] font-bold text-brand-blue tracking-widest uppercase">Play · Wear · Smile</span>
                    </div>
                </div>

                <!-- Desktop Navigation Links -->
                <nav class="hidden lg:flex items-center space-x-6 text-sm font-bold text-gray-700">
                    <button onclick="navigateTo('home')" class="hover:text-brand-pink transition-colors">Home</button>
                    <button onclick="filterCategory('Toys')" class="hover:text-brand-pink transition-colors">Toys</button>
                    <button onclick="filterCategory('Clothes')" class="hover:text-brand-pink transition-colors">Clothing</button>
                    <button onclick="filterCategory('Shoes')" class="hover:text-brand-pink transition-colors">Shoes</button>
                    <button onclick="filterCategory('Bags')" class="hover:text-brand-pink transition-colors">Bags</button>
                    <button onclick="filterCategory('Accessories')" class="hover:text-brand-pink transition-colors">Accessories</button>
                    <button onclick="filterCategory('Baby')" class="hover:text-brand-pink transition-colors">Baby</button>
                    <button onclick="filterCategory('New')" class="text-brand-purple flex items-center gap-1 font-black"><span class="w-2 h-2 rounded-full bg-brand-pink animate-ping"></span> New</button>
                    <button onclick="filterCategory('Sale')" class="text-brand-pink font-black">Sale %</button>
                </nav>

                <!-- Action Icons -->
                <div class="flex items-center space-x-3 sm:space-x-4">
                    <!-- Search Button -->
                    <button onclick="toggleSearchModal()" class="w-10 h-10 rounded-full bg-gray-100 hover:bg-brand-blue/10 hover:text-brand-blue flex items-center justify-center text-gray-600 transition-colors">
                        <i class="fa-solid fa-magnifying-glass"></i>
                    </button>

                    <!-- Wishlist -->
                    <button onclick="showWishlistModal()" class="relative w-10 h-10 rounded-full bg-gray-100 hover:bg-brand-pink/10 hover:text-brand-pink flex items-center justify-center text-gray-600 transition-colors">
                        <i class="fa-regular fa-heart"></i>
                        <span id="wishlistBadge" class="absolute -top-1 -right-1 bg-brand-pink text-white text-[10px] font-bold w-5 h-5 rounded-full flex items-center justify-center border-2 border-white">0</span>
                    </button>

                    <!-- Cart -->
                    <button onclick="toggleCartDrawer()" class="relative w-10 h-10 rounded-full bg-brand-purple text-white flex items-center justify-center shadow-md hover:bg-brand-purple/90 transition-transform active:scale-95">
                        <i class="fa-solid fa-bag-shopping"></i>
                        <span id="cartBadge" class="absolute -top-1 -right-1 bg-brand-yellow text-brand-text text-[10px] font-black w-5 h-5 rounded-full flex items-center justify-center border-2 border-white">0</span>
                    </button>

                    <!-- Mobile Menu Button -->
                    <button onclick="toggleMobileMenu()" class="lg:hidden w-10 h-10 rounded-full bg-gray-100 flex items-center justify-center text-gray-600">
                        <i class="fa-solid fa-bars text-lg"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Navigation Menu -->
        <div id="mobileMenu" class="hidden lg:hidden bg-white border-b border-gray-200 px-4 pt-2 pb-6 space-y-3 font-bold text-gray-700">
            <button onclick="navigateTo('home'); toggleMobileMenu()" class="block w-full text-left py-2 hover:text-brand-pink">Home</button>
            <button onclick="filterCategory('Toys'); toggleMobileMenu()" class="block w-full text-left py-2 hover:text-brand-pink">Toys & Games</button>
            <button onclick="filterCategory('Clothes'); toggleMobileMenu()" class="block w-full text-left py-2 hover:text-brand-pink">Clothing</button>
            <button onclick="filterCategory('Shoes'); toggleMobileMenu()" class="block w-full text-left py-2 hover:text-brand-pink">Shoes & Caps</button>
            <button onclick="filterCategory('Bags'); toggleMobileMenu()" class="block w-full text-left py-2 hover:text-brand-pink">Bags & Backpacks</button>
            <button onclick="filterCategory('Baby'); toggleMobileMenu()" class="block w-full text-left py-2 hover:text-brand-pink">Baby Products</button>
            <button onclick="filterCategory('Sale'); toggleMobileMenu()" class="block w-full text-left py-2 text-brand-pink">Sale & Discounts</button>
        </div>
    </header>

    <!-- MAIN DYNAMIC CONTENT CONTAINER -->
    <main id="app">
        <!-- Default: Homepage View -->
    </main>

    <!-- FOOTER SECTION -->
    <footer class="bg-gray-900 text-white pt-16 pb-12 rounded-t-[3rem] mt-20 relative overflow-hidden">
        <!-- Floating shapes background in footer -->
        <div class="absolute -top-10 left-10 w-24 h-24 bg-brand-purple/20 rounded-full blur-2xl"></div>
        <div class="absolute bottom-5 right-10 w-32 h-32 bg-brand-pink/20 rounded-full blur-2xl"></div>

        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-5 gap-10">
                
                <!-- Brand Info -->
                <div class="lg:col-span-2">
                    <div class="flex items-center cursor-pointer mb-4" onclick="navigateTo('home')">
                        <div class="w-10 h-10 rounded-xl bg-gradient-to-tr from-brand-pink to-brand-yellow flex items-center justify-center text-white text-xl">
                            <i class="fa-solid fa-shapes"></i>
                        </div>
                        <span class="ml-3 text-2xl font-black tracking-tight text-white">KIDS<span class="text-brand-pink">TIME</span></span>
                    </div>
                    <p class="text-gray-400 text-sm leading-relaxed mb-6 max-w-sm">
                        Bringing joy, style, and playful wonder to childhood! Premium quality toys, comfortable clothing, and joyful essentials designed with safety and magic in mind.
                    </p>
                    <div class="flex space-x-3">
                        <a href="#" class="w-9 h-9 rounded-full bg-gray-800 hover:bg-brand-pink flex items-center justify-center text-gray-300 hover:text-white transition-colors"><i class="fa-brands fa-facebook-f"></i></a>
                        <a href="#" class="w-9 h-9 rounded-full bg-gray-800 hover:bg-brand-purple flex items-center justify-center text-gray-300 hover:text-white transition-colors"><i class="fa-brands fa-instagram"></i></a>
                        <a href="#" class="w-9 h-9 rounded-full bg-gray-800 hover:bg-brand-blue flex items-center justify-center text-gray-300 hover:text-white transition-colors"><i class="fa-brands fa-tiktok"></i></a>
                        <a href="#" class="w-9 h-9 rounded-full bg-gray-800 hover:bg-brand-yellow flex items-center justify-center text-gray-300 hover:text-white transition-colors"><i class="fa-brands fa-youtube"></i></a>
                    </div>
                </div>

                <!-- Quick Links -->
                <div>
                    <h4 class="text-lg font-bold text-white mb-4">Quick Links</h4>
                    <ul class="space-y-2 text-sm text-gray-400 font-medium">
                        <li><a href="#" onclick="navigateTo('home')" class="hover:text-brand-yellow transition-colors">Home</a></li>
                        <li><a href="#" onclick="filterCategory('Toys')" class="hover:text-brand-yellow transition-colors">Kids Toys & Games</a></li>
                        <li><a href="#" onclick="filterCategory('Clothes')" class="hover:text-brand-yellow transition-colors">Kids Clothing</a></li>
                        <li><a href="#" onclick="filterCategory('Shoes')" class="hover:text-brand-yellow transition-colors">Footwear & Shoes</a></li>
                        <li><a href="#" onclick="filterCategory('Baby')" class="hover:text-brand-yellow transition-colors">Baby Essentials</a></li>
                    </ul>
                </div>

                <!-- Customer Care -->
                <div>
                    <h4 class="text-lg font-bold text-white mb-4">Customer Care</h4>
                    <ul class="space-y-2 text-sm text-gray-400 font-medium">
                        <li><a href="#" class="hover:text-brand-yellow transition-colors">Track Order</a></li>
                        <li><a href="#" class="hover:text-brand-yellow transition-colors">Shipping Policy</a></li>
                        <li><a href="#" class="hover:text-brand-yellow transition-colors">Returns & Refunds</a></li>
                        <li><a href="#" class="hover:text-brand-yellow transition-colors">Terms & Conditions</a></li>
                        <li><a href="#" class="hover:text-brand-yellow transition-colors">Privacy Policy</a></li>
                    </ul>
                </div>

                <!-- Contact & Support -->
                <div>
                    <h4 class="text-lg font-bold text-white mb-4">Contact Us</h4>
                    <ul class="space-y-3 text-sm text-gray-400 font-medium">
                        <li class="flex items-center gap-3">
                            <i class="fa-solid fa-location-dot text-brand-pink"></i>
                            <span>789 Rainbow Street, Wonder City</span>
                        </li>
                        <li class="flex items-center gap-3">
                            <i class="fa-solid fa-phone text-brand-blue"></i>
                            <span>+1 (800) 543-7846</span>
                        </li>
                        <li class="flex items-center gap-3">
                            <i class="fa-solid fa-envelope text-brand-yellow"></i>
                            <span>support@kidstime.com</span>
                        </li>
                    </ul>
                </div>

            </div>

            <hr class="border-gray-800 my-10">

            <div class="flex flex-col sm:flex-row items-center justify-between text-xs text-gray-500 font-medium gap-4">
                <p>&copy; 2026 KIDS TIME Inc. All rights reserved. Crafted for joyful parenting.</p>
                <div class="flex space-x-4 text-xl text-gray-400">
                    <i class="fa-brands fa-cc-visa hover:text-white"></i>
                    <i class="fa-brands fa-cc-mastercard hover:text-white"></i>
                    <i class="fa-brands fa-cc-apple-pay hover:text-white"></i>
                    <i class="fa-brands fa-cc-paypal hover:text-white"></i>
                </div>
            </div>
        </div>
    </footer>

    <!-- CART SLIDE-OVER DRAWER -->
    <div id="cartDrawer" class="fixed inset-0 z-50 overflow-hidden hidden" aria-labelledby="slide-over-title" role="dialog" aria-modal="true">
        <div class="absolute inset-0 bg-gray-900/50 backdrop-blur-sm transition-opacity" onclick="toggleCartDrawer()"></div>

        <div class="fixed inset-y-0 right-0 pl-10 max-w-full flex">
            <div class="w-screen max-w-md bg-white shadow-2xl flex flex-col justify-between">
                
                <!-- Drawer Header -->
                <div class="p-6 border-b border-gray-100 flex items-center justify-between">
                    <div class="flex items-center gap-2">
                        <i class="fa-solid fa-bag-shopping text-brand-purple text-xl"></i>
                        <h2 class="text-xl font-bold text-gray-800">Your Shopping Cart</h2>
                    </div>
                    <button onclick="toggleCartDrawer()" class="text-gray-400 hover:text-gray-600 p-2 rounded-full hover:bg-gray-100">
                        <i class="fa-solid fa-xmark text-xl"></i>
                    </button>
                </div>

                <!-- Cart Items Container -->
                <div id="cartItemsContainer" class="p-6 space-y-4 overflow-y-auto flex-1">
                    <!-- Items injected dynamically -->
                </div>

                <!-- Drawer Footer / Checkout -->
                <div class="p-6 bg-gray-50 border-t border-gray-100 space-y-4">
                    <div class="flex justify-between text-base font-bold text-gray-800">
                        <span>Subtotal</span>
                        <span id="cartSubtotal">$0.00</span>
                    </div>
                    <p class="text-xs text-gray-500">Shipping, taxes and coupons calculated at checkout.</p>
                    <button onclick="navigateTo('checkout')" class="w-full bg-brand-purple hover:bg-brand-purple/90 text-white font-bold py-3.5 rounded-2xl shadow-lg transition-transform active:scale-95 flex items-center justify-center gap-2">
                        Proceed to Checkout <i class="fa-solid fa-arrow-right text-xs"></i>
                    </button>
                </div>

            </div>
        </div>
    </div>

    <!-- SEARCH OVERLAY MODAL -->
    <div id="searchModal" class="fixed inset-0 z-50 bg-gray-900/60 backdrop-blur-md hidden flex items-start justify-center pt-20 px-4">
        <div class="bg-white rounded-3xl p-6 w-full max-w-2xl shadow-2xl relative">
            <button onclick="toggleSearchModal()" class="absolute top-4 right-4 text-gray-400 hover:text-gray-600">
                <i class="fa-solid fa-xmark text-xl"></i>
            </button>
            <h3 class="text-lg font-bold text-gray-800 mb-4">Search KIDS TIME Store</h3>
            <div class="relative">
                <input type="text" id="searchInput" onkeyup="handleSearch()" placeholder="Search toys, jackets, shoes, backpacks..." class="w-full pl-12 pr-4 py-3 bg-gray-100 rounded-2xl text-sm font-medium focus:outline-none focus:ring-2 focus:ring-brand-purple">
                <i class="fa-solid fa-magnifying-glass absolute left-4 top-3.5 text-gray-400"></i>
            </div>
            <div id="searchResults" class="mt-6 max-h-80 overflow-y-auto space-y-3">
                <p class="text-sm text-gray-400 text-center py-6">Start typing to search for products...</p>
            </div>
        </div>
    </div>

    <!-- QUICK VIEW PRODUCT MODAL -->
    <div id="quickViewModal" class="fixed inset-0 z-50 bg-gray-900/60 backdrop-blur-md hidden flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl p-6 sm:p-8 max-w-3xl w-full max-h-[90vh] overflow-y-auto relative shadow-2xl">
            <button onclick="closeQuickView()" class="absolute top-4 right-4 w-9 h-9 bg-gray-100 rounded-full flex items-center justify-center text-gray-500 hover:bg-gray-200">
                <i class="fa-solid fa-xmark"></i>
            </button>
            <div id="quickViewContent">
                <!-- Injected via JS -->
            </div>
        </div>
    </div>

    <!-- JAVASCRIPT DATA & E-COMMERCE ENGINE -->
    <script>
        // Real Sample Products Dataset
        const products = [
            {
                id: 1,
                name: "Interactive Wooden Building Blocks Set",
                category: "Toys",
                price: 29.99,
                origPrice: 39.99,
                rating: 4.9,
                reviewsCount: 42,
                badge: "Best Seller",
                image: "https://images.unsplash.com/photo-1587654780291-39c9404d746b?auto=format&fit=crop&w=600&q=80",
                description: "50-piece organic wooden block set painted with safe water-based non-toxic dyes. Promotes motor skills, creativity, and spatial logic.",
                colors: ["#FF6B8B", "#4A90E2", "#FFC837"],
                sizes: ["One Size"]
            },
            {
                id: 2,
                name: "Cozy Cotton Dino Hoodie & Jogger Set",
                category: "Clothes",
                price: 34.50,
                origPrice: 45.00,
                rating: 4.8,
                reviewsCount: 38,
                badge: "Popular",
                image: "https://images.unsplash.com/photo-1519238263530-99bdd11df2ea?auto=format&fit=crop&w=600&q=80",
                description: "Ultra-soft 100% organic cotton tracksuit with playful dinosaur spikes along the hood. Perfect for active outdoor fun.",
                colors: ["#2ECC71", "#8A4FFF"],
                sizes: ["2-3Y", "4-5Y", "6-7Y"]
            },
            {
                id: 3,
                name: "Light-Up LED Unisex Sneakers",
                category: "Shoes",
                price: 42.00,
                origPrice: 55.00,
                rating: 5.0,
                reviewsCount: 89,
                badge: "Trending",
                image: "https://images.unsplash.com/photo-1514989940723-e8e51635b782?auto=format&fit=crop&w=600&q=80",
                description: "Rechargeable light-up sneakers with 7 vibrant colors and flash modes. Breathable mesh and anti-slip rubber soles.",
                colors: ["#4A90E2", "#FF6B8B"],
                sizes: ["EU 26", "EU 28", "EU 30", "EU 32"]
            },
            {
                id: 4,
                name: "Ergonomic Cute Bear Preschool Backpack",
                category: "Bags",
                price: 24.99,
                origPrice: 32.00,
                rating: 4.7,
                reviewsCount: 29,
                badge: "New",
                image: "https://images.unsplash.com/photo-1553062407-98eeb64c6a62?auto=format&fit=crop&w=600&q=80",
                description: "Waterproof lightweight school bag with chest straps, padded shoulders, and reflective safety strips.",
                colors: ["#FFC837", "#8A4FFF"],
                sizes: ["Standard"]
            },
            {
                id: 5,
                name: "Plush Huggable Teddy Bear Companion",
                category: "Toys",
                price: 19.99,
                origPrice: 24.99,
                rating: 4.9,
                reviewsCount: 110,
                badge: "Top Choice",
                image: "https://images.unsplash.com/photo-1559454403-b8fb88521f11?auto=format&fit=crop&w=600&q=80",
                description: "Hypoallergenic plush teddy bear crafted with ultra-soft faux fur. Safe for toddlers and machine washable.",
                colors: ["#D4A373"],
                sizes: [" Medium (12-inch)"]
            },
            {
                id: 6,
                name: "Pastel Rainbow Knit Beanie Cap",
                category: "Accessories",
                price: 14.50,
                origPrice: 19.99,
                rating: 4.6,
                reviewsCount: 19,
                badge: "Sale",
                image: "https://images.unsplash.com/photo-1576053139778-7e32f2ae3cfd?auto=format&fit=crop&w=600&q=80",
                description: "Soft acrylic fleece-lined winter hat featuring a fluffy faux-fur pom pom top. Elastic fit for all ages.",
                colors: ["#FF6B8B", "#4A90E2"],
                sizes: ["S (1-3Y)", "M (4-8Y)"]
            },
            {
                id: 7,
                name: "Baby Silicone Feeding & Teething Set",
                category: "Baby",
                price: 22.00,
                origPrice: 28.00,
                rating: 4.9,
                reviewsCount: 56,
                badge: "Must-Have",
                image: "https://images.unsplash.com/photo-1584839627923-96a39788b086?auto=format&fit=crop&w=600&q=80",
                description: "BPA-free food-grade silicone bibs, suction bowl, and soft training spoon set. Microwave and dishwasher safe.",
                colors: ["#2ECC71", "#FF6B8B", "#FFC837"],
                sizes: ["One Size"]
            },
            {
                id: 8,
                name: "Remote Control STEM Speed Racer Car",
                category: "Toys",
                price: 38.99,
                origPrice: 49.99,
                rating: 4.8,
                reviewsCount: 74,
                badge: "Hot",
                image: "https://images.unsplash.com/photo-1594787318286-3d835c1d207f?auto=format&fit=crop&w=600&q=80",
                description: "High-speed 2.4GHz remote control car with 360-degree rotation tricks and rechargeable lithium battery.",
                colors: ["#8A4FFF", "#FF6B8B"],
                sizes: ["1:16 Scale"]
            }
        ];

        // Global State
        let cart = [];
        let wishlist = [];
        let activeFilter = 'All';

        // Initialize App
        document.addEventListener('DOMContentLoaded', () => {
            renderHomepage();
            updateBadges();
        });

        // SPA Navigation Manager
        function navigateTo(page, param = null) {
            window.scrollTo({ top: 0, behavior: 'smooth' });
            const app = document.getElementById('app');

            if (page === 'home') {
                renderHomepage();
            } else if (page === 'product') {
                renderProductDetails(param);
            } else if (page === 'checkout') {
                renderCheckoutPage();
            }
        }

        // RENDER HOMEPAGE
        function renderHomepage() {
            const app = document.getElementById('app');
            app.innerHTML = `
                <!-- 1. HERO SECTION -->
                <section class="relative bg-gradient-to-b from-blue-50 via-purple-50/50 to-F7F9FC pt-8 pb-20 overflow-hidden">
                    <!-- Animated Floating Shapes -->
                    <div class="absolute top-10 left-8 text-brand-pink text-4xl opacity-40 animate-float-slow"><i class="fa-solid fa-cloud"></i></div>
                    <div class="absolute top-36 right-16 text-brand-yellow text-3xl opacity-50 animate-float-medium"><i class="fa-solid fa-star"></i></div>
                    <div class="absolute bottom-10 left-1/4 text-brand-blue text-4xl opacity-30 animate-float-slow"><i class="fa-solid fa-balloon"></i></div>
                    
                    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
                        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                            
                            <!-- Hero Text -->
                            <div class="text-center lg:text-left">
                                <span class="inline-block px-4 py-2 rounded-full bg-brand-pink/10 text-brand-pink text-xs font-bold uppercase tracking-wider mb-4 border border-brand-pink/20">
                                    ✨ Premium Kids Store
                                </span>
                                <h1 class="text-4xl sm:text-5xl lg:text-6xl font-black text-gray-900 tracking-tight leading-tight mb-6">
                                    Little Things, <br><span class="text-transparent bg-clip-text bg-gradient-to-r from-brand-pink via-brand-purple to-brand-blue">Big Smiles! 🌈</span>
                                </h1>
                                <p class="text-base sm:text-lg text-gray-600 mb-8 max-w-lg mx-auto lg:mx-0 font-medium leading-relaxed">
                                    Discover fun educational toys, trendy comfortable outfits, and adorable accessories crafted with love and safety for your little ones.
                                </p>
                                <div class="flex flex-col sm:flex-row items-center justify-center lg:justify-start gap-4">
                                    <button onclick="scrollToProducts()" class="w-full sm:w-auto bg-brand-pink hover:bg-brand-pink/90 text-white font-bold px-8 py-4 rounded-2xl shadow-lg shadow-brand-pink/30 hover:scale-105 transition-all text-base flex items-center justify-center gap-2">
                                        Shop Now <i class="fa-solid fa-bag-shopping"></i>
                                    </button>
                                    <button onclick="filterCategory('Toys')" class="w-full sm:w-auto bg-white hover:bg-gray-50 text-gray-800 font-bold px-8 py-4 rounded-2xl shadow-md border border-gray-200 hover:scale-105 transition-all text-base flex items-center justify-center gap-2">
                                        Explore Toys <i class="fa-solid fa-gamepad text-brand-purple"></i>
                                    </button>
                                </div>

                                <!-- Trust Badges -->
                                <div class="mt-10 pt-8 border-t border-gray-200/60 flex items-center justify-center lg:justify-start gap-8 text-xs font-bold text-gray-500">
                                    <div class="flex items-center gap-2">
                                        <i class="fa-solid fa-shield-cat text-brand-mint text-base"></i> 100% Non-Toxic
                                    </div>
                                    <div class="flex items-center gap-2">
                                        <i class="fa-solid fa-truck-fast text-brand-blue text-base"></i> Fast Delivery
                                    </div>
                                    <div class="flex items-center gap-2">
                                        <i class="fa-solid fa-rotate-left text-brand-purple text-base"></i> Easy Returns
                                    </div>
                                </div>
                            </div>

                            <!-- Hero Banner Image Card -->
                            <div class="relative flex justify-center">
                                <div class="relative w-full max-w-md bg-white p-4 rounded-4xl shadow-2xl rotate-2 hover:rotate-0 transition-transform duration-500 border-4 border-white">
                                    <img src="https://images.unsplash.com/photo-1502086223501-7ea6ecd79368?auto=format&fit=crop&w=800&q=80" alt="Happy Kids Playing" class="w-full h-80 sm:h-96 object-cover rounded-3xl">
                                    
                                    <!-- Floating Badge 1 -->
                                    <div class="absolute -top-6 -left-6 bg-brand-yellow text-gray-900 p-4 rounded-2xl shadow-xl flex items-center gap-3 animate-float-medium">
                                        <div class="w-10 h-10 bg-white rounded-xl flex items-center justify-center text-brand-pink text-xl font-black">
                                            40%
                                        </div>
                                        <div>
                                            <p class="text-[10px] uppercase font-black text-gray-600">Season Sale</p>
                                            <p class="text-xs font-bold">Up to 40% OFF</p>
                                        </div>
                                    </div>

                                    <!-- Floating Badge 2 -->
                                    <div class="absolute -bottom-6 -right-6 bg-white p-4 rounded-2xl shadow-xl flex items-center gap-3 animate-float-slow">
                                        <div class="flex text-brand-yellow text-sm">
                                            <i class="fa-solid fa-star"></i>
                                            <i class="fa-solid fa-star"></i>
                                            <i class="fa-solid fa-star"></i>
                                            <i class="fa-solid fa-star"></i>
                                            <i class="fa-solid fa-star"></i>
                                        </div>
                                        <span class="text-xs font-bold text-gray-700">10k+ Happy Moms</span>
                                    </div>
                                </div>
                            </div>

                        </div>
                    </div>
                </section>

                <!-- 2. SHOP BY CATEGORY -->
                <section class="py-16 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                    <div class="text-center max-w-2xl mx-auto mb-12">
                        <span class="text-brand-purple text-xs font-bold uppercase tracking-widest">Explore Joy</span>
                        <h2 class="text-3xl sm:text-4xl font-black text-gray-900 mt-1">Shop By Category</h2>
                    </div>

                    <div class="grid grid-cols-2 sm:grid-cols-4 lg:grid-cols-8 gap-4">
                        ${renderCategoryCard('Toys', 'fa-puzzle-piece', 'bg-pink-100 text-brand-pink')}
                        ${renderCategoryCard('Clothes', 'fa-shirt', 'bg-purple-100 text-brand-purple')}
                        ${renderCategoryCard('Shoes', 'fa-shoe-prints', 'bg-blue-100 text-brand-blue')}
                        ${renderCategoryCard('Caps', 'fa-hat-wizard', 'bg-yellow-100 text-brand-yellow')}
                        ${renderCategoryCard('Bags', 'fa-bag-shopping', 'bg-green-100 text-brand-mint')}
                        ${renderCategoryCard('Accessories', 'fa-glasses', 'bg-red-100 text-red-500')}
                        ${renderCategoryCard('Baby', 'fa-baby-carriage', 'bg-indigo-100 text-indigo-500')}
                        ${renderCategoryCard('Gifts', 'fa-gift', 'bg-orange-100 text-orange-500')}
                    </div>
                </section>

                <!-- 3. PRODUCTS GRID WITH FILTER -->
                <section id="productsSection" class="py-12 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                    <div class="flex flex-col md:flex-row md:items-end justify-between mb-8 gap-4">
                        <div>
                            <span class="text-brand-pink text-xs font-bold uppercase tracking-widest">Handpicked for Kids</span>
                            <h2 class="text-3xl font-black text-gray-900 mt-1">Popular Products</h2>
                        </div>

                        <!-- Filter Tabs -->
                        <div class="flex flex-wrap gap-2">
                            ${renderFilterTab('All')}
                            ${renderFilterTab('Toys')}
                            ${renderFilterTab('Clothes')}
                            ${renderFilterTab('Shoes')}
                            ${renderFilterTab('Bags')}
                            ${renderFilterTab('Baby')}
                        </div>
                    </div>

                    <!-- Products Grid -->
                    <div id="productsGrid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
                        ${renderProductsList(products)}
                    </div>
                </section>

                <!-- 4. SPECIAL PROMOTIONAL BANNER -->
                <section class="py-12 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                    <div class="bg-gradient-to-r from-brand-purple via-brand-pink to-brand-yellow rounded-4xl p-8 sm:p-12 text-white relative overflow-hidden shadow-2xl flex flex-col lg:flex-row items-center justify-between gap-8">
                        <div class="relative z-10 max-w-xl text-center lg:text-left">
                            <span class="inline-block bg-white/20 backdrop-blur-md px-4 py-1.5 rounded-full text-xs font-black tracking-wider uppercase mb-3">Limited Time Offer</span>
                            <h2 class="text-3xl sm:text-5xl font-black mb-4">Kids Special Sale — Up to 40% OFF</h2>
                            <p class="text-white/90 text-sm sm:text-base mb-6 font-medium">Upgrade your kid's wardrobe and toy collection today. Premium durable quality tested for maximum playful fun.</p>
                            <button onclick="filterCategory('Sale')" class="bg-white text-brand-purple font-black px-8 py-4 rounded-2xl hover:bg-gray-100 shadow-xl transition-all hover:scale-105">
                                Claim Discount Now <i class="fa-solid fa-arrow-right ml-2"></i>
                            </button>
                        </div>
                        <div class="relative z-10 w-48 h-48 sm:w-64 sm:h-64 bg-white/10 backdrop-blur-md rounded-full border-4 border-white/30 flex items-center justify-center animate-pulse-glow">
                            <i class="fa-solid fa-wand-magic-sparkles text-7xl sm:text-8xl text-brand-yellow"></i>
                        </div>
                    </div>
                </section>

                <!-- 5. WHY CHOOSE US -->
                <section class="py-16 bg-white my-12">
                    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                        <div class="text-center max-w-2xl mx-auto mb-12">
                            <h2 class="text-3xl font-black text-gray-900">Why Parents Trust KIDS TIME</h2>
                            <p class="text-gray-500 text-sm font-medium mt-2">Designed to bring peace of mind to parents and joy to children.</p>
                        </div>

                        <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
                            <div class="text-center p-6 rounded-3xl bg-gray-50 border border-gray-100 hover:shadow-md transition-shadow">
                                <div class="w-14 h-14 bg-pink-100 text-brand-pink rounded-2xl flex items-center justify-center text-2xl mx-auto mb-4">
                                    <i class="fa-solid fa-shield-heart"></i>
                                </div>
                                <h3 class="font-bold text-gray-800 text-lg mb-2">100% Safe & Certified</h3>
                                <p class="text-gray-500 text-xs leading-relaxed">All products pass strict child safety, non-toxic chemical testing.</p>
                            </div>
                            <div class="text-center p-6 rounded-3xl bg-gray-50 border border-gray-100 hover:shadow-md transition-shadow">
                                <div class="w-14 h-14 bg-purple-100 text-brand-purple rounded-2xl flex items-center justify-center text-2xl mx-auto mb-4">
                                    <i class="fa-solid fa-truck-fast"></i>
                                </div>
                                <h3 class="font-bold text-gray-800 text-lg mb-2">Express Fast Shipping</h3>
                                <p class="text-gray-500 text-xs leading-relaxed">Quick dispatch so your little ones never have to wait long.</p>
                            </div>
                            <div class="text-center p-6 rounded-3xl bg-gray-50 border border-gray-100 hover:shadow-md transition-shadow">
                                <div class="w-14 h-14 bg-blue-100 text-brand-blue rounded-2xl flex items-center justify-center text-2xl mx-auto mb-4">
                                    <i class="fa-solid fa-arrow-rotate-left"></i>
                                </div>
                                <h3 class="font-bold text-gray-800 text-lg mb-2">30 Days Hassle Return</h3>
                                <p class="text-gray-500 text-xs leading-relaxed">Wrong size? No worries! Instant returns & exchange support.</p>
                            </div>
                            <div class="text-center p-6 rounded-3xl bg-gray-50 border border-gray-100 hover:shadow-md transition-shadow">
                                <div class="w-14 h-14 bg-yellow-100 text-brand-yellow rounded-2xl flex items-center justify-center text-2xl mx-auto mb-4">
                                    <i class="fa-solid fa-headset"></i>
                                </div>
                                <h3 class="font-bold text-gray-800 text-lg mb-2">24/7 Parent Support</h3>
                                <p class="text-gray-500 text-xs leading-relaxed">Dedicated friendly team available to answer any question anytime.</p>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- 6. PARENT REVIEWS -->
                <section class="py-12 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                    <div class="text-center max-w-2xl mx-auto mb-12">
                        <span class="text-brand-purple text-xs font-bold uppercase tracking-widest">Real Feedback</span>
                        <h2 class="text-3xl font-black text-gray-900 mt-1">Loved by Parents Worldwide</h2>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                        <div class="bg-white p-6 rounded-3xl shadow-sm border border-gray-100">
                            <div class="flex text-brand-yellow text-sm mb-3">
                                <i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i>
                            </div>
                            <p class="text-gray-600 text-sm italic mb-4">"The wooden building blocks set is amazing quality! Smooth edges and vivid colors. My 3-year-old hasn't stopped playing with it!"</p>
                            <div class="flex items-center gap-3">
                                <div class="w-10 h-10 rounded-full bg-brand-pink/20 text-brand-pink font-bold flex items-center justify-center text-sm">SP</div>
                                <div>
                                    <h4 class="font-bold text-gray-800 text-sm">Sarah P.</h4>
                                    <span class="text-xs text-gray-400">Verified Parent</span>
                                </div>
                            </div>
                        </div>

                        <div class="bg-white p-6 rounded-3xl shadow-sm border border-gray-100">
                            <div class="flex text-brand-yellow text-sm mb-3">
                                <i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i>
                            </div>
                            <p class="text-gray-600 text-sm italic mb-4">"Light-up sneakers arrived in 2 days! My son was over the moon. Will definitely buy all his clothes and shoes from KIDS TIME."</p>
                            <div class="flex items-center gap-3">
                                <div class="w-10 h-10 rounded-full bg-brand-blue/20 text-brand-blue font-bold flex items-center justify-center text-sm">MK</div>
                                <div>
                                    <h4 class="font-bold text-gray-800 text-sm">Michael K.</h4>
                                    <span class="text-xs text-gray-400">Verified Parent</span>
                                </div>
                            </div>
                        </div>

                        <div class="bg-white p-6 rounded-3xl shadow-sm border border-gray-100">
                            <div class="flex text-brand-yellow text-sm mb-3">
                                <i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i>
                            </div>
                            <p class="text-gray-600 text-sm italic mb-4">"The dino hoodie set is super soft cotton and washed really well without shrinking. Highly recommend KIDS TIME store!"</p>
                            <div class="flex items-center gap-3">
                                <div class="w-10 h-10 rounded-full bg-brand-purple/20 text-brand-purple font-bold flex items-center justify-center text-sm">EL</div>
                                <div>
                                    <h4 class="font-bold text-gray-800 text-sm">Emily L.</h4>
                                    <span class="text-xs text-gray-400">Verified Parent</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- 7. NEWSLETTER SECTION -->
                <section class="py-12 max-w-4xl mx-auto px-4 text-center">
                    <div class="bg-white rounded-4xl p-8 sm:p-12 shadow-xl border border-gray-100">
                        <div class="w-16 h-16 bg-brand-yellow/20 text-brand-yellow rounded-2xl flex items-center justify-center text-3xl mx-auto mb-4">
                            <i class="fa-solid fa-paper-plane"></i>
                        </div>
                        <h2 class="text-2xl sm:text-3xl font-black text-gray-900 mb-2">Get Deals & Secret Discounts</h2>
                        <p class="text-gray-500 text-sm mb-6 max-w-md mx-auto">Subscribe to get secret coupon codes, new product drops, and parenting tips right in your inbox.</p>
                        <form onsubmit="handleSubscribe(event)" class="flex flex-col sm:flex-row gap-3 max-w-md mx-auto">
                            <input type="email" required placeholder="Enter your email address..." class="flex-1 px-5 py-3.5 rounded-2xl bg-gray-100 text-sm focus:outline-none focus:ring-2 focus:ring-brand-purple font-medium">
                            <button type="submit" class="bg-brand-purple hover:bg-brand-purple/90 text-white font-bold px-6 py-3.5 rounded-2xl shadow-md transition-all active:scale-95">
                                Subscribe
                            </button>
                        </form>
                    </div>
                </section>
            `;
        }

        // Category Card Generator
        function renderCategoryCard(title, icon, colors) {
            return `
                <div onclick="filterCategory('${title}')" class="bg-white p-4 rounded-3xl text-center shadow-sm border border-gray-100 hover:shadow-lg hover:-translate-y-1 transition-all cursor-pointer group">
                    <div class="w-12 h-12 rounded-2xl ${colors} flex items-center justify-center text-xl mx-auto mb-3 group-hover:scale-110 transition-transform">
                        <i class="fa-solid ${icon}"></i>
                    </div>
                    <span class="text-xs font-bold text-gray-700 block">${title}</span>
                </div>
            `;
        }

        // Filter Tab Generator
        function renderFilterTab(category) {
            const isActive = activeFilter === category;
            return `
                <button onclick="filterCategory('${category}')" class="px-5 py-2.5 rounded-full text-xs font-bold transition-all ${
                    isActive 
                    ? 'bg-brand-purple text-white shadow-md' 
                    : 'bg-white text-gray-600 hover:bg-gray-100 border border-gray-200'
                }">
                    ${category}
                </button>
            `;
        }

        // Render Product Items
        function renderProductsList(items) {
            if (items.length === 0) {
                return `<p class="col-span-full text-center py-12 text-gray-400 font-medium">No products found in this category.</p>`;
            }

            return items.map(product => {
                const isWishlisted = wishlist.some(i => i.id === product.id);
                return `
                    <div class="bg-white rounded-3xl p-4 shadow-sm border border-gray-100 product-card relative flex flex-col justify-between group">
                        
                        <!-- Top Badges -->
                        <div class="flex items-center justify-between mb-3 z-10">
                            <span class="bg-brand-yellow/20 text-brand-text text-[10px] font-black px-3 py-1 rounded-full uppercase tracking-wider">${product.badge}</span>
                            <button onclick="toggleWishlist(${product.id})" class="w-8 h-8 rounded-full bg-gray-50 hover:bg-red-50 text-gray-400 hover:text-brand-pink flex items-center justify-center transition-colors">
                                <i class="${isWishlisted ? 'fa-solid text-brand-pink' : 'fa-regular'} fa-heart text-sm"></i>
                            </button>
                        </div>

                        <!-- Product Image -->
                        <div class="relative overflow-hidden rounded-2xl mb-4 bg-gray-50 h-48 cursor-pointer" onclick="navigateTo('product', ${product.id})">
                            <img src="${product.image}" alt="${product.name}" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                            <button onclick="event.stopPropagation(); openQuickView(${product.id})" class="absolute bottom-3 left-1/2 -translate-x-1/2 bg-white/90 backdrop-blur-sm text-gray-800 text-xs font-bold px-4 py-2 rounded-xl shadow-md opacity-0 group-hover:opacity-100 transition-opacity flex items-center gap-1 hover:bg-brand-purple hover:text-white">
                                <i class="fa-regular fa-eye"></i> Quick View
                            </button>
                        </div>

                        <!-- Product Info -->
                        <div>
                            <span class="text-[11px] font-bold text-brand-blue uppercase tracking-wider">${product.category}</span>
                            <h3 onclick="navigateTo('product', ${product.id})" class="font-bold text-gray-800 text-sm leading-snug line-clamp-2 my-1 cursor-pointer hover:text-brand-pink transition-colors">
                                ${product.name}
                            </h3>
                            
                            <!-- Rating -->
                            <div class="flex items-center gap-1 text-xs text-brand-yellow my-2">
                                <i class="fa-solid fa-star"></i>
                                <span class="font-bold text-gray-700 ml-1">${product.rating}</span>
                                <span class="text-gray-400 font-normal">(${product.reviewsCount})</span>
                            </div>

                            <!-- Price & Add Button -->
                            <div class="flex items-center justify-between mt-4 pt-3 border-t border-gray-100">
                                <div>
                                    <span class="text-lg font-black text-gray-900">$${product.price.toFixed(2)}</span>
                                    <span class="text-xs text-gray-400 line-through ml-1">$${product.origPrice.toFixed(2)}</span>
                                </div>
                                <button onclick="addToCart(${product.id})" class="w-10 h-10 rounded-2xl bg-brand-purple/10 text-brand-purple hover:bg-brand-purple hover:text-white flex items-center justify-center transition-all active:scale-95">
                                    <i class="fa-solid fa-plus font-bold"></i>
                                </button>
                            </div>
                        </div>

                    </div>
                `;
            }).join('');
        }

        // Filter Category Function
        function filterCategory(category) {
            activeFilter = category;

            let filtered = products;
            if (category === 'Sale') {
                filtered = products.filter(p => p.origPrice > p.price);
            } else if (category === 'New') {
                filtered = products.filter(p => p.badge === 'New' || p.id > 4);
            } else if (category !== 'All') {
                filtered = products.filter(p => p.category.toLowerCase() === category.toLowerCase());
            }

            const grid = document.getElementById('productsGrid');
            if (grid) {
                grid.innerHTML = renderProductsList(filtered);
            } else {
                renderHomepage();
                setTimeout(() => filterCategory(category), 50);
            }

            // Scroll to products if on homepage
            const sec = document.getElementById('productsSection');
            if(sec) sec.scrollIntoView({ behavior: 'smooth' });
        }

        function scrollToProducts() {
            const sec = document.getElementById('productsSection');
            if (sec) sec.scrollIntoView({ behavior: 'smooth' });
        }

        // RENDER PRODUCT DETAIL PAGE
        function renderProductDetails(productId) {
            const product = products.find(p => p.id === productId) || products[0];
            const related = products.filter(p => p.category === product.category && p.id !== product.id);

            const app = document.getElementById('app');
            app.innerHTML = `
                <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-10">
                    <!-- Breadcrumbs -->
                    <div class="flex items-center gap-2 text-xs font-bold text-gray-400 mb-8">
                        <span class="hover:text-brand-pink cursor-pointer" onclick="navigateTo('home')">Home</span>
                        <i class="fa-solid fa-chevron-right text-[10px]"></i>
                        <span>${product.category}</span>
                        <i class="fa-solid fa-chevron-right text-[10px]"></i>
                        <span class="text-gray-700">${product.name}</span>
                    </div>

                    <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 bg-white rounded-4xl p-6 sm:p-10 shadow-sm border border-gray-100">
                        
                        <!-- Images Gallery -->
                        <div>
                            <div class="rounded-3xl overflow-hidden bg-gray-50 h-96 mb-4 border border-gray-100">
                                <img id="mainProductImg" src="${product.image}" alt="${product.name}" class="w-full h-full object-cover">
                            </div>
                            <div class="grid grid-cols-4 gap-3">
                                <img src="${product.image}" onclick="changeDetailImg(this.src)" class="rounded-xl h-20 w-full object-cover border-2 border-brand-purple cursor-pointer">
                                <img src="https://images.unsplash.com/photo-1515488042361-ee00e0ddd4e4?auto=format&fit=crop&w=400&q=80" onclick="changeDetailImg(this.src)" class="rounded-xl h-20 w-full object-cover border-2 border-transparent hover:border-brand-purple cursor-pointer">
                                <img src="https://images.unsplash.com/photo-1596461404969-9ae70f2830c1?auto=format&fit=crop&w=400&q=80" onclick="changeDetailImg(this.src)" class="rounded-xl h-20 w-full object-cover border-2 border-transparent hover:border-brand-purple cursor-pointer">
                            </div>
                        </div>

                        <!-- Product Info Details -->
                        <div class="flex flex-col justify-between">
                            <div>
                                <span class="bg-brand-pink/10 text-brand-pink text-xs font-bold px-3 py-1 rounded-full uppercase tracking-wider">${product.badge}</span>
                                <h1 class="text-2xl sm:text-3xl font-black text-gray-900 mt-3 mb-2">${product.name}</h1>
                                
                                <div class="flex items-center gap-2 mb-4">
                                    <div class="flex text-brand-yellow text-sm">
                                        <i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i><i class="fa-solid fa-star"></i>
                                    </div>
                                    <span class="text-xs font-bold text-gray-700">${product.rating}</span>
                                    <span class="text-xs text-gray-400">(${product.reviewsCount} customer reviews)</span>
                                </div>

                                <div class="flex items-baseline gap-3 mb-6">
                                    <span class="text-3xl font-black text-gray-900">$${product.price.toFixed(2)}</span>
                                    <span class="text-base text-gray-400 line-through">$${product.origPrice.toFixed(2)}</span>
                                    <span class="text-xs font-bold text-brand-pink bg-pink-50 px-2 py-1 rounded-lg">Save ${(100 - (product.price/product.origPrice*100)).toFixed(0)}%</span>
                                </div>

                                <p class="text-gray-600 text-sm leading-relaxed mb-6 font-medium">
                                    ${product.description}
                                </p>

                                <!-- Available Sizes -->
                                <div class="mb-6">
                                    <label class="block text-xs font-bold uppercase tracking-wider text-gray-500 mb-2">Select Size / Age</label>
                                    <div class="flex gap-2">
                                        ${product.sizes.map(size => `<button class="px-4 py-2 border-2 border-brand-purple bg-purple-50 text-brand-purple font-bold text-xs rounded-xl">${size}</button>`).join('')}
                                    </div>
                                </div>
                            </div>

                            <!-- Actions -->
                            <div class="space-y-4 pt-6 border-t border-gray-100">
                                <div class="flex gap-4">
                                    <div class="flex items-center border-2 border-gray-200 rounded-2xl bg-gray-50 px-3">
                                        <button onclick="adjustDetailQty(-1)" class="text-gray-500 font-bold px-2 py-2">-</button>
                                        <span id="detailQty" class="font-bold text-sm px-3">1</span>
                                        <button onclick="adjustDetailQty(1)" class="text-gray-500 font-bold px-2 py-2">+</button>
                                    </div>
                                    <button onclick="addDetailToCart(${product.id})" class="flex-1 bg-brand-purple hover:bg-brand-purple/90 text-white font-bold py-4 rounded-2xl shadow-lg flex items-center justify-center gap-2">
                                        <i class="fa-solid fa-bag-shopping"></i> Add to Cart
                                    </button>
                                </div>
                                <button onclick="buyNow(${product.id})" class="w-full bg-brand-pink hover:bg-brand-pink/90 text-white font-bold py-4 rounded-2xl shadow-md">
                                    Buy It Now
                                </button>
                            </div>

                        </div>
                    </div>

                    <!-- Related Products -->
                    <div class="mt-16">
                        <h3 class="text-2xl font-black text-gray-900 mb-6">You Might Also Like</h3>
                        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
                            ${renderProductsList(related.length ? related : products.slice(0, 4))}
                        </div>
                    </div>
                </div>
            `;
        }

        function changeDetailImg(src) {
            document.getElementById('mainProductImg').src = src;
        }

        let detailQuantity = 1;
        function adjustDetailQty(delta) {
            detailQuantity = Math.max(1, detailQuantity + delta);
            document.getElementById('detailQty').innerText = detailQuantity;
        }

        function addDetailToCart(id) {
            for(let i = 0; i < detailQuantity; i++) {
                addToCart(id, false);
            }
            toggleCartDrawer();
        }

        function buyNow(id) {
            addDetailToCart(id);
            navigateTo('checkout');
        }

        // RENDER CHECKOUT PAGE
        function renderCheckoutPage() {
            const subtotal = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            const shipping = subtotal > 50 || subtotal === 0 ? 0 : 5.99;
            const total = subtotal + shipping;

            const app = document.getElementById('app');
            app.innerHTML = `
                <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-10">
                    <h1 class="text-3xl font-black text-gray-900 mb-8">Checkout & Place Order</h1>

                    <div class="grid grid-cols-1 lg:grid-cols-12 gap-10">
                        
                        <!-- Customer Info Form -->
                        <div class="lg:col-span-7 bg-white p-6 sm:p-8 rounded-4xl shadow-sm border border-gray-100 space-y-6">
                            <h2 class="text-lg font-bold text-gray-800 border-b border-gray-100 pb-3">Shipping Information</h2>
                            
                            <form id="checkoutForm" onsubmit="handlePlaceOrder(event)" class="space-y-4">
                                <div class="grid grid-cols-2 gap-4">
                                    <div>
                                        <label class="block text-xs font-bold text-gray-500 mb-1">First Name</label>
                                        <input type="text" required class="w-full px-4 py-3 bg-gray-50 rounded-xl text-sm border border-gray-200 focus:outline-none focus:ring-2 focus:ring-brand-purple">
                                    </div>
                                    <div>
                                        <label class="block text-xs font-bold text-gray-500 mb-1">Last Name</label>
                                        <input type="text" required class="w-full px-4 py-3 bg-gray-50 rounded-xl text-sm border border-gray-200 focus:outline-none focus:ring-2 focus:ring-brand-purple">
                                    </div>
                                </div>

                                <div>
                                    <label class="block text-xs font-bold text-gray-500 mb-1">Email Address</label>
                                    <input type="email" required class="w-full px-4 py-3 bg-gray-50 rounded-xl text-sm border border-gray-200 focus:outline-none focus:ring-2 focus:ring-brand-purple">
                                </div>

                                <div>
                                    <label class="block text-xs font-bold text-gray-500 mb-1">Street Address</label>
                                    <input type="text" required placeholder="House number and street name" class="w-full px-4 py-3 bg-gray-50 rounded-xl text-sm border border-gray-200 focus:outline-none focus:ring-2 focus:ring-brand-purple">
                                </div>

                                <div class="grid grid-cols-3 gap-4">
                                    <div>
                                        <label class="block text-xs font-bold text-gray-500 mb-1">City</label>
                                        <input type="text" required class="w-full px-4 py-3 bg-gray-50 rounded-xl text-sm border border-gray-200 focus:outline-none focus:ring-2 focus:ring-brand-purple">
                                    </div>
                                    <div>
                                        <label class="block text-xs font-bold text-gray-500 mb-1">State</label>
                                        <input type="text" required class="w-full px-4 py-3 bg-gray-50 rounded-xl text-sm border border-gray-200 focus:outline-none focus:ring-2 focus:ring-brand-purple">
                                    </div>
                                    <div>
                                        <label class="block text-xs font-bold text-gray-500 mb-1">Zip Code</label>
                                        <input type="text" required class="w-full px-4 py-3 bg-gray-50 rounded-xl text-sm border border-gray-200 focus:outline-none focus:ring-2 focus:ring-brand-purple">
                                    </div>
                                </div>

                                <h2 class="text-lg font-bold text-gray-800 border-b border-gray-100 pb-3 pt-4">Payment Method</h2>
                                <div class="space-y-2">
                                    <label class="flex items-center gap-3 p-4 bg-gray-50 rounded-2xl border border-gray-200 cursor-pointer">
                                        <input type="radio" name="payment" checked class="text-brand-purple focus:ring-brand-purple">
                                        <i class="fa-solid fa-credit-card text-brand-purple"></i>
                                        <span class="text-sm font-bold text-gray-800">Credit / Debit Card</span>
                                    </label>
                                    <label class="flex items-center gap-3 p-4 bg-gray-50 rounded-2xl border border-gray-200 cursor-pointer">
                                        <input type="radio" name="payment" class="text-brand-purple focus:ring-brand-purple">
                                        <i class="fa-brands fa-paypal text-blue-500"></i>
                                        <span class="text-sm font-bold text-gray-800">PayPal</span>
                                    </label>
                                </div>

                                <button type="submit" class="w-full bg-brand-pink hover:bg-brand-pink/90 text-white font-bold py-4 rounded-2xl shadow-lg mt-6 transition-all">
                                    Complete Order ($${total.toFixed(2)})
                                </button>
                            </form>
                        </div>

                        <!-- Order Summary -->
                        <div class="lg:col-span-5 bg-gray-50 p-6 sm:p-8 rounded-4xl border border-gray-200/80 h-fit space-y-6">
                            <h2 class="text-lg font-bold text-gray-800 border-b border-gray-200 pb-3">Order Summary</h2>
                            
                            <div class="space-y-3 max-h-60 overflow-y-auto pr-2">
                                ${cart.length === 0 ? '<p class="text-xs text-gray-400">Your cart is empty.</p>' : cart.map(item => `
                                    <div class="flex items-center justify-between text-xs">
                                        <div class="flex items-center gap-3">
                                            <img src="${item.image}" class="w-10 h-10 object-cover rounded-lg">
                                            <div>
                                                <h4 class="font-bold text-gray-800">${item.name}</h4>
                                                <span class="text-gray-400">Qty: ${item.quantity}</span>                                             </div>                                         </div>                                         <span class="font-bold text-gray-800">$${(item.price * item.quantity).toFixed(2)}</span>
                                    </div>
                                `).join('')}
                            </div>

                            <hr class="border-gray-200">

                            <div class="space-y-2 text-sm">
                                <div class="flex justify-between text-gray-600">
                                    <span>Subtotal</span>
                                    <span class="font-bold text-gray-800">$${subtotal.toFixed(2)}</span>
                                </div>
                                <div class="flex justify-between text-gray-600">
                                    <span>Shipping</span>
                                    <span class="font-bold text-gray-800">${shipping === 0 ? 'FREE' : '$' + shipping.toFixed(2)}</span>
                                </div>
                                <div class="flex justify-between text-base font-black text-gray-900 pt-3 border-t border-gray-200">
                                    <span>Total</span>
                                    <span class="text-brand-purple">$${total.toFixed(2)}</span>
                                </div>
                            </div>
                        </div>

                    </div>
                </div>
            `;
        }

        // CART MANAGEMENT SYSTEM
        function addToCart(productId, showNotification = true) {
            const product = products.find(p => p.id === productId);
            const existing = cart.find(item => item.id === productId);

            if (existing) {
                existing.quantity += 1;
            } else {
                cart.push({ ...product, quantity: 1 });
            }

            updateBadges();
            renderCartItems();

            if (showNotification) {
                toggleCartDrawer();
            }
        }

        function updateCartQty(productId, delta) {
            const item = cart.find(i => i.id === productId);
            if (item) {
                item.quantity += delta;
                if (item.quantity <= 0) {
                    cart = cart.filter(i => i.id !== productId);
                }
            }
            updateBadges();
            renderCartItems();
        }

        function renderCartItems() {
            const container = document.getElementById('cartItemsContainer');
            const subtotalEl = document.getElementById('cartSubtotal');

            if (cart.length === 0) {
                container.innerHTML = `
                    <div class="text-center py-12 space-y-3">
                        <div class="w-16 h-16 bg-gray-100 rounded-full flex items-center justify-center mx-auto text-gray-400 text-2xl">
                            <i class="fa-solid fa-basket-shopping"></i>
                        </div>
                        <p class="text-sm text-gray-500 font-bold">Your cart is currently empty.</p>
                        <button onclick="toggleCartDrawer()" class="text-xs text-brand-pink font-bold hover:underline">Start Shopping</button>
                    </div>
                `;
                subtotalEl.innerText = '$0.00';
                return;
            }

            const subtotal = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            subtotalEl.innerText = `$${subtotal.toFixed(2)}`;

            container.innerHTML = cart.map(item => `
                <div class="flex items-center gap-4 bg-gray-50 p-3 rounded-2xl border border-gray-100">
                    <img src="${item.image}" alt="${item.name}" class="w-16 h-16 object-cover rounded-xl">
                    <div class="flex-1">
                        <h4 class="text-xs font-bold text-gray-800 line-clamp-1">${item.name}</h4>
                        <span class="text-xs font-black text-brand-purple">$${item.price.toFixed(2)}</span>
                        
                        <div class="flex items-center gap-2 mt-2">
                            <button onclick="updateCartQty(${item.id}, -1)" class="w-6 h-6 rounded-lg bg-white border border-gray-200 text-gray-600 text-xs font-bold flex items-center justify-center">-</button>
                            <span class="text-xs font-bold text-gray-700 px-1">${item.quantity}</span>
                            <button onclick="updateCartQty(${item.id}, 1)" class="w-6 h-6 rounded-lg bg-white border border-gray-200 text-gray-600 text-xs font-bold flex items-center justify-center">+</button>
                        </div>
                    </div>
                    <button onclick="updateCartQty(${item.id}, -${item.quantity})" class="text-gray-400 hover:text-red-500 p-2">
                        <i class="fa-solid fa-trash-can text-sm"></i>
                    </button>
                </div>
            `).join('');
        }

        function toggleWishlist(productId) {
            const product = products.find(p => p.id === productId);
            const index = wishlist.findIndex(i => i.id === productId);

            if (index > -1) {
                wishlist.splice(index, 1);
            } else {
                wishlist.push(product);
            }

            updateBadges();
            
            // Re-render products grid if visible
            const grid = document.getElementById('productsGrid');
            if (grid) {
                grid.innerHTML = renderProductsList(products);
            }
        }

        function updateBadges() {
            const cartCount = cart.reduce((sum, item) => sum + item.quantity, 0);
            document.getElementById('cartBadge').innerText = cartCount;
            document.getElementById('wishlistBadge').innerText = wishlist.length;
        }

        function toggleCartDrawer() {
            const drawer = document.getElementById('cartDrawer');
            drawer.classList.toggle('hidden');
        }

        function toggleMobileMenu() {
            const menu = document.getElementById('mobileMenu');
            menu.classList.toggle('hidden');
        }

        function toggleSearchModal() {
            const modal = document.getElementById('searchModal');
            modal.classList.toggle('hidden');
        }

        function handleSearch() {
            const query = document.getElementById('searchInput').value.toLowerCase();
            const resultsContainer = document.getElementById('searchResults');

            if (query.trim() === '') {
                resultsContainer.innerHTML = `<p class="text-sm text-gray-400 text-center py-6">Start typing to search for products...</p>`;
                return;
            }

            const matched = products.filter(p => p.name.toLowerCase().includes(query) || p.category.toLowerCase().includes(query));

            if (matched.length === 0) {
                resultsContainer.innerHTML = `<p class="text-sm text-gray-400 text-center py-6">No products match your search.</p>`;
                return;
            }

            resultsContainer.innerHTML = matched.map(p => `
                <div onclick="navigateTo('product', ${p.id}); toggleSearchModal();" class="flex items-center gap-4 p-3 hover:bg-gray-50 rounded-2xl cursor-pointer border border-gray-100">
                    <img src="${p.image}" class="w-12 h-12 object-cover rounded-xl">
                    <div>
                        <h4 class="text-xs font-bold text-gray-800">${p.name}</h4>
                        <span class="text-xs font-black text-brand-purple">$${p.price.toFixed(2)}</span>
                    </div>
                </div>
            `).join('');
        }

        // QUICK VIEW MODAL
        function openQuickView(productId) {
            const product = products.find(p => p.id === productId);
            const container = document.getElementById('quickViewContent');

            container.innerHTML = `
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                    <img src="${product.image}" class="w-full h-64 object-cover rounded-2xl">
                    <div class="flex flex-col justify-between">
                        <div>
                            <span class="text-xs font-bold text-brand-pink uppercase tracking-wider">${product.category}</span>
                            <h3 class="text-xl font-black text-gray-900 mt-1 mb-2">${product.name}</h3>
                            <p class="text-gray-500 text-xs leading-relaxed mb-4">${product.description}</p>
                            <div class="flex items-baseline gap-2 mb-4">
                                <span class="text-2xl font-black text-gray-900">$${product.price.toFixed(2)}</span>
                                <span class="text-xs text-gray-400 line-through">$${product.origPrice.toFixed(2)}</span>
                            </div>
                        </div>
                        <button onclick="addToCart(${product.id}); closeQuickView();" class="w-full bg-brand-purple hover:bg-brand-purple/90 text-white font-bold py-3 rounded-xl shadow-md">
                            Add to Shopping Bag
                        </button>
                    </div>
                </div>
            `;

            document.getElementById('quickViewModal').classList.remove('hidden');
        }

        function closeQuickView() {
            document.getElementById('quickViewModal').classList.add('hidden');
        }

        function showWishlistModal() {
            alert(`Wishlist contains ${wishlist.length} item(s).`);
        }

        function handleSubscribe(e) {
            e.preventDefault();
            alert('🎉 Thank you for subscribing to KIDS TIME deals!');
            e.target.reset();
        }

        function handlePlaceOrder(e) {
            e.preventDefault();
            alert('🎉 Order Placed Successfully! Thank you for shopping with KIDS TIME.');
            cart = [];
            updateBadges();
            navigateTo('home');
        }
    </script>
</body>
</html>
