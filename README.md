<!DOCTYPE html><html lang="zh-Hant">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>生日快樂 陳誌軒</title>
  <link href="https://fonts.googleapis.com/css2?family=Dancing+Script&family=Noto+Sans+TC&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      font-family: 'Noto Sans TC', sans-serif;
      background: #ffeef3;
      overflow-x: hidden;
    }
    .center {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      text-align: center;
    }
    h1 {
      font-family: 'Dancing Script', cursive;
      font-size: 3em;
      color: #ff8ab0;
      animation: fadeIn 2s ease-in-out forwards;
    }
    @keyframes fadeIn {
      from {opacity: 0; transform: translateY(-30px);}
      to {opacity: 1; transform: translateY(0);}
    }
    .btn {
      background: #ffc0cb;
      border: none;
      border-radius: 20px;
      padding: 12px 24px;
      font-size: 1.2em;
      margin: 10px;
      color: white;
      cursor: pointer;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    }
    .love-note, .photo-gallery, .gift-box, .quiz, .closing {
      display: none;
      text-align: center;
      padding: 30px;
    }
    .photo {
      max-width: 80vw;
      border-radius: 20px;
      margin: 20px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    }
    .heart {
      color: pink;
      font-size: 2em;
    }
  </style>
</head>
<body>
  <audio autoplay loop>
    <source src="https://example.com/love-song.mp3" type="audio/mpeg">
    您的瀏覽器不支援音訊播放。
  </audio>  <div class="center" id="opening">
    <h1>生日快樂，陳誌軒！</h1>
    <button class="btn" onclick="startExperience()">點我開始</button>
  </div>  <div class="love-note" id="loveNote">
    <h2 class="heart">你知道嗎？</h2>
    <p id="noteText"></p>
    <button class="btn" onclick="newNote()">再來一句</button>
  </div>  <div class="photo-gallery" id="gallery">
    <h2>我們的回憶</h2>
    <img class="photo" src="photo1.jpg" alt="Memory 1">
    <img class="photo" src="photo2.jpg" alt="Memory 2">
  </div>  <div class="gift-box" id="gift">
    <h2>禮物盒打開了！</h2>
    <p>你就是我這輩子收到最棒的禮物。</p>
  </div>  <div class="quiz" id="quiz">
    <h2>戀愛小測驗</h2>
    <p>我第一次牽你的手是在？</p>
    <button class="btn">捷運站</button>
    <button class="btn">電影院</button>
    <button class="btn">雨中</button>
  </div>  <div class="closing" id="closing">
    <h2 style="font-size:2em;color:#ff5c8a">I love you baby</h2>
  </div>  <div class="center" id="mainButtons" style="display:none">
    <button class="btn" onclick="showSection('loveNote')">甜言蜜語</button>
    <button class="btn" onclick="showSection('gallery')">我們的回憶</button>
    <button class="btn" onclick="showSection('gift')">禮物盒</button>
    <button class="btn" onclick="showSection('quiz')">戀愛測驗</button>
    <button class="btn" onclick="showSection('closing')">結尾</button>
  </div>  <script>
    const notes = [
      "你笑的樣子，比整個宇宙還閃耀。",
      "你是我每天醒來最想見到的人。",
      "喜歡你，是我最甜蜜的習慣。",
      "愛你，不需要理由，只需要你在。",
      "和你在一起的每一刻，都像在夢裡。"
    ];

    function startExperience() {
      document.getElementById('opening').style.display = 'none';
      document.getElementById('mainButtons').style.display = 'flex';
    }

    function showSection(id) {
      document.querySelectorAll('.love-note, .photo-gallery, .gift-box, .quiz, .closing').forEach(div => div.style.display = 'none');
      document.getElementById(id).style.display = 'block';
      if (id === 'loveNote') newNote();
    }

    function newNote() {
      const random = Math.floor(Math.random() * notes.length);
      document.getElementById('noteText').innerText = notes[random];
    }
  </script></body>
</html>
