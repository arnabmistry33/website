<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AR LIFE - Elevate the Everyday</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            color: #222222; /* Charcoal */
            background-color: #F5F5F5; /* Alabaster */
        }
        .font-playfair {
            font-family: 'Playfair Display', serif;
        }
        .btn {
            @apply inline-block text-sm uppercase tracking-wider font-medium rounded-md transition-all duration-300 ease-in-out py-3 px-8;
        }
        .btn-primary {
            @apply bg-[#B89F5D] text-[#222222] hover:opacity-90; /* Gold Foil, Charcoal text */
        }
        .btn-secondary {
            @apply border border-[#222222] text-[#222222] hover:bg-[#222222] hover:text-[#F5F5F5]; /* Charcoal border, Charcoal text, hover: Charcoal bg, Alabaster text */
        }
        .btn-ai-feature {
            @apply bg-gradient-to-r from-[#0D4F3F] to-[#126B53] text-white hover:opacity-90 shadow-lg; /* Emerald gradient for AI features */
        }
        .link {
            @apply text-[#0D4F3F] relative after:content-[''] after:absolute after:bg-[#B89F5D] after:h-[2px] after:w-0 after:bottom-[-2px] after:left-0 after:transition-all after:duration-300 hover:after:w-full; /* Emerald Green, Gold underline */
        }
        .section-padding {
            @apply py-16 md:py-24 px-4 sm:px-6 lg:px-8;
        }
        .hero-bg-video {
            @apply absolute top-0 left-0 w-full h-full object-cover z-[-1];
        }
        .sticky-nav {
            @apply sticky top-0 z-50 bg-opacity-80 backdrop-blur-md;
        }
        .product-card img {
            @apply transition-transform duration-300 ease-in-out group-hover:scale-105;
        }
         .testimonial-card {
            @apply bg-white p-6 rounded-lg shadow-lg;
        }
        .footer-bg {
            background-color: #222222; /* Charcoal */
            color: #F5F5F5; /* Alabaster */
        }
        .footer-link {
            @apply text-gray-300 hover:text-[#B89F5D] transition-colors duration-300;
        }
        .motion-element {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.5s ease-out, transform 0.5s ease-out;
        }
        .motion-element.is-visible {
            opacity: 1;
            transform: translateY(0);
        }
        .floating-bottle {
            animation: float 6s ease-in-out infinite;
        }
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }
        .parallax-bg {
            background-attachment: fixed;
            background-position: center;
            background-repeat: no-repeat;
            background-size: cover;
        }
        /* Modal Styles */
        .modal {
            @apply fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center p-4 z-[100] transition-opacity duration-300;
        }
        .modal-content {
            @apply bg-white p-6 sm:p-8 rounded-lg shadow-2xl w-full max-w-lg transform transition-all duration-300 scale-95 opacity-0;
        }
        .modal.open .modal-content {
            @apply scale-100 opacity-100;
        }
        .modal-close-btn {
            @apply absolute top-4 right-4 text-gray-500 hover:text-gray-800 transition-colors;
        }
        .spinner {
            border: 4px solid rgba(0, 0, 0, 0.1);
            width: 36px;
            height: 36px;
            border-radius: 50%;
            border-left-color: #0D4F3F; /* Emerald */
            animation: spin 1s ease infinite;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body class="antialiased">

    <!-- Header / Sticky Navigation -->
    <header id="main-header" class="sticky-nav shadow-md bg-white/80">
        <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                <div class="flex items-center">
                    <a href="index.html" class="font-playfair text-3xl font-bold text-[#0D4F3F]">AR</a>
                </div>
                <div class="hidden md:flex space-x-8">
                    <a href="shop.html" class="text-gray-700 hover:text-[#0D4F3F] px-3 py-2 rounded-md text-sm font-medium transition-colors">Shop</a>
                    <a href="about.html" class="text-gray-700 hover:text-[#0D4F3F] px-3 py-2 rounded-md text-sm font-medium transition-colors">About</a>
                    <a href="journal.html" class="text-gray-700 hover:text-[#0D4F3F] px-3 py-2 rounded-md text-sm font-medium transition-colors">Journal</a>
                    <a href="contact.html" class="text-gray-700 hover:text-[#0D4F3F] px-3 py-2 rounded-md text-sm font-medium transition-colors">Contact</a>
                </div>
                <div class="flex items-center space-x-4">
                    <a href="#" aria-label="Search" class="text-gray-700 hover:text-[#0D4F3F]">
                        <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path></svg>
                    </a>
                    <a href="#" aria-label="Shopping Cart" class="text-gray-700 hover:text-[#0D4F3F]">
                        <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z"></path></svg>
                    </a>
                    <a href="#" aria-label="My Account" class="text-gray-700 hover:text-[#0D4F3F]">
                       <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"></path></svg>
                    </a>
                </div>
                <div class="md:hidden flex items-center">
                    <button id="mobile-menu-button" class="inline-flex items-center justify-center p-2 rounded-md text-gray-700 hover:text-[#0D4F3F] focus:outline-none focus:ring-2 focus:ring-inset focus:ring-[#0D4F3F]">
                        <span class="sr-only">Open main menu</span>
                        <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7" />
                        </svg>
                    </button>
                </div>
            </div>
        </nav>
        <div class="md:hidden hidden" id="mobile-menu">
            <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
                <a href="shop.html" class="text-gray-700 hover:bg-gray-100 hover:text-[#0D4F3F] block px-3 py-2 rounded-md text-base font-medium transition-colors">Shop</a>
                <a href="about.html" class="text-gray-700 hover:bg-gray-100 hover:text-[#0D4F3F] block px-3 py-2 rounded-md text-base font-medium transition-colors">About</a>
                <a href="journal.html" class="text-gray-700 hover:bg-gray-100 hover:text-[#0D4F3F] block px-3 py-2 rounded-md text-base font-medium transition-colors">Journal</a>
                <a href="contact.html" class="text-gray-700 hover:bg-gray-100 hover:text-[#0D4F3F] block px-3 py-2 rounded-md text-base font-medium transition-colors">Contact</a>
            </div>
        </div>
    </header>

    <main>
        <!-- Hero Section -->
        <section class="relative h-screen flex items-center justify-center text-center text-white overflow-hidden">
            <video autoplay muted loop playsinline class="hero-bg-video">
                <source src="https://placehold.co/1920x1080.mp4?text=Luxury+Pour+Video" type="video/mp4"> <!-- Placeholder for cinematic video -->
                Your browser does not support the video tag.
            </video>
            <div class="absolute inset-0 bg-black/50 z-0"></div> <!-- Overlay for text readability -->
            <div class="relative z-10 p-4">
                <h1 class="font-playfair text-5xl sm:text-6xl md:text-7xl lg:text-8xl font-bold mb-6 motion-element">
                    Elevate the Everyday.
                </h1>
                <p class="text-lg sm:text-xl md:text-2xl mb-10 max-w-2xl mx-auto motion-element" style="transition-delay: 0.2s;">
                    Discover a symphony of botanical-based, low-calorie soft drinks meticulously crafted for the modern palate.
                </p>
                <div class="space-y-4 sm:space-y-0 sm:space-x-4 motion-element" style="transition-delay: 0.4s;">
                    <a href="shop.html" class="btn btn-primary">Shop Now</a>
                    <a href="#product-highlights" class="btn btn-secondary">Discover Flavors</a>
                    <button id="openSignatureSipModal" class="btn btn-ai-feature mt-4 sm:mt-0">✨ Discover Your Signature Sip</button>
                </div>
            </div>
        </section>

        <!-- The AR LIFE Difference -->
        <section class="section-padding bg-white">
            <div class="max-w-5xl mx-auto grid md:grid-cols-3 gap-10 text-center">
                <div class="motion-element">
                    <svg class="w-16 h-16 mx-auto mb-4 text-[#0D4F3F]" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19.428 15.428a4 4 0 00-5.656 0M14 10l-2 1m0 0l-2-1m2 1v2.586a1 1 0 001.707.707l3.414-3.414a1 1 0 00-.707-1.707H16m4 0a2 2 0 110-4 2 2 0 010 4zM4.572 15.428a4 4 0 105.656 0M10 10l2 1m0 0l2-1m-2 1v2.586a1 1 0 01-1.707.707l-3.414-3.414a1 1 0 01.707-1.707H8M6 18a2 2 0 11-4 0 2 2 0 014 0z"></path></svg>
                    <h3 class="font-playfair text-2xl font-semibold mb-2">Botanical Infusions</h3>
                    <p class="text-gray-600">Sourced from the world's finest gardens for unparalleled purity and taste.</p>
                </div>
                <div class="motion-element" style="transition-delay: 0.15s;">
                     <svg class="w-16 h-16 mx-auto mb-4 text-[#0D4F3F]" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
                    <h3 class="font-playfair text-2xl font-semibold mb-2">Low-Calorie Indulgence</h3>
                    <p class="text-gray-600">Pure taste, zero compromise. Refreshment designed for your wellness.</p>
                </div>
                <div class="motion-element" style="transition-delay: 0.3s;">
                    <svg class="w-16 h-16 mx-auto mb-4 text-[#0D4F3F]" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 3v4M3 5h4M6 17v4m-2-2h4m5-16l2.286 6.857L21 12l-5.714 2.143L13 21l-2.286-6.857L5 12l5.714-2.143L13 3z"></path></svg>
                    <h3 class="font-playfair text-2xl font-semibold mb-2">Artfully Crafted</h3>
                    <p class="text-gray-600">Designed for moments of refined refreshment and sophisticated enjoyment.</p>
                </div>
            </div>
        </section>

        <!-- Product Highlights -->
        <section id="product-highlights" class="section-padding parallax-bg" style="background-image: url('https://placehold.co/1920x1080/F0EFEB/D1C7B8?text=Soft+Linen+Texture');"> <!-- Updated background texture -->
            <div class="max-w-6xl mx-auto text-center">
                <h2 class="font-playfair text-4xl md:text-5xl font-bold mb-4 motion-element">The Collection</h2>
                <p class="text-lg text-gray-700 mb-12 max-w-xl mx-auto motion-element" style="transition-delay: 0.2s;">Experience the exquisite fusion of nature's finest, bottled with sophistication.</p>
                <div class="grid md:grid-cols-3 gap-8">
                    <!-- Product Card 1 -->
                    <div class="group bg-white p-6 rounded-lg shadow-xl overflow-hidden motion-element" style="transition-delay: 0.4s;">
                        <img src="https://placehold.co/400x500/0D4F3F/FFFFFF?text=Luxury+AR+LIFE+Bottle+1&font=playfair+display" alt="AR LIFE Ginger & Elderflower - Luxury Bottle" class="w-full h-auto object-cover mb-6 rounded floating-bottle"> <!-- Updated placeholder -->
                        <h3 class="font-playfair text-2xl font-semibold mb-2">Ginger & Elderflower</h3>
                        <p class="text-gray-600 mb-4 text-sm">Aromatic ginger with delicate notes of sweet elderflower and a hint of citrus.</p>
                        <a href="product.html?product=ginger-elderflower" class="btn btn-primary text-sm">Shop Now</a>
                    </div>
                    <!-- Product Card 2 -->
                    <div class="group bg-white p-6 rounded-lg shadow-xl overflow-hidden motion-element" style="transition-delay: 0.55s;">
                        <img src="https://placehold.co/400x500/B89F5D/FFFFFF?text=Luxury+AR+LIFE+Bottle+2&font=playfair+display" alt="AR LIFE Rosemary & Grapefruit - Luxury Bottle" class="w-full h-auto object-cover mb-6 rounded floating-bottle" style="animation-delay: -2s;"> <!-- Updated placeholder -->
                        <h3 class="font-playfair text-2xl font-semibold mb-2">Rosemary & Grapefruit</h3>
                        <p class="text-gray-600 mb-4 text-sm">Herbaceous rosemary perfectly balanced with the zest of ripe grapefruit.</p>
                        <a href="product.html?product=rosemary-grapefruit" class="btn btn-primary text-sm">Shop Now</a>
                    </div>
                    <!-- Product Card 3 -->
                    <div class="group bg-white p-6 rounded-lg shadow-xl overflow-hidden motion-element" style="transition-delay: 0.7s;">
                        <img src="https://placehold.co/400x500/8C6C4A/FFFFFF?text=Luxury+AR+LIFE+Bottle+3&font=playfair+display" alt="AR LIFE Lavender & Blackberry - Luxury Bottle" class="w-full h-auto object-cover mb-6 rounded floating-bottle" style="animation-delay: -4s;"> <!-- Updated placeholder -->
                        <h3 class="font-playfair text-2xl font-semibold mb-2">Lavender & Blackberry</h3>
                        <p class="text-gray-600 mb-4 text-sm">Soothing lavender complemented by the rich sweetness of blackberries.</p>
                        <a href="product.html?product=lavender-blackberry" class="btn btn-primary text-sm">Shop Now</a>
                    </div>
                </div>
            </div>
        </section>

        <!-- Lifestyle Section -->
        <section class="section-padding bg-white">
            <div class="max-w-6xl mx-auto">
                <h2 class="font-playfair text-4xl md:text-5xl font-bold text-center mb-12 motion-element">The Art of Living Well.</h2>
                <div class="grid md:grid-cols-2 gap-8 items-center">
                    <div class="motion-element">
                        <img src="https://placehold.co/600x400/E5E0DA/333333?text=Elegant+Lifestyle+Scene" alt="AR LIFE Lifestyle" class="rounded-lg shadow-lg w-full"> <!-- More descriptive placeholder -->
                    </div>
                    <div class="motion-element" style="transition-delay: 0.2s;">
                        <h3 class="font-playfair text-3xl font-semibold mb-4">Moments, Elevated.</h3>
                        <p class="text-gray-700 text-lg mb-6">
                            AR LIFE is more than a drink; it's an invitation to pause, savor, and appreciate the finer details. It's the perfect companion for your serene mornings, creative afternoons, and elegant evenings.
                        </p>
                        <a href="journal.html" class="link text-lg">Explore Our Journal</a>
                    </div>
                </div>
                 <div class="grid md:grid-cols-2 gap-8 items-center mt-12 md:mt-16">
                    <div class="motion-element order-2 md:order-1" style="transition-delay: 0.2s;">
                        <h3 class="font-playfair text-3xl font-semibold mb-4">Conscious Choices.</h3>
                        <p class="text-gray-700 text-lg mb-6">
                           Crafted for those who seek wellness without sacrificing sophistication. Our commitment to natural ingredients and mindful production means every sip is one you can feel good about.
                        </p>
                        <a href="about.html" class="link text-lg">Our Philosophy</a>
                    </div>
                     <div class="motion-element order-1 md:order-2">
                        <img src="https://placehold.co/600x400/F0F3F0/333333?text=Wellness+Inspired+Setting" alt="AR LIFE Wellness" class="rounded-lg shadow-lg w-full"> <!-- More descriptive placeholder -->
                    </div>
                </div>
            </div>
        </section>

        <!-- Social Proof / Testimonials -->
        <section class="section-padding bg-[#F5F5F5]">
            <div class="max-w-4xl mx-auto text-center">
                <h2 class="font-playfair text-4xl md:text-5xl font-bold mb-12 motion-element">What Our Community Says</h2>
                <div class="grid md:grid-cols-2 gap-8">
                    <div class="testimonial-card motion-element" style="transition-delay: 0.2s;">
                        <p class="text-gray-700 italic mb-4">"AR LIFE has completely transformed my afternoon ritual. It's the perfect guilt-free indulgence that actually tastes amazing!"</p>
                        <p class="font-semibold text-gray-800">- Olivia R., New York</p>
                    </div>
                    <div class="testimonial-card motion-element" style="transition-delay: 0.35s;">
                        <p class="text-gray-700 italic mb-4">"Finally, a sophisticated soft drink that aligns with my wellness goals. The botanical flavors are so unique and refreshing."</p>
                        <p class="font-semibold text-gray-800">- Marcus B., Los Angeles</p>
                    </div>
                </div>
                <div class="mt-12 motion-element" style="transition-delay: 0.5s;">
                    <h3 class="text-xl font-semibold text-gray-700 mb-6">As Seen In</h3>
                    <div class="flex flex-wrap justify-center items-center gap-8 sm:gap-12 grayscale opacity-75">
                        <img src="https://placehold.co/120x40/cccccc/888888?text=VOGUE" alt="Vogue Logo" class="h-8 sm:h-10">
                        <img src="https://placehold.co/150x40/cccccc/888888?text=CONDÉ+NAST" alt="Condé Nast Traveler Logo" class="h-8 sm:h-10">
                        <img src="https://placehold.co/100x40/cccccc/888888?text=FORBES" alt="Forbes Logo" class="h-8 sm:h-10">
                        <img src="https://placehold.co/130x40/cccccc/888888?text=ELLE" alt="Elle Logo" class="h-8 sm:h-10">
                    </div>
                </div>
            </div>
        </section>

        <!-- Trust Badges -->
        <section class="py-12 bg-white">
            <div class="max-w-5xl mx-auto">
                <div class="flex flex-wrap justify-center items-center gap-x-8 gap-y-6 sm:gap-x-12 md:gap-x-16 motion-element">
                    <div class="flex items-center space-x-2 text-gray-700">
                        <svg class="w-8 h-8 text-[#0D4F3F]" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
                        <span class="font-medium">USDA Organic</span>
                    </div>
                    <div class="flex items-center space-x-2 text-gray-700">
                         <svg class="w-8 h-8 text-[#0D4F3F]" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M12 1l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 1z"></path></svg>
                        <span class="font-medium">Vegan Certified</span>
                    </div>
                    <div class="flex items-center space-x-2 text-gray-700">
                        <svg class="w-8 h-8 text-[#0D4F3F]" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M7 16V8m4 8V8m4 8V8m2-4H5a2 2 0 00-2 2v10a2 2 0 002 2h14a2 2 0 002-2V6a2 2 0 00-2-2z"></path></svg>
                        <span class="font-medium">Non-GMO Project</span>
                    </div>
                     <div class="flex items-center space-x-2 text-gray-700">
                         <svg class="w-8 h-8 text-[#0D4F3F]" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M20.625 8.375c0-2.456-1.994-4.45-4.45-4.45H7.825c-2.456 0-4.45 1.994-4.45 4.45v7.25c0 2.456 1.994 4.45 4.45 4.45h8.35c2.456 0 4.45-1.994 4.45-4.45v-7.25zM12 11.75a.75.75 0 00-.75.75v3a.75.75 0 001.5 0v-3a.75.75 0 00-.75-.75zm0-3a.75.75 0 000 1.5.75.75 0 000-1.5z"></path></svg>
                        <span class="font-medium">Gluten-Free</span>
                    </div>
                    <div class="flex items-center space-x-2 text-gray-700">
                       <svg class="w-8 h-8 text-[#0D4F3F]" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z"></path></svg>
                        <span class="font-medium">Ethically Sourced</span>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="footer-bg section-padding">
        <div class="max-w-7xl mx-auto">
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 mb-12">
                <div class="md:col-span-2 lg:col-span-2">
                    <h3 class="font-playfair text-2xl font-semibold mb-3">Sip in Style. Stay in the Know.</h3>
                    <p class="text-gray-400 mb-4 text-sm">Receive exclusive offers, early access to new flavors, and inspiration directly to your inbox.</p>
                    <form class="flex flex-col sm:flex-row gap-2">
                        <input type="email" placeholder="Enter your email" class="w-full px-4 py-3 rounded-md bg-gray-700 text-white border border-gray-600 focus:ring-2 focus:ring-[#B89F5D] focus:border-[#B89F5D] outline-none placeholder-gray-400" required>
                        <button type="submit" class="btn btn-primary whitespace-nowrap">Subscribe</button>
                    </form>
                </div>
                <div>
                    <h4 class="font-semibold text-lg mb-4">Shop</h4>
                    <ul class="space-y-2">
                        <li><a href="shop.html" class="footer-link text-sm">All Products</a></li>
                        <li><a href="#" class="footer-link text-sm">Best Sellers</a></li>
                        <li><a href="#" class="footer-link text-sm">Bundles & Sets</a></li>
                        <li><a href="#" class="footer-link text-sm">Gifting</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="font-semibold text-lg mb-4">AR LIFE</h4>
                    <ul class="space-y-2">
                        <li><a href="about.html" class="footer-link text-sm">Our Story</a></li>
                        <li><a href="journal.html" class="footer-link text-sm">Journal</a></li>
                        <li><a href="#" class="footer-link text-sm">Ingredients</a></li>
                        <li><a href="contact.html" class="footer-link text-sm">Contact Us</a></li>
                        <li><a href="#" class="footer-link text-sm">FAQ</a></li>
                    </ul>
                </div>
            </div>
            <div class="border-t border-gray-700 pt-8 flex flex-col md:flex-row justify-between items-center">
                <p class="text-gray-400 text-sm mb-4 md:mb-0">&copy; <span id="currentYear"></span> AR LIFE. All Rights Reserved.</p>
                <div class="flex space-x-5">
                    <a href="#" class="footer-link" aria-label="Instagram"><svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919C8.416 2.175 8.796 2.163 12 2.163zm0 1.802c-3.073 0-3.45.011-4.653.067-2.629.12-3.948 1.436-4.069 4.069-.056 1.203-.066 1.578-.066 4.518s.01 3.315.066 4.518c.12 2.633 1.44 3.948 4.07 4.069 1.202.056 1.578.066 4.652.066 3.074 0 3.45-.01 4.653-.066 2.63-.12 3.948-1.436 4.069-4.069.056-1.203.066-1.578.066-4.518s-.01-3.315-.066-4.518c-.12-2.633-1.44-3.948-4.069-4.069-1.203-.056-1.578-.067-4.653-.067zm0 3.449c-2.658 0-4.818 2.16-4.818 4.818s2.16 4.818 4.818 4.818 4.818-2.16 4.818-4.818-2.16-4.818-4.818-4.818zm0 7.834c-1.601 0-2.9-1.299-2.9-2.9s1.299-2.9 2.9-2.9 2.9 1.299 2.9 2.9-1.299 2.9-2.9 2.9zm4.818-8.734a1.162 1.162 0 100-2.324 1.162 1.162 0 000 2.324z"></path></svg></a>
                    <a href="#" class="footer-link" aria-label="Pinterest"><svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M12.017 0C5.396 0 .029 5.367.029 11.987c0 5.079 3.158 9.417 7.618 11.162-.105-.949-.198-2.403.041-3.439.239-.999.636-2.496.636-2.496s-.25-.499-.25-.999c0-.932.541-1.639 1.227-1.639.581 0 .865.436.865 1.009 0 .627-.394 1.565-.599 2.442-.164.713.369 1.299.999 1.299 1.206 0 2.126-1.586 2.126-3.861 0-2.025-1.384-3.308-3.206-3.308-2.258 0-3.684 1.706-3.684 3.449 0 .682.244 1.43.585 1.844.048.058.059.119.039.182-.059.18-.187.724-.229.884-.05.19-.198.239-.383.139-1.095-.499-1.782-1.827-1.782-3.131 0-2.435 1.756-4.726 5.251-4.726 2.793 0 4.926 1.995 4.926 4.611 0 2.751-1.733 4.976-4.148 4.976-.985 0-1.932-.509-2.25-.999L9.771 18.64c-.383 1.43.094 3.398.094 3.398s.436.18.585.094c.149-.094.608-1.026.608-1.026s.308.509 1.265.509c2.143 0 4.256-2.961 4.256-6.678 0-3.603-2.793-6.707-6.516-6.707z"></path></svg></a>
                    <a href="#" class="footer-link" aria-label="TikTok"><svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M12.525.02c1.31-.02 2.61-.01 3.91-.02.08 1.53.63 3.09 1.75 4.17 1.12 1.11 2.7 1.62 4.24 1.79v4.03c-1.44-.05-2.89-.35-4.2-.97-.57-.26-1.1-.59-1.62-.93-.01 2.92.01 5.84-.02 8.75-.08 1.4-.54 2.79-1.35 3.94-1.31 1.92-3.58 3.17-5.91 3.21-1.43.08-2.86-.31-4.08-1.03-2.02-1.19-3.44-3.37-3.65-5.71-.02-.5-.03-1-.01-1.49.18-1.9 1.12-3.72 2.58-4.96 1.66-1.44 3.98-2.13 6.15-1.72.02 1.48-.04 2.96-.04 4.44-.99-.32-2.15-.23-3.02.37-.63.41-1.11 1.04-1.36 1.75-.21.51-.15 1.07-.14 1.61.24 1.64 1.82 3.02 3.5 2.87 1.12-.01 2.19-.66 2.77-1.61.19-.33.4-.67.41-1.06.1-1.79.06-3.57.07-5.36.01-4.03-.01-8.05.02-12.07z"></path></svg></a>
                </div>
                 <div class="text-gray-400 text-sm mt-4 md:mt-0 flex space-x-4">
                    <a href="#" class="footer-link">Terms of Service</a>
                    <a href="#" class="footer-link">Privacy Policy</a>
                </div>
            </div>
        </div>
    </footer>

    <!-- Signature Sip Modal -->
    <div id="signatureSipModal" class="modal hidden" aria-labelledby="modal-title" role="dialog" aria-modal="true">
        <div class="modal-content">
            <button id="closeSignatureSipModal" class="modal-close-btn" aria-label="Close modal">
                <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path></svg>
            </button>
            <h2 id="modal-title" class="font-playfair text-2xl sm:text-3xl font-bold mb-6 text-center">✨ Discover Your Signature Sip ✨</h2>
            <form id="signatureSipForm" class="space-y-6">
                <div>
                    <label for="flavorProfile" class="block text-sm font-medium text-gray-700 mb-1">What's your preferred flavor profile?</label>
                    <select id="flavorProfile" name="flavorProfile" class="w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-[#0D4F3F] focus:border-[#0D4F3F]">
                        <option>Sweet & Fruity</option>
                        <option>Tart & Zesty</option>
                        <option>Spicy & Warming</option>
                        <option>Herbal & Earthy</option>
                        <option>Floral & Delicate</option>
                        <option>Surprise Me!</option>
                    </select>
                </div>
                <div>
                    <label for="occasion" class="block text-sm font-medium text-gray-700 mb-1">What's the occasion?</label>
                    <select id="occasion" name="occasion" class="w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-[#0D4F3F] focus:border-[#0D4F3F]">
                        <option>Relaxing at home</option>
                        <option>A sophisticated dinner party</option>
                        <option>An afternoon pick-me-up</option>
                        <option>A celebratory toast</option>
                        <option>Outdoor adventure</option>
                    </select>
                </div>
                <div>
                    <label for="mood" class="block text-sm font-medium text-gray-700 mb-1">How are you feeling today?</label>
                    <select id="mood" name="mood" class="w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-[#0D4F3F] focus:border-[#0D4F3F]">
                        <option>Adventurous & Curious</option>
                        <option>Calm & Centered</option>
                        <option>Energized & Inspired</option>
                        <option>Indulgent & Pampered</option>
                    </select>
                </div>
                <button type="submit" class="btn btn-ai-feature w-full">Get My Recommendation</button>
            </form>
            <div id="sipRecommendation" class="mt-6 text-center">
                <!-- Recommendation will be displayed here -->
            </div>
            <div id="loadingSpinner" class="hidden mt-6 flex justify-center">
                <div class="spinner"></div>
            </div>
             <div id="errorMessage" class="hidden mt-4 text-center text-red-600 p-3 bg-red-100 rounded-md"></div>
        </div>
    </div>


    <script>
        // --- General UI Scripts ---
        const menuButton = document.getElementById('mobile-menu-button');
        const mobileMenu = document.getElementById('mobile-menu');
        menuButton.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
        });

        document.getElementById('currentYear').textContent = new Date().getFullYear();

        const motionElements = document.querySelectorAll('.motion-element');
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('is-visible');
                }
            });
        }, { threshold: 0.1 });
        motionElements.forEach(el => observer.observe(el));

        // --- Signature Sip Modal Scripts ---
        const signatureSipModal = document.getElementById('signatureSipModal');
        const openSignatureSipModalButton = document.getElementById('openSignatureSipModal');
        const closeSignatureSipModalButton = document.getElementById('closeSignatureSipModal');
        const signatureSipForm = document.getElementById('signatureSipForm');
        const sipRecommendationDiv = document.getElementById('sipRecommendation');
        const loadingSpinner = document.getElementById('loadingSpinner');
        const errorMessageDiv = document.getElementById('errorMessage');

        const availableFlavors = [
            "Ginger & Elderflower (Aromatic ginger, sweet elderflower, citrus hint)",
            "Rosemary & Grapefruit (Herbaceous rosemary, zesty grapefruit)",
            "Lavender & Blackberry (Soothing lavender, rich blackberries)",
            "Chili & Lime (Spicy chili, tangy lime, smoky undertone)",
            "Mint & Cucumber (Cooling mint, refreshing cucumber, light sparkle)"
        ];

        openSignatureSipModalButton.addEventListener('click', () => {
            signatureSipModal.classList.remove('hidden');
            signatureSipModal.classList.add('open');
            // Reset form and results when opening
            signatureSipForm.reset();
            sipRecommendationDiv.innerHTML = '';
            errorMessageDiv.classList.add('hidden');
            errorMessageDiv.textContent = '';

        });

        closeSignatureSipModalButton.addEventListener('click', () => {
            signatureSipModal.classList.add('hidden');
            signatureSipModal.classList.remove('open');
        });

        // Close modal if backdrop is clicked
        signatureSipModal.addEventListener('click', (event) => {
            if (event.target === signatureSipModal) {
                signatureSipModal.classList.add('hidden');
                signatureSipModal.classList.remove('open');
            }
        });

        signatureSipForm.addEventListener('submit', async (event) => {
            event.preventDefault();
            loadingSpinner.classList.remove('hidden');
            sipRecommendationDiv.innerHTML = ''; // Clear previous recommendation
            errorMessageDiv.classList.add('hidden'); // Clear previous error

            const flavorProfile = document.getElementById('flavorProfile').value;
            const occasion = document.getElementById('occasion').value;
            const mood = document.getElementById('mood').value;

            // --- Gemini API Call ---
            const prompt = `You are a sophisticated beverage curator for a luxury soft drink brand called AR LIFE.
Our available flavors are: ${availableFlavors.join(', ')}.
A user is looking for a recommendation. Their preferences are:
- Flavor Profile: ${flavorProfile}
- Occasion: ${occasion}
- Mood: ${mood}

Based on these preferences, recommend ONE AR LIFE flavor.
Provide the recommendation in the following format:
"For your desire for something ${flavorProfile.toLowerCase()} for a ${occasion.toLowerCase()} when you're feeling ${mood.toLowerCase()}, we believe you'll adore our **[AR LIFE Flavor Name]**. [Provide a 1-2 sentence compelling and elegant description of why this flavor is a perfect match, highlighting its key notes and how it suits the user's preferences. Make it sound luxurious and inviting. Do not mention other flavors or suggest alternatives. Focus only on the single best match.]"
Ensure the flavor name is bolded.`;

            try {
                let chatHistory = [{ role: "user", parts: [{ text: prompt }] }];
                const payload = { contents: chatHistory };
                const apiKey = ""; // Canvas will provide this if needed for models other than gemini-2.0-flash
                const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${apiKey}`;

                const response = await fetch(apiUrl, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });

                if (!response.ok) {
                    const errorData = await response.json();
                    console.error('API Error:', errorData);
                    throw new Error(`API request failed with status ${response.status}. ${errorData?.error?.message || 'Please try again.'}`);
                }

                const result = await response.json();

                if (result.candidates && result.candidates.length > 0 &&
                    result.candidates[0].content && result.candidates[0].content.parts &&
                    result.candidates[0].content.parts.length > 0) {
                    let recommendationText = result.candidates[0].content.parts[0].text;
                    // Sanitize and format: replace markdown bold with HTML bold
                    recommendationText = recommendationText.replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
                    sipRecommendationDiv.innerHTML = `<p class="text-lg text-gray-700">${recommendationText}</p>`;
                } else {
                    console.error('Unexpected API response structure:', result);
                    throw new Error('Sorry, we couldn\'t generate a recommendation at this time. The response from our curator was unexpected.');
                }

            } catch (error) {
                console.error('Error fetching recommendation:', error);
                errorMessageDiv.textContent = `An error occurred: ${error.message}. Please try again shortly.`;
                errorMessageDiv.classList.remove('hidden');
                sipRecommendationDiv.innerHTML = `<p class="text-red-600">We encountered a hiccup trying to find your perfect sip. Please try again.</p>`;
            } finally {
                loadingSpinner.classList.add('hidden');
            }
        });

    </script>
</body>
</html>
