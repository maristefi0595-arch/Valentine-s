# Valentine-s
<!DOCTYPE html>
<html lang="ro">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Valentine 💖</title>

<style>
    body {
        margin: 0;
        height: 100vh;
        overflow: hidden;
        font-family: Arial, sans-serif;
        background: linear-gradient(135deg, #ff9a9e, #fad0c4);
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
    }

    .card {
        background: white;
        padding: 30px 20px;
        border-radius: 25px;
        box-shadow: 0 15px 30px rgba(0,0,0,0.25);
        width: 90%;
        max-width: 400px;
        position: relative;
        z-index: 2;
    }

    h1 {
        font-size: 24px;
        margin-bottom: 25px;
    }

    button {
        font-size: 18px;
        padding: 12px 25px;
        border: none;
        border-radius: 12px;
        cursor: pointer;
        margin: 10px;
    }

    #yes {
        background-color: #ff4d6d;
        color: white;
    }

    #no {
        background-color: #ccc;
        position: absolute;
    }

    .heart {
        position: absolute;
        animation: floatUp 6s linear infinite;
        opacity: 0.8;
        pointer-events: none;
    }

    @keyframes floatUp {
        0% {
            transform: translateY(100vh) scale(1);
            opacity: 1;
        }
        100% {
            transform: translateY(-10vh) scale(1.5);
            opacity: 0;
        }
    }
</style>
</head>
<body>

<div class="card">
    <h1>💘 Vrei să fii partenera mea de Valentine’s Day? 💘</h1>

    <button id="yes" onclick="yesClick()">DA</button>
    <button id="no" ontouchstart="moveNo()" onmouseover="moveNo()">NU</button>
</div>

<script>
    function yesClick() {
        document.body.innerHTML = `
        <div style="
            height:100vh;
            display:flex;
            justify-content:center;
            align-items:center;
            flex-direction:column;
            background:linear-gradient(135deg,#ff9a9e,#fad0c4);
            font-family:Arial;
            text-align:center;
        ">
            <h1>💖 Știam eu!!! 💖</h1>
            <h2>Ne vedem de Valentine’s Day 🥰</h2>
        </div>
        `;
    }

    function moveNo() {
        const noBtn = document.getElementById("no");
        const x = Math.random() * (window.innerWidth - 120);
        const y = Math.random() * (window.innerHeight - 60);
        noBtn.style.left = x + "px";
        noBtn.style.top = y + "px";
    }

    // Inimioare animate
    setInterval(() => {
        const heart = document.createElement("div");
        heart.className = "heart";
        heart.innerHTML = "❤️";
        heart.style.left = Math.random() * window.innerWidth + "px";
        heart.style.fontSize = (Math.random() * 20 + 15) + "px";
        document.body.appendChild(heart);

        setTimeout(() => heart.remove(), 6000);
    }, 300);
</script>

</body>
</html>
