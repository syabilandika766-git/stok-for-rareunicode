<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Strawberry Dev Vault</title>
    <link href="https://fonts.googleapis.com/css2?family=Bungee&display=swap" rel="stylesheet">
    <style>
        body {
            background-color: #0d0d0d;
            color: #00ffcc;
            font-family: 'Segoe UI', sans-serif;
            text-align: center;
            padding: 20px;
        }
        h1 { font-family: 'Bungee', cursive; color: #ff0077; text-shadow: 3px 3px #000; }
        .container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(70px, 1fr));
            gap: 10px;
            padding: 20px;
            background: #1a1a1a;
            border-radius: 20px;
            border: 2px solid #333;
        }
        .btn-copy {
            background: #252525;
            border: 1px solid #444;
            color: white;
            padding: 15px 5px;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.2s;
            font-size: 1.5rem;
        }
        .btn-copy:active {
            transform: scale(0.9);
            background: #ff0077;
            border-color: #fff;
        }
        .toast {
            position: fixed;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            background: #00ffcc;
            color: #000;
            padding: 10px 25px;
            border-radius: 30px;
            font-weight: bold;
            display: none;
            z-index: 100;
        }
    </style>
</head>
<body>

    <h1>STOK UNICODE LANGKA 🍓</h1>
    <p>Klik buat langsung copy ke keyboard, Bro!</p>
    
    <div class="container" id="box"></div>
    <div id="notif" class="toast">COPIED! 🔥</div>

    <script>
        // Gabungan stok lu & stok tambahan gue
        const stok = [
            '♼','⛃','⛐','⛿','⛟','🫯','🪎','🫪',
            '𓁹','⌬','⏻','⌗','⎔','𒈓','𓊈','𓊉',
            '⛧','⛯','⎋','⎌','֎','֏','𓃑','⛤'
        ];

        const box = document.getElementById('box');
        const notif = document.getElementById('notif');

        stok.forEach(item => {
            const btn = document.createElement('button');
            btn.className = 'btn-copy';
            btn.innerText = item;
            btn.onclick = () => {
                navigator.clipboard.writeText(item);
                notif.style.display = 'block';
                setTimeout(() => { notif.style.display = 'none'; }, 1000);
            };
            box.appendChild(btn);
        });
    </script>
</body>
</html>
