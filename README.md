<!DOCTYPE html>
<html lang="bn">
<head>
  <meta charset="UTF-8">
  <title>Premium Ludo Medal Tracker</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      text-align: center;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      color: white;
    }

    h1 {
      margin-top: 30px;
      font-size: 28px;
      color: white;
      text-shadow: 2px 2px 8px black;
    }

    .buttons {
      margin: 40px 0;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 15px;
      z-index: 2;
      position: relative;
    }

    button {
      padding: 15px 30px;
      font-size: 18px;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      background: linear-gradient(135deg, rgba(255,204,0,0.9), rgba(255,136,0,0.9));
      color: #fff;
      font-weight: bold;
      box-shadow: 0 6px 12px rgba(0,0,0,0.4);
      transition: transform 0.2s, box-shadow 0.2s;
    }

    button:hover {
      transform: translateY(-3px);
      box-shadow: 0 10px 18px rgba(0,0,0,0.6);
    }

    .container {
      display: none;
      padding: 20px;
      flex: 1;
      color: white;
      position: relative;
    }

    #home { display: block; }

    #medalPage img {
      width: 90%;
      max-width: 350px;
      border-radius: 16px;
      box-shadow: 0 6px 12px rgba(0,0,0,0.7);
      margin: 25px auto;
      display: block;
    }

    #owner {
      font-size: 26px;   /* বড় করা নাম */
      font-weight: bold;
      margin-top: 15px;
      text-shadow: 2px 2px 8px black;
    }

    #liveMatch {
      font-size: 22px;
      font-weight: bold;
      margin: 20px 0;
      text-shadow: 2px 2px 8px black;
    }

    .backBtn {
      width: 100%;
      padding: 18px;
      background: #2a9d8f;
      border: none;
      font-size: 20px;
      font-weight: bold;
      position: fixed;   /* fixed করে নিচে রাখা */
      bottom: 0;
      left: 0;
      cursor: pointer;
      z-index: 2;
    }

    /* ================== */
    /* হোম এবং মেডেল পেজ ব্যাকগ্রাউন্ড */
    #home {
      background: url('ludo-bg.jpg') no-repeat center center fixed;
      background-size: cover;
    }

    #medalPage {
      background: url('medal-bg.jpg') no-repeat center center fixed;
      background-size: cover;
    }

    /* overlay + blur */
    #home::before,
    #medalPage::before {
      content: "";
      position: absolute;
      top:0; left:0;
      width:100%; height:100%;
      background-color: rgba(0,0,0,0.35);  /* হালকা কালো overlay */
      backdrop-filter: blur(4px);           /* হালকা blur */
      z-index: 1;
    }

    .container > * {
      position: relative;
      z-index: 2;
    }
  </style>
</head>
<body>

  <!-- হোম পেজ -->
  <div id="home" class="container">
    <h1>🎲  Ludo Medal Showdown By Every 10 Match 🎲</h1>
    <div class="buttons">
      <button onclick="openMedal(10)">10</button>
      <button onclick="openMedal(20)">20</button>
      <button onclick="openMedal(30)">30</button>
      <button onclick="openMedal(40)">40</button>
      <button onclick="openMedal(50)">50</button>
      <button onclick="openMedal(60)">60</button>
      <button onclick="openMedal(70)">70</button>


    <div id="liveMatch">📡 লাইভ ম্যাচ:আরিফ বিল্লা VS আলতাফ মাহমুদ : 36 VS 35 
    
</div id= "liveMatch"> ও হয়না ও </div

<div></div>
  <!-- মেডেল পেজ -->
  <div id="medalPage" class="container">
    <h1 id="matchTitle">Match</h1>
    <img id="medalImg" src="medal10.jpg" alt="Medal">
    <div id="owner">আরিফ বিল্লা</div>  <!-- বড় নাম -->
    <button class="backBtn" onclick="goBack()">⬅  Back </button>
  </div>

<script>
    const medals = {
      10: { img: "medal10.jpg", owner: "আলতাফ মাহমুদ is owner of the medal" },
      20: { img: "medal20.jpg", owner: "আলতাফ মাহমুদ is owner of the medal" },
      30: { img: "medal30.jpg", owner: "আলতাফ মাহমুদ is owner of the medal" },
      40: { img: "medal40.jpg", owner: "আরিফ বিল্লা is owner of the medal" },
      50: { img: "medal50.jpg", owner: "আরিফ বিল্লা is owner of the medal" },
      60: { img: "medal60.jpg", owner: "আরিফ বিল্লা is owner of the medal" },
      70: { img: "medal70.jpg", owner: "আরিফ বিল্লা is owner of the medal " }
    };

    function openMedal(num) {
      document.getElementById("home").style.display = "none";
      document.getElementById("medalPage").style.display = "block";
      document.getElementById("matchTitle").innerText = num + " ম্যাচের রিওয়ার্ড মেডেল";
      document.getElementById("medalImg").src = medals[num].img;
      document.getElementById("owner").innerText = medals[num].owner;
    }

    function goBack() {
      document.getElementById("medalPage").style.display = "none";
      document.getElementById("home").style.display = "block";
    }
  </script>

</body>
</html>
