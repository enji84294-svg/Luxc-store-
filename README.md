<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Luxc Store Roblox</title>
<style>
    :root {
        --primary: #ff2da5;
        --secondary: #6d00ff;
        --accent: #25d366;
        --dark-bg: #0d0d0d;
        --card-bg: rgba(21, 21, 21, 0.9);
        --text-light: #fff;
    }

    body {
        margin: 0;
        font-family: 'Poppins', sans-serif;
        background: var(--dark-bg);
        color: var(--text-light);
        overflow-x: hidden;
        position: relative;
        min-height: 100vh;
    }

    /* Background particles dengan animasi lebih smooth */
    .particles {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: -1;
        overflow: hidden;
    }

    .particle {
        position: absolute;
        border-radius: 50%;
        background: rgba(255, 0, 106, 0.2);
        animation: float 20s infinite ease-in-out;
    }

    /* Header dengan animasi lebih menarik */
    header {
        padding: 30px 20px;
        text-align: center;
        background: linear-gradient(135deg, var(--primary), var(--secondary), #ff006a);
        background-size: 300% 300%;
        animation: gradientFlow 5s ease infinite, headerGlow 3s ease-in-out infinite alternate;
        position: relative;
        overflow: hidden;
        box-shadow: 0 10px 30px rgba(255, 0, 106, 0.3);
        transform: translateY(0);
        transition: transform 0.5s ease;
    }

    header:hover {
        transform: translateY(-5px);
    }

    header::before {
        content: '';
        position: absolute;
        top: 0;
        left: -100%;
        width: 100%;
        height: 100%;
        background: linear-gradient(90deg, transparent, rgba(255,255,255,0.1), transparent);
        animation: shine 3s ease-in-out infinite;
    }

    header h1 {
        margin: 0;
        font-size: 36px;
        text-shadow: 0 0 15px rgba(255, 0, 106, 0.8);
        letter-spacing: 1px;
        animation: textPop 1.2s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        transform-origin: center;
    }

    header p {
        margin-top: 15px;
        opacity: 0.9;
        font-size: 18px;
        animation: fadeInUp 1s ease-out 0.5s both;
    }

    /* Container dengan animasi masuk */
    .container {
        width: 90%;
        max-width: 900px;
        margin: auto;
        margin-top: 40px;
        padding-bottom: 60px;
        animation: containerSlide 1s ease-out;
    }

    /* Title Section dengan efek hover */
    .section-title {
        font-size: 28px;
        text-align: center;
        margin-bottom: 25px;
        margin-top: 50px;
        padding-bottom: 15px;
        border-bottom: 2px solid transparent;
        background: linear-gradient(90deg, transparent, var(--primary), transparent) no-repeat;
        background-size: 0% 2px;
        background-position: center bottom;
        text-shadow: 0 0 8px var(--primary);
        opacity: 0;
        transform: translateY(20px);
        animation: titleSlide 0.8s ease forwards;
        transition: all 0.3s ease;
    }

    .section-title:hover {
        transform: scale(1.05);
        text-shadow: 0 0 15px var(--primary);
    }

    .section-title.animate {
        animation: titleUnderline 2s ease forwards;
        background-size: 80% 2px;
    }

    /* Card dengan animasi bertahap */
    .card {
        background: var(--card-bg);
        padding: 25px;
        margin-bottom: 20px;
        border-radius: 15px;
        border: 1px solid #242424;
        transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        backdrop-filter: blur(10px);
        opacity: 0;
        transform: translateY(30px) scale(0.95);
        animation: cardAppear 0.6s ease forwards;
        position: relative;
        overflow: hidden;
    }

    .card::before {
        content: '';
        position: absolute;
        top: 0;
        left: -100%;
        width: 100%;
        height: 100%;
        background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
        transition: left 0.7s ease;
    }

    .card:hover::before {
        left: 100%;
    }

    .card:hover {
        transform: translateY(-10px) scale(1.05);
        box-shadow: 0 20px 40px rgba(255, 0, 85, 0.4), 0 0 60px rgba(109, 0, 255, 0.2);
        border-color: var(--primary);
    }

    /* Animasi delay untuk card */
    .card:nth-child(1) { animation-delay: 0.2s; }
    .card:nth-child(2) { animation-delay: 0.4s; }
    .card:nth-child(3) { animation-delay: 0.6s; }
    .card:nth-child(4) { animation-delay: 0.8s; }

    .title {
        font-size: 24px;
        color: var(--primary);
        margin-bottom: 12px;
        position: relative;
        display: inline-block;
        padding-left: 25px;
    }

    .title::before {
        content: '🎮';
        position: absolute;
        left: 0;
        font-size: 20px;
        animation: iconBounce 2s infinite ease-in-out;
    }

    /* Tombol dengan animasi lebih smooth */
    .btn-wa {
        display: inline-flex;
        align-items: center;
        justify-content: center;
        margin-top: 15px;
        padding: 14px 28px;
        background: linear-gradient(135deg, var(--accent), #128c7e);
        color: white;
        font-weight: bold;
        border-radius: 12px;
        text-decoration: none;
        transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        position: relative;
        overflow: hidden;
        border: none;
        cursor: pointer;
        gap: 10px;
        animation: pulse 2s infinite ease-in-out;
        transform: scale(1);
    }

    .btn-wa::before {
        content: '';
        position: absolute;
        top: 0;
        left: -100%;
        width: 100%;
        height: 100%;
        background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
        transition: left 0.7s ease;
    }

    .btn-wa:hover::before {
        left: 100%;
    }

    .btn-wa:hover {
        transform: translateY(-5px) scale(1.08);
        box-shadow: 0 15px 30px rgba(37, 211, 102, 0.5), 0 0 40px rgba(37, 211, 102, 0.3);
        background: linear-gradient(135deg, #128c7e, var(--accent));
        letter-spacing: 1px;
    }

    .btn-wa::after {
        content: '📱';
        font-size: 20px;
        animation: phoneShake 2s infinite ease-in-out;
    }

    /* Animations lebih smooth */
    @keyframes gradientFlow {
        0%, 100% { 
            background-position: 0% 50%; 
        }
        50% { 
            background-position: 100% 50%; 
        }
    }

    @keyframes float {
        0% { 
            transform: translateY(100vh) rotate(0deg); 
            opacity: 0; 
        }
        10% { 
            opacity: 0.7; 
        }
        90% { 
            opacity: 0.7; 
        }
        100% { 
            transform: translateY(-100px) rotate(360deg); 
            opacity: 0; 
        }
    }

    @keyframes headerGlow {
        from { 
            box-shadow: 0 10px 30px rgba(255, 0, 106, 0.3); 
        }
        to { 
            box-shadow: 0 10px 40px rgba(109, 0, 255, 0.4); 
        }
    }

    @keyframes shine {
        0% { 
            left: -100%; 
        }
        50% { 
            left: 100%; 
        }
        100% { 
            left: 100%; 
        }
    }

    @keyframes textPop {
        0% { 
            transform: scale(0.5) rotate(-5deg); 
            opacity: 0; 
        }
        70% { 
            transform: scale(1.1) rotate(2deg); 
        }
        100% { 
            transform: scale(1) rotate(0deg); 
            opacity: 1; 
        }
    }

    @keyframes fadeInUp {
        from { 
            transform: translateY(30px); 
            opacity: 0; 
        }
        to { 
            transform: translateY(0); 
            opacity: 1; 
        }
    }

    @keyframes containerSlide {
        from { 
            transform: translateY(50px); 
            opacity: 0; 
        }
        to { 
            transform: translateY(0); 
            opacity: 1; 
        }
    }

    @keyframes titleSlide {
        to { 
            opacity: 1; 
            transform: translateY(0); 
        }
    }

    @keyframes titleUnderline {
        0% { 
            background-size: 0% 2px; 
        }
        100% { 
            background-size: 80% 2px; 
        }
    }

    @keyframes cardAppear {
        to { 
            opacity: 1; 
            transform: translateY(0) scale(1); 
        }
    }

    @keyframes iconBounce {
        0%, 100% { 
            transform: translateY(0) rotate(0deg); 
        }
        50% { 
            transform: translateY(-5px) rotate(10deg); 
        }
    }

    @keyframes pulse {
        0%, 100% { 
            transform: scale(1); 
            box-shadow: 0 5px 15px rgba(37, 211, 102, 0.3); 
        }
        50% { 
            transform: scale(1.03); 
            box-shadow: 0 8px 25px rgba(37, 211, 102, 0.5); 
        }
    }

    @keyframes phoneShake {
        0%, 100% { 
            transform: rotate(0deg); 
        }
        25% { 
            transform: rotate(10deg); 
        }
        75% { 
            transform: rotate(-10deg); 
        }
    }

    /* Floating elements */
    .floating-element {
        position: fixed;
        width: 60px;
        height: 60px;
        border-radius: 50%;
        background: rgba(255, 45, 165, 0.1);
        animation: floatingElement 8s infinite ease-in-out;
        z-index: -1;
        border: 2px solid rgba(255, 45, 165, 0.3);
    }

    .floating-element:nth-child(1) {
        top: 20%;
        left: 5%;
        animation-delay: 0s;
    }

    .floating-element:nth-child(2) {
        top: 60%;
        right: 10%;
        animation-delay: 2s;
    }

    .floating-element:nth-child(3) {
        bottom: 20%;
        left: 15%;
        animation-delay: 4s;
    }

    @keyframes floatingElement {
        0%, 100% { 
            transform: translateY(0) rotate(0deg); 
        }
        50% { 
            transform: translateY(-40px) rotate(180deg); 
        }
    }

    /* Scroll animation */
    .animate-on-scroll {
        opacity: 0;
        transform: translateY(30px);
        transition: all 0.8s ease;
    }

    .animate-on-scroll.visible {
        opacity: 1;
        transform: translateY(0);
    }

    /* Responsive */
    @media (max-width: 768px) {
        header h1 {
            font-size: 28px;
        }
        
        .section-title {
            font-size: 24px;
        }
        
        .title {
            font-size: 20px;
        }
        
        .btn-wa {
            padding: 12px 20px;
            font-size: 14px;
        }
    }
</style>
</head>

<body>

<div class="particles" id="particles"></div>

<!-- Floating elements -->
<div class="floating-element"></div>
<div class="floating-element"></div>
<div class="floating-element"></div>

<header>
    <h1> Luxc Store ✔️</h1>
    <p>Selamat datang di website resmi Luxc store</p>
</header>

<div class="container">

    <!-- ====================== BAGIAN 1 — FORUM JOKI ====================== -->
    <div class="section-title animate-on-scroll" id="joki-title">FORUM JOKI ROBLOX 🎮</div>

    <!-- Joki Card 1 -->
    <div class="card animate-on-scroll">
        <div class="">Joki 99 Malam</div>
        <p>Joki hari atau diamond. Proses aman tanpa risiko banned. Garansi 100% keamanan akun.</p>
        <a class="btn-wa" href="https://chat.whatsapp.com/G2UdYE2nxiCGRqDb1C4Jtq?mode=hqrt1" target="_blank">
            Pesan Via WhatsApp
        </a>
    </div>

    <!-- Joki Card 2 -->
    <div class="card animate-on-scroll">
        <div class="">Fish It Coin Farm</div>
        <p>Auto farm 24 jam atau seterusnya, sistem aman & stabil. Boost coin dengan metode terbaik.</p>
        <a class="btn-wa" href="https://chat.whatsapp.com/G2UdYE2nxiCGRqDb1C4Jtq?mode=hqrt1" target="_blank">
            Pesan Via WhatsApp
        </a>
    </div>

    <!-- Joki Card 3 -->
    <div class="card animate-on-scroll">
        <div class="">Blox Fruits</div>
        <p>Joki level, boss hunt, mastery, raid, awakening. Layanan lengkap untuk semua kebutuhan Blox Fruits.</p>
        <a class="btn-wa" href="https://chat.whatsapp.com/G2UdYE2nxiCGRqDb1C4Jtq?mode=hqrt1" target="_blank">
            Pesan Via WhatsApp
        </a>
    </div>

    <!-- ====================== BAGIAN 2 — FORUM TOP UP ROBUX ====================== -->
    <div class="section-title animate-on-scroll" id="topup-title">Forum Top Up Robux 💲</div>

    <!-- Top Up Card -->
    <div class="card animate-on-scroll">
        <div class="">Top Up Robux</div>
        <p>
            Top Up Robux tercepat & terpercaya.  
            Pilihan 80 – 500 Robux.  
            Metode: ID Login / Gamepass.
        </p>
        <a class="btn-wa" href="https://chat.whatsapp.com/GzUmbGbnlCF1fFGcKVNgYE?mode=hqrt1" target="_blank">
            Top Up Sekarang
        </a>
    </div>

    <!-- ====================== BAGIAN 3 — Developer Support ====================== -->
    <div class="section-title animate-on-scroll" id="dev-title">Support Developer 🛠️</div>
    
    <div class="card animate-on-scroll">
        <div class="">Laporkan Bug Website</div>
        <p>
            Mengalami kendala atau bug di website? Hubungi developer langsung melalui WhatsApp.
            Kami siap membantu memperbaiki masalah teknis.
        </p>
        <a class="btn-wa"href="https://chat.whatsapp.com/Iumlh5HAKsG2bfZfwTwkEH?mode=hqrtv1" target="_blank">
          Laporkan Bug Sekarang
        </a>
    </div>

</div>

    <!-- ====================== BAGIAN 4 — Developer maker  ====================== -->
    <div class="section-title animate-on-scroll" id="dev-title">pesan Dvoloper  </div>
    
<div class="card animate-on-scroll">
        <div class=""></div>
        <p>
            pembuat website atau Dvoloper bernama enji jika web ini terjadi masalah diluar kendali permanent maka website ini akan di tutup resmi
             dan kalian semua yang takut di scam admin laporan saja ke wa developer nanti saya akan tangani masalah ini
        </p>
        <a class="" href="" target="_blank">
            
        </a>
    </div>

</div>

<script>
    // Background Particles dengan animasi lebih smooth
    document.addEventListener('DOMContentLoaded', function() {
        const particlesContainer = document.getElementById('particles');
        const colors = ['rgba(255, 0, 106, 0.2)', 'rgba(109, 0, 255, 0.2)', 'rgba(255, 45, 165, 0.2)', 'rgba(37, 211, 102, 0.2)'];

        // Create 30 particles dengan variasi
        for (let i = 0; i < 30; i++) {
            const particle = document.createElement('div');
            particle.classList.add('particle');
            
            // Random properties untuk variasi
            const size = Math.random() * 30 + 5;
            const color = colors[Math.floor(Math.random() * colors.length)];
            const left = Math.random() * 100;
            const duration = Math.random() * 25 + 15;
            const delay = Math.random() * 10;
            const blur = Math.random() * 10;
            
            // Apply styles
            particle.style.width = `${size}px`;
            particle.style.height = `${size}px`;
            particle.style.left = `${left}%`;
            particle.style.background = color;
            particle.style.animationDuration = `${duration}s`;
            particle.style.animationDelay = `${delay}s`;
            particle.style.filter = `blur(${blur}px)`;
            
            particlesContainer.appendChild(particle);
        }

        // Scroll animation
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                    
                    // Tambahkan animasi khusus untuk title
                    if (entry.target.classList.contains('section-title')) {
                        setTimeout(() => {
                            entry.target.classList.add('animate');
                        }, 300);
                    }
                }
            });
        }, observerOptions);

        // Observe semua elemen dengan class animate-on-scroll
        document.querySelectorAll('.animate-on-scroll').forEach(el => {
            observer.observe(el);
        });

        // Hover effect untuk header
        const header = document.querySelector('header');
        document.addEventListener('mousemove', (e) => {
            const x = e.clientX / window.innerWidth;
            const y = e.clientY / window.innerHeight;
            
            header.style.transform = `translateY(${-y * 5}px)`;
            header.style.backgroundPosition = `${x * 100}% ${y * 100}%`;
        });

        // Click ripple effect untuk tombol
        const buttons = document.querySelectorAll('.btn-wa');
        buttons.forEach(button => {
            button.addEventListener('click', function(e) {
                const ripple = document.createElement('span');
                const rect = this.getBoundingClientRect();
                const size = Math.max(rect.width, rect.height);
                const x = e.clientX - rect.left - size / 2;
                const y = e.clientY - rect.top - size / 2;
                
                ripple.style.cssText = `
                    position: absolute;
                    border-radius: 50%;
                    background: rgba(255, 255, 255, 0.6);
                    transform: scale(0);
                    animation: ripple 0.6s linear;
                    width: ${size}px;
                    height: ${size}px;
                    left: ${x}px;
                    top: ${y}px;
                `;
                
                this.appendChild(ripple);
                
                setTimeout(() => {
                    ripple.remove();
                }, 600);
            });
        });

        // Tambahkan keyframe untuk ripple effect
        const style = document.createElement('style');
        style.textContent = `
            @keyframes ripple {
                to {
                    transform: scale(4);
                    opacity: 0;
                }
            }
        `;
        document.head.appendChild(style);

        // Parallax effect untuk floating elements
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const rate = scrolled * -0.5;
            
            const floatingElements = document.querySelectorAll('.floating-element');
            floatingElements.forEach((el, index) => {
                const speed = 0.1 + (index * 0.1);
                el.style.transform = `translateY(${rate * speed}px)`;
            });
        });
    });
</script>

</body>
</html>
