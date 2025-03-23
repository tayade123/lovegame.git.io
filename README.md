# lovegame.git.io
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Love Game</title>
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #fff0f3;
            text-align: center;
            color: #590d22;
        }
        header {
            background-color: #ff4d6d;
            color: white;
            padding: 20px;
            font-size: 24px;
            font-weight: bold;
        }
        .container {
            max-width: 900px;
            margin: auto;
            padding: 20px;
        }
        .game-box, .quiz-box, .fortune-box {
            background: #ffccd5;
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            margin: 30px auto;
            max-width: 90%;
        }
        .button {
            background: #ff4d6d;
            color: white;
            padding: 15px 30px;
            border: none;
            font-size: 18px;
            border-radius: 8px;
            cursor: pointer;
            margin-top: 20px;
            transition: 0.3s;
            width: 100%;
            max-width: 300px;
        }
        .button:hover {
            background: #590d22;
        }
        .love-result {
            font-size: 24px;
            font-weight: bold;
            margin-top: 20px;
        }
        .question {
            font-size: 18px;
            margin-top: 10px;
        }
        input {
            padding: 10px;
            margin: 10px;
            border: 1px solid #ff4d6d;
            border-radius: 5px;
            font-size: 16px;
            width: 80%;
            max-width: 300px;
        }
        @media (max-width: 600px) {
            header {
                font-size: 20px;
            }
            .button {
                font-size: 16px;
                padding: 12px;
            }
            .love-result {
                font-size: 20px;
            }
        }
    </style>
</head>
<body>
    <header>Love Match Game ❤️</header>
    <div class="container">
        <section class="game-box">
            <h2>Find Your Love Percentage! 💖</h2>
            <p>Enter two names to see how much love is in the air!</p>
            <input type="text" id="name1" placeholder="Your Name">
            <input type="text" id="name2" placeholder="Partner's Name">
            <br>
            <button class="button" onclick="calculateLove()">Check Love</button>
            <div class="love-result" id="result"></div>
        </section>
        
        <section class="quiz-box">
            <h2>Love Compatibility Quiz 💘</h2>
            <p>Answer a few fun questions to test your love compatibility!</p>
            <div class="question">Do you like the same hobbies?</div>
            <button class="button" onclick="quizResult(1)">Yes</button>
            <button class="button" onclick="quizResult(0)">No</button>
            
            <div class="question">Do you support each other's dreams?</div>
            <button class="button" onclick="quizResult(1)">Yes</button>
            <button class="button" onclick="quizResult(0)">No</button>
            
            <div class="question">Do you enjoy spending time together?</div>
            <button class="button" onclick="quizResult(1)">Yes</button>
            <button class="button" onclick="quizResult(0)">No</button>
            
            <div class="love-result" id="quizResult"></div>
        </section>
        
        <section class="fortune-box">
            <h2>Love Fortune Teller 🔮</h2>
            <p>Click below to reveal your romantic fortune!</p>
            <button class="button" onclick="loveFortune()">Reveal Fortune</button>
            <div class="love-result" id="fortuneResult"></div>
        </section>
    </div>
    
    <script>
        function calculateLove() {
            let name1 = document.getElementById("name1").value;
            let name2 = document.getElementById("name2").value;
            if(name1 === "" || name2 === "") {
                document.getElementById("result").innerHTML = "Please enter both names!";
                return;
            }
            let loveScore = Math.floor(Math.random() * 100) + 1;
            document.getElementById("result").innerHTML = `💞 Love Score: ${loveScore}% 💞`;
        }
        
        let score = 0;
        function quizResult(value) {
            score += value;
            let compatibility = (score / 3) * 100;
            document.getElementById("quizResult").innerHTML = `💘 Compatibility Score: ${compatibility.toFixed(0)}% 💘`;
        }
        
        function loveFortune() {
            const fortunes = [
                "A romantic surprise is coming your way! 💌",
                "Your love will grow stronger day by day! 🌹",
                "An unexpected admirer is thinking about you! 😍",
                "A special date night is in your future! 🍷",
                "You and your partner are soulmates! 💞",
                "A new romantic adventure awaits you! ✈️",
                "Love is in the air—embrace it! 💖"
            ];
            let randomFortune = fortunes[Math.floor(Math.random() * fortunes.length)];
            document.getElementById("fortuneResult").innerHTML = randomFortune;
        }
    </script>
</body>
</html>
