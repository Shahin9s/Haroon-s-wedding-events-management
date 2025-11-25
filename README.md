<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Haroon's Weddings & Events</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Lato:wght@300;400;700&display=swap" rel="stylesheet">

    <!-- Config -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        gold: '#C5A059',
                        dark: '#0f392b',
                        darker: '#0a2e22'
                    },
                    fontFamily: {
                        serif: ['"Playfair Display"', 'serif'],
                        sans: ['"Lato"', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        html { scroll-behavior: smooth; }
        
        /* Scroll Animation */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s cubic-bezier(0.5, 0, 0, 1);
        }
        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Star Hover Animation */
        .star-btn svg {
            transition: transform 0.2s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }
        .star-btn:hover svg {
            transform: scale(1.3); /* Make hover bigger */
        }
        
        /* Star Click 'Pop' Animation */
        @keyframes pop {
            0% { transform: scale(1); }
            50% { transform: scale(1.5); }
            100% { transform: scale(1); }
        }
        .star-pop svg {
            animation: pop 0.3s ease-out;
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-800 font-sans">

    <!-- Navigation -->
    <nav id="navbar" class="fixed w-full z-50 bg-dark py-4 text-white shadow-lg transition-all duration-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center">
                
                <!-- Logo -->
                <div class="flex items-center gap-3 cursor-pointer" onclick="window.scrollTo(0,0)">
                    <div class="w-12 h-12 rounded-full border-2 border-gold bg-dark overflow-hidden flex items-center justify-center relative">
                        <img src="SAVE_20230525_200707.jpg" 
                             onerror="this.onerror=null; this.src='https://placehold.co/100x100/0f392b/C5A059?text=H'" 
                             class="w-full h-full object-cover">
                    </div>
                    <div class="flex flex-col leading-tight">
                        <span class="text-xl font-serif font-bold tracking-wide">HAROON'S</span>
                        <span class="text-xs uppercase tracking-widest text-gold">Weddings & Events</span>
                    </div>
                </div>

                <!-- Desktop Menu -->
                <div class="hidden md:flex space-x-8 items-center">
                    <button onclick="scrollToId('home')" class="hover:text-gold transition text-sm font-medium uppercase tracking-wider">Home</button>
                    <button onclick="scrollToId('services')" class="hover:text-gold transition text-sm font-medium uppercase tracking-wider">Services</button>
                    <button onclick="scrollToId('gallery')" class="hover:text-gold transition text-sm font-medium uppercase tracking-wider">Gallery</button>
                    <button onclick="scrollToId('contact')" class="hover:text-gold transition text-sm font-medium uppercase tracking-wider">Contact</button>
                    <button onclick="scrollToId('contact')" class="bg-gold text-white px-6 py-2.5 rounded-full font-medium hover:bg-yellow-600 transition shadow-lg hover:scale-105 transform">
                        Get a Quote
                    </button>
                </div>

                <!-- Mobile Menu Button -->
                <div class="md:hidden">
                    <button onclick="toggleMenu()" class="text-white p-2">
                        <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="3" y1="12" x2="21" y2="12"/><line x1="3" y1="6" x2="21" y2="6"/><line x1="3" y1="18" x2="21" y2="18"/></svg>
                    </button>
                </div>
            </div>
        </div>
        
        <!-- Mobile Dropdown -->
        <div id="mobile-menu" class="hidden bg-white text-dark absolute w-full top-full left-0 shadow-xl border-t">
            <div class="flex flex-col p-4 space-y-4 font-bold">
                <button onclick="scrollToId('home')" class="text-left py-2 border-b border-gray-100">Home</button>
                <button onclick="scrollToId('services')" class="text-left py-2 border-b border-gray-100">Services</button>
                <button onclick="scrollToId('gallery')" class="text-left py-2 border-b border-gray-100">Gallery</button>
                <button onclick="scrollToId('contact')" class="text-left py-2">Contact</button>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="relative h-screen flex items-center justify-center bg-gray-900 overflow-hidden">
        <div class="absolute inset-0">
            <img src="https://images.unsplash.com/photo-1527529482837-4698179dc6ce?ixlib=rb-1.2.1&auto=format&fit=crop&w=1920&q=80" 
                 class="w-full h-full object-cover opacity-60"
                 onerror="this.style.display='none'">
            <div class="absolute inset-0 bg-gradient-to-br from-gray-900 to-black -z-10"></div>
        </div>
        
        <div class="absolute inset-0 bg-dark/60"></div>

        <div class="relative z-10 text-center px-4 max-w-4xl mx-auto mt-16 text-white">
            <p class="text-gold tracking-[0.2em] mb-4 uppercase text-lg reveal">Since 1989</p>
            <h1 class="text-5xl md:text-7xl font-serif font-bold mb-6 reveal" style="transition-delay: 200ms">
                We Plan Your <br>
                <span class="text-gold italic">Dream Events</span>
            </h1>
            <p class="text-xl mb-10 max-w-2xl mx-auto text-gray-200 reveal" style="transition-delay: 400ms">
                Premium wedding and event management services tailored to your unique style and vision.
            </p>
            <div class="flex flex-col sm:flex-row gap-4 justify-center reveal" style="transition-delay: 600ms">
                <button onclick="scrollToId('contact')" class="bg-gold text-white px-8 py-4 rounded-full font-bold text-lg hover:bg-yellow-600 transition shadow-lg hover:scale-105 transform">Start Planning</button>
                <button onclick="scrollToId('gallery')" class="border-2 border-white/30 text-white px-8 py-4 rounded-full font-bold text-lg hover:bg-white/10 transition hover:scale-105 transform">View Portfolio</button>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="py-24 bg-white">
        <div class="max-w-7xl mx-auto px-4">
            <div class="text-center mb-16 reveal">
                <h2 class="text-gold tracking-wider uppercase mb-2 font-medium">Our Expertise</h2>
                <h3 class="text-4xl font-serif font-bold text-dark">Services We Offer</h3>
                <div class="w-24 h-1 bg-gold mx-auto mt-4 rounded-full"></div>
            </div>

            <div class="grid md:grid-cols-3 gap-8">
                <!-- Service 1 -->
                <div class="bg-gray-50 p-8 rounded-2xl hover:shadow-xl transition duration-300 hover:-translate-y-2 group border border-gray-100 reveal">
                    <div class="w-16 h-16 bg-white rounded-full flex items-center justify-center text-gold mb-6 shadow-sm group-hover:scale-110 transition">
                        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M19 14c1.49-1.46 3-3.21 3-5.5A5.5 5.5 0 0 0 16.5 3c-1.76 0-3 .5-4.5 2-1.5-1.5-2.74-2-4.5-2A5.5 5.5 0 0 0 2 8.5c0 2.3 1.5 4.05 3 5.5l7 7Z"/></svg>
                    </div>
                    <h4 class="text-xl font-bold text-dark mb-3">Wedding Planning</h4>
                    <p class="text-gray-600 leading-relaxed">From venue selection to the final vow, we craft your perfect fairytale wedding.</p>
                </div>
                <!-- Service 2 -->
                <div class="bg-gray-50 p-8 rounded-2xl hover:shadow-xl transition duration-300 hover:-translate-y-2 group border border-gray-100 reveal" style="transition-delay: 200ms">
                    <div class="w-16 h-16 bg-white rounded-full flex items-center justify-center text-gold mb-6 shadow-sm group-hover:scale-110 transition">
                        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect width="18" height="18" x="3" y="4" rx="2" ry="2"/><line x1="16" x2="16" y1="2" y2="6"/><line x1="8" x2="8" y1="2" y2="6"/><line x1="3" x2="21" y1="10" y2="10"/></svg>
                    </div>
                    <h4 class="text-xl font-bold text-dark mb-3">Corporate Events</h4>
                    <p class="text-gray-600 leading-relaxed">Professional conferences, product launches, and company galas executed with precision.</p>
                </div>
                <!-- Service 3 -->
                <div class="bg-gray-50 p-8 rounded-2xl hover:shadow-xl transition duration-300 hover:-translate-y-2 group border border-gray-100 reveal" style="transition-delay: 400ms">
                    <div class="w-16 h-16 bg-white rounded-full flex items-center justify-center text-gold mb-6 shadow-sm group-hover:scale-110 transition">
                        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M9 18V5l12-2v13"/><circle cx="6" cy="18" r="3"/><circle cx="18" cy="16" r="3"/></svg>
                    </div>
                    <h4 class="text-xl font-bold text-dark mb-3">Social Gatherings</h4>
                    <p class="text-gray-600 leading-relaxed">Birthdays, anniversaries, and reunions. We handle the logistics so you can enjoy.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Gallery Section -->
    <section id="gallery" class="py-24 bg-gray-50">
        <div class="max-w-7xl mx-auto px-4">
            <div class="text-center mb-16 reveal">
                <h2 class="text-gold tracking-wider uppercase mb-2 font-medium">Our Portfolio</h2>
                <h3 class="text-4xl font-serif font-bold text-dark">Recent Events</h3>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6 h-auto md:h-[600px]">
                <div class="md:col-span-2 h-64 md:h-full rounded-2xl overflow-hidden relative group reveal">
                    <img src="https://images.unsplash.com/photo-1519741497674-611481863552?w=800&q=80" class="w-full h-full object-cover transition duration-700 group-hover:scale-110">
                    <div class="absolute bottom-0 left-0 p-8 bg-gradient-to-t from-dark/90 to-transparent w-full">
                        <p class="text-gold font-bold uppercase text-sm">Wedding</p>
                        <h4 class="text-white text-2xl font-bold">Royal Celebration</h4>
                    </div>
                </div>
                <div class="grid grid-rows-2 gap-6 h-full">
                    <div class="h-64 md:h-full rounded-2xl overflow-hidden relative group reveal" style="transition-delay: 200ms">
                        <img src="https://images.unsplash.com/photo-1511795409834-ef04bbd61622?w=800&q=80" class="w-full h-full object-cover transition duration-700 group-hover:scale-110">
                    </div>
                    <div class="h-64 md:h-full rounded-2xl overflow-hidden relative group reveal" style="transition-delay: 400ms">
                        <img src="https://images.unsplash.com/photo-1470225620780-dba8ba36b745?w=800&q=80" class="w-full h-full object-cover transition duration-700 group-hover:scale-110">
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="bg-dark py-20 text-white">
        <div class="max-w-7xl mx-auto px-4">
            <div class="grid grid-cols-2 md:grid-cols-4 gap-8 text-center">
                <div class="reveal">
                    <div class="text-4xl md:text-5xl font-bold text-gold mb-2">10M+</div>
                    <div class="text-gray-300 font-medium">Happy Guests</div>
                </div>
                <div class="reveal" style="transition-delay: 100ms">
                    <div class="text-4xl md:text-5xl font-bold text-gold mb-2">1M+</div>
                    <div class="text-gray-300 font-medium">Customers</div>
                </div>
                <div class="reveal" style="transition-delay: 200ms">
                    <div class="text-4xl md:text-5xl font-bold text-gold mb-2">30+</div>
                    <div class="text-gray-300 font-medium">Years</div>
                </div>
                <div class="reveal" style="transition-delay: 300ms">
                    <div class="text-4xl md:text-5xl font-bold text-gold mb-2">50+</div>
                    <div class="text-gray-300 font-medium">Awards</div>
                </div>
            </div>
        </div>
    </section>

    <!-- REVIEWS & FEEDBACK SYSTEM -->
    <section class="py-24 bg-darker text-white border-t border-white/10 relative overflow-hidden">
        <!-- Background Pattern -->
        <div class="absolute inset-0 opacity-5" style="background-image: radial-gradient(#C5A059 1px, transparent 1px); background-size: 30px 30px;"></div>
        
        <div class="max-w-7xl mx-auto px-4 relative z-10">
            <div class="text-center mb-16 reveal">
                <h2 class="text-gold font-medium tracking-wider uppercase mb-2">Client Stories</h2>
                <h3 class="text-4xl font-serif font-bold text-white">Feedback & Reviews</h3>
                <div class="w-24 h-1 bg-gold mx-auto mt-4 rounded-full"></div>
            </div>

            <!-- 1. TESTIMONIALS GRID (ID added for JS) -->
            <div id="testimonials-grid" class="grid md:grid-cols-3 gap-8 mb-16">
                <div class="bg-[#0a2e22] p-8 rounded-xl border border-[#1a4f3d] hover:border-gold/50 transition reveal">
                    <div class="flex gap-1 mb-4 text-gold">★★★★★</div>
                    <p class="text-gray-300 italic mb-6">"Haroon's made our dream wedding a reality. The stage decoration was breathtaking and exactly what we imagined!"</p>
                    <div class="flex items-center gap-3">
                        <div class="w-10 h-10 rounded-full bg-[#1a4f3d] flex items-center justify-center text-gold font-bold">A</div>
                        <div>
                            <h4 class="font-bold text-white text-sm">Adnan & Fatima</h4>
                            <span class="text-xs text-gold uppercase tracking-wider">Wedding</span>
                        </div>
                    </div>
                </div>
                <div class="bg-[#0a2e22] p-8 rounded-xl border border-[#1a4f3d] hover:border-gold/50 transition reveal" style="transition-delay: 150ms">
                    <div class="flex gap-1 mb-4 text-gold">★★★★★</div>
                    <p class="text-gray-300 italic mb-6">"Professional, punctual, and perfect execution. The annual meet was handled flawlessly. Highly recommended."</p>
                    <div class="flex items-center gap-3">
                        <div class="w-10 h-10 rounded-full bg-[#1a4f3d] flex items-center justify-center text-gold font-bold">T</div>
                        <div>
                            <h4 class="font-bold text-white text-sm">TechSolutions Pvt Ltd</h4>
                            <span class="text-xs text-gold uppercase tracking-wider">Corporate Event</span>
                        </div>
                    </div>
                </div>
                <div class="bg-[#0a2e22] p-8 rounded-xl border border-[#1a4f3d] hover:border-gold/50 transition reveal" style="transition-delay: 300ms">
                    <div class="flex gap-1 mb-4 text-gold">★★★★★</div>
                    <p class="text-gray-300 italic mb-6">"My daughter's 5th birthday was magical thanks to the team. The decor and food were just amazing."</p>
                    <div class="flex items-center gap-3">
                        <div class="w-10 h-10 rounded-full bg-[#1a4f3d] flex items-center justify-center text-gold font-bold">R</div>
                        <div>
                            <h4 class="font-bold text-white text-sm">Riya's Parents</h4>
                            <span class="text-xs text-gold uppercase tracking-wider">Birthday Party</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- 2. INTERACTIVE RATING -->
            <div class="max-w-2xl mx-auto text-center reveal">
                <div class="bg-white/5 p-8 rounded-3xl border border-gold/30 backdrop-blur-sm shadow-2xl">
                    <h4 class="text-2xl font-serif font-bold text-white mb-2">How was your experience?</h4>
                    <p class="text-gray-400 mb-8">Click a star to rate us and leave a review.</p>
                    
                    <!-- Star Buttons with Pop Animation -->
                    <div class="flex justify-center gap-3 mb-8" id="star-container">
                        <button onclick="setRating(1)" class="star-btn p-1 focus:outline-none"><svg id="star-1" width="44" height="44" viewBox="0 0 24 24" fill="none" stroke="#6B7280" stroke-width="2"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg></button>
                        <button onclick="setRating(2)" class="star-btn p-1 focus:outline-none"><svg id="star-2" width="44" height="44" viewBox="0 0 24 24" fill="none" stroke="#6B7280" stroke-width="2"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg></button>
                        <button onclick="setRating(3)" class="star-btn p-1 focus:outline-none"><svg id="star-3" width="44" height="44" viewBox="0 0 24 24" fill="none" stroke="#6B7280" stroke-width="2"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg></button>
                        <button onclick="setRating(4)" class="star-btn p-1 focus:outline-none"><svg id="star-4" width="44" height="44" viewBox="0 0 24 24" fill="none" stroke="#6B7280" stroke-width="2"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg></button>
                        <button onclick="setRating(5)" class="star-btn p-1 focus:outline-none"><svg id="star-5" width="44" height="44" viewBox="0 0 24 24" fill="none" stroke="#6B7280" stroke-width="2"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg></button>
                    </div>

                    <div id="rating-text" class="text-gold font-medium mb-4 h-6"></div>

                    <!-- Review Form (Reverted to simple div structure) -->
                    <div id="review-form" class="hidden space-y-4 animate-fade-in-up">
                        <div class="relative">
                            <input type="text" id="review-name" placeholder="Your Name" class="w-full p-3 pl-4 rounded-xl bg-dark/50 border border-white/20 text-white placeholder-gray-500 focus:outline-none focus:border-gold">
                        </div>
                        <textarea id="review-text" rows="3" placeholder="Tell us about your event experience..." class="w-full p-3 pl-4 rounded-xl bg-dark/50 border border-white/20 text-white placeholder-gray-500 focus:outline-none focus:border-gold resize-none"></textarea>
                        
                        <button onclick="submitReview()" class="bg-gold px-8 py-3 rounded-full font-bold hover:bg-yellow-600 transition w-full flex items-center justify-center gap-2 shadow-lg">
                            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect width="20" height="16" x="2" y="4" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
                            Submit Review via Gmail
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-24 bg-white">
        <div class="max-w-7xl mx-auto px-4">
            <div class="grid md:grid-cols-2 gap-16 items-start">
                <div class="reveal">
                    <h2 class="text-gold tracking-wider uppercase mb-2 font-medium">Get in Touch</h2>
                    <h3 class="text-4xl font-serif font-bold text-dark mb-6">Let's Plan Your Big Day</h3>
                    <p class="text-gray-600 mb-10 text-lg leading-relaxed">
                        Ready to start planning? Fill out the form or contact us directly. We offer free initial consultations.
                    </p>
                    
                    <div class="space-y-6">
                        <!-- Phone -->
                        <div class="flex items-center gap-4 group">
                            <div class="w-12 h-12 bg-dark/5 rounded-xl flex items-center justify-center text-dark group-hover:bg-gold group-hover:text-white transition duration-300">
                                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
                            </div>
                            <div>
                                <h4 class="font-bold text-dark">Phone</h4>
                                <p class="text-gray-600">+91 9037874001, +91 9567525723</p>
                            </div>
                        </div>
                        <!-- Email -->
                        <div class="flex items-center gap-4 group">
                            <div class="w-12 h-12 bg-dark/5 rounded-xl flex items-center justify-center text-dark group-hover:bg-gold group-hover:text-white transition duration-300">
                                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect width="20" height="16" x="2" y="4" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg>
                            </div>
                            <div>
                                <h4 class="font-bold text-dark">Email</h4>
                                <p class="text-gray-600">haroonsevent@gmail.com</p>
                            </div>
                        </div>
                        <!-- Location -->
                        <div class="flex items-center gap-4 group">
                            <div class="w-12 h-12 bg-dark/5 rounded-xl flex items-center justify-center text-dark group-hover:bg-gold group-hover:text-white transition duration-300">
                                <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M20 10c0 6-8 12-8 12s-8-6-8-12a8 8 0 0 1 16 0Z"/><circle cx="12" cy="10" r="3"/></svg>
                            </div>
                            <div>
                                <h4 class="font-bold text-dark">Location</h4>
                                <p class="text-gray-600">Near Jamia College, Chembakuth, Edavanna</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- ENQUIRY FORM with RED STARS -->
                <div class="bg-gray-50 p-8 rounded-3xl shadow-lg border border-gray-100 reveal" style="transition-delay: 200ms">
                    <form onsubmit="sendWhatsApp(event)" class="space-y-6">
                        <div class="grid grid-cols-2 gap-4">
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">First Name <span class="text-red-500">*</span></label>
                                <input type="text" id="fname" required class="w-full px-4 py-3 rounded-xl border border-gray-200 focus:outline-none focus:border-gold focus:ring-1 focus:ring-gold bg-white">
                            </div>
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">Last Name <span class="text-red-500">*</span></label>
                                <input type="text" id="lname" required class="w-full px-4 py-3 rounded-xl border border-gray-200 focus:outline-none focus:border-gold focus:ring-1 focus:ring-gold bg-white">
                            </div>
                        </div>
                        <div class="grid grid-cols-2 gap-4">
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">Email <span class="text-red-500">*</span></label>
                                <input type="email" id="email" required class="w-full px-4 py-3 rounded-xl border border-gray-200 focus:outline-none focus:border-gold focus:ring-1 focus:ring-gold bg-white">
                            </div>
                            <div>
                                <label class="block text-sm font-medium text-gray-700 mb-2">WhatsApp <span class="text-red-500">*</span></label>
                                <input type="tel" id="phone" required class="w-full px-4 py-3 rounded-xl border border-gray-200 focus:outline-none focus:border-gold focus:ring-1 focus:ring-gold bg-white">
                            </div>
                        </div>
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Event Type</label>
                            <select id="event" class="w-full px-4 py-3 rounded-xl border border-gray-200 focus:outline-none focus:border-gold bg-white">
                                <option>Wedding</option>
                                <option>Corporate Event</option>
                                <option>Birthday Party</option>
                                <option>Other</option>
                            </select>
                        </div>
                        <div>
                            <label class="block text-sm font-medium text-gray-700 mb-2">Message</label>
                            <textarea id="message" rows="4" class="w-full px-4 py-3 rounded-xl border border-gray-200 focus:outline-none focus:border-gold focus:ring-1 focus:ring-gold bg-white"></textarea>
                        </div>
                        <button type="submit" class="w-full bg-gold text-white font-bold py-4 rounded-xl hover:bg-yellow-600 transition shadow-lg flex items-center justify-center gap-2 transform hover:-translate-y-1">
                            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><line x1="22" x2="11" y1="2" y2="13"/><polygon points="22 2 15 22 11 13 2 9 22 2"/></svg>
                            Send Inquiry via WhatsApp
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer - 3 Columns -->
    <footer class="bg-[#0f392b] text-white pt-16 pb-8 border-t border-white/10">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-12 mb-12">
                
                <!-- Column 1: Brand & Social -->
                <div class="space-y-6">
                    <div class="flex items-center gap-3">
                        <div class="w-12 h-12 rounded-full border border-gold flex items-center justify-center text-gold font-serif text-xl">H</div>
                        <div>
                            <h3 class="text-2xl font-serif font-bold text-white tracking-wide">HAROON'S</h3>
                            <p class="text-[10px] text-gold uppercase tracking-[0.3em]">Weddings & Events</p>
                        </div>
                    </div>
                    <p class="text-gray-300 text-sm leading-relaxed max-w-sm">
                        Turning your special moments into lifelong memories. We provide full-service planning for weddings, corporate galas, and private parties.
                    </p>
                    <div class="flex gap-4">
                        <a href="https://www.instagram.com/haroons_weddings/?hl=en" target="_blank" class="w-10 h-10 rounded-full bg-[#1a4f3d] flex items-center justify-center text-white hover:bg-gold hover:scale-110 transition duration-300">
                            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"/></svg>
                        </a>
                        <a href="https://www.facebook.com/p/Haroons-weddings-events-100063703044091/" target="_blank" class="w-10 h-10 rounded-full bg-[#1a4f3d] flex items-center justify-center text-white hover:bg-gold hover:scale-110 transition duration-300">
                            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"/></svg>
                        </a>
                        <a href="https://www.youtube.com/channel/UC5XX2UPV5JB6wIaPxrPlMbg" target="_blank" class="w-10 h-10 rounded-full bg-[#1a4f3d] flex items-center justify-center text-white hover:bg-gold hover:scale-110 transition duration-300">
                            <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M2.5 17a24.12 24.12 0 0 1 0-10 2 2 0 0 1 1.4-1.4 49.56 49.56 0 0 1 16.2 0A2 2 0 0 1 21.5 7a24.12 24.12 0 0 1 0 10 2 2 0 0 1-1.4 1.4 49.55 49.55 0 0 1-16.2 0A2 2 0 0 1 2.5 17"/><path d="m10 15 5-3-5-3z"/></svg>
                        </a>
                    </div>
                </div>

                <!-- Column 2: Quick Links -->
                <div class="md:pl-10">
                    <h4 class="text-gold font-bold text-lg mb-6">Quick Links</h4>
                    <ul class="space-y-3">
                        <li><a href="#" onclick="scrollToId('home')" class="text-gray-300 hover:text-gold transition flex items-center gap-2 text-sm"><span class="text-xs text-gold font-bold">></span> Home</a></li>
                        <li><a href="#" onclick="scrollToId('services')" class="text-gray-300 hover:text-gold transition flex items-center gap-2 text-sm"><span class="text-xs text-gold font-bold">></span> Services</a></li>
                        <li><a href="#" onclick="scrollToId('gallery')" class="text-gray-300 hover:text-gold transition flex items-center gap-2 text-sm"><span class="text-xs text-gold font-bold">></span> Gallery</a></li>
                        <li><a href="#" onclick="scrollToId('contact')" class="text-gray-300 hover:text-gold transition flex items-center gap-2 text-sm"><span class="text-xs text-gold font-bold">></span> Contact</a></li>
                    </ul>
                </div>

                <!-- Column 3: Contact -->
                <div>
                    <h4 class="text-gold font-bold text-lg mb-6">Contact</h4>
                    <ul class="space-y-4 text-gray-300 text-sm">
                        <li class="flex items-start gap-3">
                            <span class="text-gold mt-1"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M20 10c0 6-8 12-8 12s-8-6-8-12a8 8 0 0 1 16 0Z"/><circle cx="12" cy="10" r="3"/></svg></span>
                            <span>Near Jamia College, Chembakuth,<br>Edavanna, Kerala 676541</span>
                        </li>
                        <li class="flex items-center gap-3">
                            <span class="text-gold"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/></svg></span>
                            <div>
                                <div class="block">+91 9037874001</div>
                                <div class="block">+91 9567525723</div>
                            </div>
                        </li>
                        <li class="flex items-center gap-3">
                            <span class="text-gold"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect width="20" height="16" x="2" y="4" rx="2"/><path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/></svg></span>
                            <span>haroonsevent@gmail.com</span>
                        </li>
                    </ul>
                </div>
            </div>

            <!-- Copyright -->
            <div class="border-t border-white/10 pt-8 text-center text-gray-400 text-xs">
                <p>&copy; 2025 Haroon's Weddings & Events Management Company. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <!-- Logic -->
    <script>
        // --- 1. Mobile Menu ---
        function toggleMenu() {
            const menu = document.getElementById('mobile-menu');
            menu.classList.toggle('hidden');
        }

        // --- 2. Smooth Scroll ---
        function scrollToId(id) {
            const el = document.getElementById(id);
            if(el) {
                el.scrollIntoView({ behavior: 'smooth' });
                document.getElementById('mobile-menu').classList.add('hidden');
            }
        }

        // --- 3. WhatsApp Form ---
        function sendWhatsApp(e) {
            e.preventDefault();
            const fname = document.getElementById('fname').value;
            const lname = document.getElementById('lname').value;
            const email = document.getElementById('email').value;
            const phone = document.getElementById('phone').value;
            const event = document.getElementById('event').value;
            const msg = document.getElementById('message').value;

            const text = `*New Website Inquiry*%0A%0A*Name:* ${fname} ${lname}%0A*Email:* ${email}%0A*Phone:* ${phone}%0A*Event:* ${event}%0A*Message:* ${msg}`;
            window.open(`https://wa.me/919037874001?text=${text}`, '_blank');
        }

        // --- 4. Review System with Animation and Persistence (Local Storage) ---
        let currentRating = 0;
        
        // --- 4a. Helper: Create HTML for a single review card ---
        function createReviewCard(name, text, rating) {
            const newCard = document.createElement('div');
            // Add "reveal" class for animation if this is rendered on load
            newCard.className = "bg-[#0a2e22] p-8 rounded-xl border border-[#1a4f3d] hover:border-gold/50 transition reveal active";
            
            let starsHtml = "";
            for(let i=0; i<rating; i++) starsHtml += "★";
            
            newCard.innerHTML = `
                <div class="flex gap-1 mb-4 text-gold text-lg">${starsHtml}</div>
                <p class="text-gray-300 italic mb-6">"${text}"</p>
                <div class="flex items-center gap-3">
                    <div class="w-10 h-10 rounded-full bg-[#1a4f3d] flex items-center justify-center text-gold font-bold border border-gold/30">${name.charAt(0).toUpperCase()}</div>
                    <div>
                        <h4 class="font-bold text-white text-sm">${name}</h4>
                        <span class="text-xs text-gold uppercase tracking-wider">Recent Customer</span>
                    </div>
                </div>
            `;
            return newCard;
        }

        // --- 4b. Load Reviews from Local Storage on Start ---
        function loadReviews() {
            const grid = document.getElementById('testimonials-grid');
            const storedReviews = JSON.parse(localStorage.getItem('haroon_reviews') || '[]');
            
            // Reverse loop to keep newest on top if appended sequentially
            // OR just loop normal and prepend. Let's loop normal and prepend to match submit logic.
            storedReviews.forEach(review => {
                const card = createReviewCard(review.name, review.text, review.rating);
                // Insert at the beginning of the grid, before static testimonials
                grid.insertBefore(card, grid.firstChild);
            });
        }

        // --- 4c. Star Rating Visuals ---
        function setRating(n) {
            currentRating = n;
            document.getElementById('review-form').classList.remove('hidden');
            document.getElementById('review-form').classList.add('animate-fade-in-up');
            
            for (let i = 1; i <= 5; i++) {
                const starBtn = document.querySelector(`button[onclick="setRating(${i})"]`);
                const starSvg = document.getElementById(`star-${i}`);
                
                starBtn.classList.remove('star-pop');
                void starBtn.offsetWidth; 
                starBtn.classList.add('star-pop');

                if (i <= n) {
                    starSvg.setAttribute('fill', '#C5A059');
                    starSvg.setAttribute('stroke', '#C5A059');
                } else {
                    starSvg.setAttribute('fill', 'none');
                    starSvg.setAttribute('stroke', '#6B7280');
                }
            }
            
            document.getElementById('rating-text').innerText = `You selected ${n} star${n > 1 ? 's' : ''}`;
        }

        // --- 4d. Submit Logic (Mobile Mailto Fix) ---
        function submitReview() {
            const name = document.getElementById('review-name').value;
            const text = document.getElementById('review-text').value;
            
            if(!name || !text) {
                alert("Please enter your name and review text.");
                return;
            }

            // 1. Save to Local Storage
            const newReview = { name, text, rating: currentRating };
            const existingReviews = JSON.parse(localStorage.getItem('haroon_reviews') || '[]');
            existingReviews.push(newReview);
            localStorage.setItem('haroon_reviews', JSON.stringify(existingReviews));

            // 2. Add to UI Instantly
            const grid = document.getElementById('testimonials-grid');
            const card = createReviewCard(name, text, currentRating);
            card.classList.add('animate-fade-in-up');
            grid.insertBefore(card, grid.firstChild);
            
            grid.scrollIntoView({ behavior: 'smooth', block: 'center' });

            // 3. Universal Mailto (Works on Mobile and Desktop)
            const subject = `New ${currentRating}-Star Review from ${name}`;
            const body = `Name: ${name}%0ARating: ${currentRating}/5%0AFeedback: ${text}`;
            
            // This is the key fix for mobile "about:blank" errors
            window.location.href = `mailto:haroonsevent@gmail.com?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
            
            // 4. Reset Form
            document.getElementById('review-name').value = '';
            document.getElementById('review-text').value = '';
            setRating(0);
            document.getElementById('review-form').classList.add('hidden');
            
            // alert("Thank you! Your review has been saved.");
        }

        // --- 5. Scroll Animations Trigger ---
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if(entry.isIntersecting) {
                    entry.target.classList.add('active');
                } else {
                    entry.target.classList.remove('active');
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

        // --- 6. Initialize ---
        // Load saved reviews when page opens
        loadReviews();

    </script>
</body>
</html>
