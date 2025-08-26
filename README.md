<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Slideshow Kariel</title>
  <style>
    body, html {
      margin: 0;
      padding: 0;
      overflow: hidden;
      font-family: 'Comic Sans MS', cursive, sans-serif;
      background: #fff;
    }

    /* Background utama */
    .background {
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: url('https://pin.it/6sTt6eNs7') no-repeat center center/cover;
      z-index: -2;
    }

    /* Background teks (gambar2.png) */
    .text-bg {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%,-50%);
      width: 80%;
      height: auto;
      background: url('gambar2.png') no-repeat center/contain;
      padding: 40px;
      text-align: center;
      font-size: 18px;
      color: #333;
    }

    /* Kotak 3D masuk */
    .intro-box {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%,-50%) rotateY(90deg);
      width: 300px;
      height: 200px;
      background: #ffc;
      border-radius: 15px;
      box-shadow: 0 10px 20px rgba(0,0,0,0.3);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 22px;
      font-weight: bold;
      animation: introBox 3s forwards;
      z-index: 5;
    }

    @keyframes introBox {
      0% {transform: translate(-50%,-50%) rotateY(90deg);}
      50% {transform: translate(-50%,-50%) rotateY(0deg);}
      100% {transform: translate(-50%,-50%) rotateY(0deg); opacity: 0;}
    }

    /* Slideshow */
    .slideshow {
      position: relative;
      width: 100%;
      height: 100vh;
      display: none;
    }

    .slide {
      position: absolute;
      top: 0; left: 0;
      width: 100%; height: 100%;
      opacity: 0;
      transition: opacity 1.5s ease;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
    }

    .slide.active {
      opacity: 1;
    }

    .slide img {
      max-width: 300px;
      margin-bottom: 20px;
    }

    .text-bg {
      font-size: 18px;
      line-height: 1.6;
    }
  </style>
</head>
<body>
  <!-- Background -->
  <div class="background"></div>

  <!-- Intro Box -->
  <div class="intro-box">Hai Kariel 💖</div>

  <!-- Slideshow -->
  <div class="slideshow">
    <!-- Slide 1 -->
    <div class="slide active">
      <img src="https://pin.it/72DfqtvsV" alt="Slide 1">
      <div class="text-bg">
        Hai Kariel yang manis, apa kabar kamu hari ini? Tau gak seberapa besar aku suka sama kamu? 
        Kalau boleh jujur, nilainya bukan 10 dari 10, tapi 100.000 dari 10! 
        Kamu itu spesial banget buat aku, bahkan lebih dari yang bisa aku jelasin dengan kata-kata.
      </div>
    </div>

    <!-- Slide 2 -->
    <div class="slide">
      <img src="https://pin.it/2lQLRkA43" alt="Slide 2">
      <div class="text-bg">
        Sejujurnya, aku pengen banget bisa lebih dekat sama kamu, kenal kamu lebih dalam, 
        dan jadi bagian kecil di hidup kamu. Tapi tadi aku lihat story kamu... hmm, 
        itu pacar kamu bukan atau mungkin orang yang kamu suka? 
        Aku pengen tau biar aku bisa mutusin, Kalau iya, mungkin aku harus banyak tahan perasaan ini ya.
      </div>
    </div>

    <!-- Slide 3 -->
    <div class="slide">
      <img src="https://pin.it/9121xn7HE" alt="Slide 3">
      <div class="text-bg">
        Kemarin aku sempat bilang mau mundur, biar gak terlalu berharap. 
        Tapi jujur rasanya berat banget. Hati aku nyut-nyutan kayak habis lari maraton wkwk. 
        Sulit banget buat pura-pura biasa aja, apalagi kalau lihat kamu kelihatan bahagia, 
        rasanya campur aduk antara seneng dan sakit sedikit.
      </div>
    </div>

    <!-- Slide 4 -->
    <div class="slide">
      <img src="https://pin.it/14Ni5xps5" alt="Slide 4">
      <div class="text-bg">
        Tapi aku sadar, aku gak punya hak buat cemburu atau marah. 
        Aku bukan siapa-siapa kamu, cuma seseorang yang diam-diam ngehargain kamu dari jauh. 
        Aku cuma bisa doa yang baik buat kamu, semoga kamu selalu bahagia meskipun bukan sama aku.
      </div>
    </div>

    <!-- Slide 5 -->
    <div class="slide">
      <img src="https://pin.it/4kNsUR3Ge" alt="Slide 5">
      <img src="https://pin.it/5DE5OwFyA" alt="Slide 5 extra">
      <div class="text-bg">
        Asal kamu bahagia, aku juga ikut bahagia. Aku sayang kamu, Kariel. 
        Mungkin rasa ini gak cuma 1.000 atau 2.000, tapi puluhan ribu.  
        Semoga kamu gak risih sama aku, dan semoga kamu selalu bahagia, di mana pun dan sama siapa pun.
      </div>
    </div>
  </div>

  <!-- Musik -->
  <audio autoplay loop>
    <source src="https://od.lk/s/OTFfMjc2NjYwMTBf/take-a-chance-with-me.mp3" type="audio/mp3">
  </audio>

  <script>
    // Setelah intro selesai, tampilkan slideshow
    setTimeout(() => {
      document.querySelector('.intro-box').style.display = 'none';
      document.querySelector('.slideshow').style.display = 'block';
    }, 3000);

    // Slideshow otomatis
    let slides = document.querySelectorAll('.slide');
    let index = 0;

    setInterval(() => {
      slides[index].classList.remove('active');
      index = (index + 1) % slides.length;
      slides[index].classList.add('active');
    }, 9000); // ganti slide tiap 9 detik
  </script>
</body>
</html>
