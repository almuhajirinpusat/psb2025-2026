<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tes Seleksi Santri Baru - Pondok Pesantren Al-Muhajirin</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
        }
        header {
            background-color: #0056b3;
            color: #fff;
            padding: 20px;
            text-align: center;
        }
        header h1 {
            margin: 0;
            font-size: 24px;
        }
        header p {
            margin: 5px 0 0;
            font-size: 16px;
        }
        #timer {
            font-size: 24px;
            font-weight: bold;
            text-align: center;
            margin: 20px 0;
            color: #ff0000;
        }
        main {
            padding: 20px;
        }
        .content {
            max-width: 800px;
            margin: 0 auto;
            background: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            text-align: center;
        }
        .content h2 {
            color: #0056b3;
            margin-bottom: 10px;
        }
        .content p {
            line-height: 1.6;
        }
        .btn-container {
            margin-top: 20px;
        }
        .btn {
            background-color: #0056b3;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            text-decoration: none;
            font-size: 16px;
            transition: background-color 0.3s;
        }
        .btn:hover {
            background-color: #004494;
        }
        iframe {
            width: 100%;
            height: 80vh;
            border: none;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            display: none;
        }
        footer {
            text-align: center;
            padding: 10px;
            background-color: #0056b3;
            color: #fff;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
        footer p {
            margin: 0;
            font-size: 14px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Tes Seleksi Santri Baru</h1>
        <p>Pondok Pesantren Al-Muhajirin Pusat</p>
        <p>Tahun Pelajaran 2025/2026</p>
    </header>
    <div id="timer" style="display: none;">30:00</div>
    <main>
        <div class="content" id="welcomeSection">
            <h2>Selamat Datang!</h2>
            <p>
                Terima kasih telah memilih Pondok Pesantren Al-Muhajirin sebagai tempat pendidikan putra-putri Anda.
                Untuk mengikuti tes seleksi santri baru, silakan klik tombol di bawah ini.
            </p>
            <div class="btn-container">
                <a href="#" class="btn" onclick="startTest()">Mulai Tes</a>
            </div>
        </div>
        <iframe id="googleForm" src=""></iframe>
    </main>
    <footer>
        <p>&copy; 2025 Pondok Pesantren Al-Muhajirin Pusat | Semua Hak Dilindungi</p>
    </footer>
    <script>
        let timerInterval;

        function startTest() {
            // Hilangkan bagian pengantar
            const welcomeSection = document.getElementById('welcomeSection');
            welcomeSection.style.display = 'none';

            // Tampilkan form dan timer
            const iframe = document.getElementById('googleForm');
            const timer = document.getElementById('timer');
            iframe.src = "https://docs.google.com/forms/d/e/1FAIpQLSdjzU9VhxVzvj0CBYCcNPDN59EfmgL4I8LXBjNgDg0ekAYefQ/viewform";
            iframe.style.display = 'block';
            timer.style.display = 'block';

            // Mulai timer
            startTimer(30 * 60); // 30 menit dalam detik
        }

        function startTimer(duration) {
            const timerDisplay = document.getElementById('timer');
            let timeRemaining = duration;

            timerInterval = setInterval(() => {
                const minutes = Math.floor(timeRemaining / 60);
                const seconds = timeRemaining % 60;
                timerDisplay.textContent = `${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;

                timeRemaining--;

                if (timeRemaining < 0) {
                    clearInterval(timerInterval);
                    timerDisplay.textContent = "Waktu Habis";
                    alert("Waktu untuk mengerjakan tes telah habis.");
                    document.getElementById('googleForm').style.display = 'none';
                }
            }, 1000);
        }
    </script>
</body>
</html>
# psb2025-2026
