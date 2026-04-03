<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pro Colour Trading Panel</title>
<style>
    body {
        margin: 0;
        font-family: Arial, sans-serif;
        background: #0f172a;
        color: white;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        height: 100vh;
    }

    h1 {
        margin-bottom: 10px;
        font-size: 28px;
        letter-spacing: 2px;
    }

    .panel {
        background: #1e293b;
        padding: 20px;
        border-radius: 20px;
        box-shadow: 0 0 25px rgba(0,0,0,0.5);
        text-align: center;
        width: 300px;
    }

    .display-box {
        border: 3px solid #22c55e;
        border-radius: 20px;
        height: 120px;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 48px;
        margin-bottom: 20px;
    }

    .buttons {
        display: flex;
        justify-content: space-between;
        gap: 10px;
    }

    button {
        flex: 1;
        padding: 10px;
        border: none;
        border-radius: 10px;
        font-size: 16px;
        cursor: pointer;
        transition: 0.2s;
    }

    .green { background: #22c55e; color: black; }
    .red { background: #ef4444; color: white; }
    .blue { background: #3b82f6; color: white; }

    button:hover {
        opacity: 0.8;
        transform: scale(1.05);
    }

    .result {
        margin-top: 15px;
        font-size: 18px;
        font-weight: bold;
    }
</style>
</head>
<body>

<h1>𝐙𝐗10𝐑_𝐓𝐗</h1>

<div class="panel">
    <div class="display-box" id="numberBox">--</div>

    <div class="buttons">
        <button class="green" onclick="bet('Green')">Green</button>
        <button class="red" onclick="bet('Red')">Red</button>
        <button class="blue" onclick="bet('Blue')">Blue</button>
    </div>

    <button style="margin-top:15px;width:100%;" onclick="generate()">SHOW RESULT</button>

    <div class="result" id="resultText"></div>
</div>

<script>
    let hasPlayed = false;

    function generate() {
        if (hasPlayed) {
            alert("Wait for next round (1 minute)");
            return;
        }

        let num = Math.floor(Math.random() * 10);
        document.getElementById("numberBox").innerText = num;

        let color;
        if (num <= 3) color = "Red";
        else if (num <=
