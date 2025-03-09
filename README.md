<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>I'm Sorry</title>
    <style>
        body {
            background-color: #222;
            color: white;
            text-align: center;
            font-family: Arial, sans-serif;
            overflow: hidden;
        }
        .container {
            position: absolute;
            width: 100%;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 40px;
            font-weight: bold;
        }
        .apology {
            position: absolute;
            bottom: -100px;
            font-size: 24px;
            opacity: 0;
            transition: all 1s ease-in-out;
        }
    </style>
</head>
<body>

    <div class="container">
        <span id="sorryText">SORRY 😔</span>
    </div>
    <div class="apology" id="apologyMessage">
        💙 I'm really sorry! 💙 <br>
        I didn't mean to hurt you. <br>
        Please forgive me. 🥺
    </div>

    <script>
        let pos = 0;
        let direction = 1;
        let maxWidth = window.innerWidth - 150;
        let text = document.getElementById("sorryText");

        function moveText() {
            pos += 10 * direction;
            text.style.transform = `translateX(${pos}px)`;

            if (pos >= maxWidth || pos <= 0) {
                direction *= -1;
            }
        }

        setInterval(moveText, 100);

        // Show the apology message after a few seconds
        setTimeout(() => {
            document.getElementById("apologyMessage").style.bottom = "20px";
            document.getElementById("apologyMessage").style.opacity = "1";
        }, 5000);
    </script>

</body>
</html>

