```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Le Futur du Web est ici</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet">
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Arial', sans-serif;
      background: #000;
      color: white;
    }

    .hero {
      height: 100vh;
      background: linear-gradient(120deg, #1f4037, #99f2c8);
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      position: relative;
      overflow: hidden;
    }

    .hero::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: url('https://source.unsplash.com/random/1600x900') center/cover no-repeat;
      opacity: 0.3;
      z-index: -1;
      animation: backgroundMove 10s ease-in-out infinite alternate;
    }

    @keyframes backgroundMove {
      0% {
        transform: scale(1);
      }
      100% {
        transform: scale(1.1);
      }
    }

    h1 {
      font-size: 5em;
      text-transform: uppercase;
      animation: textZoom 2s ease-out;
      background: linear-gradient(90deg, #ff6a00, #ee0979);
      background-clip: text;
      -webkit-background-clip: text;
      color: transparent;
    }

    @keyframes textZoom {
      0% {
        transform: scale(0.7);
        opacity: 0;
      }
      100% {
        transform: scale(1);
        opacity: 1;
      }
    }

    p {
      font-size: 1.8em;
      animation: fadeInUp 2s ease-in-out 1s forwards;
      opacity: 0;
    }

    @keyframes fadeInUp {
      0% {
        transform: translateY(50px);
        opacity: 0;
      }
      100% {
        transform: translateY(0);
        opacity: 1;
      }
    }

    .icon-grid {
      display: flex;
      justify-content: space-around;
      margin-top: 50px;
      animation: fadeInUp 3s ease-in-out 2s forwards;
      opacity: 0;
    }

    .icon-grid i {
      font-size: 4em;
      transition: transform 0.3s ease-in-out, color 0.3s ease-in-out;
      color: #ffcc00;
    }

    .icon-grid i:hover {
      transform: rotate(20deg) scale(1.3);
      color: #ffffff;
    }

    .cta {
      margin-top: 50px;
      padding: 15px 40px;
      background: linear-gradient(90deg, #00c6ff, #0072ff);
      border: none;
      border-radius: 50px;
      color: white;
      font-size: 1.5em;
      transition: background-color 0.3s ease-in-out, transform 0.3s ease-in-out;
      animation: fadeInUp 3.5s ease-in-out 2.5s forwards;
      opacity: 0;
    }

    .cta:hover {
      background-color: #0072ff;
      transform: scale(1.1);
    }

  </style>
</head>
<body>

  <div class="hero">
    <div>
      <h1>Bienvenue dans le Futur</h1>
      <p>Le web, réinventé pour l’ère de l’innovation extrême.</p>
      <div class="icon-grid">
        <i class="fas fa-rocket"></i>
        <i class="fas fa-brain"></i>
        <i class="fas fa-laptop-code"></i>
        <i class="fas fa-globe"></i>
      </div>
      <button class="cta">Explorez Maintenant</button>
    </div>
  </div>

  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
``
