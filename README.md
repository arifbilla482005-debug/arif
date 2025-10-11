
<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Golden Shine Buttons</title>
<style>
body {
  margin: 0;
  font-family: "Poppins", sans-serif;
  background: radial-gradient(circle at top, #1a1a1a, #000);
  display: flex;
  flex-direction: column;
  align-items: center;
  min-height: 100vh;
  color: #f5d76e;
}

/* উপরের টাইটেল */
h1 {
  margin-top: 30px;
  margin-bottom: 15px;
  font-size: 26px;
  color: #ffd700;
  text-shadow: 0 0 15px gold;
}

/* বাটনের গ্রিড */
.button-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 30px 18px;
  padding: 15px;
  width: 90%;
  max-width: 700px;
  justify-items: center;
}

/* বাটনের স্টাইল */
button {
  position: relative;
  width: 95%;
  max-width: 260px;
  height: 36px; /* আগের 48px থেকে কমানো (চিকন) */
  background: linear-gradient(145deg, #d4af37, #f5e08c);
  color: #111;
  border: 2px solid #f5d76e;
  border-radius: 40px;
  font-size: 17px;
  font-weight: 600;
  cursor: pointer;
  overflow: hidden;
  transition: all 0.3s ease;
  box-shadow: 0 0 10px rgba(255, 215, 0, 0.4);
}

/* Shine effect */
button::before {
  content: "";
  position: absolute;
  top: 0;
  left: -80px;
  width: 60px;
  height: 100%;
  background: linear-gradient(120deg, transparent, rgba(255,255,255,0.8), transparent);
  animation: shine 4.5s infinite linear;
  transform: skewX(-20deg);
  will-change: left;
}

@keyframes shine {
  0% { left: -80px; }
  50% { left: 130%; }
  100% { left: 130%; }
}

/* Hover effect */
button:hover {
  transform: scale(1.07) translateY(-3px);
  background: linear-gradient(145deg, #ffe46b, #ffd700);
  box-shadow: 0 0 25px rgba(255, 255, 0, 0.7);
}

/* Click effect */
button:active {
  transform: scale(1.1) translateY(-2px);
  background: linear-gradient(145deg, #e8ffb3, #d4af37);
  box-shadow: 0 0 25px rgba(0, 255, 100, 0.5);
}

/* ভিডিও পপআপ */
.video-popup {
  display: none;
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.85);
  justify-content: center;
  align-items: center;
  z-index: 999;
}

.video-popup iframe {
  width: 90%;
  max-width: 360px;
  height: 600px;
  border: none;
  border-radius: 12px;
  box-shadow: 0 0 25px gold;
}

.close-btn {
  position: absolute;
  top: 20px; right: 30px;
  font-size: 30px;
  color: #fff;
  cursor: pointer;
  font-weight: bold;
}
</style>
</head>
<body>

<h1>✨ গোল্ডেন রিং ভিডিও বাটন ✨</h1>

<div class="button-container">
  <button data-video="https://www.youtube.com/embed/nEOoL6gW-Fs?autoplay=1">ভিডিও ১</button>
  <button data-video="https://www.youtube.com/embed/yourlink2?autoplay=1">ভিডিও ২</button>
  <button data-video="https://www.youtube.com/embed/yourlink3?autoplay=1">ভিডিও ৩</button>
  <button data-video="https://www.youtube.com/embed/yourlink4?autoplay=1">ভিডিও ৪</button>
  <button data-video="https://www.youtube.com/embed/yourlink5?autoplay=1">ভিডিও ৫</button>
  <button data-video="https://www.youtube.com/embed/yourlink6?autoplay=1">ভিডিও ৬</button>
  <button data-video="https://www.youtube.com/embed/yourlink7?autoplay=1">ভিডিও ৭</button>
  <button data-video="https://www.youtube.com/embed/yourlink8?autoplay=1">ভিডিও ৮</button>
  <button data-video="https://www.youtube.com/embed/yourlink9?autoplay=1">ভিডিও ৯</button>
  <button data-video="https://www.youtube.com/embed/yourlink10?autoplay=1">ভিডিও ১০</button>
</div>

<!-- 🎬 ভিডিও পপআপ -->
<div class="video-popup" id="popup">
  <span class="close-btn" id="close">&times;</span>
  <iframe id="videoFrame" allowfullscreen></iframe>
</div>

<script>
const buttons = document.querySelectorAll("button");
const popup = document.getElementById("popup");
const videoFrame = document.getElementById("videoFrame");
const closeBtn = document.getElementById("close");

buttons.forEach(btn => {
  btn.addEventListener("click", () => {
    const videoUrl = btn.getAttribute("data-video");
    videoFrame.src = videoUrl;
    popup.style.display = "flex";
  });
});

closeBtn.addEventListener("click", () => {
  popup.style.display = "none";
  videoFrame.src = "";
});
</script>

</body>
</html>