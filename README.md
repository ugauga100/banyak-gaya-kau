# banyak-gaya-kau
probowo peler 1
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>PPT Mulkan Style</title>
  <style>
    body {
      margin: 0;
      font-family: 'Comic Sans MS', sans-serif;
      overflow: hidden;
    }
    .slide {
      width: 100vw;
      height: 100vh;
      display: none;
      justify-content: center;
      align-items: center;
      color: white;
      font-size: 60px;
      text-align: center;
      padding: 40px;
      transition: all 0.5s;
    }
    .slide1 { background-color: red; }
    .slide2 { background-color: royalblue; }
    .slide3 { background-color: gold; color: black; }

    img {
      max-height: 60vh;
      border: 5px solid white;
      border-radius: 20px;
    }

    .controls {
      position: absolute;
      bottom: 20px;
      left: 50%;
      transform: translateX(-50%);
    }

    button {
      font-size: 20px;
      margin: 0 10px;
      padding: 10px 20px;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <div class="slide slide1" style="display: flex;">Oi Mulkan!</div>

  <div class="slide slide2">
    <div>
      <div>Palak awk</div>
      <img src="foto_kawan.jpg" alt="Foto kawanmu">
    </div>
  </div>

  <div class="slide slide3">Kok telele org ni</div>

  <div class="controls">
    <button onclick="prevSlide()">Sebelumnya</button>
    <button onclick="nextSlide()">Selanjutnya</button>
  </div>

  <script>
    let slides = document.querySelectorAll('.slide');
    let current = 0;

    function showSlide(index) {
      slides.forEach((slide, i) => {
        slide.style.display = i === index ? 'flex' : 'none';
      });
    }

    function nextSlide() {
      current = (current + 1) % slides.length;
      showSlide(current);
    }

    function prevSlide() {
      current = (current - 1 + slides.length) % slides.length;
      showSlide(current);
    }

    // Optional: keyboard navigation
    document.addEventListener('keydown', function(e) {
      if (e.key === 'ArrowRight') nextSlide();
      if (e.key === 'ArrowLeft') prevSlide();
    });
  </script>

</body>
</html>
