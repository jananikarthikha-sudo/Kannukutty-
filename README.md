# Kannukutty-
To kannukutty withlove Janani 🤍💗✨
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Kannukutty ⚡❤️</title>
    <style>
        :root {
            --gryffindor-red: #740001;
            --hogwarts-gold: #ffd700;
            --parchment: #f4e4bc;
        }

        body {
            background: radial-gradient(circle, #2b0000 0%, #000000 100%);
            margin: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Georgia', serif;
            overflow: hidden;
            color: var(--hogwarts-gold);
        }

        /* Extra Decorations: Floating Hearts & Snitches */
        .decorations span {
            position: absolute;
            font-size: 25px;
            animation: floatUp 6s linear infinite;
            opacity: 0.7;
            z-index: 1;
        }

        @keyframes floatUp {
            0% { transform: translateY(110vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }

        /* Envelope Styling */
        .wrapper { z-index: 10; text-align: center; }
        
        .envelope-wrapper {
            position: relative;
            width: 300px;
            height: 200px;
            background: var(--parchment);
            cursor: pointer;
            margin: 0 auto;
            transition: 0.5s;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }

        .flap {
            position: absolute;
            top: 0; width: 0; height: 0;
            border-left: 150px solid transparent;
            border-right: 150px solid transparent;
            border-top: 100px solid #d4c49c;
            transform-origin: top;
            transition: 0.6s;
            z-index: 3;
        }

        .envelope-wrapper.open .flap { transform: rotateX(180deg); }

        .letter {
            position: absolute;
            bottom: 0; left: 10px;
            width: 280px; height: 180px;
            background: white;
            transition: 0.9s;
            z-index: 2;
            padding: 20px;
            box-sizing: border-box;
            color: #333;
            border: 2px solid #8b4513;
            overflow-y: auto;
            text-align: left;
        }

        .envelope-wrapper.open .letter { bottom: 100px; height: 380px; }

        .seal {
            position: absolute;
            top: 80px; left: 130px;
            width: 40px; height: 40px;
            background: var(--gryffindor-red);
            border-radius: 50%;
            color: var(--hogwarts-gold);
            display: flex;
            justify-content: center;
            align-items: center;
            font-weight: bold;
            z-index: 5;
            box-shadow: 0 0 10px gold;
        }

        /* Content Styling */
        h2 { color: var(--gryffindor-red); font-size: 18px; margin-top: 0; }
        #story-text { font-size: 14px; line-height: 1.6; font-weight: bold; }
        
        .buttons {
            display: flex;
            gap: 10px;
            margin-top: 20px;
            position: relative;
        }

        button {
            padding: 10px 15px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            flex: 1;
        }

        .yes-btn { background: var(--gryffindor-red); color: var(--hogwarts-gold); border: 2px solid var(--hogwarts-gold); }
        .no-btn { background: #555; color: white; transition: 0.3s; }

        .final-msg {
            color: var(--gryffindor-red);
            font-weight: bold;
            margin-top: 15px;
            display: none;
            animation: fadeIn 1s;
        }

        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
    </style>
</head>
<body>

    <div class="decorations">
        </div>

    <div class="wrapper">
        <div class="envelope-wrapper" id="envelope" onclick="openLetter()">
            <div class="flap"></div>
            <div class="letter" id="letter">
                <h2>Dearest Kannukutty... ⚡</h2>
                <div id="story-text"></div>
                
                <div class="buttons" id="btn-group">
                    <button class="yes-btn" onclick="sayYes()">YES! ❤️</button>
                    <button class="no-btn" id="noBtn" onclick="punishment()">NO ❌</button>
                </div>

                <div id="final" class="final-msg">
                    Love you moreeee kanukutty 🤍💗✨🫂😘<br><br>
                    Happy first valentine's day chellameyyy🤍💗✨
                </div>
            </div>
            <div class="seal">H</div>
        </div>
        <p id="instruction" style="margin-top:20px; font-style: italic;">Tap the Seal to open your magic letter!</p>
    </div>

    <script>
        // Generating random decorations
        const decos = ['❤️', '✨', '⚡', '🦉', '💖', '🧹'];
        const container = document.querySelector('.decorations');
        for (let i = 0; i < 30; i++) {
            const span = document.createElement('span');
            span.innerText = decos[Math.floor(Math.random() * decos.length)];
            span.style.left = Math.random() * 100 + 'vw';
            span.style.animationDelay = Math.random() * 5 + 's';
            container.appendChild(span);
        }

        const myStory = "Naama senthu irukura intha moments ellaமே romba magical-ah iruku. Enna 'Kannu' nu nee kupdurathu thaan enaku romba pudicha magic. Unnoda intha Kannukutty/Chellamma eppovum unakaga kaathirupen. Will you be my Valentine and Always stay with me? ✨";

        function openLetter() {
            document.getElementById('envelope').classList.add('open');
            document.getElementById('instruction').style.opacity = '0';
            setTimeout(typeWriter, 1000);
        }

        let i = 0;
        function typeWriter() {
            if (i < myStory.length) {
                document.getElementById("story-text").innerHTML += myStory.charAt(i);
                i++;
                setTimeout(typeWriter, 50);
            }
        }

        // NO Button Punishment Logic
        function punishment() {
            alert("Ennakaye NO solriya?! 😤 \n\nPunishment: 100,000,000k Kisses and 1 year non-stop Hug thara poran! Ippo YES sollu!");
            // Making the No button disappear so he has to click Yes
            document.getElementById('noBtn').style.display = 'none';
        }

        function sayYes() {
            document.getElementById('btn-group').style.display = 'none';
            document.getElementById('final').style.display = 'block';
            alert("Mischief Managed! I love you so much Kannukutty! ❤️✨");
        }
    </script>
</body>
</html>
