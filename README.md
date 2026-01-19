<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday! ❤️</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.5.1/dist/confetti.browser.min.js"></script>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        html { scroll-behavior: smooth; }
        body { font-family: 'Poppins', sans-serif; background-color: #fff5f7; color: #333; overflow-x: hidden; }

        /* Floating Hearts Background */
        .hearts-container { position: fixed; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: 0; }
        .heart-float { position: absolute; color: rgba(136, 14, 79, 0.15); animation: float linear infinite; }
        @keyframes float { from { transform: translateY(100vh) rotate(0deg); } to { transform: translateY(-10vh) rotate(360deg); } }

        /* Hero Section */
        .hero { min-height: 100vh; background: linear-gradient(135deg, #fce4ec 0%, #f8bbd0 100%); display: flex; align-items: center; justify-content: center; text-align: center; padding: 20px; position: relative; z-index: 1; }
        .typewriter { font-family: 'Dancing Script', cursive; font-size: clamp(2rem, 7vw, 4rem); color: #880e4f; border-right: .15em solid #880e4f; white-space: nowrap; overflow: hidden; margin: 0 auto; animation: typing 3.5s steps(30, end), blink 0.5s step-end infinite; }
        @keyframes typing { from { width: 0 } to { width: 100% } }
        @keyframes blink { 50% { border-color: transparent } }

        .floating-hearts { display: flex; justify-content: center; gap: 10px; margin: 20px 0; font-size: 1.5rem; }
        .heart { animation: bounce 2s infinite ease-in-out; }
        @keyframes bounce { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-15px); } }

        /* Gallery/Photos */
        .gallery-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 30px; padding: 60px 20px; max-width: 1100px; margin: 0 auto; position: relative; z-index: 1; }
        .photo-card { background: white; padding: 12px 12px 35px 12px; border-radius: 4px; box-shadow: 0 10px 25px rgba(0,0,0,0.1); transition: 0.5s; transform: rotate(-1.5deg); }
        .photo-card:nth-child(even) { transform: rotate(1.5deg); }
        .photo-card:hover { transform: scale(1.05) rotate(0deg); z-index: 10; box-shadow: 0 15px 35px rgba(136, 14, 79, 0.2); }
        .photo-card img { width: 100%; height: auto; display: block; border-radius: 2px; }
        .photo-caption { padding: 15px; text-align: center; font-size: 0.9rem; color: #555; line-height: 1.4; }

        /* Message Section */
        .message-section { padding: 60px 20px; position: relative; z-index: 1; }
        .message-card { background: white; padding: 40px 30px; border-radius: 20px; box-shadow: 0 10px 30px rgba(0,0,0,0.05); text-align: center; max-width: 600px; margin: 0 auto; border: 1px solid #fce4ec; }
        .message-title { font-family: 'Dancing Script', cursive; font-size: 2.5rem; color: #880e4f; margin-bottom: 15px; }
        .message-content { line-height: 1.8; color: #444; white-space: pre-line; }

        .cta-button { background: #880e4f; color: white; padding: 12px 30px; border: none; border-radius: 25px; margin-top: 20px; cursor: pointer; font-weight: 600; transition: 0.3s; }
        .cta-button:hover { background: #ad1457; transform: translateY(-2px); }

        .reveal { opacity: 0; transform: translateY(30px); transition: 1s all ease; }
        .reveal.active { opacity: 1; transform: translateY(0); }

        footer { text-align: center; padding: 40px; color: #880e4f; font-family: 'Dancing Script', cursive; font-size: 1.2rem; }
    </style>
</head>
<body>

    <div class="hearts-container" id="hearts-bg"></div>

    <section class="hero">
        <div>
            <h1 class="typewriter">Happy Birthday, Pratima ! ❤️</h1>
            <p>You are the best thing that ever happened to me.</p>
            <div class="floating-hearts">
                <div class="heart">❤️</div><div class="heart" style="animation-delay:0.2s">💖</div><div class="heart" style="animation-delay:0.4s">❤️</div>
            </div>
            <button class="cta-button" onclick="celebrate()">See your Memories 🎁</button>
        </div>
    </section>

    <div id="gallery" class="gallery-grid">
        <div class="photo-card reveal">
            <img src="https://i.ibb.co/d4mXs4mT/IMG-20260114-WA0023.jpg" alt="Memory 1">
            <div class="photo-caption">Traditional or modern, you carry every look with such grace. You are truly beautiful, inside and out.</div>
        </div>
        <div class="photo-card reveal">
            <img src="https://i.ibb.co/xV7Kyj4/IMG-20251217-WA0001-1.jpg" alt="Memory 2">
            <div class="photo-caption">Even when the world is a blur, you’re the only thing I see clearly. You are my constant.</div>
        </div>
    </div>

    <section class="message-section reveal">
        <div class="message-card">
            <h2 class="message-title">My Message To You</h2>
            <div class="message-content">
"To my dearest willow,
Happy Birthday! On this special day, I wanted to take a moment to tell you just how much you mean to me. You aren't just a part of my life; you are the best part of it. Your kindness, your strength, and the way you make everything feel better just by being there are things I never take for granted.
Watching you grow and achieve your dreams is one of my greatest joys. I hope this year brings you as much happiness as you give to everyone around you. Thank you for being my partner, my best friend, and my favorite person. I love you more than yesterday, but not as much as I will tomorrow.
Happy Birthday, beautiful!
            </div>
            <br>
            <p><strong>With love, Naresh</strong></p>
        </div>
    </section>

    <footer>Made with ❤️ for Pratima</footer>

    <script>
        function celebrate() {
            confetti({
                particleCount: 150,
                spread: 70,
                origin: { y: 0.6 },
                colors: ['#880e4f', '#f8bbd0', '#ffeb3b']
            });
            document.getElementById('gallery').scrollIntoView();
        }

        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart-float');
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = Math.random() * 3 + 4 + 's';
            heart.style.fontSize = Math.random() * 15 + 10 + 'px';
            document.getElementById('hearts-bg').appendChild(heart);
            setTimeout(() => { heart.remove(); }, 6000);
        }
        setInterval(createHeart, 500);

        window.addEventListener('scroll', () => {
            document.querySelectorAll('.reveal').forEach(el => {
                if (el.getBoundingClientRect().top < window.innerHeight - 100) el.classList.add('active');
            });
        });
    </script>
</body>
</html>
