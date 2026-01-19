# stillanig
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Sound Buttons</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    body {
      margin: 0;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: #111;
      font-family: Arial, sans-serif;
    }

    .container {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
      gap: 24px;
      width: 90%;
      max-width: 500px;
    }

    .sound-btn {
      background: none;
      border: none;
      padding: 0;
      cursor: pointer;
      touch-action: manipulation;
    }

    .sound-btn img {
      width: 100%;
      aspect-ratio: 1 / 1;
      object-fit: cover;
      border-radius: 50%;
      border: 4px solid black;
      transition:
        transform 0.08s ease,
        box-shadow 0.08s ease,
        filter 0.08s ease;
    }

    /* Press animation */
    .sound-btn:active img {
      transform: scale(0.92);
      box-shadow: inset 0 0 20px rgba(0,0,0,0.6);
      filter: brightness(0.85);
    }

    /* Optional subtle idle glow */
    .sound-btn img {
      box-shadow: 0 6px 14px rgba(0,0,0,0.5);
    }
  </style>
</head>
<body>

  <div class="container">
    <button class="sound-btn" onclick="playSound('sound1.mp3')">
      <img src="button1.png" alt="Sound 1">
    </button>

    <button class="sound-btn" onclick="playSound('sound2.mp3')">
      <img src="button2.png" alt="Sound 2">
    </button>

    <button class="sound-btn" onclick="playSound('sound3.mp3')">
      <img src="button3.png" alt="Sound 3">
    </button>
  </div>

  <script>
    function playSound(src) {
      const audio = new Audio(src);
      audio.play();
    }
  </script>

</body>
</html>
