---
title: Create a simple javascript game under 5 minutes 
categories: ai
tags: [ai,chatgpt,games]
---

# 👋 First Post

<div style="position:relative;">
<canvas id="gameCanvas" style="display: block;background-color: #70c5ce;width:100%;aspect-ratio: 8 / 6;"></canvas>
<button id="startButton" style="position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            padding: 10px 20px;
            font-size: 20px;
            background-color: #ffeb3b;
            border: none;
            z-index:1000;
            cursor: pointer;">Start</button>
</div>
<script>
const canvas = document.getElementById('gameCanvas');
const ctx = canvas.getContext('2d');
const startButton = document.getElementById('startButton');

canvas.width = 800;
canvas.height = 600;

const bird = {
    x: 50,
    y: 150,
    width: 20,
    height: 20,
    gravity: 0.6,
    lift: -15,
    velocity: 0
};

let pipes = [];
const pipeWidth = 50;
const pipeGap = 150;
let frameCount = 0;
let score = 0;
let gameRunning = false;

document.addEventListener('keydown', () => {
    if (gameRunning) {
        bird.velocity = bird.lift;
    }
});

startButton.addEventListener('click', () => {
    startButton.style.display = 'none';
    resetGame();
    gameRunning = true;
    gameLoop();
});

function drawBird() {
    ctx.fillStyle = '#ffeb3b';
    ctx.fillRect(bird.x, bird.y, bird.width, bird.height);
}

function drawPipes() {
    ctx.fillStyle = '#4caf50';
    pipes.forEach(pipe => {
        ctx.fillRect(pipe.x, 0, pipeWidth, pipe.top);
        ctx.fillRect(pipe.x, canvas.height - pipe.bottom, pipeWidth, pipe.bottom);
    });
}

function updatePipes() {
    if (frameCount % 100 === 0) {
        const topHeight = Math.floor(Math.random() * (canvas.height - pipeGap));
        const bottomHeight = canvas.height - topHeight - pipeGap;
        pipes.push({
            x: canvas.width,
            top: topHeight,
            bottom: bottomHeight,
            passed: false
        });
    }

    pipes.forEach(pipe => {
        pipe.x -= 2;
    });

    pipes = pipes.filter(pipe => pipe.x + pipeWidth > 0);
}

function drawScore() {
    ctx.fillStyle = '#fff';
    ctx.font = '20px Arial';
    ctx.fillText(`Score: ${score}`, 10, 20);
}

function updateBird() {
    bird.velocity += bird.gravity;
    bird.y += bird.velocity;

    if (bird.y + bird.height > canvas.height || bird.y < 0) {
        endGame();
    }
}

function checkCollision() {
    pipes.forEach(pipe => {
        if (
            bird.x < pipe.x + pipeWidth &&
            bird.x + bird.width > pipe.x &&
            (bird.y < pipe.top || bird.y + bird.height > canvas.height - pipe.bottom)
        ) {
            endGame();
        }

        if (pipe.x + pipeWidth < bird.x && !pipe.passed) {
            score++;
            pipe.passed = true;
        }
    });
}

function resetGame() {
    bird.y = 150;
    bird.velocity = 0;
    pipes = [];
    score = 0;
    frameCount = 0;
    gameRunning = true;
}

function endGame() {
    gameRunning = false;
    startButton.style.display = 'block';
}

function gameLoop() {
    if (gameRunning) {
        ctx.clearRect(0, 0, canvas.width, canvas.height);

        drawBird();
        drawPipes();
        drawScore();
        
        updateBird();
        updatePipes();
        checkCollision();

        frameCount++;
        requestAnimationFrame(gameLoop);
    }
}

</script>

Press any key to fly.

If you are reading this is because you are one of the first visitors, otherwise, pleased read other posts, I'm sure I can write better and more engaging content.

Meanwhile enjoy this game ChatGPT prepared for you.

  **Hey ChatGPT**: 
```
act like a senior javascript web videogame.
Creaate an engaging, simple,flappy bird style, don't use any external asset.
Add an start button.
```

See you later!




