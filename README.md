<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<title>Untuk Kamu ❤️</title>

<style>
body {
  margin: 0;
  font-family: 'Segoe UI', sans-serif;
  background: black;
  color: white;
  overflow: hidden;
  text-align: center;
}

#startScreen, #mainContent {
  position: absolute;
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}

#mainContent {
  display: none;
  background: linear-gradient(135deg, #ff758c, #ff7eb3);
}

button {
  padding: 12px 20px;
  border: none;
  border-radius: 20px;
  background: white;
  color: #ff4d6d;
  font-size: 1em;
  cursor: pointer;
}

h1 {
  font-size: 2.5em;
}

#text {
  width: 70%;
  margin-top: 20px;
  font-size: 1.3em;
  line-height: 1.6;
}

/* efek bintang */
.star {
  position: absolute;
  width: 2px;
  height: 2px;
  background: white;
  animation: twinkle 2s infinite;
}

@keyframes twinkle {
  0%,100% {opacity: 0;}
  50% {opacity: 1;}
}
</style>
</head>

<body>

<!-- Opening -->
<div id="startScreen">
  <h1>Ada sesuatu buat kamu 💌</h1>
  <button onclick="start()">Buka</button>
</div>

<!-- Main -->
<div id="mainContent">
  <h1>Selamat Ulang Tahun, Sayang ❤️</h1>
  <div id="text"></div>
</div>

<audio id="music" loop>
  <source src="https://www.bensound.com/bensound-music/bensound-love.mp3">
</audio>

<script>
const message = `Hari ini bukan cuma tentang bertambahnya usia kamu.

Tapi tentang betapa beruntungnya aku,
karena di antara banyak kemungkinan di dunia ini,
aku dipertemukan dengan kamu.

Kamu bukan sekadar "seseorang",
kamu adalah cerita yang ingin aku baca berulang-ulang.

Semoga kamu selalu bahagia,
dan kalau boleh jujur...
aku ingin jadi bagian dari bahagia itu, selalu.

Selamat ulang tahun, sayang ❤️`;

let i = 0;

function start() {
  document.getElementById("startScreen").style.display = "none";
  document.getElementById("mainContent").style.display = "flex";
  document.getElementById("music").play();
  typing();
}

function typing() {
  if (i < message.length) {
    document.getElementById("text").innerHTML += message.charAt(i);
    i++;
    setTimeout(typing, 40);
  }
}

// bintang random
for (let i = 0; i < 100; i++) {
  let star = document.createElement("div");
  star.classList.add("star");
  star.style.top = Math.random() * 100 + "%";
  star.style.left = Math.random() * 100 + "%";
  document.body.appendChild(star);
}
</script>

</body>
</html>
