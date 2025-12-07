<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Six Months & Forever</title>
    <!-- Load Tailwind CSS --><script src="https://cdn.tailwindcss.com"></script>
    <!-- Use Inter and Playfair Display fonts --><link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&family=Playfair+Display:ital,wght@0,400..900;1,400..900&display=swap" rel="stylesheet">
    <style>
        /* Custom styles for a modern, elegant feel */
        body {
            font-family: 'Inter', sans-serif;
            background-color: #1e293b; /* Dark Slate Background */
            color: #f1f5f9; /* Light text for the body */
            overflow-x: hidden;
            scroll-behavior: smooth;
        }

        /* Subtle scroll animation */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 1.2s cubic-bezier(0.25, 0.46, 0.45, 0.94), transform 1s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }
        .reveal.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Custom gradient for the hero section title */
        .hero-title {
            /* Vibrant Fuchsia/Rose Gradient */
            background-image: linear-gradient(45deg, #e879f9, #f43f5e, #f0abfc);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-family: 'Playfair Display', serif; 
            letter-spacing: -0.05em; /* Tighten kerning for large title */
        }
        
        /* Countdown Box Style (Dark theme component) */
        .counter-box {
            background-color: #334155; /* Dark Slate Blue */
            border: 1px solid #64748b;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            color: #f0f9ff;
        }
        .counter-value {
            font-family: 'Playfair Display', serif;
            color: #f0abfc; /* Light Fuchsia */
            text-shadow: 0 0 8px rgba(240, 171, 252, 0.7);
        }

        /* Main Content Area Styling (The "Paper" Block) */
        .center-content-area { 
            background-color: #ffffff; /* Crisp White */
            color: #1e293b; /* Dark text */
            box-shadow: 0 0 50px rgba(0, 0, 0, 0.3); /* Stronger boundary shadow */
            max-width: 800px; /* Constrain width for better readability */
            margin: 0 auto;
        }
        .center-content-area h3 { 
            color: #9d174d; /* Deep Pink/Berry for section titles */
            font-family: 'Playfair Display', serif;
            font-weight: 700;
        } 

        /* Memory Card Styling */
        .memory-card {
            border: 1px solid #fce7f3;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            transition: all 0.5s cubic-bezier(0.19, 1, 0.22, 1);
        }
        .memory-card:hover {
            box-shadow: 0 15px 35px rgba(244, 63, 94, 0.2), 0 5px 15px rgba(0, 0, 0, 0.1);
            transform: translateY(-5px) rotate(-0.5deg);
        }

        /* --- BACKGROUND FLOATING IMAGE STYLES --- */
        
        /* Moved keyframes from JS to here to fix security error */
        @keyframes float-x-1 { 0% { transform: translateX(0); } 50% { transform: translateX(100px); } 100% { transform: translateX(0); } }
        @keyframes float-y-1 { 0% { transform: translateY(0); } 50% { transform: translateY(50px) rotate(2deg); } 100% { transform: translateY(0); } }
        
        @keyframes float-x-2 { 0% { transform: translateX(0); } 50% { transform: translateX(-100px); } 100% { transform: translateX(0); } }
        @keyframes float-y-2 { 0% { transform: translateY(0); } 50% { transform: translateY(-50px) rotate(-2deg); } 100% { transform: translateY(0); } }

        @keyframes float-x-3 { 0% { transform: translateX(0); } 50% { transform: translateX(120px); } 100% { transform: translateX(0); } }
        @keyframes float-y-3 { 0% { transform: translateY(0); } 50% { transform: translateY(60px) rotate(1deg); } 100% { transform: translateY(0); } }

        @keyframes float-x-4 { 0% { transform: translateX(0); } 50% { transform: translateX(-120px); } 100% { transform: translateX(0); } }
        @keyframes float-y-4 { 0% { transform: translateY(0); } 50% { transform: translateY(-60px) rotate(-3deg); } 100% { transform: translateY(0); } }

        .floating-image {
            position: fixed; 
            opacity: 0.05; /* Even more subtle */
            border-radius: 1rem;
            filter: saturate(1.2) blur(4px); 
            z-index: 0;
            pointer-events: none; 
        }

        @media (max-width: 1024px) {
            .floating-image { display: none; }
        }
        /* --- END BACKGROUND STYLES --- */
    </style>
</head>
<body>
    
    <!-- Floating Images for Ambiance -->
    <img class="floating-image img-1" src="1.png" alt="Floating Image 1" style="top: 5%; left: 10%; width: 250px; animation: float-x-1 15s ease-in-out infinite alternate, float-y-1 20s ease-in-out infinite alternate;" onerror="this.onerror=null;this.src='https://placehold.co/250x150/f0abfc/1e293b?text=M+1'">
    <img class="floating-image img-2" src="2.png" alt="Floating Image 2" style="top: 20%; right: 5%; width: 300px; animation: float-x-2 18s ease-in-out infinite alternate, float-y-2 25s ease-in-out infinite alternate;" onerror="this.onerror=null;this.src='https://placehold.co/300x200/f0abfc/1e293b?text=M+2'">
    <img class="floating-image img-3" src="3.png" alt="Floating Image 3" style="bottom: 15%; left: 5%; width: 200px; animation: float-x-3 12s ease-in-out infinite alternate, float-y-3 17s ease-in-out infinite alternate;" onerror="this.onerror=null;this.src='https://placehold.co/200x250/f0abfc/1e293b?text=M+3'">
    <img class="floating-image img-4" src="4.png" alt="Floating Image 4" style="bottom: 5%; right: 20%; width: 280px; animation: float-x-4 22s ease-in-out infinite alternate, float-y-4 14s ease-in-out infinite alternate;" onerror="this.onerror=null;this.src='https://placehold.co/280x180/f0abfc/1e293b?text=M+4'">

    <!-- Header (Sticky and Dark/Slightly Transparent) -->
    <header class="sticky top-0 z-50 p-4 bg-slate-900/90 backdrop-blur-sm shadow-xl shadow-fuchsia-900/50">
        <div class="max-w-4xl mx-auto flex justify-center items-center">
            <h1 class="text-xl md:text-2xl font-extrabold text-fuchsia-300 tracking-widest transition duration-500">SIX MONTHS OF US</h1>
        </div>
    </header>

    <!-- MAIN CONTENT COLUMN (Center aligned on dark background) -->
    <div class="py-12 md:py-20 relative z-10">
        
        <div class="center-content-area mx-4 md:mx-auto rounded-xl">
            <main class="max-w-4xl mx-auto py-12 md:py-20 space-y-16 md:space-y-24 px-6 md:px-12">

                <!-- 1. Hero Section -->
                <section class="text-center reveal p-4 md:p-8">
                    <!-- Date updated to Dec. 7th, 2025 -->
                    <p class="text-lg md:text-xl font-semibold text-fuchsia-500 mb-4 tracking-widest uppercase">Dec. 7th, 2025</p>
                    <h2 class="text-6xl md:text-8xl font-black hero-title leading-none md:leading-tight">
                        Our Story So Far...
                    </h2>
                    <p class="mt-8 text-xl md:text-2xl max-w-3xl mx-auto text-slate-700">
                        Six months ago was just the start of our official journey, but my heart has been yours for three years now. This is a tribute to the most beautiful, brilliant, and kind person I know.
                    </p>
                    <svg class="mx-auto mt-12 animate-bounce text-fuchsia-600" xmlns="http://www.w3.org/2000/svg" width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 5v14M19 12l-7 7-7-7"/></svg>
                </section>
                
                <!-- 2. Live Counter Section -->
                <section class="text-center reveal max-w-2xl mx-auto">
                    <div class="p-6 md:p-8 rounded-2xl counter-box shadow-xl">
                        <h2 id="counter-title" class="text-2xl md:text-3xl font-bold mb-6 font-serif text-fuchsia-200">
                            Counting Down To Forever...
                        </h2>
                        <div id="countdown-timer" class="grid grid-cols-2 md:grid-cols-4 gap-4 md:gap-6">
                            <div class="p-3 rounded-lg bg-slate-700/50">
                                <div id="days" class="counter-value text-3xl md:text-5xl font-extrabold">00</div>
                                <div class="text-xs md:text-sm text-slate-300 mt-1 uppercase tracking-wider">Days</div>
                            </div>
                            <div class="p-3 rounded-lg bg-slate-700/50">
                                <div id="hours" class="counter-value text-3xl md:text-5xl font-extrabold">00</div>
                                <div class="text-xs md:text-sm text-slate-300 mt-1 uppercase tracking-wider">Hours</div>
                            </div>
                            <div class="p-3 rounded-lg bg-slate-700/50">
                                <div id="minutes" class="counter-value text-3xl md:text-5xl font-extrabold">00</div>
                                <div class="text-xs md:text-sm text-slate-300 mt-1 uppercase tracking-wider">Minutes</div>
                            </div>
                            <div class="p-3 rounded-lg bg-slate-700/50">
                                <div id="seconds" class="counter-value text-3xl md:text-5xl font-extrabold">00</div>
                                <div class="text-xs md:text-sm text-slate-300 mt-1 uppercase tracking-wider">Seconds</div>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- 3. Our Song / Playlist Section -->
                <section class="reveal border-b border-t border-fuchsia-100 py-10 md:py-14 max-w-3xl mx-auto text-center">
                    <h3 class="text-3xl md:text-4xl font-bold mb-6">Our Song: "we fell in love in october"</h3>
                    <p class="text-lg italic font-serif text-slate-600 mb-6">
                        This song captures the hidden feeling I had for you since the beginning. The moment I realized I was secretly falling for my best friend's amazing cousin.
                    </p>
                    <a href="https://open.spotify.com/album/7vud0sY43VTv28MbWiglDa" target="_blank" class="inline-flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-full text-white bg-fuchsia-600 hover:bg-fuchsia-700 md:py-4 md:text-lg md:px-10 shadow-lg transition duration-300 transform hover:scale-105">
                        <svg class="w-6 h-6 mr-3" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm3.32 15.65a.49.49 0 01-.6-.18c-.97-1.18-2.45-1.55-4.22-1.28-1.56.24-2.86.84-3.56 1.48a.49.49 0 01-.63-.23.5.5 0 01.19-.66c.8-.73 2.25-1.35 3.96-1.61 2.1-.31 3.8-.1 5.06 1.48a.5.5 0 01-.19.66zM15.4 14.5a.49.49 0 01-.6-.22c-.9-1.2-2.3-1.65-4.04-1.39-1.5.22-2.73.78-3.39 1.37a.49.49 0 01-.63-.25.5.5 0 01.21-.65c.7-.6 2.05-1.2 3.78-1.44 2.1-.3 3.8-.08 5.05 1.54a.5.5 0 01-.21.64zM16.14 13.43a.5.5 0 01-.61-.25c-.75-1.1-1.9-1.65-3.4-1.89-1.5-.24-2.8.2-3.5.83a.5.5 0 01-.61-.25.5.5 0 01.25-.6c.8-.75 2.1-1.2 3.6-1.39 1.6-.19 3 .2 4.1 1.7a.5.5 0 01-.25.65z"/></svg>
                        Listen to The Song
                    </a>
                </section>
                
                <!-- 4. Memory Gallery -->
                <section class="space-y-16">
                    <h2 class="text-center text-5xl font-black text-rose-500 font-serif reveal">Our Shared Memories</h2>

                    <!-- Memory: The Scold (Image 1.png) -->
                    <div class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal pt-10 border-t border-fuchsia-100">
                        <div class="order-2 md:order-1 space-y-6">
                            <h3 class="text-3xl font-bold">The Scold (My Favorite View)</h3>
                            <p class="text-lg text-slate-700">
                                You pretend to scold me, but since you're so much shorter, you have to look all the way up. It's the cutest thing in the world, and honestly, I wouldn't trade that view for anything.
                            </p>
                            <p class="text-sm italic text-slate-500">
                                A snapshot of your fierce, adorable side.
                            </p>
                        </div>
                        <div class="order-1 md:order-2 rounded-2xl overflow-hidden memory-card">
                            <!-- Image 1.png -->
                            <img src="1.png" 
                                alt="Picture of her looking up while pretend scolding"
                                class="w-full h-auto object-cover aspect-[4/3]"
                                onerror="this.onerror=null;this.src='https://placehold.co/400x300/f43f5e/ffffff?text=M+1+Scold'">
                        </div>
                    </div>

                    <!-- Memory: Matching PJs & Gifts (Image 2.png) -->
                    <div class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal pt-10 border-t border-fuchsia-100">
                        <div class="rounded-2xl overflow-hidden memory-card">
                            <!-- Image 2.png -->
                            <img src="2.png" 
                                alt="Picture of us in matching PJs holding a gift"
                                class="w-full h-auto object-cover aspect-[4/3]"
                                onerror="this.onerror=null;this.src='https://placehold.co/400x300/f43f5e/ffffff?text=M+2+PJs'">
                        </div>
                        <div class="space-y-6">
                            <h3 class="text-3xl font-bold">Matching PJs & Gifts</h3>
                            <p class="text-lg text-slate-700">
                                Remember giving you that gift and us immediately taking a picture in our ridiculously comfortable, matching PJs? It’s a perfect snapshot of our happy, cozy life together.
                            </p>
                            <p class="text-sm italic text-slate-500">
                                A picture that captures your amazing spirit.
                            </p>
                        </div>
                    </div>

                    <!-- Memory: Your Always Perfect Smile (Image 3.png) -->
                    <div class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal pt-10 border-t border-fuchsia-100">
                        <div class="order-2 md:order-1 space-y-6">
                            <h3 class="text-3xl font-bold">Your Always Perfect Smile</h3>
                            <p class="text-lg text-slate-700">
                                This picture captures that beautiful, bright, infectious smile of yours perfectly. It’s the energy and light you bring into my life every single day.
                            </p>
                            <p class="text-sm italic text-slate-500">
                                A beautiful memory of one of our best days.
                            </p>
                        </div>
                        <div class="order-1 md:order-2 rounded-2xl overflow-hidden memory-card">
                            <!-- Image 3.png -->
                            <img src="3.png" 
                                alt="A close-up picture of her beautiful smile"
                                class="w-full h-auto object-cover aspect-[4/3]"
                                onerror="this.onerror=null;this.src='https://placehold.co/400x300/f43f5e/ffffff?text=M+3+Smile'">
                        </div>
                    </div>
                    
                    <!-- Memory: Cheer Captain Stunner (Image 4.png) -->
                    <div class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal pt-10 border-t border-fuchsia-100">
                        <div class="rounded-2xl overflow-hidden memory-card">
                            <!-- Image 4.png -->
                            <img src="4.png" 
                                alt="A picture of us where she is in her cheer captain uniform"
                                class="w-full h-auto object-cover aspect-[4/3]"
                                onerror="this.onerror=null;this.src='https://placehold.co/400x300/f43f5e/ffffff?text=M+4+Cheer'">
                        </div>
                        <div class="space-y-6">
                            <h3 class="text-3xl font-bold">Cheer Captain Stunner (My Favorite)</h3>
                            <p class="text-lg text-slate-700">
                                This is my favorite photo of us because we both just look amazing, especially you in your cheer captain uniform. You truly own every room you walk into.
                            </p>
                            <p class="text-sm italic text-slate-500">
                                A moment of deep connection.
                            </p>
                        </div>
                    </div>

                    <!-- Memory: 4th of July (on the 5th!) (Image 5.png) -->
                    <div class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal pt-10 border-t border-fuchsia-100">
                        <div class="order-2 md:order-1 space-y-6">
                            <h3 class="text-3xl font-bold">4th of July (on the 5th!)</h3>
                            <p class="text-lg text-slate-700">
                                Your favorite pic from that 4th of July party, even though we ended up taking it on the 5th. It was a chaotic, beautiful weekend, just like our lives—in the best way.
                            </p>
                            <p class="text-sm italic text-slate-500">
                                A photo from our best date.
                            </p>
                        </div>
                        <div class="order-1 md:order-2 rounded-2xl overflow-hidden memory-card">
                            <!-- Image 5.png -->
                            <img src="5.png" 
                                alt="A favorite memory from our 4th of July party"
                                class="w-full h-auto object-cover aspect-[4/3]"
                                onerror="this.onerror=null;this.src='https://placehold.co/400x300/f43f5e/ffffff?text=M+5+4th'">
                        </div>
                    </div>

                    <!-- Memory: The "Steamy Movie" Afterglow (Image 6.png) -->
                    <div class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal pt-10 border-t border-fuchsia-100">
                        <div class="rounded-2xl overflow-hidden memory-card">
                            <!-- Image 6.png -->
                            <img src="6.png" 
                                alt="Picture of her smiling after a steamy movie"
                                class="w-full h-auto object-cover aspect-[4/3]"
                                onerror="this.onerror=null;this.src='https://placehold.co/400x300/f43f5e/ffffff?text=M+6+Movie'">
                        </div>
                        <div class="space-y-6">
                            <h3 class="text-3xl font-bold">The "Steamy Movie" Afterglow</h3>
                            <p class="text-lg text-slate-700">
                                Just after that... uh... "steamy movie," you were glowing and smiling like this. It's a reminder of all the good times, and how easily you make me blush.
                            </p>
                            <p class="text-sm italic text-slate-500">
                                A picture from a moment of focused thought or achievement.
                            </p>
                        </div>
                    </div>

                    <!-- Memory: The Birthday PJs (Your Gift to Me) (Image 7.png) -->
                    <div class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal pt-10 border-t border-fuchsia-100">
                        <div class="order-2 md:order-1 space-y-6">
                            <h3 class="text-3xl font-bold">The Birthday PJs (Your Gift to Me)</h3>
                            <p class="text-lg text-slate-700">
                                This is a picture of the incredible birthday gift you gave me—a photo of us in our matching PJs. It’s the thoughtfulness behind your gifts that means the most.
                            </p>
                            <p class="text-sm italic text-slate-500">
                                A memory of us being there for each other.
                            </p>
                        </div>
                        <div class="order-1 md:order-2 rounded-2xl overflow-hidden memory-card">
                            <!-- Image 7.png -->
                            <img src="7.png" 
                                alt="Picture of the gift she gave me on my birthday"
                                class="w-full h-auto object-cover aspect-[4/3]"
                                onerror="this.onerror=null;this.src='https://placehold.co/400x300/f43f5e/ffffff?text=M+7+Gift'">
                        </div>
                    </div>

                    <!-- Memory: The Stunning Student (Image 8.png) -->
                    <div class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal pt-10 border-t border-fuchsia-100">
                        <div class="rounded-2xl overflow-hidden memory-card">
                            <!-- Image 8.png -->
                            <img src="8.png" 
                                alt="Picture of her and her teacher where she looks beautiful"
                                class="w-full h-auto object-cover aspect-[4/3]"
                                onerror="this.onerror=null;this.src='https://placehold.co/400x300/f43f5e/ffffff?text=M+8+Teacher'">
                        </div>
                        <div class="space-y-6">
                            <h3 class="text-3xl font-bold">The Stunning Student</h3>
                            <p class="text-lg text-slate-700">
                                A picture with your teacher, but seriously, you look so so pretty in this one. It perfectly captures your grace and professionalism while still showcasing your incredible beauty.
                            </p>
                            <p class="text-sm italic text-slate-500">
                                A picture of you doing what you love.
                            </p>
                        </div>
                    </div>

                    <!-- Memory: Another Gorgeous Smile (Image 9.png) -->
                    <div class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal pt-10 border-t border-fuchsia-100">
                        <div class="order-2 md:order-1 space-y-6">
                            <h3 class="text-3xl font-bold">Another Gorgeous Smile</h3>
                            <p class="text-lg text-slate-700">
                                I can never have too many photos of you smiling. This one is another favorite—pure, happy, and just you.
                            </p>
                            <p class="text-sm italic text-slate-500">
                                A scenic or aspirational photo that feels like our future.
                            </p>
                        </div>
                        <div class="order-1 md:order-2 rounded-2xl overflow-hidden memory-card">
                            <!-- Image 9.png -->
                            <img src="9.png" 
                                alt="Another picture of her smiling"
                                class="w-full h-auto object-cover aspect-[4/3]"
                                onerror="this.onerror=null;this.src='https://placehold.co/400x300/f43f5e/ffffff?text=M+9+Smile+2'">
                        </div>
                    </div>
                    
                    <!-- Memory: Our Sweetest Moment (Image 10.png) -->
                    <div class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal pt-10 border-t border-fuchsia-100">
                        <div class="rounded-2xl overflow-hidden memory-card">
                            <!-- Image 10.png -->
                            <img src="10.png" 
                                alt="Picture of us kissing"
                                class="w-full h-auto object-cover aspect-[4/3]"
                                onerror="this.onerror=null;this.src='https://placehold.co/400x300/f43f5e/ffffff?text=M+10+Kiss'">
                        </div>
                        <div class="space-y-6">
                            <h3 class="text-3xl font-bold">Our Sweetest Moment</h3>
                            <p class="text-lg text-slate-700">
                                I love this picture of us kissing. It encapsulates all the love, trust, and connection we share in a single, perfect moment.
                            </p>
                            <p class="text-sm italic text-slate-500">
                                A picture that reminds me of our shared laughter.
                            </p>
                        </div>
                    </div>

                    <!-- Memory: Car Ride & Gift Excitement (Image 11.png) -->
                    <div class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal pt-10 border-t border-fuchsia-100">
                        <div class="order-2 md:order-1 space-y-6">
                            <h3 class="text-3xl font-bold">Car Ride & Gift Excitement</h3>
                            <p class="text-lg text-slate-700">
                                You in the car, holding your gift, and that genuine, happy smile. It reminds me how much joy I get from seeing you happy.
                            </p>
                            <p class="text-sm italic text-slate-500">
                                A cozy photo of us together at home.
                            </p>
                        </div>
                        <div class="order-1 md:order-2 rounded-2xl overflow-hidden memory-card">
                            <!-- Image 11.png -->
                            <img src="11.png" 
                                alt="Picture of her in the car holding her gift"
                                class="w-full h-auto object-cover aspect-[4/3]"
                                onerror="this.onerror=null;this.src='https://placehold.co/400x300/f43f5e/ffffff?text=M+11+Car+Gift'">
                        </div>
                    </div>

                    <!-- Memory: Billie Eilish Vibe (Image 12.png) -->
                    <div class="grid md:grid-cols-2 gap-8 md:gap-12 items-center reveal pt-10 border-t border-fuchsia-100">
                        <div class="rounded-2xl overflow-hidden memory-card">
                            <!-- Image 12.png -->
                            <img src="12.png" 
                                alt="Picture of her at the Billie Eilish concert"
                                class="w-full h-auto object-cover aspect-[4/3]"
                                onerror="this.onerror=null;this.src='https://placehold.co/400x300/f43f5e/ffffff?text=M+12+Concert'">
                        </div>
                        <div class="space-y-6">
                            <h3 class="text-3xl font-bold">Billie Eilish Vibe</h3>
                            <p class="text-lg text-slate-700">
                                You at the Billie Eilish concert, completely lost in the moment. Your excitement is contagious, and I love watching you enjoy the things you're passionate about.
                            </p>
                            <p class="text-sm italic text-slate-500">
                                A photo that shows your inner resolve.
                            </p>
                        </div>
                    </div>

                </section>

                <!-- 5. Final Message & Signature -->
                <section class="reveal pt-16 pb-20">
                    <div class="max-w-4xl mx-auto p-10 md:p-16 rounded-3xl border-4 border-fuchsia-300/50 bg-slate-50 shadow-2xl shadow-fuchsia-400/50 text-center">
                        <h3 class="text-4xl md:text-5xl font-black text-rose-700 mb-6 font-serif">Happy Six Months!</h3>
                        <p class="text-lg md:text-xl text-slate-700 mb-8">
                            Every day with you is a gift I unwrap with joy. Thank you for being my everything. I love you more than words can say, and I can't wait to see what the rest of our lives holds.
                        </p>
                        <!-- Name is Josiyah -->
                        <p class="text-3xl font-serif italic text-fuchsia-800">
                            — Forever Yours, Josiyah
                        </p>
                    </div>
                </section>
            </main>
        
            <!-- Footer -->
            <footer class="text-center py-8 border-t border-fuchsia-100 bg-slate-100">
                <p class="text-sm text-slate-500">&copy; 2025 Our Story. All moments reserved.</p>
            </footer>
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
                
                if (elementTop < windowHeight - elementVisible) {
                    reveals[i].classList.add("visible");
                } else {
                    // Optional: remove visible class when scrolling back up
                    // reveals[i].classList.remove("visible"); 
                }
            }
        }
        window.addEventListener("scroll", reveal);
        window.addEventListener("load", reveal); 


        // --- ANNIVERSARY COUNTER LOGIC ---
        
        // IMPORTANT: Set the exact start date/time of your 6-month relationship!
        // If your anniversary is Dec 7th, 2025, your start date was June 7th, 2025.
        // Format: Date(Year, Month Index (0=Jan), Day, Hour, Minute, Second)
        const startDate = new Date(2025, 5, 7, 0, 0, 0); // June 7th, 2025 at midnight

        // Target Anniversary Date (Dec 7th, 2025)
        const anniversaryDate = new Date(2025, 11, 7, 0, 0, 0); // December 7th, 2025 at midnight

        const titleEl = document.getElementById('counter-title');
        const daysEl = document.getElementById('days');
        const hoursEl = document.getElementById('hours');
        const minutesEl = document.getElementById('minutes');
        const secondsEl = document.getElementById('seconds');

        function updateCounter() {
            const now = new Date().getTime();
            
            const isAnniversaryPassed = now >= anniversaryDate.getTime();
            
            let timeDifferenceMs;
            let counterTitleText;

            if (!isAnniversaryPassed) {
                // COUNTDOWN
                timeDifferenceMs = anniversaryDate.getTime() - now;
                counterTitleText = "Counting Down To Our 6 Months...";
                
                if (timeDifferenceMs <= 0) {
                    // Stop counting down and switch to count up immediately if interval is close to zero
                    setTimeout(updateCounter, 10); 
                    return; 
                }
            } else {
                // COUNT-UP
                timeDifferenceMs = now - startDate.getTime();
                counterTitleText = "Time We've Spent Together!";
            }
            
            const totalSeconds = Math.floor(timeDifferenceMs / 1000);
            const totalMinutes = Math.floor(totalSeconds / 60);
            const totalHours = Math.floor(totalMinutes / 60);
            
            // Time breakdown
            const days = Math.floor(totalHours / 24);
            const hours = totalHours % 24;
            const minutes = totalMinutes % 60;
            const seconds = totalSeconds % 60;
            
            // Display logic
            // Added comma separator for large numbers of days
            daysEl.textContent = String(days).replace(/\B(?=(\d{3})+(?!\d))/g, ","); 
            hoursEl.textContent = String(hours).padStart(2, '0');
            minutesEl.textContent = String(minutes).padStart(2, '0');
            secondsEl.textContent = String(seconds).padStart(2, '0');

            titleEl.textContent = counterTitleText;
        }

        // Run the function immediately and then every second
        window.onload = function() {
            updateCounter();
            setInterval(updateCounter, 1000);
            reveal(); 
        }

        // NOTE: The previous code that attempted to inject keyframes into a remote stylesheet via JavaScript was removed
        // and the keyframes were moved to the inline <style> block to resolve the SecurityError.
    </script>
</body>
</html>
