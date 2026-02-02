<head>
  <style>
    .fade {
      opacity: 0;
      animation: show 0.6s forwards;
    }

    .d1 { animation-delay: 0.2s; }
    .d2 { animation-delay: 1.0s; }
    .d3 { animation-delay: 0s; } /* задержку делаем в JS */
    .d4 { animation-delay: 25.0s; }

    @keyframes show {
      to { opacity: 1; }
    }
  </style>
</head>
<body>
  <h1 class="fade d1" align="center"><img src="svg/1.svg"></h1>
  <h2 class="fade d2"><img src="svg/2.svg"></h2>

  <!-- svg3 не загружается сразу -->
  <h3 id="h3">
    <img id="svg3" data-src="svg/3.svg" alt="">
  </h3>

  <h4 class="fade d4">
    <a href="https://git.io/streak-stats">
      <img src="https://komarev.com/ghpvc/?username=dimoroz772&color=blueviolet">
    </a>
  </h4>

  <script>
    setTimeout(() => {
      const img = document.getElementById('svg3');
      img.src = img.dataset.src;
      img.classList.add('fade', 'd3'); // старт анимации
    }, 12000);
  </script>
</body>
