
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
            <button class="nav-btn active" onclick="showSection('pendahuluan')">Pendahuluan</button>
            <button class="nav-btn" onclick="showSection('struktur')">Struktur</button>
            <button class="nav-btn" onclick="showSection('teknik')">Teknik</button>
            <button class="nav-btn" onclick="showSection('contoh')">Contoh</button>
            <button class="nav-btn" onclick="showSection('kesimpulan')">Kesimpulan</button>
        </div>

        <div id="pendahuluan" class="content-section active">
            <h2>Pendahuluan</h2>
            <!-- <p>Teks argumentasi adalah jenis teks yang bertujuan untuk meyakinkan pembaca tentang suatu pendapat atau gagasan melalui alasan-alasan yang logis dan bukti-bukti yang kuat.</p>
             -->
            <div class="highlight">
                <h3>Latar Belakang</h3>
                <p>Pada zaman serba digital dengan informasi yang semakin mudah untuk didapatkan, tentunya akan ada pihak tidak betanggung jawab yang menyebarkan informasi yang tidak benar yang biasa disebut dengan hoaks. Oleh karena itu, kita perlu meningkatkan literasi digital. Literasi digital sendiri merupakan pengetahuan serta kecakapan pengguna dalam memanfaatkan media digital seperti alat komunikasi, jaringan internet, dan berbagai hal digital lainnya.</p>
            </div>

            <div class="argument-points">
                <div class="point-card">
                    <h4>Tujuan</h4>
                    <p>Lorem Ipsum</p>
                </div>
                <div class="point-card">
                    <h4>Tema</h4>
                    <p>Sebagai media komunikasi untuk menyampaikan gagasan dan mempengaruhi opini publik.</p>
                </div>
            </div>
        </div>

        <div id="struktur" class="content-section">
            <h2>Struktur Teks Argumentasi</h2>
            
            <h3>1. Pendahuluan (Tesis)</h3>
            <p>Bagian yang berisi pernyataan pendapat atau posisi penulis terhadap suatu isu. Tesis harus jelas, tegas, dan dapat diperdebatkan.</p>

            <h3>2. Tubuh Argumen</h3>
            <p>Berisi rangkaian argumen yang mendukung tesis. Setiap argumen harus disertai dengan:</p>
            
            <div class="argument-points">
                <div class="point-card">
                    <h4>Data dan Fakta</h4>
                    <p>Informasi objektif yang mendukung argumen, seperti statistik, hasil penelitian, atau kutipan ahli.</p>
                </div>
                <div class="point-card">
                    <h4>Alasan Logis</h4>
                    <p>Penjelasan yang menghubungkan data dengan tesis secara masuk akal.</p>
                </div>
                <div class="point-card">
                    <h4>Contoh Konkret</h4>
                    <p>Ilustrasi nyata yang memperjelas dan memperkuat argumen.</p>
                </div>
            </div>

            <h3>3. Penutup (Penegasan Ulang)</h3>
            <p>Berisi penegasan kembali tesis dan rangkuman argumen utama untuk memperkuat posisi penulis.</p>
        </div>

        <div id="teknik" class="content-section">
            <h2>Teknik Penulisan Efektif</h2>
            
            <div class="highlight">
                <h3>Prinsip AIDA dalam Argumentasi:</h3>
                <p><strong>Attention</strong> → <strong>Interest</strong> → <strong>Desire</strong> → <strong>Action</strong></p>
            </div>

            <h3>Teknik-teknik Penting:</h3>
            
            <div class="argument-points">
                <div class="point-card">
                    <h4>Gunakan Data Kredibel</h4>
                    <p>Sertakan statistik, penelitian ilmiah, dan sumber terpercaya untuk memperkuat kredibilitas argumen.</p>
                </div>
                <div class="point-card">
                    <h4>Bantah Argumen Lawan</h4>
                    <p>Antisipasi dan tanggapi argumen yang bertentangan untuk menunjukkan kekuatan posisi Anda.</p>
                </div>
                <div class="point-card">
                    <h4>Gunakan Bahasa Persuasif</h4>
                    <p>Pilih kata-kata yang kuat dan emotif tanpa kehilangan objektivitas.</p>
                </div>
                <div class="point-card">
                    <h4>Struktur Logis</h4>
                    <p>Susun argumen dari yang lemah ke kuat, atau sebaliknya, tergantung strategi yang dipilih.</p>
                </div>
            </div>
        </div>

        <div id="contoh" class="content-section">
            <h2>Contoh Penerapan</h2>
            
            <div class="highlight">
                <h3>Topik: "Pentingnya Pendidikan Digital di Era Modern"</h3>
            </div>

            <h3>Tesis:</h3>
            <p>Pendidikan digital harus segera diintegrasikan ke dalam kurikulum nasional untuk mempersiapkan generasi yang kompeten menghadapi tantangan abad ke-21.</p>

            <h3>Argumen Pendukung:</h3>
            <div class="argument-points">
                <div class="point-card">
                    <h4>Argumen 1: Kebutuhan Pasar Kerja</h4>
                    <p>85% pekerjaan di tahun 2030 akan membutuhkan keterampilan digital. Tanpa persiapan sejak dini, generasi muda akan tertinggal dalam kompetisi global.</p>
                </div>
                <div class="point-card">
                    <h4>Argumen 2: Efektivitas Pembelajaran</h4>
                    <p>Penelitian menunjukkan siswa yang terpapar teknologi sejak dini memiliki kemampuan problem-solving 40% lebih baik.</p>
                </div>
                <div class="point-card">
                    <h4>Argumen 3: Persiapan Masa Depan</h4>
                    <p>Negara-negara maju seperti Finlandia dan Singapura telah menerapkan kurikulum digital dengan hasil yang sangat positif.</p>
                </div>
            </div>

            <h3>Penegasan Ulang:</h3>
            <p>Dengan mempertimbangkan kebutuhan pasar kerja, efektivitas pembelajaran, dan pengalaman negara lain, implementasi pendidikan digital bukan lagi pilihan, melainkan keharusan untuk kemajuan bangsa.</p>
        </div>

        <div id="kesimpulan" class="content-section">
            <h2>Kesimpulan</h2>
            
            <div class="highlight">
                <h3>Kunci Sukses Teks Argumentasi:</h3>
            </div>

            <div class="argument-points">
                <div class="point-card">
                    <h4>Tesis yang Kuat</h4>
                    <p>Mulai dengan pernyataan yang jelas, spesifik, dan dapat diperdebatkan.</p>
                </div>
                <div class="point-card">
                    <h4>Bukti yang Valid</h4>
                    <p>Dukung setiap argumen dengan data, fakta, dan contoh yang relevan.</p>
                </div>
                <div class="point-card">
                    <h4>Logika yang Konsisten</h4>
                    <p>Pastikan alur berpikir mudah diikuti dan tidak ada kontradiksi.</p>
                </div>
                <div class="point-card">
                    <h4>Bahasa yang Efektif</h4>
                    <p>Gunakan kata-kata yang tepat, jelas, dan persuasif.</p>
                </div>
            </div>

            <div style="text-align: center; margin-top: 40px;">
                <p style="font-size: 1.3rem; font-weight: bold;">Terima kasih atas perhatian Anda!</p>
                <p style="opacity: 0.8; margin-top: 10px;">Semoga presentasi ini bermanfaat untuk pemahaman Anda tentang teks argumentasi.</p>
            </div>
        </div>
    </div>

    <div class="controls">
        <button class="control-btn" onclick="previousSection()" title="Sebelumnya">‹</button>
        <button class="control-btn" onclick="nextSection()" title="Selanjutnya">›</button>
        <button class="control-btn" onclick="toggleFullscreen()" title="Fullscreen">⛶</button>
    </div>

    <script>
        const sections = ['pendahuluan', 'struktur', 'teknik', 'contoh', 'kesimpulan'];
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

        // Auto-advance option (uncomment to enable)
        // setInterval(() => {
        //     nextSection();
        //     if (currentSection === sections.length - 1) {
        //         currentSection = -1; // Reset to beginning
        //     }
        // }, 10000); // Change slide every 10 seconds

        // Remove typing effect after animation completes
setTimeout(() => {
    const typingElement = document.querySelector('.typing-effect');
    typingElement.classList.add('finished');
}, 4000); // 3s typing + 1s blink
    </script>
</body>
</html>
