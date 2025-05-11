# rullzofficiall.github.io
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Lirik Penyangkalan - For Revenge</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: url('bg.jpg') no-repeat center center fixed;
      background-size: cover;
      font-family: 'Segoe UI', sans-serif;
      color: white;
      min-height: 100vh;
      overflow-y: auto;
      padding: 40px 20px;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
    }

    .container {
      text-align: center;
      backdrop-filter: blur(5px);
      background-color: rgba(0, 0, 0, 0.5);
      padding: 20px;
      border-radius: 12px;
      max-width: 800px;
      width: 100%;
    }

    .lyrics .line {
      font-size: 5vw;
      max-font-size: 28px;
      opacity: 0;
      transform: translateY(30px);
      animation: slideIn 1.2s ease-out forwards;
      margin: 12px 0;
      animation-delay: var(--delay);
      color: #f0f0f0;
      font-weight: bold;
      text-shadow: 1px 1px 5px rgba(0, 0, 0, 0.7);
    }

    @keyframes slideIn {
      from {
        opacity: 0;
        transform: translateY(30px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    #playBtn {
      position: fixed;
      top: 20px;
      left: 20px;
      padding: 10px 20px;
      background-color: #f04c4c;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      z-index: 999;
      font-size: 16px;
      box-shadow: 0 2px 6px rgba(0,0,0,0.3);
    }

    #playBtn:hover {
      background-color: #d43a3a;
    }

    @media screen and (max-width: 600px) {
      .lyrics .line {
        font-size: 5vw;
      }

      #playBtn {
        font-size: 14px;
        padding: 8px 16px;
      }
    }
  </style>
</head>
<body>

  <button id="playBtn" onclick="playMusic()">Putar Musik</button>
  <audio id="bgm" src="penyangkalan.mp3"></audio>

  <div class="container">
    <div class="lyrics" id="lyricsBox">
      <!-- Lirik akan dimasukkan lewat JavaScript -->
    </div>
  </div>

  <script>
    const lyrics = [
      "Selamat datang di penyangkalan",
      "Sesunyi rumah yang kuhuni",
      "Sebising derau di ujung hari",
      "Seperih luka yang abadi",
      "Sebisanya 'kan kunikmati",
      "Selamat datang di penyangkalan",
      "Dia masih di sini dan menari-nari",
      "Perlahan meracuni kewarasan yang mati",
      "Dia masih di sini dan menari-nari",
      "Perlahan menghantui kenyataan yang sepi",
      "Bertukar peran menyakiti",
      "Seakan ku tak bisa mati",
      "Berpura-pura pulih sendiri",
      "Nyatanya kutelah mati berkali-kali",
      "Dia masih di sini dan menari-nari",
      "Perlahan meracuni kewarasan yang mati",
      "Dia masih di sini dan menari-nari",
      "Perlahan menghantui kenyataan yang sepi",
      "Selamat datang di penyangkalan",
      "Selamat datang di penyangkalan",
      "Selamat datang di penyangkalan",
      "Bertukar peran saling menghantam",
      "Dia masih di sini dan menari-nari",
      "Perlahan meracuni kewarasan yang mati",
      "Dia masih di sini dan menari-nari",
      "Perlahan menghantui kenyataan yang sepi"
    ];

    const lyricsBox = document.getElementById("lyricsBox");

    // Tambahkan baris lirik ke HTML dengan animasi terjadwal
    lyrics.forEach((text, index) => {
      const line = document.createElement("p");
      line.className = "line";
      line.textContent = text;
      line.style.setProperty('--delay', `${index * 1.3}s`);
      lyricsBox.appendChild(line);
      // Ubah warna teks setelah muncul
      setTimeout(() => {
        line.style.color = `rgb(${rand255()},${rand255()},${rand255()})`;
      }, (index + 2) * 1300);
    });

    function rand255() {
      return Math.floor(Math.random() * 200 + 55); // Hindari warna terlalu gelap
    }

    function playMusic() {
      const audio = document.getElementById('bgm');
      audio.play().catch(e => alert("Klik dibutuhkan untuk memulai musik."));
    }
  </script>
</body>
</html>