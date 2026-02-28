<!DOCTYPE html>
<html>
<head>
    <title>Catch The Box Game</title>
    <style>
        body {
            margin: 0;
            background: linear-gradient(to right, #141E30, #243B55);
            font-family: Arial;
            text-align: center;
            color: white;
        }

        h1 {
            margin-top: 20px;
        }

        #gameArea {
            width: 600px;
            height: 400px;
            background: #1c1c1c;
            margin: 20px auto;
            position: relative;
            border-radius: 10px;
            border: 3px solid white;
            overflow: hidden;
        }

        #box {
            width: 50px;
            height: 50px;
            background: red;
            position: absolute;
            cursor: pointer;
            border-radius: 8px;
        }

        #score {
            font-size: 20px;
        }

        button {
            padding: 10px 20px;
            border: none;
            background: #00c3ff;
            color: black;
            font-weight: bold;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            background: #00ff99;
        }
    </style>
</head>
<body>

<h1>🎮 Catch The Box</h1>
<p id="score">Score: 0</p>
<button onclick="startGame()">Start Game</button>

<div id="gameArea">
    <div id="box" onclick="addScore()"></div>
</div>

<script>
    let score = 0;
    let gameInterval;

    function startGame() {
        score = 0;
        document.getElementById("score").innerText = "Score: " + score;

        gameInterval = setInterval(moveBox, 800);
    }

    function moveBox() {
        let box = document.getElementById("box");
        let gameArea = document.getElementById("gameArea");

        let maxX = gameArea.clientWidth - box.clientWidth;
        let maxY = gameArea.clientHeight - box.clientHeight;

        let randomX = Math.floor(Math.random() * maxX);
        let randomY = Math.floor(Math.random() * maxY);

        box.style.left = randomX + "px";
        box.style.top = randomY + "px";
    }

    function addScore() {
        score++;
        document.getElementById("score").innerText = "Score: " + score;
    }
</script>

</body>
</html>
