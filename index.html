<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dodge Game</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #000;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
        }
        #game-container {
            position: relative;
            width: 80%;
            height: 80%;
            background-color: #222;
            border: 2px solid white;
            overflow: hidden;
        }
        #player {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            width: 40px;
            height: 40px;
            background-color: #4caf50;
            border-radius: 50%;
        }
        .bullet {
            position: absolute;
            width: 20px;
            height: 20px;
            background-color: #f44336;
            border-radius: 50%;
        }
        .bonus {
            position: absolute;
            width: 50px;
            height: 50px;
            border: 2px solid white;
        }
        #timer {
            position: absolute;
            top: 10px;
            left: 50%;
            transform: translateX(-50%);
            color: white;
            font-size: 24px;
        }
        #new-game {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            padding: 20px 40px;
            background-color: #007bff;
            color: white;
            font-size: 24px;
            border: none;
            cursor: pointer;
            display: block;
        }
        #controls {
            position: absolute;
            bottom: 0;
            width: 100%;
            height: 6%;
            display: flex;
        }
        .control-button {
            flex: 1;
            background-color: rgba(255, 255, 255, 0.2);
            color: white;
            font-size: 24px;
            border: none;
            outline: none;
            cursor: pointer;
        }
        .control-button:active {
            background-color: rgba(255, 255, 255, 0.4);
        }
        /* New player shield animation */
        .shield {
            background-color: #2196F3;
            animation: blink 0.3s infinite;
        }
        @keyframes blink {
            50% {
                opacity: 0.5;
            }
        }
        /* Poison animation */
        .poison {
            background-color: #9c27b0;
            animation: blinkPoison 0.15s infinite;
        }
        @keyframes blinkPoison {
            50% {
                opacity: 0.5;
            }
        }
    </style>
