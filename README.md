<html lang="en">
<head>
<meta charset="UTF-8">
<title>Advika ❤️</title>

<style>
body {
  margin: 0;
  padding: 0;
  font-family: 'Arial', sans-serif;
  background: linear-gradient(135deg, #ff6a88, #ff99ac);
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  text-align: center;
}

.container {
  background: white;
  padding: 50px;
  border-radius: 25px;
  box-shadow: 0 20px 60px rgba(0,0,0,0.3);
  max-width: 600px;
  position: relative;
}

h1 { color: #ff2e63; }
h2 { color: #ff4d6d; }

#letter {
  margin-top: 20px;
  font-size: 1.1em;
  min-height: 100px;
  color: #444;
}

.counter {
  margin-top: 15px;
  font-weight: bold;
  color: #ff2e63;
}

.buttons {
  margin-top: 30px;
  position: relative;
  height: 80px;
}

button {
  padding: 12px 28px;
  font-size: 1em;
  border: none;
  border-radius: 30px;
  cursor: pointer;
  transition: 0.3s;
  position: absolute;
}

#yesBtn {
  background-color: #ff2e63;
  color: white;
  left: 30%;
}

#yesBtn:hover {
  transform: scale(1.2);
}

#noBtn {
  background-color: #ccc;
  left: 55%;
}

#message {
  margin-top: 25px;
  font-size: 1.5em;
  color: #ff2e63;
  display: none;
  font-weight: bold;
}

.heart {
  position: fixed;
  font-size: 20px;
  animation: float 4s linear infinite;
  color: #ff4d6d;
}

@keyframes float {
  0% { transform: translateY(100vh); opacity: 0; }
  50% { opacity: 1; }
  100% { transform: translateY(-10vh); opacity: 0; }
}

.explosion {
  position: fixed;
  font-size: 30px;
  animation: explode 1s ease-out forwards;
}

@keyframes explode {
  0% { transform: scale(0); opacity: 1; }
  100% { transform: scale(3); opacity: 0; }
}
</style>
</head>

<body>
<audio autoplay loop>
  <source src="those-eyes.mp3" type="audio/mpeg">
</audio>

<div class="container">
  <h1>Hey Darling 💕</h1>

  <div id="letter"></div>

  <div class="counter" id="counter"></div>

  <h2>Will You Be My Valentine? 💘</h2>

  <div class="buttons">
    <button id="yesBtn">Yes 💖</button>
    <button id="noBtn">No 😢</button>
  </div>

  <div id="message">
    CHOO CHOO 🚂💞  
    You just made me the happiest person alive.  
    . ❤️
  </div>
</div>

<script>
const letterText = `Since 5/7/2025, 
my life has been brighter, softer, happier.

You and me?
We're basically a chaotic choo choo train 🚂💕

Every time I hear "Those Eyes" by New West,
I think about yours.

So I have one very important question...`;

let i = 0;
function typeWriter() {
  if (i < letterText.length) {
    document.getElementById("letter").innerHTML += letterText.charAt(i);
    i++;
    setTimeout(typeWriter, 35);
  }
}
typeWriter();

// Live counter
const startDate = new Date("2025-07-05");
function updateCounter() {
  const now = new Date();
  const diff = now - startDate;
  const days = Math.floor(diff / (1000 * 60 * 60 * 24));
  document.getElementById("counter").innerHTML =
    `We've been together for 224 days ❤️`;
}
updateCounter();
setInterval(updateCounter, 1000);

// YES trap
const noBtn = document.getElementById("noBtn");
let scale = 1;

noBtn.addEventListener("mouseover", () => {
  const x = Math.random() * 350;
  const y = Math.random() * 200;
  noBtn.style.left = x + "px";
  noBtn.style.top = y + "px";

  scale -= 0.1;
  if (scale > 0.1) {
    noBtn.style.transform = `scale(${scale})`;
  }
});

// YES explosion
const yesBtn = document.getElementById("yesBtn");
const message = document.getElementById("message");

yesBtn.addEventListener("click", () => {
  message.style.display = "block";
  yesBtn.innerHTML = "I KNEW IT 😏💞";

  for (let i = 0; i < 40; i++) {
    const boom = document.createElement("div");
    boom.classList.add("explosion");
    boom.innerHTML = "💖";
    boom.style.left = Math.random() * 100 + "vw";
    boom.style.top = Math.random() * 100 + "vh";
    document.body.appendChild(boom);
    setTimeout(() => boom.remove(), 1000);
  }
});

// floating hearts
function createHeart() {
  const heart = document.createElement("div");
  heart.classList.add("heart");
  heart.innerHTML = "❤️";
  heart.style.left = Math.random() * 100 + "vw";
  heart.style.fontSize = (Math.random() * 20 + 10) + "px";
  document.body.appendChild(heart);
  setTimeout(() => heart.remove(), 4000);
}
setInterval(createHeart, 300);

</script>

</body>
</html>
