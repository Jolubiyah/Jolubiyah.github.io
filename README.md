<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Six Months & Forever</title>
    <!-- Load Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Use Inter font family -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap" rel="stylesheet">
    <style>
        /* Custom styles for the luxury feel */
        body {
            font-family: 'Inter', sans-serif;
            background-color: #0d1117; /* Darker than default gray for luxury feel */
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
        
        /* Custom gradient for the hero section text */
        .hero-title {
            background-image: linear-gradient(45deg, #fecaca, #f472b6, #e879f9); /* Light pink to magenta */
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

        /* --- SECRET GALLERY ANIMATION STYLES --- */
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

        .floating-image {
            position: absolute;
            opacity: 0.8;
            border-radius: 0.75rem; /* rounded-xl */
            box-shadow: 0 25px 50px -12px rgba(236, 72, 153, 0.5); /* shadow-2xl pink */
            animation-iteration-count: infinite;
            animation-direction: alternate;
            filter: saturate(1.1);
        }

        .img-1 { top: 5%; left: 10%; width: 250px; animation: float-x-1 15s ease-in-out infinite alternate, float-y-1 20s ease-in-out infinite alternate; }
        .img-2 { top: 20%; right: 5%; width: 300px; animation: float-x-2 18s ease-in-out infinite alternate, float-y-2 25s ease-in-out infinite alternate; }
        .img-3 { bottom: 15%; left: 5%; width: 200px; animation: float-x-3 12s ease-in-out infinite alternate, float-y-3 17s ease-in-out infinite alternate; }
        .img-4 { bottom: 5%; right: 20%; width: 280px; animation: float-x-4 22s ease-in-out infinite alternate, float-y-4 14s ease-in-out infinite alternate; }
        .img-5 { top: 35%; left: 30%; width: 180px; animation: float-x-5 16s ease-in-out infinite alternate, float-y-5 21s ease-in-out infinite alternate; }
        .img-6 { bottom: 30%; right: 40%; width: 220px; animation: float-x-1 14s ease-in-out infinite alternate reverse, float-y-2 19s ease-in-out infinite alternate reverse; }

        @media (max-width: 768px) {
            .floating-image { display: none; } /* Hide complex animations on mobile for performance/simplicity */
            #secret-gallery h2 { font-size: 3rem; }
        }
        /* --- END GALLERY STYLES --- */
    </style>
</head>
<body class="text-gray-100">

    <!-- Header & Action Buttons -->
    <header class="sticky top-0 z-50 p-4 bg-gray-900/90 backdrop-blur-sm shadow-xl">
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

    <!-- Main Content Container -->
    <main class="max-w-6xl mx-auto py-12 md:py-24 space-y-32 md:space-y-48">

        <!-- 1. Hero Section -->
        <section class="text-center px-4 pt-16 reveal">
            <p class="text-lg md:text-xl font-medium text-pink-400 mb-4 tracking-widest uppercase">Dec. 7th, 2025</p>
            <h2 class="text-6xl md:text-8xl font-black hero-title leading-tight">
                Our Story So Far...
            </h2>
            <p class="mt-8 text-xl md:text-2xl max-w-3xl mx-auto text-gray-300">
                Six months ago, you changed everything for the better. This is a small tribute to the most beautiful, brilliant, and kind person I know.
            </p>
            <svg class="mx-auto mt-12 animate-bounce text-pink-400" xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 5v14M19 12l-7 7-7-7"/></svg>
        </section>

        <!-- 2. First Memory: The Beginning -->
        <section class="grid md:grid-cols-2 gap-10 md:gap-20 items-center px-4 reveal">
            <div class="order-2 md:order-1 space-y-6">
                <h3 class="text-4xl font-bold text-pink-400">The Day We Met</h3>
                <p class="text-gray-300 text-lg">
                    I remember the first time I saw you. It felt like the world just clicked into place. Everything before that moment was monochrome, and suddenly, you were the vibrant splash of color I never knew I was missing. It wasn't just fate; it was the start of my favorite adventure.
                </p>
                <p class="text-sm italic text-gray-500">
                    A snapshot from the very start of our journey.
                </p>
            </div>
            <div class="order-1 md:order-2 shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                <!-- Image source updated to T.png -->
                <img src="T.png" 
                     alt="Placeholder for the beginning of our relationship"
                     class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                     onerror="this.onerror=null;this.src='T.png'">
            </div>
        </section>

        <!-- 3. Second Memory: Her Spirit -->
        <section class="grid md:grid-cols-2 gap-10 md:gap-20 items-center px-4 reveal">
            <div class="shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                <!-- Image source updated to T.png -->
                <img src="T.png" 
                     alt="Placeholder for a picture of her smile"
                     class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                     onerror="this.onerror=null;this.src='T.png'">
            </div>
            <div class="space-y-6">
                <h3 class="text-4xl font-bold text-pink-400">The Power of Your Joy</h3>
                <p class="text-gray-300 text-lg">
                    Your smile is my favorite thing in the worldb it's genuine, infectious, and lights up every room. More than that, your kindness, resilience, and incredible passion for everything you do inspire me every single day. You are truly brilliant, and I'm so proud to watch you chase your dreams.
                </p>
                <p class="text-sm italic text-gray-500">
                    A picture that captures your amazing spirit.
                </p>
            </div>
        </section>

        <!-- 4. Third Memory: Adventures -->
        <section class="grid md:grid-cols-2 gap-10 md:gap-20 items-center px-4 reveal">
            <div class="order-2 md:order-1 space-y-6">
                <h3 class="text-4xl font-bold text-pink-400">Our Shared Adventures</h3>
                <p class="text-gray-300 text-lg">
                    From quiet nights watching movies to that chaotic weekend trip we took, every moment with you is an adventure. You make the mundane magical and the exciting unforgettable. Thank you for being my favorite co-pilot through all of life's twists and turns.
                </p>
                <p class="text-sm italic text-gray-500">
                    A beautiful memory of one of our best days.
                </p>
            </div>
            <div class="order-1 md:order-2 shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                <!-- Image source updated to T.png -->
                <img src="T.png" 
                     alt="Placeholder for an adventure we had together"
                     class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                     onerror="this.onerror=null;this.src='T.png'">
            </div>
        </section>
        
        <!-- 5. Her Empathy -->
        <section class="grid md:grid-cols-2 gap-10 md:gap-20 items-center px-4 reveal">
            <div class="shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                <!-- Image source updated to T.png -->
                <img src="T.png" 
                     alt="Placeholder for a moment of quiet reflection or caring"
                     class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                     onerror="this.onerror=null;this.src='T.png'">
            </div>
            <div class="space-y-6">
                <h3 class="text-4xl font-bold text-pink-400">The Depth of Your Empathy</h3>
                <p class="text-gray-300 text-lg">
                    The way you listen, truly listen, is a rare gift. You have this incredible ability to understand and support me without judgment. In a chaotic world, you are my calm, my confidante, and my most trusted advisor. Thank you for showing me what unconditional support feels like.
                </p>
                <p class="text-sm italic text-gray-500">
                    A moment of deep connection.
                </p>
            </div>
        </section>

        <!-- 6. Favorite Date Night -->
        <section class="grid md:grid-cols-2 gap-10 md:gap-20 items-center px-4 reveal">
            <div class="order-2 md:order-1 space-y-6">
                <h3 class="text-4xl font-bold text-pink-400">That One Date Night</h3>
                <p class="text-gray-300 text-lg">
                    Remember that night? It wasn't the place or the food, but the way we talked for hours until we realized everyone else had left. It’s those simple, genuine, time-stands-still moments that I cherish the most. Every date with you feels like the best one yet.
                </p>
                <p class="text-sm italic text-gray-500">
                    A photo from our best date.
                </p>
            </div>
            <div class="order-1 md:order-2 shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                <!-- Image source updated to T.png -->
                <img src="T.png" 
                     alt="Placeholder for a favorite date night memory"
                     class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                     onerror="this.onerror=null;this.src='T.png'">
            </div>
        </section>

        <!-- 7. Her Intelligence -->
        <section class="grid md:grid-cols-2 gap-10 md:gap-20 items-center px-4 reveal">
            <div class="shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                <!-- Image source updated to T.png -->
                <img src="T.png" 
                     alt="Placeholder for a picture showing her focused or achieving something"
                     class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                     onerror="this.onerror=null;this.src='T.png'">
            </div>
            <div class="space-y-6">
                <h3 class="text-4xl font-bold text-pink-400">Your Brilliant Mind</h3>
                <p class="text-gray-300 text-lg">
                    I love our conversations. Your perspective, your curiosity, and the sheer force of your intelligence are mesmerizing. You constantly challenge me to think deeper and better. Being with you means never being bored, and always learning something new.
                </p>
                <p class="text-sm italic text-gray-500">
                    A picture from a moment of focused thought or achievement.
                </p>
            </div>
        </section>

        <!-- 8. First Big Challenge -->
        <section class="grid md:grid-cols-2 gap-10 md:gap-20 items-center px-4 reveal">
            <div class="order-2 md:order-1 space-y-6">
                <h3 class="text-4xl font-bold text-pink-400">Facing Our First Challenge</h3>
                <p class="text-gray-300 text-lg">
                    Every relationship faces hurdles, and I’m thankful we faced ours early. It wasn't easy, but seeing how we navigated that moment together solidified my belief in us. We are a team, capable of overcoming anything, because we prioritize communication and trust.
                </p>
                <p class="text-sm italic text-gray-500">
                    A memory of us being there for each other.
                </p>
            </div>
            <div class="order-1 md:order-2 shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                <!-- Image source updated to T.png -->
                <img src="T.png" 
                     alt="Placeholder for a picture symbolizing resilience"
                     class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                     onerror="this.onerror=null;this.src='T.png'">
            </div>
        </section>
        
        <!-- 9. Her Hobbies/Passions -->
        <section class="grid md:grid-cols-2 gap-10 md:gap-20 items-center px-4 reveal">
            <div class="shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                <!-- Image source updated to T.png -->
                <img src="T.png" 
                     alt="Placeholder for a picture of her pursuing a passion or hobby"
                     class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                     onerror="this.onerror=null;this.src='T.png'">
            </div>
            <div class="space-y-6">
                <h3 class="text-4xl font-bold text-pink-400">The Things You Love</h3>
                <p class="text-gray-300 text-lg">
                    Watching you immerse yourself in [Mention a specific hobby, e.g., painting, reading, hiking] is a beautiful thing. That focused energy, the dedication, and the genuine excitement you bring to the things you care about is intoxicating. I love that I get to be a part of your world.
                </p>
                <p class="text-sm italic text-gray-500">
                    A picture of you doing what you love.
                </p>
            </div>
        </section>

        <!-- 10. Future Dreams -->
        <section class="grid md:grid-cols-2 gap-10 md:gap-20 items-center px-4 reveal">
            <div class="order-2 md:order-1 space-y-6">
                <h3 class="text-4xl font-bold text-pink-400">A Glimpse of Our Future</h3>
                <p class="text-gray-300 text-lg">
                    I love talking to you about the future. It doesn't matter if we're planning a trip next year or just laughing about what we'll be like when we're old; every dream we share feels tangible and exciting. You make me excited for tomorrow.
                </p>
                <p class="text-sm italic text-gray-500">
                    A scenic or aspirational photo that feels like our future.
                </p>
            </div>
            <div class="order-1 md:order-2 shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                <!-- Image source updated to T.png -->
                <img src="T.png" 
                     alt="Placeholder for a picture symbolizing shared future dreams"
                     class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                     onerror="this.onerror=null;this.src='T.png'">
            </div>
        </section>
        
        <!-- 11. Compliment: Humor -->
        <section class="grid md:grid-cols-2 gap-10 md:gap-20 items-center px-4 reveal">
            <div class="shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                <!-- Image source updated to T.png -->
                <img src="T.png" 
                     alt="Placeholder for a funny picture or a picture of us laughing"
                     class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                     onerror="this.onerror=null;this.src='T.png'">
            </div>
            <div class="space-y-6">
                <h3 class="text-4xl font-bold text-pink-400">Your Sense of Humor</h3>
                <p class="text-gray-300 text-lg">
                    Honestly, your goofy side is one of my favorite things. You always know how to make me laugh, even when I'm having the worst day. Our inside jokes and ridiculous banter are the soundtracks to my happiness.
                </p>
                <p class="text-sm italic text-gray-500">
                    A picture that reminds me of our shared laughter.
                </p>
            </div>
        </section>

        <!-- 12. Comfort and Home -->
        <section class="grid md:grid-cols-2 gap-10 md:gap-20 items-center px-4 reveal">
            <div class="order-2 md:order-1 space-y-6">
                <h3 class="text-4xl font-bold text-pink-400">Where I Feel at Home</h3>
                <p class="text-gray-300 text-lg">
                    Home isn't a place; it's being with you. Whether we are curled up on the couch or navigating a crowded room, your presence is the most comforting thing I know. You are my safe harbor.
                </p>
                <p class="text-sm italic text-gray-500">
                    A cozy photo of us together at home.
                </p>
            </div>
            <div class="order-1 md:order-2 shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                <!-- Image source updated to T.png -->
                <img src="T.png" 
                     alt="Placeholder for a comfortable, cozy moment"
                     class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                     onerror="this.onerror=null;this.src='T.png'">
            </div>
        </section>

        <!-- 13. Compliment: Inner Strength -->
        <section class="grid md:grid-cols-2 gap-10 md:gap-20 items-center px-4 reveal">
            <div class="shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                <!-- Image source updated to T.png -->
                <img src="T.png" 
                     alt="Placeholder for an empowering or determined photo"
                     class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                     onerror="this.onerror=null;this.src='T.png'">
            </div>
            <div class="space-y-6">
                <h3 class="text-4xl font-bold text-pink-400">The Strength in Your Character</h3>
                <p class="text-gray-300 text-lg">
                    You approach life with such grace and quiet determination. Your internal compass is always set to what is right, and I admire your commitment to your values. That inner strength is what makes you the best version of yourself, and I am so honored to stand by you.
                </p>
                <p class="text-sm italic text-gray-500">
                    A picture that shows your confidence.
                </p>
            </div>
        </section>

        <!-- 14. Favorite Trip/Outing -->
        <section class="grid md:grid-cols-2 gap-10 md:gap-20 items-center px-4 reveal">
            <div class="order-2 md:order-1 space-y-6">
                <h3 class="text-4xl font-bold text-pink-400">Our Weekend Getaway</h3>
                <p class="text-gray-300 text-lg">
                    I’ll never forget our trip to [Name of Place]. It was full of new experiences, bad navigation, and incredible food. You make every ordinary place extraordinary just by being there. Thank you for making every trip feel like a lifetime memory.
                </p>
                <p class="text-sm italic text-gray-500">
                    A photo from our first weekend away.
                </p>
            </div>
            <div class="order-1 md:order-2 shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                <!-- Image source updated to T.png -->
                <img src="T.png" 
                     alt="Placeholder for a great trip or outing"
                     class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                     onerror="this.onerror=null;this.src='T.png'">
            </div>
        </section>

        <!-- 15. The Small Moments -->
        <section class="grid md:grid-cols-2 gap-10 md:gap-20 items-center px-4 reveal">
            <div class="shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                <!-- Image source updated to T.png -->
                <img src="T.png" 
                     alt="Placeholder for a candid, everyday photo"
                     class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                     onerror="this.onerror=null;this.src='T.png'">
            </div>
            <div class="space-y-6">
                <h3 class="text-4xl font-bold text-pink-400">The Beauty in the Ordinary</h3>
                <p class="text-gray-300 text-lg">
                    It's not just the big events; it's the Tuesday nights, the shared cups of coffee, and the quiet moments before we fall asleep. These small, mundane moments are the fabric of our relationship, and they are perfect because I spend them with you.
                </p>
                <p class="text-sm italic text-gray-500">
                    A candid photo of us just 'being'.
                </p>
            </div>
        </section>

        <!-- 16. Compliment: Generosity -->
        <section class="grid md:grid-cols-2 gap-10 md:gap-20 items-center px-4 reveal">
            <div class="order-2 md:order-1 space-y-6">
                <h3 class="text-4xl font-bold text-pink-400">Your Generous Heart</h3>
                <p class="text-gray-300 text-lg">
                    The kindness you show to everyone around you—friends, family, and even strangers—is breathtaking. You never expect anything in return, and your generosity, whether of time or spirit, is a constant reminder to be a better person.
                </p>
                <p class="text-sm italic text-gray-500">
                    A photo of you doing something kind or helpful.
                </p>
            </div>
            <div class="order-1 md:order-2 shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                <!-- Image source updated to T.png -->
                <img src="T.png" 
                     alt="Placeholder for a moment showing her generosity"
                     class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                     onerror="this.onerror=null;this.src='T.png'">
            </div>
        </section>

        <!-- 17. Looking Forward to the 1-Year -->
        <section class="grid md:grid-cols-2 gap-10 md:gap-20 items-center px-4 reveal">
            <div class="shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                <!-- Image source updated to T.png -->
                <img src="T.png" 
                     alt="Placeholder for a happy, forward-looking photo"
                     class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                     onerror="this.onerror=null;this.src='T.png'">
            </div>
            <div class="space-y-6">
                <h3 class="text-4xl font-bold text-pink-400">Counting Down to One Year</h3>
                <p class="text-gray-300 text-lg">
                    These six months have flown by, but they feel like a lifetime because we've packed them with so much love and growth. I'm already brainstorming how to celebrate our one-year. Every day is a step closer to the future we are building together.
                </p>
                <p class="text-sm italic text-gray-500">
                    A photo that shows how happy we are together.
                </p>
            </div>
        </section>

        <!-- 18. The Feeling of Love -->
        <section class="grid md:grid-cols-2 gap-10 md:gap-20 items-center px-4 reveal">
            <div class="order-2 md:order-1 space-y-6">
                <h3 class="text-4xl font-bold text-pink-400">The Feeling of Being Loved</h3>
                <p class="text-gray-300 text-lg">
                    You have taught me so much about love, acceptance, and being vulnerable. The feeling of your hand in mine, or just sitting silently next to you, is pure magic. Thank you for making me feel seen, cherished, and completely, unconditionally loved.
                </p>
                <p class="text-sm italic text-gray-500">
                    A picture that means 'I love you'.
                </p>
            </div>
            <div class="order-1 md:order-2 shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                <!-- Image source updated to T.png -->
                <img src="T.png" 
                     alt="Placeholder for a picture symbolizing love and connection"
                     class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                     onerror="this.onerror=null;this.src='T.png'">
            </div>
        </section>

        <!-- 19. Her Best Quality -->
        <section class="grid md:grid-cols-2 gap-10 md:gap-20 items-center px-4 reveal">
            <div class="shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                <!-- Image source updated to T.png -->
                <img src="T.png" 
                     alt="Placeholder for her most stunning portrait"
                     class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                     onerror="this.onerror=null;this.src='T.png'">
            </div>
            <div class="space-y-6">
                <h3 class="text-4xl font-bold text-pink-400">The Very Best of You</h3>
                <p class="text-gray-300 text-lg">
                    If I had to pick one quality, it would be your incredible authenticity. You are unapologetically you, and that is truly the most attractive, inspiring thing about you. Never change, my love.
                </p>
                <p class="text-sm italic text-gray-500">
                    A perfect picture of you.
                </p>
            </div>
        </section>

        <!-- 20. Final Memory: My Gratitude -->
        <section class="grid md:grid-cols-2 gap-10 md:gap-20 items-center px-4 reveal">
            <div class="order-2 md:order-1 space-y-6">
                <h3 class="text-4xl font-bold text-pink-400">My Endless Gratitude</h3>
                <p class="text-gray-300 text-lg">
                    I made this website because you deserve something as carefully crafted and beautiful as you are. It's a testament to the effort you inspire in me. Every day is better because you're in it. Thank you for this beautiful six months.
                </p>
                <p class="text-sm italic text-gray-500">
                    A final, loving picture of us.
                </p>
            </div>
            <div class="order-1 md:order-2 shadow-2xl shadow-pink-900/50 rounded-xl overflow-hidden transform hover:scale-[1.01] transition duration-500 ease-in-out">
                <!-- Image source updated to T.png -->
                <img src="T.png" 
                     alt="Placeholder for a final picture of us together"
                     class="w-full h-auto object-cover transition duration-700 ease-in-out hover:opacity-90"
                     onerror="this.onerror=null;this.src='T.png'">
            </div>
        </section>


        <!-- 21. Final Message -->
        <section class="text-center px-4 reveal">
            <div class="border-y-2 border-pink-600/50 py-10 max-w-4xl mx-auto rounded-lg bg-gray-800/50">
                <h3 class="text-5xl font-bold text-pink-400 mb-6">Happy 6 Months</h3>
                <p class="text-2xl text-gray-200 leading-relaxed">
                    I love you more than words can say. Every day with you is a gift, and I can't wait to see what the next six months, and the rest of our lives, bring. Thank you for being you.
                </p>
                <p class="mt-8 text-xl font-semibold text-pink-300">
                    Yours, Always.
                </p>
            </div>
        </section>

    </main>

    <!-- 1. Password Entry Modal (Password is 6724) -->
    <div id="password-modal" class="fixed inset-0 z-[200] bg-black/95 hidden flex items-center justify-center p-4 transition-opacity duration-300 opacity-0">
        <div class="bg-gray-800 rounded-xl p-8 max-w-sm w-full shadow-2xl shadow-indigo-900 border border-indigo-600/30 transform scale-95 transition-transform duration-300" id="password-content">
            
            <h4 class="text-3xl font-bold text-indigo-400 mb-4 text-center">Secret Code Required</h4>
            <p class="text-gray-400 mb-6 text-center">Only for the one who holds the key to my heart.</p>

            <input type="password" id="password-input" 
                   class="w-full p-3 mb-4 text-center text-xl tracking-widest bg-gray-900 border border-gray-700 rounded-lg focus:ring-indigo-500 focus:border-indigo-500 outline-none" 
                   maxlength="4" placeholder="••••">
            
            <button id="submit-password-btn" class="w-full py-3 bg-indigo-600 text-white font-semibold rounded-lg hover:bg-indigo-700 transition duration-200 shadow-md shadow-indigo-500/50">
                Unlock
            </button>

            <p id="password-message" class="mt-4 text-center text-red-400 hidden"></p>
        </div>
    </div>
    
    <!-- 2. Secret Gallery Carousel Modal (Password Accepted) -->
    <div id="secret-gallery" class="fixed inset-0 z-[300] bg-black hidden overflow-hidden transition-opacity duration-1000">
        <div class="absolute inset-0 z-0">
            <!-- FLOATING IMAGES (T1.png to T6.png placeholders) -->
            <img src="T1.png" alt="Gallery Photo 1" class="floating-image img-1" onerror="this.onerror=null;this.src='https://placehold.co/250x180/1e293b/a5b4fc?text=T1'">
            <img src="T2.png" alt="Gallery Photo 2" class="floating-image img-2" onerror="this.onerror=null;this.src='https://placehold.co/300x200/1e293b/a5b4fc?text=T2'">
            <img src="T3.png" alt="Gallery Photo 3" class="floating-image img-3" onerror="this.onerror=null;this.src='https://placehold.co/200x250/1e293b/a5b4fc?text=T3'">
            <img src="T4.png" alt="Gallery Photo 4" class="floating-image img-4" onerror="this.onerror=null;this.src='https://placehold.co/280x200/1e293b/a5b4fc?text=T4'">
            <img src="T5.png" alt="Gallery Photo 5" class="floating-image img-5" onerror="this.onerror=null;this.src='https://placehold.co/180x250/1e293b/a5b4fc?text=T5'">
            <img src="T6.png" alt="Gallery Photo 6" class="floating-image img-6" onerror="this.onerror=null;this.src='https://placehold.co/220x300/1e293b/a5b4fc?text=T6'">
        </div>
        <div class="relative z-10 w-full h-full flex flex-col items-center justify-center p-8 text-center bg-black/50">
             <h2 class="text-7xl md:text-9xl font-black hero-title leading-tight text-pink-400/90 tracking-widest uppercase mb-10 [text-shadow:0_0_15px_rgba(236,72,153,0.8)]">
                My Sweet Girl
             </h2>
             <button id="close-gallery-btn" class="px-6 py-3 text-lg font-semibold rounded-full bg-pink-600 text-white shadow-xl hover:bg-pink-700 transition transform hover:scale-105">
                 Return to Tribute
             </button>
        </div>
    </div>

    <!-- 3. Dev Log Modal (Existing) -->
    <div id="dev-log-modal" class="fixed inset-0 z-[100] bg-black/80 hidden flex items-center justify-center p-4 transition-opacity duration-300 opacity-0">
        <div class="bg-gray-800 rounded-xl p-8 max-w-lg w-full shadow-2xl shadow-pink-900 border border-pink-600/30 transform scale-95 transition-transform duration-300" id="dev-log-content">
            
            <div class="flex justify-between items-start mb-6">
                <h4 class="text-3xl font-bold text-pink-400">Project Dev Log v1.0</h4>
                <button id="close-dev-log-btn" class="text-gray-400 hover:text-white transition">
                    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="18" y1="6" x2="6" y2="18"></line><line x1="6" y1="6" x2="18" y2="18"></line></svg>
                </button>
            </div>

            <div class="space-y-4 text-gray-300">
                <div class="p-3 bg-gray-700/50 rounded-lg">
                    <p class="text-lg font-medium text-pink-300">Project Conception Date (Start of Effort):</p>
                    <p class="font-mono text-xl">November 1, 2025</p>
                </div>
                <p class="italic">
                    "This site was built over the last month to ensure every detail was perfect for you. I spent every spare evening designing, writing, and coding this, pouring as much love into it as you pour into my life. Every pixel is for you."
                </p>
                <p class="text-sm text-gray-400 pt-2">
                    — The dedicated developer (That's me!)
                </p>
            </div>

        </div>
    </div>

    <script>
        // --- General Modal Handlers ---
        function openModal(modalId, contentId) {
            const modal = document.getElementById(modalId);
            const content = document.getElementById(contentId);
            modal.classList.remove('hidden');
            // Trigger transition via delayed property setting
            setTimeout(() => {
                modal.style.opacity = '1';
                content.style.transform = 'scale(1)';
            }, 10);
        }

        function closeModal(modalId, contentId) {
            const modal = document.getElementById(modalId);
            const content = document.getElementById(contentId);
            modal.style.opacity = '0';
            content.style.transform = 'scale(0.95)';
            setTimeout(() => {
                modal.classList.add('hidden');
            }, 300); // Wait for transition to finish
        }

        // --- Dev Log Logic ---
        const devLogBtn = document.getElementById('dev-log-btn');
        const devLogModal = document.getElementById('dev-log-modal');
        const devLogContent = document.getElementById('dev-log-content');
        const closeDevLogBtn = document.getElementById('close-dev-log-btn');

        devLogBtn.addEventListener('click', () => openModal('dev-log-modal', 'dev-log-content'));
        closeDevLogBtn.addEventListener('click', () => closeModal('dev-log-modal', 'dev-log-content'));
        
        // Close modal when clicking outside of the content
        devLogModal.addEventListener('click', (e) => {
            if (e.target === devLogModal) {
                closeModal('dev-log-modal', 'dev-log-content');
            }
        });

        // --- Password & Gallery Logic ---
        const SECRET_PASSWORD = "6724";
        const secretGalleryBtn = document.getElementById('secret-gallery-btn');
        const passwordModal = document.getElementById('password-modal');
        const passwordContent = document.getElementById('password-content');
        const passwordInput = document.getElementById('password-input');
        const submitPasswordBtn = document.getElementById('submit-password-btn');
        const passwordMessage = document.getElementById('password-message');
        const secretGallery = document.getElementById('secret-gallery');
        const closeGalleryBtn = document.getElementById('close-gallery-btn');

        // Show Password Modal
        secretGalleryBtn.addEventListener('click', () => {
            passwordInput.value = ''; // Clear previous input
            passwordMessage.classList.add('hidden');
            openModal('password-modal', 'password-content');
            passwordInput.focus();
        });

        // Password Validation Function
        const validatePassword = () => {
            if (passwordInput.value === SECRET_PASSWORD) {
                // Success: Hide password modal and show gallery
                closeModal('password-modal', 'password-content');
                
                // Show Gallery (using custom transition logic for full screen)
                secretGallery.classList.remove('hidden');
                setTimeout(() => {
                    secretGallery.style.opacity = '1';
                }, 10);
                
            } else {
                // Failure: Show error message
                passwordMessage.textContent = "Incorrect code. Please try again.";
                passwordMessage.classList.remove('hidden');
                passwordInput.value = '';
            }
        };

        // Trigger validation on button click
        submitPasswordBtn.addEventListener('click', validatePassword);

        // Trigger validation on Enter key press in the input field
        passwordInput.addEventListener('keydown', (e) => {
            if (e.key === 'Enter') {
                validatePassword();
            }
        });

        // Close Gallery Modal
        closeGalleryBtn.addEventListener('click', () => {
             secretGallery.style.opacity = '0';
             setTimeout(() => {
                secretGallery.classList.add('hidden');
            }, 1000); // 1s transition
        });


        // --- Scroll Reveal Logic for the 'high-effort' feel (Existing) ---
        const revealElements = document.querySelectorAll('.reveal');

        const observerOptions = {
            root: null, // viewport
            rootMargin: '0px',
            threshold: 0.2 // When 20% of the element is visible
        };

        const observer = new IntersectionObserver((entries, observer) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                } else {
                    entry.target.classList.remove('visible'); // re-hide on scroll up
                }
            });
        }, observerOptions);

        revealElements.forEach(el => {
            observer.observe(el);
        });

        // Accessibility: Close modals with Escape key
        document.addEventListener('keydown', (e) => {
            if (e.key === 'Escape') {
                if (!devLogModal.classList.contains('hidden')) {
                    closeModal('dev-log-modal', 'dev-log-content');
                } else if (!passwordModal.classList.contains('hidden')) {
                    closeModal('password-modal', 'password-content');
                } else if (!secretGallery.classList.contains('hidden')) {
                     closeGalleryBtn.click();
                }
            }
        });

    </script>
</body>
</html>
