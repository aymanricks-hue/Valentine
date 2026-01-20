<!DOCTYPE html>  
<html lang="en">  
<head>  
<meta charset="UTF-8" />  
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>  
<title>For Oyshe 💖</title>  
  
<style>  
    body {  
        margin: 0;  
        height: 100vh;  
        background: linear-gradient(135deg, #ff9a9e, #fad0c4);  
        display: flex;  
        justify-content: center;  
        align-items: center;  
        font-family: 'Poppins', sans-serif;  
        overflow: hidden;  
    }  
  
    .container {  
        background: white;  
        padding: 30px;  
        border-radius: 20px;  
        text-align: center;  
        box-shadow: 0 15px 40px rgba(0,0,0,0.25);  
        max-width: 350px;  
        width: 90%;  
        position: relative;  
    }  
  
    h1 {  
        color: #ff4d6d;  
        margin-bottom: 10px;  
    }  
  
    p {  
        color: #555;  
    }  
  
    .buttons {  
        margin-top: 25px;  
        position: relative;  
        height: 60px;  
    }  
  
    button {  
        padding: 12px 25px;  
        font-size: 16px;  
        border: none;  
        border-radius: 30px;  
        cursor: pointer;  
        transition: 0.3s;  
        position: absolute;  
    }  
  
    .yes {  
        background: #ff4d6d;  
        color: white;  
        left: 20%;  
    }  
  
    .yes:hover {  
        transform: scale(1.1);  
    }  
  
    .no {  
        background: #ccc;  
        right: 20%;  
    }  
  
    .result {  
        display: none;  
        margin-top: 20px;  
    }  
  
    .emoji {  
        font-size: 90px;  
        animation: pop 1s ease infinite alternate;  
    }  
  
    @keyframes pop {  
        from { transform: scale(1); }  
        to { transform: scale(1.1); }  
    }  
  
    .confetti {  
        position: fixed;  
        width: 10px;  
        height: 10px;  
        animation: fall 3s linear infinite;  
        opacity: 0.9;  
    }  
  
    @keyframes fall {  
        from { transform: translateY(-10px) rotate(0deg); }  
        to { transform: translateY(100vh) rotate(360deg); }  
    }  
</style>  
</head>  
  
<body>  
  
<audio id="bgMusic" loop>  
    <source src="https://cdn.pixabay.com/audio/2023/02/28/audio_4a4c5dbf8d.mp3" type="audio/mpeg">  
</audio>  
  
<div class="container">  
    <h1>Oyshe 💖</h1>  
    <p>Will you be my Valentine?</p>  
  
    <div class="buttons">  
        <button class="yes" onclick="yesClicked()">Yes ❤️</button>  
        <button class="no" id="noBtn" onclick="noClicked()">No 💔</button>  
    </div>  
  
    <div class="result" id="result"></div>  
</div>  
  
<script>  
let noMoves = 0;  
  
document.body.addEventListener("click", () => {  
    document.getElementById("bgMusic").play();  
}, { once: true });  
  
const noBtn = document.getElementById("noBtn");  
  
noBtn.addEventListener("mouseover", () => {  
    if (noMoves < 5) {  
        const x = Math.random() * 200 - 100;  
        const y = Math.random() * 80 - 40;  
        noBtn.style.transform = `translate(${x}px, ${y}px)`;  
        noMoves++;  
    }  
});  
  
function yesClicked() {  
    document.getElementById("result").style.display = "block";  
    document.getElementById("result").innerHTML = `  
        <div class="emoji">🎉🥰💖</div>  
        <h2>YAY Oyshe!!! 💕</h2>  
        <p>You just made my Valentine perfect 🥹❤️</p>  
    `;  
    createConfetti();  
}  
  
function noClicked() {  
    document.getElementById("result").style.display = "block";  
    document.getElementById("result").innerHTML = `  
        <div class="emoji">😭</div>  
        <h2>The poor boy is crying…</h2>  
        <p>Look what you did 💔</p>  
    `;  
}  
  
function createConfetti() {  
    for (let i = 0; i < 100; i++) {  
        let confetti = document.createElement("div");  
        confetti.className = "confetti";  
        confetti.style.left = Math.random() * 100 + "vw";  
        confetti.style.backgroundColor =  
            ["#ff4d6d","#ffd166","#06d6a0","#4d96ff"][Math.floor(Math.random()*4)];  
        confetti.style.animationDuration = (Math.random() * 2 + 2) + "s";  
        document.body.appendChild(confetti);  
        setTimeout(() => confetti.remove(), 3000);  
    }  
}  
</script>  
  
</body>  
</html>  
