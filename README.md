# JANAMDIN-KI-HARDIK-SHUBHKAMNAYE
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Bhonduu</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --pink: #ff85a1;
            --soft-white: #fff5f7;
            --panda-black: #333;
        }

        body, html {
            margin: 0;
            padding: 0;
            height: 100%;
            font-family: 'Poppins', sans-serif;
            background-color: var(--soft-white);
            overflow: hidden;
            text-align: center;
        }

        .page {
            display: none;
            height: 100vh;
            width: 100vw;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: absolute;
            transition: all 0.5s ease;
            padding: 20px;
            box-sizing: border-box;
        }

        .active { display: flex; animation: fadeIn 1s ease-in; }

        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        /* Floating Panda/Heart Animations */
        .animation-overlay {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            pointer-events: none;
            z-index: 100;
        }

        /* Styling Elements */
        h1 { font-family: 'Dancing Script', cursive; color: var(--pink); font-size: 2.5rem; }
        .bhondu-img { 
            width: 250px; height: 250px; 
            border-radius: 50%; border: 5px solid var(--pink);
            object-fit: cover; margin: 20px;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {transform: translateY(0);}
            40% {transform: translateY(-20px);}
            60% {transform: translateY(-10px);}
        }

        button, input {
            padding: 12px 25px;
            border-radius: 25px;
            border: 2px solid var(--pink);
            margin: 10px;
            font-size: 1rem;
            outline: none;
        }

        button {
            background: var(--pink);
            color: white;
            cursor: pointer;
            transition: 0.3s;
        }

        button:hover { transform: scale(1.1); background: #ff4d7d; }

        /* Gift Box */
        .gift-box {
            font-size: 100px;
            cursor: pointer;
            transition: transform 0.3s;
        }
        .gift-box:hover { transform: rotate(15deg); }

        .letter-container {
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            max-width: 500px;
            line-height: 1.6;
        }

        .hindi-text { font-size: 1.2rem; color: #555; font-style: italic; }
    </style>
</head>
<body>

    <div class="animation-overlay" id="anime"></div>

    <div class="page active" id="page1">
        <h1>THIS IS FOR YOU MY BHONDUU....</h1>
        <img src="https://drive.google.com/file/d/1QO6l3p3zUNc1sZblGxMvhXaOSW1cT7fQ/view?usp=sharing" class="bhondu-img" alt="Bhondu">
        <input type="password" id="pass" placeholder="Enter Password...">
        <button onclick="checkPassword()">Enter</button>
    </div>

    <div class="page" id="page2">
        <h1>Happy Birthday Pyaaari Bhonduu</h1>
        <img src="https://drive.google.com/file/d/1rdVd6sgKWsodlG2BhqGrRQnK875DrOVe/view?usp=sharing" style="width: 80%; max-width: 500px; border-radius: 15px;" alt="Collage">
        <button onclick="nextPage(3)">Next ❤️</button>
    </div>

    <div class="page" id="page3">
        <h1>Click to Open</h1>
        <div class="gift-box" id="box" onclick="openGift()">🎁</div>
        <div id="gift-content" style="display:none;">
            <img src="https://drive.google.com/file/d/1QO6l3p3zUNc1sZblGxMvhXaOSW1cT7fQ/view?usp=sharing" class="bhondu-img" alt="Surprise">
            <p><strong>Cutest thing in the whole world!</strong></p>
            <button onclick="nextPage(4)">Continue</button>
        </div>
    </div>

    <div class="page" id="page4">
        <img src="https://drive.google.com/file/d/1QO6l3p3zUNc1sZblGxMvhXaOSW1cT7fQ/view?usp=sharing" class="bhondu-img" alt="Elegance">
        <p class="hindi-text">"आपका व्यक्तित्व उस अलौकिक आभा के समान है, जो बिना किसी श्रृंगार के भी मन को मुग्ध कर लेती है। आपकी सादगी ही आपका वास्तविक सौंदर्य है।"</p>
        <button onclick="nextPage(5)">One last thing...</button>
    </div>

    <div class="page" id="page5">
        <div class="letter-container">
            <p>Happy Birthday pyaari Bhonduuuu! 🎂❤️</p>
            <p>Tumhe pata hai na ki tum mere liye kitni special ho? Tum thodi si buddhu ho thodi si ziddi bhi 😝😝 lekin jaisi bhi ho... Bestest ever ho.</p>
            <p>I promise ki main hamesha tumahre saath khada raunga tumhari saari baate sunne ke liye aur tumhe har mushkil mein sambhalne ke liye Tayyar hu tum hamesha aise hi hasti rehna kyunki tumhari smile dekh kar mera din ban jata hai.</p>
            <p>Stay the same, my favorite Bhonduuuu! ✨🥹🎈</p>
        </div>
        <button onclick="location.reload()">Start Over 🐼</button>
    </div>

    <script>
        function checkPassword() {
            const p = document.getElementById('pass').value;
            if(p.toLowerCase() === "panda") {
                nextPage(2);
            } else {
                alert("Wrong password! Hint: 🐼");
            }
        }

        function nextPage(num) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById('page' + num).classList.add('active');
        }

        function openGift() {
            document.getElementById('box').style.display = 'none';
            document.getElementById('gift-content').style.display = 'block';
        }

        // Floating Hearts and Pandas
        function createEmoji() {
            const emojis = ['❤️', '🐼', '✨', '💖'];
            const e = document.createElement('div');
            e.innerHTML = emojis[Math.floor(Math.random() * emojis.length)];
            e.style.position = 'fixed';
            e.style.left = Math.random() * 100 + 'vw';
            e.style.top = '110vh';
            e.style.fontSize = Math.random() * 20 + 20 + 'px';
            e.style.transition = 'transform 5s linear, opacity 5s';
            e.style.zIndex = '100';
            document.getElementById('anime').appendChild(e);

            setTimeout(() => {
                e.style.transform = `translateY(-120vh) rotate(${Math.random() * 360}deg)`;
                e.style.opacity = '0';
            }, 100);

            setTimeout(() => e.remove(), 6000);
        }

        setInterval(createEmoji, 500);
    </script>
</body>
</html>
