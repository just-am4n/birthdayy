<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Happy Birthday Kittu Baccha</title>
  <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">
  <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Poppins', sans-serif;
      background: url('https://images.unsplash.com/photo-1508615070457-7baeba4003ab?auto=format&fit=crop&w=1950&q=80') no-repeat center center fixed;
      background-size: cover;
      color: #fff;
      overflow-x: hidden;
    }

    .overlay {
      background: rgba(0, 0, 0, 0.7);
      min-height: 100vh;
      padding: 60px 20px;
      text-align: center;
      position: relative;
      z-index: 1;
    }

    h1 {
      font-family: 'Great Vibes', cursive;
      font-size: 4em;
      color: #ff9ecb;
      margin-bottom: 0.5em;
    }

    .date {
      font-size: 2em;
      font-weight: 700;
      color: #ffd1dc;
      margin-bottom: 60px;
    }

    p {
      font-size: 1.2em;
      margin: 20px 0;
      line-height: 1.8;
    }

    .highlight {
      color: #ff69b4;
      font-weight: bold;
    }

    .colorful {
      color: #fce4ec;
    }

    .heart {
      font-size: 2.5em;
      color: #ff4d6d;
      animation: heartbeat 1.2s infinite ease-in-out;
    }

    @keyframes heartbeat {
      0%, 100% { transform: scale(1); }
      25% { transform: scale(1.15); }
      50% { transform: scale(1); }
      75% { transform: scale(1.15); }
    }

    .gallery {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
      margin: 40px 0;
    }

    .photo {
      width: 100%;
      max-width: 320px;
      border-radius: 20px;
      box-shadow: 0 0 25px rgba(255, 192, 203, 0.3);
      transition: transform 0.5s;
    }

    .photo:hover {
      transform: scale(1.05);
    }

    footer {
      margin-top: 40px;
      font-size: 1.1em;
      color: #ffc0cb;
    }

    canvas {
      position: fixed;
      top: 0;
      left: 0;
      z-index: 0;
      pointer-events: none;
    }
  </style>
</head>
<body>
  <!-- Heart Explosions Canvas -->
  <canvas id="fireworksCanvas"></canvas>

  <!-- Main Container -->
  <div class="overlay">
    <!-- First Page Only -->
    <h1 data-aos="fade-down">Happy Birthday, Kittu Baccha</h1>
    
    <!-- Scroll Content -->
    <div data-aos="fade-up" data-aos-delay="300" class="date">4 June</div>

    <p class="colorful" data-aos="fade-up" data-aos-delay="500">
      My sweetest Kittu, every moment with you is like a beautiful dream I never want to end. You bring love, peace, and light to my world. You're the smile in my mornings and the warmth in my nights.
    </p>
    <p class="highlight" data-aos="fade-up" data-aos-delay="700">
      With you, I feel like it's heaven for me.
    </p>
    <p data-aos="fade-up" data-aos-delay="900">
      Your presence turns ordinary days into extraordinary ones. You are my heartbeat, my forever, and everything I could ever wish for. You are special beyond words, and I'm endlessly grateful to share my life with you.
    </p>
    <p data-aos="fade-up" data-aos-delay="1100">
      I promise to stand by your side through every joy and storm, to hold your hand through all seasons of life. You're not just loved, you're cherished.
    </p>
    <p class="heart" data-aos="zoom-in" data-aos-delay="1300">❤️</p>

    <!-- Gallery -->
    <div class="gallery">
      <img src="https://i.postimg.cc/Nf7H85sT/Chat-GPT-Image-Mar-30-2025-03-48-17-PM.png" class="photo" data-aos="fade-up" alt="Photo 1">
      <img src="https://i.postimg.cc/6ppydc1J/Chat-GPT-Image-Mar-30-2025-04-13-31-PM.png" class="photo" data-aos="fade-up" data-aos-delay="200" alt="Photo 2">
      <img src="https://i.postimg.cc/VNyPYLtG/Chat-GPT-Image-Mar-30-2025-03-47-49-PM.png" class="photo" data-aos="fade-up" data-aos-delay="400" alt="Photo 3">
      <img src="https://i.postimg.cc/d0RpwRw3/Chat-GPT-Image-Mar-30-2025-at-05-56-42-PM.png" class="photo" data-aos="fade-up" data-aos-delay="600" alt="Photo 4">
    </div>

    <footer data-aos="fade-up" data-aos-delay="1000">
      Forever yours,<br>
      – Aman 💌
    </footer>
  </div>

  <!-- Scripts -->
  <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
  <script>
    AOS.init({ once: true });

    // Heart Explosion Effect
    const canvas = document.getElementById('fireworksCanvas');
    const ctx = canvas.getContext('2d');
    let particles = [];

    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    window.addEventListener('resize', () => {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
    });

    class HeartParticle {
      constructor(x, y, dx, dy, size, color, life) {
        this.x = x;
        this.y = y;
        this.dx = dx;
        this.dy = dy;
        this.size = size;
        this.color = color;
        this.life = life;
        this.opacity = 1;
      }

      update() {
        this.x += this.dx;
        this.y += this.dy;
        this.dy += 0.03;
        this.life--;
        this.opacity = this.life / 100;
      }

      drawHeart(ctx) {
        ctx.save();
        ctx.translate(this.x, this.y);
        ctx.scale(this.size, this.size);
        ctx.beginPath();
        ctx.moveTo(0, 0);
        ctx.bezierCurveTo(0, -3, -3, -3, -3, 0);
        ctx.bezierCurveTo(-3, 3, 0, 5, 0, 7);
        ctx.bezierCurveTo(0, 5, 3, 3, 3, 0);
        ctx.bezierCurveTo(3, -3, 0, -3, 0, 0);
        ctx.closePath();
        ctx.fillStyle = `rgba(${this.color}, ${this.opacity})`;
        ctx.fill();
        ctx.restore();
      }

      draw() {
        this.drawHeart(ctx);
      }
    }

    function heartExplosion() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);

      if (Math.random() < 0.05) {
        const x = Math.random() * canvas.width;
        const y = Math.random() * canvas.height / 2;
        const color = `${Math.floor(Math.random() * 255)}, ${Math.floor(Math.random() * 100)}, ${Math.floor(Math.random() * 150)}`;
        for (let i = 0; i < 30; i++) {
          const angle = Math.random() * 2 * Math.PI;
          const speed = Math.random() * 3 + 1;
          const size = Math.random() * 0.5 + 0.2;
          particles.push(new HeartParticle(x, y, Math.cos(angle) * speed, Math.sin(angle) * speed, size, color, 100));
        }
      }

      particles.forEach((p, index) => {
        p.update();
        p.draw();
        if (p.life <= 0) particles.splice(index, 1);
      });

      requestAnimationFrame(heartExplosion);
    }

    heartExplosion();
  </script>
</body>
</html>
