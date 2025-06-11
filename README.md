<!DOCTYPE html><html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Serta Mulia</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
  <style>
    * {
      box-sizing: border-box;
    }
    body, html {
      margin: 0;
      padding: 0;
      font-family: 'Poppins', sans-serif;
      height: 100vh;
      overflow: hidden;
    }
    .page {
      display: none;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      text-align: center;
      height: 100vh;
      background-size: cover;
      background-position: center;
      color: white;
      padding: 20px;
      position: relative;
    }
    .active {
      display: flex;
    }
    .overlay {
      background: rgba(0,0,0,0.5);
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 0;
    }
    .content {
      position: relative;
      z-index: 1;
      background: rgba(255,255,255,0.1);
      backdrop-filter: blur(6px);
      padding: 20px;
      border-radius: 20px;
    }
    button {
      margin-top: 20px;
      padding: 10px 20px;
      font-size: 16px;
      border: none;
      border-radius: 30px;
      background: #fca311;
      color: white;
      cursor: pointer;
    }
    button:hover {
      background: #ffba08;
    }
    video, img {
      max-width: 90%;
      margin-top: 20px;
      border-radius: 10px;
    }
  </style>
</head>
<body>
  <!-- Audio Global (diputar setelah interaksi) -->
  <audio id="musikLatar" loop>
    <source src="Tulus - Monokrom _ Lirik Lagu Indonesia.mp3" type="audio/mpeg">
    Browser tidak mendukung audio.
  </audio>  <!-- Halaman 1 -->  <div id="halaman1" class="page active" style="background-image: url(bg1.jpg);">
    <div class="overlay"></div>
    <div class="content">
      <h1> Apa nihh??</h1>
      <p>Klik untuk melanjutkan</p>
      <button onclick="pindahHalaman(2)">Lanjut</button>
    </div>
  </div>  <!-- Halaman 2 -->  <div id="halaman2" class="page" style="background-image: url(bg2.jpg);">
    <div class="overlay"></div>
    <div class="content">
      <h1>Pibesdeyy!!</h1>
      <p>Wish u all the bestt!
Semoga menjadi pribadi yang lebih baik,
semua keinginan bisa terwujud,
dan tetaplah menjadi orang baik. Ini hasil gabut aku wkwkk, maaf ya kalo jelek. SELAMAT MENONTON :)</p>
      <video id="videoUlangTahun" controls>
        <source src="Tak berjudul55 (2).mp4" type="video/mp4">
        Browser tidak mendukung video.
      </video>
      <div>
        <button onclick="pindahHalaman(3)">Mau download fotonya? Klik tombolnya aja</button>
      </div>
    </div>
  </div>  <!-- Halaman 3 -->  <div id="halaman3" class="page" style="background-color: #222;">
    <div class="content">
      <h2>Download Foto</h2>
      <img src="Pibesdeyy.jpg" alt="Foto Kejutan" id="fotoKejutan">
      <a href="Pibesdeyy.jpg" download>
        <button>Klik untuk download</button>
      </a>
    </div>
  </div>  <script>
    function pindahHalaman(no) {
      document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
      document.getElementById('halaman' + no).classList.add('active');

      if (no === 2) {
        const musik = document.getElementById('musikLatar');
        musik.play().catch(() => {
          console.log("Autoplay gagal. Pengguna perlu interaksi lebih dulu.");
        });
      }
    }
  </script></body>
</html>
