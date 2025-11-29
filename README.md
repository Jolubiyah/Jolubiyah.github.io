<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Six Months & Forever</title>
    <!-- Load Tailwind CSS --><script src="https://cdn.tailwindcss.com"></script>
    <!-- Use Inter font family --><link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap" rel="stylesheet">
    <style>
        /* Custom styles for the luxury feel */
        body {
            font-family: 'Inter', sans-serif;
            background-color: #0d1117; /* Dark background for outside the main layout container */
            overflow-x: hidden;
            scroll-behavior: smooth;
        }

        /* Subtle scroll animation */
        .reveal {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 1s ease-out, transform 0.8s ease-out;
        }
        .reveal.visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        /* Custom gradient for the hero section title */
        .hero-title {
            /* Gradient optimized for white background */
            background-image: linear-gradient(45deg, #f472b6, #e879f9, #be185d);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* Dev Log Button Hover Effect */
        .header-btn {
            transition: transform 0.3s ease, background-color 0.3s ease;
        }
        .header-btn:hover {
            transform: scale(1.05);
            background-color: #be185d; /* Darker pink on hover */
        }

        /* --- SECRET GALLERY ANIMATION STYLES (Unchanged) --- */
        @keyframes float-x-1 { 0% { transform: translateX(0); } 50% { transform: translateX(100px); } 100% { transform: translateX(0); } }
        @keyframes float-y-1 { 0% { transform: translateY(0); } 50% { transform: translateY(50px) rotate(2deg); } 100% { transform: translateY(0); } }
        @keyframes float-x-2 { 0% { transform: translateX(0); } 50% { transform: translateX(-80px); } 100% { transform: translateX(0); } }
        @keyframes float-y-2 { 0% { transform: translateY(0); } 50% { transform: translateY(-70px) rotate(-3deg); } 100% { transform: translateY(0); } }
        @keyframes float-x-3 { 0% { transform: translateX(0); } 50% { transform: translateX(120px); } 100% { transform: translateX(0); } }
        @keyframes float-y-3 { 0% { transform: translateY(0); } 50% { transform: translateY(60px) rotate(5deg); } 100% { transform: translateY(0); } }
        @keyframes float-x-4 { 0% { transform: translateX(0); } 50% { transform: translateX(-90px); } 100% { transform: translateX(0); } }
        @keyframes float-y-4 { 0% { transform: translateY(0); } 50% { transform: translateY(-40px) rotate(-1deg); } 100% { transform: translateY(0); } }
        @keyframes float-x-5 { 0% { transform: translateX(0); } 50% { transform: translateX(70px); } 100% { transform: translateX(0); } }
        @keyframes float-y-5 { 0% { transform: translateY(0); } 50% { transform: translateY(-80px) rotate(4deg); } 100% { transform: translateY(0); } }
        @keyframes float-x-6 { 0% { transform: translateX(0); } 50% { transform: translateX(60px); } 100% { transform: translateX(0); } }
        @keyframes float-y-6 { 0% { transform: translateY(0); } 50% { transform: translateY(90px) rotate(-2deg); } 100% { transform: translateY(0); } }

        .floating-image {
            position: absolute;
            opacity: 0.8;
            border-radius: 0.75rem;
            box-shadow: 0 25px 50px -12px rgba(236, 72, 153, 0.5);
            animation-iteration-count: infinite;
            animation-direction: alternate;
            filter: saturate(1.1);
        }
        .img-1 { top: 5%; left: 10%; width: 250px; animation: float-x-1 15s ease-in-out infinite alternate, float-y-1 20s ease-in-out infinite alternate; }
        .img-2 { top: 20%; right: 5%; width: 300px; animation: float-x-2 18s ease-in-out infinite alternate, float-y-2 25s ease-in-out infinite alternate; }
        .img-3 { bottom: 15%; left: 5%; width: 200px; animation: float-x-3 12s ease-in-out infinite alternate, float-y-3 17s ease-in-out infinite alternate; }
        .img-4 { bottom: 5%; right: 20%; width: 280px; animation: float-x-4 22s ease-in-out infinite alternate, float-y-4 14s ease-in-out infinite alternate; }
        .img-5 { top: 35%; left: 30%; width: 180px; animation: float-x-5 16s ease-in-out infinite alternate, float-y-5 21s ease-in-out infinite alternate; }
        .img-6 { bottom: 30%; right: 40%; width: 220px; animation: float-x-6 14s ease-in-out infinite alternate reverse, float-y-6 19s ease-in-out infinite alternate reverse; }

        @media (max-width: 1024px) {
            .floating-image { display: none; } /* Hide animations on smaller screens */
        }
        /* --- END GALLERY STYLES --- */

        /* --- VERTICAL PINK GUTTER STYLE --- */
        .pink-hearts-bg {
            background-color: #fecaca; /* Light pink */
            /* Pink hearts SVG pattern for the gutters */
            background-image: url("data:image/svg+xml,%3Csvg width='12' height='12' viewBox='0 0 12 12' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M10 3.5c-.388-1.527-1.464-2.583-3-2.5-1.536-.083-2.612 1.056-3 2.5C2.562 5.093 1.948 6.557 3 8c1.052 1.443 2.536 1.917 3 2.5.464-.583 1.948-1.057 3-2.5 1.052-1.443.438-2.907-1-4.5z' fill='%23ec4899' fill-opacity='0.2'/%3E%3C/svg%3E"); 
        }

        /* --- MAIN LAYOUT GRID --- */
        /* This sets up the Pink | White | Pink structure on screens larger than 'lg' (1024px) */
        .three-column-grid {
            display: grid;
            /* Defines 3 columns: 1 fractional unit | Max 800px center content | 1 fractional unit */
            grid-template-columns: 1fr minmax(0, 800px) 1fr;
            min-height: 100vh;
        }

        /* On screens below 'lg', the grid collapses to a single column for the content. */
        @media (max-width: 1023px) {
            .three-column-grid {
                grid-template-columns: 1fr; 
            }
        }

        /* Style tweaks for text readability on white background */
        .white-content-area h3 { color: #ec4899; } /* Pink for titles */
        .white-content-area p.italic { color: #718096; } /* Lighter gray for italics */
        .white-content-area .text-pink-500 { color: #db2777; } /* Darker pink for uppercase date */
        .white-content-area .text-pink-600 { color: #ec4899; } /* Pink for bounce arrow */

    </style>
</head>
<body>

    <!-- Header & Action Buttons (Full Width, Sticky) --><header class="sticky top-0 z-50 p-4 bg-gray-900/90 backdrop-blur-sm shadow-xl">
        <div class="max-w-7xl mx-auto flex justify-between items-center">
            <h1 class="text-xl font-extrabold text-pink-400 tracking-wider">6 MONTHS</h1>
            <div class="space-x-4 flex">
                <button id="secret-gallery-btn" class="header-btn px-4 py-2 text-sm font-semibold rounded-full bg-indigo-600 text-white shadow-lg">
                    Secret Gallery
                </button>
                <button id="dev-log-btn" class="header-btn px-4 py-2 text-sm font-semibold rounded-full bg-pink-600 text-white shadow-lg">
                    View Project Dev Log
                </button>
            </div>
        </div>
    </header>

    <!-- MAIN VERTICAL LAYOUT: PINK | WHITE | PINK -->
    <div class="three-column-grid">

        <!-- 1. LEFT PINK GUTTER (Hidden on smaller screens) -->
        <div class="pink-hearts-bg hidden lg:block"></div>
        
        <!-- 2. CENTRAL WHITE CONTENT COLUMN -->
        <div class="bg-white w-full text-gray-800 white-content-area overflow-x-hidden">
            <main class="max-w-6xl mx-auto py-12 md:py-16 space-y-16 md:space-y-24 px-6 md:px-12">

                <!-- 1. Hero Section -->
                <section class="text-center reveal p-4 md:p-8">
                    <p class="text-lg md:text-xl font-medium text-pink-500 mb-4 tracking-widest uppercase">Dec. 7th, 2025</p>
                    <h2 class="text-6xl md:text-8xl font-black hero-title leading-tight">
                        Our Story So Far...
                    </h2>
                    <p class="mt-8 text-xl md:text-2xl max-w-3xl mx-auto text-gray-700">
                        Six months ago, you changed everything for the better. This is a small tribute to the most beautiful, brilliant, and kind person I know.
                    </p>
                    <svg class="mx-auto mt-12 animate-bounce text-pink-600" xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 5v14M19 12l-7 7-7-7"/></svg>
                </section>

                <!-- 2. First Memory: The Beginning -->
                <section class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal">
                    <div class="order-2 md:order-1 space-y-6">
                        <h3 class="text-4xl font-bold">The Day We Met</h3>
                        <p class="text-lg">
                            I remember the first time I saw you. It felt like the world just clicked into place. Everything before that moment was monochrome, and suddenly, you were the vibrant splash of color I never knew I was missing. It wasn't just fate; it was the start of my favorite adventure.
                        </p>
                        <p class="text-sm italic">
                            A snapshot from the very start of our journey.
                        </p>
                    </div>
                    <div class="order-1 md:order-2 shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                        <!-- Image source updated to T.png --><img src="T.png" 
                             alt="Placeholder for the beginning of our relationship"
                             class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                             onerror="this.onerror=null;this.src='https://placehold.co/400x250/f472b6/ffffff?text=M+1+Start'">
                    </div>
                </section>

                <!-- 3. Second Memory: Her Spirit -->
                <section class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal">
                    <div class="shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                        <!-- Image source updated to T.png --><img src="T.png" 
                             alt="Placeholder for a picture of her smile"
                             class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                             onerror="this.onerror=null;this.src='https://placehold.co/400x250/f472b6/ffffff?text=M+2+Smile'">
                    </div>
                    <div class="space-y-6">
                        <h3 class="text-4xl font-bold">The Power of Your Joy</h3>
                        <p class="text-lg">
                            Your smile is my favorite thing in the world—it's genuine, infectious, and lights up every room. More than that, your kindness, resilience, and incredible passion for everything you do inspire me every single day. You are truly brilliant, and I'm so proud to watch you chase your dreams.
                        </p>
                        <p class="text-sm italic">
                            A picture that captures your amazing spirit.
                        </p>
                    </div>
                </section>

                <!-- 4. Third Memory: Adventures -->
                <section class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal">
                    <div class="order-2 md:order-1 space-y-6">
                        <h3 class="text-4xl font-bold">Our Shared Adventures</h3>
                        <p class="text-lg">
                            From quiet nights watching movies to that chaotic weekend trip we took, every moment with you is an adventure. You make the mundane magical and the exciting unforgettable. Thank you for being my favorite co-pilot through all of life's twists and turns.
                        </p>
                        <p class="text-sm italic">
                            A beautiful memory of one of our best days.
                        </p>
                    </div>
                    <div class="order-1 md:order-2 shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                        <!-- Image source updated to T.png --><img src="T.png" 
                             alt="Placeholder for an adventure we had together"
                             class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                             onerror="this.onerror=null;this.src='https://placehold.co/400x250/f472b6/ffffff?text=M+3+Adventure'">
                    </div>
                </section>

                <!-- 5. Her Empathy -->
                <section class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal">
                    <div class="shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                        <!-- Image source updated to T.png --><img src="T.png" 
                             alt="Placeholder for a moment of quiet reflection or caring"
                             class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                             onerror="this.onerror=null;this.src='https://placehold.co/400x250/f472b6/ffffff?text=M+4+Empathy'">
                    </div>
                    <div class="space-y-6">
                        <h3 class="text-4xl font-bold">The Depth of Your Empathy</h3>
                        <p class="text-lg">
                            The way you listen, truly listen, is a rare gift. You have this incredible ability to understand and support me without judgment. In a chaotic world, you are my calm, my confidante, and my most trusted advisor. Thank you for showing me what unconditional support feels like.
                        </p>
                        <p class="text-sm italic">
                            A moment of deep connection.
                        </p>
                    </div>
                </section>

                <!-- 6. Favorite Date Night -->
                <section class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal">
                    <div class="order-2 md:order-1 space-y-6">
                        <h3 class="text-4xl font-bold">That One Date Night</h3>
                        <p class="text-lg">
                            Remember that night? It wasn't the place or the food, but the way we talked for hours until we realized everyone else had left. It’s those simple, genuine, time-stands-still moments that I cherish the most. Every date with you feels like the best one yet.
                        </p>
                        <p class="text-sm italic">
                            A photo from our best date.
                        </p>
                    </div>
                    <div class="order-1 md:order-2 shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                        <!-- Image source updated to T.png --><img src="T.png" 
                             alt="Placeholder for a favorite date night memory"
                             class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                             onerror="this.onerror=null;this.src='https://placehold.co/400x250/f472b6/ffffff?text=M+5+Date'">
                    </div>
                </section>

                <!-- 7. Her Intelligence -->
                <section class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal">
                    <div class="shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                        <!-- Image source updated to T.png --><img src="T.png" 
                             alt="Placeholder for a picture showing her focused or achieving something"
                             class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                             onerror="this.onerror=null;this.src='https://placehold.co/400x250/f472b6/ffffff?text=M+6+Intelligence'">
                    </div>
                    <div class="space-y-6">
                        <h3 class="text-4xl font-bold">Your Brilliant Mind</h3>
                        <p class="text-lg">
                            I love our conversations. Your perspective, your curiosity, and the sheer force of your intelligence are mesmerizing. You constantly challenge me to think deeper and better. Being with you means never being bored, and always learning something new.
                        </p>
                        <p class="text-sm italic">
                            A picture from a moment of focused thought or achievement.
                        </p>
                    </div>
                </section>

                <!-- 8. First Big Challenge -->
                <section class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal">
                    <div class="order-2 md:order-1 space-y-6">
                        <h3 class="text-4xl font-bold">Facing Our First Challenge</h3>
                        <p class="text-lg">
                            Every relationship faces hurdles, and I’m thankful we faced ours early. It wasn't easy, but seeing how we navigated that moment together solidified my belief in us. We are a team, capable of overcoming anything, because we prioritize communication and trust.
                        </p>
                        <p class="text-sm italic">
                            A memory of us being there for each other.
                        </p>
                    </div>
                    <div class="order-1 md:order-2 shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                        <!-- Image source updated to T.png --><img src="T.png" 
                             alt="Placeholder for a picture symbolizing resilience"
                             class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                             onerror="this.onerror=null;this.src='https://placehold.co/400x250/f472b6/ffffff?text=M+7+Challenge'">
                    </div>
                </section>
                
                <!-- 9. Her Hobbies/Passions -->
                <section class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal">
                    <div class="shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                        <!-- Image source updated to T.png --><img src="T.png" 
                             alt="Placeholder for a picture of her pursuing a passion or hobby"
                             class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                             onerror="this.onerror=null;this.src='https://placehold.co/400x250/f472b6/ffffff?text=M+8+Hobbies'">
                    </div>
                    <div class="space-y-6">
                        <h3 class="text-4xl font-bold">The Things You Love</h3>
                        <p class="text-lg">
                            Watching you immerse yourself in [Mention a specific hobby, e.g., painting, reading, hiking] is a beautiful thing. That focused energy, the dedication, and the genuine excitement you bring to the things you care about is intoxicating. I love that I get to be a part of your world.
                        </p>
                        <p class="text-sm italic">
                            A picture of you doing what you love.
                        </p>
                    </div>
                </section>

                <!-- 10. Future Dreams -->
                <section class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal">
                    <div class="order-2 md:order-1 space-y-6">
                        <h3 class="text-4xl font-bold">A Glimpse of Our Future</h3>
                        <p class="text-lg">
                            I love talking to you about the future. It doesn't matter if we're planning a trip next year or just laughing about what we'll be like when we're old; every dream we share feels tangible and exciting. You make me excited for tomorrow.
                        </p>
                        <p class="text-sm italic">
                            A scenic or aspirational photo that feels like our future.
                        </p>
                    </div>
                    <div class="order-1 md:order-2 shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                        <!-- Image source updated to T.png --><img src="T.png" 
                             alt="Placeholder for a picture symbolizing shared future dreams"
                             class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                             onerror="this.onerror=null;this.src='https://placehold.co/400x250/f472b6/ffffff?text=M+9+Future'">
                    </div>
                </section>
                
                <!-- 11. Compliment: Humor -->
                <section class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal">
                    <div class="shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                        <!-- Image source updated to T.png --><img src="T.png" 
                             alt="Placeholder for a funny picture or a picture of us laughing"
                             class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                             onerror="this.onerror=null;this.src='https://placehold.co/400x250/f472b6/ffffff?text=M+10+Humor'">
                    </div>
                    <div class="space-y-6">
                        <h3 class="text-4xl font-bold">Your Sense of Humor</h3>
                        <p class="text-lg">
                            Honestly, your goofy side is one of my favorite things. You always know how to make me laugh, even when I'm having the worst day. Our inside jokes and ridiculous banter are the soundtracks to my happiness.
                        </p>
                        <p class="text-sm italic">
                            A picture that reminds me of our shared laughter.
                        </p>
                    </div>
                </section>

                <!-- 12. Comfort and Home -->
                <section class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal">
                    <div class="order-2 md:order-1 space-y-6">
                        <h3 class="text-4xl font-bold">Where I Feel at Home</h3>
                        <p class="text-lg">
                            Home isn't a place; it's being with you. Whether we are curled up on the couch or navigating a crowded room, your presence is the most comforting thing I know. You are my safe harbor.
                        </p>
                        <p class="text-sm italic">
                            A cozy photo of us together at home.
                        </p>
                    </div>
                    <div class="order-1 md:order-2 shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                        <!-- Image source updated to T.png --><img src="T.png" 
                             alt="Placeholder for a comfortable, cozy moment"
                             class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                             onerror="this.onerror=null;this.src='https://placehold.co/400x250/f472b6/ffffff?text=M+11+Home'">
                    </div>
                </section>

                <!-- 13. Compliment: Inner Strength -->
                <section class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal">
                    <div class="shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                        <!-- Image source updated to T.png --><img src="T.png" 
                             alt="Placeholder for an empowering or determined photo"
                             class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                             onerror="this.onerror=null;this.src='https://placehold.co/400x250/f472b6/ffffff?text=M+12+Strength'">
                    </div>
                    <div class="space-y-6">
                        <h3 class="text-4xl font-bold">The Strength in Your Character</h3>
                        <p class="text-lg">
                            You approach life with such grace and quiet determination. I admire your commitment to your values and the way you always strive to be your best self. It's a privilege to be on your team.
                        </p>
                        <p class="text-sm italic">
                            A photo that shows your inner resolve.
                        </p>
                    </div>
                </section>

                <!-- 14. Final Message & Signature -->
                <section class="reveal pt-4 pb-16">
                    <div class="max-w-4xl mx-auto p-10 md:p-16 rounded-3xl border-4 border-pink-200 shadow-2xl shadow-pink-300/50 text-center">
                        <h3 class="text-5xl md:text-6xl font-black text-pink-600 mb-6">Happy Six Months!</h3>
                        <p class="text-xl md:text-2xl text-gray-700 mb-8">
                            Every day with you is a gift I unwrap with joy. Thank you for being my everything. I love you more than words can say, and I can't wait to see what the rest of our lives holds.
                        </p>
                        <p class="text-3xl font-serif text-pink-700">
                            Forever Yours, Josiyah Perez
                        </p>
                    </div>
                </section>
            </main>
        
            <!-- Footer -->
            <footer class="text-center py-12 border-t border-gray-200">
                <p class="text-sm text-gray-500">&copy; 2025 Our Story. All moments reserved.</p>
            </footer>
        </div>

        <!-- 3. RIGHT PINK GUTTER (Hidden on smaller screens) -->
        <div class="pink-hearts-bg hidden lg:block"></div>
    </div>


    <!-- Secret Gallery Modal (Unchanged) -->
    <div id="secret-gallery-modal" class="hidden fixed inset-0 z-[100] bg-gray-900/95 backdrop-blur-md flex items-center justify-center p-4" onclick="closeSecretGallery()">
        <div class="absolute inset-0 z-0" onclick="event.stopPropagation()">
            <!-- Floating Images for Ambiance -->
            <img class="floating-image img-1" src="T.png" alt="Floating Image 1" onerror="this.onerror=null;this.src='https://placehold.co/250x150/f472b6/ffffff?text=M+1'">
            <img class="floating-image img-2" src="T.png" alt="Floating Image 2" onerror="this.onerror=null;this.src='https://placehold.co/300x200/f472b6/ffffff?text=M+2'">
            <img class="floating-image img-3" src="T.png" alt="Floating Image 3" onerror="this.onerror=null;this.src='https://placehold.co/200x250/f472b6/ffffff?text=M+3'">
            <img class="floating-image img-4" src="T.png" alt="Floating Image 4" onerror="this.onerror=null;this.src='https://placehold.co/280x180/f472b6/ffffff?text=M+4'">
            <img class="floating-image img-5" src="T.png" alt="Floating Image 5" onerror="this.onerror=null;this.src='https://placehold.co/180x280/f472b6/ffffff?text=M+5'">
            <img class="floating-image img-6" src="T.png" alt="Floating Image 6" onerror="this.onerror=null;this.src='https://placehold.co/220x220/f472b6/ffffff?text=M+6'">
        </div>
        
        <div id="secret-gallery" class="relative z-10 max-w-4xl mx-auto text-center p-10 bg-white/10 rounded-3xl shadow-2xl border border-pink-400/50">
            <h2 class="text-5xl font-extrabold text-white mb-6 tracking-tight">Gallery Access Denied.</h2>
            <p class="text-xl text-pink-200 mb-8">
                This area is for our eyes only. You'll need the secret code!
            </p>
            <input type="password" id="secret-code-input" placeholder="Enter Secret Code" class="p-3 w-64 rounded-full text-center text-gray-800 bg-white focus:ring-4 focus:ring-pink-500 focus:outline-none transition duration-300">
            <button onclick="checkSecretCode()" class="mt-4 md:mt-0 md:ml-4 header-btn px-6 py-3 text-lg font-semibold rounded-full bg-pink-600 text-white shadow-xl hover:bg-pink-700 transition duration-300">
                Unlock
            </button>
            <p id="gallery-message" class="mt-4 text-pink-300"></p>
        </div>
    </div>

    <!-- Dev Log Modal (Unchanged) -->
    <div id="dev-log-modal" class="hidden fixed inset-0 z-[100] bg-gray-900/95 backdrop-blur-md flex items-center justify-center p-4" onclick="closeDevLog()">
        <div class="bg-gray-800 rounded-xl max-w-2xl w-full p-8 shadow-2xl border border-indigo-500/50 space-y-4 relative" onclick="event.stopPropagation()">
            <h2 class="text-3xl font-bold text-indigo-400 border-b border-indigo-700 pb-2">Project Development Log</h2>
            <p class="text-gray-300 text-sm italic">Tracking the development of this website, just like tracking the development of our relationship.</p>
            <ul class="list-disc list-inside text-gray-400 space-y-2 text-left">
                <li><strong class="text-indigo-300">2025-11-29:</strong> Implemented the correct **vertical** layout: Pink Gutter | White Content | Pink Gutter, ensuring the text is always on a clean white background.</li>
                <li><strong class="text-indigo-200">2025-11-29:</strong> Adjusted the layout based on horizontal scroll instruction, using white cards on pink backgrounds. (Superseded by current layout).</li>
                <li><strong class="text-indigo-300">2025-11-28:</strong> Added the Secret Gallery Modal (hidden behind a code) and the floating image effect using CSS keyframe animations.</li>
                <li><strong class="text-indigo-300">2025-11-27:</strong> Scaffolding complete with Header, Scroll Animations, and 12 core memory sections. Image placeholders added.</li>
                <li><strong class="text-indigo-300">2025-11-26:</strong> Initial concept design completed: Luxury, romantic, dark theme with pink accents.</li>
            </ul>
            <button onclick="closeDevLog()" class="absolute top-3 right-3 text-gray-400 hover:text-white transition">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="18" y1="6" x2="6" y2="18"></line><line x1="6" y1="6" x2="18" y2="18"></line></svg>
            </button>
        </div>
    </div>

    <script>
        // --- SCROLL REVEAL LOGIC ---
        function reveal() {
            var reveals = document.querySelectorAll(".reveal");
            for (var i = 0; i < reveals.length; i++) {
                var windowHeight = window.innerHeight;
                var elementTop = reveals[i].getBoundingClientRect().top;
                var elementVisible = 150; 
                
                // Only show if the element is above the bottom of the viewport (minus buffer)
                if (elementTop < windowHeight - elementVisible) {
                    reveals[i].classList.add("visible");
                } else {
                    reveals[i].classList.remove("visible");
                }
            }
        }
        window.addEventListener("scroll", reveal);
        window.addEventListener("load", reveal); // Run on load to reveal initial elements

        // --- MODAL LOGIC ---
        const galleryModal = document.getElementById('secret-gallery-modal');
        const devLogModal = document.getElementById('dev-log-modal');
        const galleryBtn = document.getElementById('secret-gallery-btn');
        const devLogBtn = document.getElementById('dev-log-btn');
        const galleryMessage = document.getElementById('gallery-message');

        galleryBtn.onclick = () => galleryModal.classList.remove('hidden');
        devLogBtn.onclick = () => devLogModal.classList.remove('hidden');

        function closeSecretGallery() {
            galleryModal.classList.add('hidden');
            galleryMessage.textContent = ''; // Clear message on close
        }

        function closeDevLog() {
            devLogModal.classList.add('hidden');
        }

        function checkSecretCode() {
            const input = document.getElementById('secret-code-input').value.toLowerCase().trim();
            const correctCode = "120125"; // Dec 7th, 2025
            
            if (input === correctCode) {
                galleryMessage.textContent = "Welcome back, my love. Gallery unlocked!";
                // In a real app, this is where you'd redirect or dynamically load a private gallery
                // For this example, we just update the text of the modal itself to simulate access.
                setTimeout(() => {
                    const galleryContent = document.getElementById('secret-gallery');
                    galleryContent.innerHTML = `
                        <h2 class="text-5xl font-extrabold text-pink-400 mb-6 tracking-tight">The Unlocked Vault</h2>
                        <p class="text-xl text-white mb-8">
                            This is where all our most precious, silly, and wonderful photos go.
                            Since I can't load real images, imagine a beautiful, scrolling wall of polaroids here.
                        </p>
                        <p class="text-2xl text-pink-300">
                            I love every single one of these memories.
                        </p>
                        <button onclick="closeSecretGallery()" class="mt-8 header-btn px-6 py-3 text-lg font-semibold rounded-full bg-pink-600 text-white shadow-xl hover:bg-pink-700 transition duration-300">
                            Close Vault
                        </button>
                    `;
                }, 1000);
            } else {
                galleryMessage.textContent = "Incorrect code. Try again, sweetheart!";
            }
        }
    </script>
</body>
</html>
