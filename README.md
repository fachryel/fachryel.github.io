
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Presentasi Teks Argumentasi</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(#1B2838 0%, #020317 100%);
            color: white;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .header {
            text-align: center;
            padding: 40px 0;
            animation: fadeInDown 1s ease-out;
        }

        .header h1 {
            font-size: 3rem;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .header p {
            font-size: 1.2rem;
            opacity: 0.9;
        }

        .navigation {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 30px 0;
            flex-wrap: wrap;
        }

        .nav-btn {
            background: rgba(255,255,255,0.2);
            border: 2px solid rgba(255,255,255,0.3);
            color: white;
            padding: 12px 24px;
            border-radius: 50px;
            cursor: pointer;
            font-size: 16px;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }

        .nav-btn:hover {
            background: rgba(255,255,255,0.3);
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.2);
        }

        .nav-btn.active {
            background: rgba(255,255,255,0.4);
            transform: scale(1.05);
        }

        .content-section {
            display: none;
            animation: fadeInUp 0.8s ease-out;
            background: rgba(255,255,255,0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            margin: 30px 0;
            box-shadow: 0 8px 32px rgba(0,0,0,0.1);
            border: 1px solid rgba(255,255,255,0.2);
        }

        .content-section.active {
            display: block;
        }

        .content-section h2 {
            font-size: 2.5rem;
            margin-bottom: 20px;
            text-align: center;
            color: #fff;
        }

        .content-section h3 {
            font-size: 1.8rem;
            margin: 25px 0 15px 0;
            color: #f0f8ff;
        }

        .content-section p {
            font-size: 1.1rem;
            line-height: 1.8;
            margin-bottom: 20px;
            text-align: justify;
        }

        .highlight {
            background: rgba(255,255,255,0.2);
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
            border-left: 5px solid #ffd700;
            font-size: 20px;
        }

        .argument-points {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .point-card {
            background: rgba(255,255,255,0.15);
            padding: 25px;
            border-radius: 15px;
            transition: transform 0.3s ease;
            border: 1px solid rgba(255,255,255,0.2);
        }

        .point-card:hover {
            transform: translateY(-5px);
            background: rgba(255,255,255,0.2);
        }

        .point-card h4 {
            color: #ffd700;
            margin-bottom: 15px;
            font-size: 1.3rem;
        }

        .progress-bar {
            position: fixed;
            top: 0;
            left: 0;
            height: 4px;
            background: #ffd700;
            transition: width 0.3s ease;
            z-index: 1000;
        }

        .controls {
            position: fixed;
            bottom: 30px;
            right: 30px;
            display: flex;
            gap: 10px;
        }

        .control-btn {
            background: rgba(255,255,255,0.2);
            border: none;
            color: white;
            padding: 15px;
            border-radius: 50%;
            cursor: pointer;
            font-size: 18px;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }

        .control-btn:hover {
            background: rgba(255,255,255,0.3);
            transform: scale(1.1);
        }

        .reference-list {
            list-style: none;
            padding: 0;
        }

        .reference-list li {
            background: rgba(255,255,255,0.1);
            padding: 15px;
            margin: 10px 0;
            border-radius: 10px;
            border-left: 3px solid #ffd700;
        }

        .reflection-question {
            background: rgba(255,255,255,0.15);
            padding: 20px;
            margin: 15px 0;
            border-radius: 15px;
            border: 1px solid rgba(255,255,255,0.2);
        }

        .reflection-question h4 {
            color: #ffd700;
            margin-bottom: 10px;
            font-size: 1.2rem;
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .typing-effect {
            overflow: hidden;
            border-right: 3px solid #ffd700;
            white-space: nowrap;
            animation: typing 3s steps(40, end), blink-caret 0.75s step-end infinite 3s;
            animation-fill-mode: forwards;
        }

        .typing-effect.finished {
            border-right: none;
            overflow: visible;
            white-space: normal;
        }

        @keyframes typing {
            from { width: 0 }
            to { width: 100% }
        }

        @keyframes blink-caret {
            from, to { border-color: transparent }
            50% { border-color: #ffd700; }
        }

        @media (max-width: 768px) {
            .header h1 {
                font-size: 2rem;
            }
            
            .content-section {
                padding: 20px;
                margin: 15px 0;
            }
            
            .navigation {
                gap: 10px;
            }
            
            .nav-btn {
                padding: 10px 16px;
                font-size: 14px;
            }
        }
    </style>
</head>
<body>
    <div class="progress-bar" id="progressBar"></div>
    
    <div class="container">
        <div class="header">
            <h1 class="typing-effect">Teks Argumentasi Persuasif</h1>
            <p>Anti Hoaks dan Literasi Digital</p>
        </div>

        <div class="navigation">
            <button class="nav-btn" onclick="showSection('struktur')">Pendahuluan</button>
            <button class="nav-btn" onclick="showSection('contoh')">Teks Kampanye</button>
            <button class="nav-btn" onclick="showSection('kesimpulan')">Kesimpulan</button>
            <button class="nav-btn" onclick="showSection('daftar-pustaka')">Daftar Pustaka</button>
            <button class="nav-btn" onclick="showSection('refleksi')">Refleksi Diri</button>
        </div>

        <div id="struktur" class="content-section">
            <h2>Pendahuluan</h2>
            
            <h3>Latar Belakang</h3>
            <p>Pada zaman serba digital dengan informasi yang semakin mudah untuk didapatkan, tentunya akan ada pihak tidak betanggung jawab yang menyebarkan informasi yang tidak benar yang biasa disebut dengan hoaks. Oleh karena itu, kita perlu meningkatkan literasi digital.

Literasi digital sendiri merupakan pengetahuan serta kecakapan pengguna dalam memanfaatkan media digital seperti alat komunikasi, jaringan internet, dan berbagai hal digital lainnya.</p>

            <h3>2. Tujuan</h3>
            
            <div class="argument-points">
                <div class="point-card">
                    <p>Menyadarkan masyarakat mengenai bahaya hoaks</p>
                </div>
                <div class="point-card">
                    <p>Mengajarkan masyarakat mengenai Literasi Digital</p>
                </div>
                <div class="point-card">
                    <p>Mencerdaskan masyarakat dalam menggunakan media digital</p>
                </div>
            </div>

            <h3>3. Target Audience</h3>
            
            <div class="argument-points">
                <div class="point-card">
                    <p>Masyarakat yang masih awam dengan media digital</p>
                </div>
                <div class="point-card">
                    <p>Segala jenis usia</p>
                </div>
            </div>
        </div>

        <div id="contoh" class="content-section">
            <h2>Teks Kampanye</h2>
            
            <div class="highlight">
                <h3>Topik: "Literasi Digital dan Anti Hoaks"</h3>
            </div>

            <h3>Penyataan Pendapat</h3>
            <p>Hoaks adalah ancaman serius di era digital karena dapat menyesatkan masyarakat. Oleh sebab itu, literasi digital sangat penting agar kita mampu memilah dan memahami informasi dengan bijak.</p>

            <h3>Argumen Pendukung:</h3>
            <div class="argument-points">
                <div class="point-card">
                    <h4>Argumen 1</h4>
                    <p>Hoaks dapat menimbulkan keresahan sosial. Banyak berita bohong yang sengaja dibuat untuk memecah belah persatuan, menimbulkan kebencian, atau bahkan kepanikan di tengah masyarakat.</p>
                </div>
                <div class="point-card">
                    <h4>Argumen 2</h4>
                    <p>Literasi digital membantu masyarakat mengenali sumber informasi yang benar. Dengan pengetahuan yang cukup, kita bisa melakukan cek fakta, membandingkan sumber, dan tidak mudah percaya begitu saja pada informasi yang beredar.</p>
                </div>
                <div class="point-card">
                    <h4>Argumen 3</h4>
                    <p>Mmasyarakat yang cerdas digital tidak mudah terprovokasi. Mereka mampu menyaring informasi, hanya menyebarkan hal yang bermanfaat, serta ikut menjaga lingkungan digital agar tetap sehat dan aman.</p>
                </div>
            </div>

            <h3>Penegasan Ulang:</h3>
            <p>Dengan meningkatkan literasi digital, kita dapat melindungi diri dari hoaks sekaligus ikut menjaga lingkungan digital yang sehat, aman, dan bermanfaat bagi semua.</p>
        </div>

        <div id="kesimpulan" class="content-section">
            <h2>Kesimpulan</h2>
            
            <div class="highlight">
                <h4>Melawan hoaks dapat dilakukan dengan memperkuat literasi digital. Semakin cerdas masyarakat dalam menggunakan teknologi, semakin kecil peluang hoaks menyebar luas. Mari bersama-sama menjadi pengguna digital yang bijak, kritis, dan bertanggung jawab.</h4>
            </div>
        </div>

        <div id="daftar-pustaka" class="content-section">
            <h2>Daftar Pustaka</h2>
            
            <ul class="reference-list">
                <li>RSUD Grobogan. Anti-Hoax. Retrieved from https://ppid.rsud.grobogan.go.id/anti-hoax/</li>
<li>Kompas.com. (2021, Juni 15). Literasi Digital: Pengertian, Prinsip, Manfaat, Tantangan dan Contoh. Retrieved from https://www.kompas.com/skola/read/2021/06/15/142539669/literasi-digital-pengertian-prinsip-manfaat-tantangan-dan-contoh</li>
<li>Tsaniyah, N., & Juliana, K. A. (2019). Literasi Digital Sebagai Upaya Menangkal Hoaks di Era Disrupsi. Al-Balagh: Jurnal Dakwah dan Komunikasi.</li>
<li>Noer, U. (2022). Literasi Digital dan Mobile Learning. IAIN Parepare.</li>
<li>Fitriarti, E. A. Urgensi Literasi Digital dalam Menangkal Hoax. Jurnal MC, Universitas Lambung Mangkurat.</li>
<li>Februari, A., dkk. (2024). Peran Literasi di Era Digital dalam Menghadapi Hoaks. International Journal of Education.</li>
<li>Tim Pengabdian. (2021). Penyuluhan Literasi Digital Anti Hoax, Bullying, dan Ujaran Kebencian pada Remaja di Kota Ternate. ABSYARA: Jurnal Pengabdian Pada Masyarakat, 3(2).</li>
<li>Meyarsa. (2023). Penanganan Hoaks Keagamaan di Sosial Media Melalui Literasi Digital Milenial. Meyarsa: Jurnal Ilmu Komunikasi dan Dakwah.</li>
            </ul>
        </div>

        <div id="refleksi" class="content-section">
            <h2>Refleksi Diri</h2>
            
            <div class="reflection-question">
                <h4>1. Apa yang kamu pelajari dari tugas ini?</h4>
                <p>Mempelajari bagaimana cara membuat teks argumentasi dan mempelajari tenttang Literasi Digital dan Anti Hoaks.</p>
                </div>

            <div class="reflection-question">
                <h4>2. Apa tantangan terbesar dalam membuat kampanye digital?</h4>
               <p>Mencari sumber yang tepat untuk dijadikan referensi.</p>
            </div>

            <div class="reflection-question">
                <h4>3. Bagaimana kamu menilai kemampuan kolaborasi tim (jika berkelompok)?</h4>
              <p>Tugas ini adalah tugas individu</p>
            </div>
        </div>
    </div>

    <div class="controls">
        <button class="control-btn" onclick="previousSection()" title="Sebelumnya">‹</button>
        <button class="control-btn" onclick="nextSection()" title="Selanjutnya">›</button>
        <button class="control-btn" onclick="toggleFullscreen()" title="Fullscreen">⛶</button>
    </div>

    <script>
        const sections = ['struktur', 'contoh', 'kesimpulan', 'daftar-pustaka', 'refleksi'];
        let currentSection = 0;

        function showSection(sectionId) {
            // Hide all sections
            document.querySelectorAll('.content-section').forEach(section => {
                section.classList.remove('active');
            });
            
            // Remove active class from all nav buttons
            document.querySelectorAll('.nav-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            
            // Show selected section
            document.getElementById(sectionId).classList.add('active');
            
            // Add active class to corresponding nav button
            event.target.classList.add('active');
            
            // Update current section index
            currentSection = sections.indexOf(sectionId);
            
            // Update progress bar
            updateProgressBar();
            
            // Scroll to top
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function nextSection() {
            if (currentSection < sections.length - 1) {
                currentSection++;
                const sectionId = sections[currentSection];
                showSectionById(sectionId);
            }
        }

        function previousSection() {
            if (currentSection > 0) {
                currentSection--;
                const sectionId = sections[currentSection];
                showSectionById(sectionId);
            }
        }

        function showSectionById(sectionId) {
            // Hide all sections
            document.querySelectorAll('.content-section').forEach(section => {
                section.classList.remove('active');
            });
            
            // Remove active class from all nav buttons
            document.querySelectorAll('.nav-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            
            // Show selected section
            document.getElementById(sectionId).classList.add('active');
            
            // Add active class to corresponding nav button
            const navButtons = document.querySelectorAll('.nav-btn');
            navButtons[currentSection].classList.add('active');
            
            // Update progress bar
            updateProgressBar();
            
            // Scroll to top
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function updateProgressBar() {
            const progress = ((currentSection + 1) / sections.length) * 100;
            document.getElementById('progressBar').style.width = progress + '%';
        }

        function toggleFullscreen() {
            if (!document.fullscreenElement) {
                document.documentElement.requestFullscreen().catch(err => {
                    console.log('Fullscreen not supported');
                });
            } else {
                document.exitFullscreen();
            }
        }

        // Keyboard navigation
        document.addEventListener('keydown', function(e) {
            if (e.key === 'ArrowRight' || e.key === 'Space') {
                e.preventDefault();
                nextSection();
            } else if (e.key === 'ArrowLeft') {
                e.preventDefault();
                previousSection();
            } else if (e.key === 'Escape') {
                if (document.fullscreenElement) {
                    document.exitFullscreen();
                }
            }
        });

        // Initialize progress bar
        updateProgressBar();

        // Add smooth scrolling for better UX
        document.addEventListener('DOMContentLoaded', function() {
            // Add entrance animation to cards
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.animation = 'fadeInUp 0.6s ease-out';
                    }
                });
            });

            document.querySelectorAll('.point-card').forEach(card => {
                observer.observe(card);
            });
        });

        // Remove typing effect after animation completes
        setTimeout(() => {
            const typingElement = document.querySelector('.typing-effect');
            typingElement.classList.add('finished');
        }, 4000); // 3s typing + 1s blink
    </script>
</body>
</html>