</head>
<body>
    <div id="game-container">
        <div id="timer">60</div>
        <div id="player"></div>
        <button id="new-game">НОВАЯ ИГРА</button>
        <div id="controls">
            <button class="control-button" id="left-button">←</button>
            <button class="control-button" id="right-button">→</button>
        </div>
    </div>
    <audio id="bg-music" src="fon.mp3" loop></audio>
    <audio id="bullet-sound" src="puli.mp3"></audio>
    <audio id="win-sound" src="win.mp3"></audio>
    <audio id="lose-sound" src="lose.mp3"></audio>
    <script>
        const gameContainer = document.getElementById('game-container');
        const player = document.getElementById('player');
        const timer = document.getElementById('timer');
        const newGameButton = document.getElementById('new-game');
        const leftButton = document.getElementById('left-button');
        const rightButton = document.getElementById('right-button');
        const bgMusic = document.getElementById('bg-music');
        const bulletSound = document.getElementById('bullet-sound');
        const winSound = document.getElementById('win-sound');
        const loseSound = document.getElementById('lose-sound');

        let gameInterval;
        let bulletInterval;
        let bonusInterval;
        let timeLeft = 77;
        let isGameRunning = false;
        let bulletSpeed = 2;
        let bullets = [];
        let bonuses = [];
        let shieldActive = false;
        let stage = 1;

        function startGame() {
            isGameRunning = true;
            timeLeft = 77;
            stage = 1;
            bulletSpeed = 2;
            timer.textContent = timeLeft;
            newGameButton.style.display = 'none';
            bullets.forEach(bullet => bullet.remove());
            bonuses.forEach(bonus => bonus.remove());
            bullets = [];
            bonuses = [];
            shieldActive = false;
            player.classList.remove('shield', 'poison');
            player.style.left = '50%';
            bgMusic.play();

            gameInterval = setInterval(updateGame, 16);
            bulletInterval = setInterval(createBullet, 1000);
            bonusInterval = setInterval(createBonus, 8000); // increased frequency of bonuses
        }

        function endGame(win = false) {
            isGameRunning = false;
            clearInterval(gameInterval);
            clearInterval(bulletInterval);
            clearInterval(bonusInterval);
            bullets.forEach(bullet => bullet.remove());
            bonuses.forEach(bonus => bonus.remove());
            bullets = [];
            bonuses = [];
            bgMusic.pause();
            bgMusic.currentTime = 0;

            if (win) {
                winSound.play();
                timer.textContent = 'ПОБЕДА!';
            } else {
                loseSound.play();
                timer.textContent = 'ИГРА ОКОНЧЕНА';
            }

            newGameButton.style.display = 'block';
        }

        function createBullet() {
            if (!isGameRunning) return;
            const bullet = document.createElement('div');
            bullet.classList.add('bullet');
            bullet.style.left = Math.random() * (gameContainer.clientWidth - 20) + 'px';
            bullet.style.top = '-20px';
            gameContainer.appendChild(bullet);
            bullets.push(bullet);
            bulletSound.play();
        }

        function createBonus() {
            if (!isGameRunning) return;
            const bonus = document.createElement('div');
            bonus.classList.add('bonus');
            const bonusType = Math.ceil(Math.random() * 4);
            bonus.dataset.type = bonusType;
            bonus.style.left = Math.random() * (gameContainer.clientWidth - 10) + 'px';
            bonus.style.top = '-10px';
            bonus.style.backgroundImage = `url(${bonusType.toString().padStart(3, '0')}.jpg)`;
            bonus.style.backgroundSize = 'cover';
            gameContainer.appendChild(bonus);
            bonuses.push(bonus);
        }

        function applyBonus(bonusType) {
            switch (bonusType) {
                case '1': // Slow bullets
                    bulletSpeed /= 3;
                    setTimeout(() => bulletSpeed *= 3, 3000);
                    break;
                case '2': // Delayed death (Poison)
                    player.classList.add('poison');
                    setTimeout(() => endGame(false), 3000);
                    break;
                case '3': // Shield
                    shieldActive = true;
                    player.classList.add('shield');
                    setTimeout(() => {
                        shieldActive = false;
                        player.classList.remove('shield');
                    }, 3000);
                    break;
                case '4': // More bullets
                    for (let i = 0; i < stage + 1; i++) {
                        setInterval(createBullet, 500);
                    }
                    setTimeout(() => {
                        clearInterval(bulletInterval);
                        bulletInterval = setInterval(createBullet, 1000);
                    }, 2000);
                    break;
            }
        }

        function updateGame() {
            // Stage adjustments
            if (timeLeft <= 33) {
                stage = Math.min(Math.floor((77 - timeLeft) / 11) + 1, 7);
                if (stage >= 4) {
                    gameContainer.style.backgroundColor = '#3e2723';
                }
            }

            // Update bullets
            bullets.forEach((bullet, index) => {
                const top = parseFloat(bullet.style.top);
                bullet.style.top = top + bulletSpeed + 'px';

                if (top > gameContainer.clientHeight) {
                    bullet.remove();
                    bullets.splice(index, 1);
                }

                // Check collision
                const bulletRect = bullet.getBoundingClientRect();
                const playerRect = player.getBoundingClientRect();
                if (
                    bulletRect.left < playerRect.right &&
                    bulletRect.right > playerRect.left &&
                    bulletRect.top < playerRect.bottom &&
                    bulletRect.bottom > playerRect.top
                ) {
                    if (!shieldActive) {
                        endGame(false);
                    }
                }
            });

            // Update bonuses
            bonuses.forEach((bonus, index) => {
                const top = parseFloat(bonus.style.top);
                bonus.style.top = top + 2 + 'px';

                if (top > gameContainer.clientHeight) {
                    bonus.remove();
                    bonuses.splice(index, 1);
                }

                // Check collision
                const bonusRect = bonus.getBoundingClientRect();
                const playerRect = player.getBoundingClientRect();
                if (
                    bonusRect.left < playerRect.right &&
                    bonusRect.right > playerRect.left &&
                    bonusRect.top < playerRect.bottom &&
                    bonusRect.bottom > playerRect.top
                ) {
                    applyBonus(bonus.dataset.type);
                    bonus.remove();
                    bonuses.splice(index, 1);
                }
            });

            // Update timer
            timeLeft -= 0.016;
            timer.textContent = Math.ceil(timeLeft);

            if (timeLeft <= 0) {
                endGame(true);
            }
        }

        function movePlayer(direction) {
            if (!isGameRunning) return;

            const playerRect = player.getBoundingClientRect();
            const containerRect = gameContainer.getBoundingClientRect();

            if (direction === 'left' && playerRect.left > containerRect.left + 2) {
                player.style.left = player.offsetLeft - 15 + 'px';
            } else if (direction === 'right' && playerRect.right < containerRect.right - 2) {
                player.style.left = player.offsetLeft + 15 + 'px';
            }
        }

        document.addEventListener('keydown', (e) => {
            if (e.key === 'ArrowLeft') {
                movePlayer('left');
            } else if (e.key === 'ArrowRight') {
                movePlayer('right');
            }
        });

        leftButton.addEventListener('touchstart', () => movePlayer('left'));
        rightButton.addEventListener('touchstart', () => movePlayer('right'));

        newGameButton.addEventListener('click', startGame);
    </script>
</body>
</html>
