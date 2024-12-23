# surprise-website
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Surprise</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(to bottom, #fce4ec, #f8bbd0);
            margin: 0;
            height: 100vh;
            overflow-y: scroll;
            position: relative;
            box-sizing: border-box;
            padding: 0 15px;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            color: #ff1493;
            animation: backgroundAnimation 20s infinite alternate;
        }

        @keyframes backgroundAnimation {
            0% {
                background: linear-gradient(to bottom, #fce4ec, #f8bbd0);
            }
            100% {
                background: linear-gradient(to bottom, #f8bbd0, #ff69b4);
            }
        }

        .login-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            background-color: rgba(255, 255, 255, 0.8);
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            width: 350px;
            margin: 10px;
            z-index: 10;
            position: relative;
            transition: all 0.3s ease;
        }

        .login-container:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.2);
        }

        input[type="text"], input[type="password"] {
            width: 80%;
            padding: 15px;
            margin: 10px 0;
            border-radius: 10px;
            border: 1px solid #ccc;
            text-align: center;
            font-size: 16px;
            transition: all 0.3s ease;
        }

        input[type="text"]:focus, input[type="password"]:focus {
            border-color: #ff1493;
            transform: scale(1.05);
        }

        .login-btn {
            width: 80%;
            padding: 15px;
            background-color: #ff69b4;
            color: white;
            font-size: 16px;
            font-weight: bold;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .login-btn:hover {
            background-color: #ff1493;
            transform: scale(1.05);
        }

        .welcome-container {
            display: none;
            text-align: center;
            padding: 40px;
            background-color: rgba(255, 255, 255, 0.9);
            width: 80%;
            max-width: 800px;
            margin: 20px auto;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            font-size: 18px;
            color: #ff1493;
            line-height: 1.6;
            margin-top: 30px;
            animation: fadeIn 1s ease-in;
        }

        @keyframes fadeIn {
            0% {
                opacity: 0;
                transform: translateY(30px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        h1 {
            color: #ff1493;
            font-size: 2.5em;
            margin-bottom: 20px;
        }

        .typing {
            display: inline-block;
            font-size: 20px;
            white-space: nowrap;
            overflow: hidden;
            border-right: .15em solid #ff1493;
            width: 0;
            animation: typing 4s steps(40) 1s forwards, blinkCaret 0.75s step-end infinite;
        }

        @keyframes typing {
            from {
                width: 0;
            }
            to {
                width: 100%;
            }
        }

        @keyframes blinkCaret {
            50% {
                border-color: transparent;
            }
        }

        .text-glow {
            text-shadow: 0 0 8px #ff1493, 0 0 15px #ff1493, 0 0 25px #ff1493;
        }

        .scrollable-content {
            max-height: 400px;
            overflow-y: auto;
            padding-right: 15px;
        }

        .glowing {
            animation: glow 1.5s ease-in-out infinite alternate;
        }

        @keyframes glow {
            0% {
                text-shadow: 0 0 5px #ff1493, 0 0 10px #ff1493, 0 0 15px #ff1493;
            }
            100% {
                text-shadow: 0 0 20px #ff1493, 0 0 30px #ff1493, 0 0 40px #ff1493;
            }
        }

    </style>
</head>
<body>

    <!-- Login Container -->
    <div class="login-container" id="login-container">
        <h2>Login</h2>
        <input type="text" id="username" placeholder="Username" required><br>
        <input type="password" id="password" placeholder="Password" required><br>
        <button class="login-btn" onclick="login()">Login</button>
        <p class="login-error" id="login-error"></p>
    </div>

    <!-- Welcome Message -->
    <div class="welcome-container" id="welcome-container">
        <h1>Hey Ilana</h1>
        <div class="scrollable-content" id="message">
            <p>Ilana, I know this Christmas hasn’t been the best for you, and I wish I could’ve done more to make it easier. But I want you to know that you mean so much to me, more than words can say. You're my person, and I truly feel lucky to have you in my life. ❤️</p>

            <p>Honestly, every time things got tough for me, you’ve been there to help me get through it. You’ve always known what to say or what to do to pick me up when I was down, and I will never forget that. The way you just get me and know exactly what I need... it's something I could never take for granted. 💕</p>

            <p>When we're hanging out—whether we're laughing at something stupid, talking about life, or just sitting in silence—it’s the best feeling. It’s not just about the big moments; it’s those little, quiet ones that I love the most. Those moments are everything to me, and I’m so happy to share them with you. ❤️</p>

            <p>Every time I think about how I met you, I can't help but smile. You really are everything, and I feel so grateful to have you around. You bring so much light and joy into my life. I know we’ve had our struggles, but nothing will ever change how much you mean to me. 💖</p>

            <p>This Christmas, I just want you to know how much I care about you. I know things are tough right now, but I hope you can still find little moments of joy and love today. You deserve it all and more. Merry Christmas, Ilana! 🎄</p>

            <p>You are my person, my best friend, and the one I want by my side no matter what. We've been through so much, and I know there's even more to come. Together, we can handle anything. I’ll always be here for you, through thick and thin. 💕</p>

            <p>I know this message is long, but I just want you to understand how much you really mean to me. Sometimes words don’t feel like enough, but I hope this comes close to showing you the depth of my feelings. ❤️</p>

            <p>You are your own unique, amazing person. You light up every room you walk into, and I feel so lucky to be the one who gets to be with you. Your heart, your strength, your kindness... it all makes me love you even more every single day. ❤️</p>

            <p>Forever yours, <br> Mosuab ❤️</p>
        </div>
    </div>

    <script>
        function login() {
            var username = document.getElementById('username').value;
            var password = document.getElementById('password').value;
            var errorMessage = document.getElementById('login-error');

            var correctUsername = "Ilana"; // Updated username
            var correctPassword = "26/6/1997";  // Updated password

            if (username === correctUsername && password === correctPassword) {
                document.getElementById('login-container').style.display = 'none';
                document.getElementById('welcome-container').style.display = 'block';
                errorMessage.textContent = "";
            } else {
                errorMessage.textContent = "Invalid username or password!";
            }
        }
    </script>
</body>
</html>
