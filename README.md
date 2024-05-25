<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Amor Infinito</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
            background-image: url('https://static.vecteezy.com/ti/vetor-gratis/p3/18792888-padrao-de-fundos-de-amor-para-banner-poster-modelos-de-design-de-capa-historias-de-papel-de-parede-de-feed-de-midia-social-conceito-de-saudacao-de-feliz-dia-dos-namorados-gratis-vetor.jpg');
            background-size: cover;
            background-position: center;
        }
        .container {
            text-align: center;
            background: rgba(255, 255, 255, 0.9);
            padding: 1rem;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            border-radius: 10px;
            position: relative;
            z-index: 1;
            max-width: 90%;
            box-sizing: border-box;
        }
        h1 {
            color: #333;
            font-size: 1.2rem;
        }
        button {
            padding: 0.5rem 1rem;
            margin: 0.5rem;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
            position: relative;
        }
        .yes {
            background-color: #4CAF50;
            color: white;
        }
        .no {
            background-color: #f44336;
            color: white;
        }
        .cats {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            pointer-events: none;
            display: none;
        }
        .cat {
            position: absolute;
            width: 60px;
            height: 60px;
            background-size: cover;
            animation: float 5s infinite;
        }
        @keyframes float {
            0% { transform: translateY(100vh); }
            100% { transform: translateY(-100vh); }
        }
        .message {
            position: absolute;
            font-size: 1rem;
            color: red;
            font-weight: bold;
            animation: appearDisappear 3s infinite;
        }
        @keyframes appearDisappear {
            0%, 100% { opacity: 0; }
            50% { opacity: 1; }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Você aceita ser o amor da minha vida até o infinito e além?</h1>
        <button class="yes" onclick="showCats()">Sim</button>
        <button class="no" onmouseover="moveButton()">Não</button>
    </div>
    <div class="cats"></div>
    <div class="message" id="message">Eu te amo Ana Beatriz</div>

    <script>
        const catImages = [
            'https://placekitten.com/60/60',
            'https://placekitten.com/61/61',
            'https://placekitten.com/62/62',
            'https://placekitten.com/63/63',
            'https://placekitten.com/64/64'
        ];

        function showCats() {
            const catsContainer = document.querySelector('.cats');
            catsContainer.style.display = 'block';
            addCats();

            const message = document.getElementById('message');
            moveMessage(message);

            setTimeout(() => {
                window.location.href = 'https://drive.google.com/file/d/1TNT4pKbUQKKjso0i6aUXo1ysZZOaJcp0/view?usp=sharing';
            }, 5000); // Redireciona após 5 segundos
        }

        function addCats() {
            const catsContainer = document.querySelector('.cats');
            catImages.forEach(src => {
                const img = document.createElement('div');
                img.classList.add('cat');
                img.style.backgroundImage = `url(${src})`;
                img.style.left = `${Math.random() * 100}vw`;
                catsContainer.appendChild(img);
            });
        }

        function moveButton() {
            const button = document.querySelector('.no');
            const container = document.querySelector('.container');
            const containerRect = container.getBoundingClientRect();
            const maxX = containerRect.width - button.offsetWidth;
            const maxY = containerRect.height - button.offsetHeight;

            const randomX = Math.floor(Math.random() * maxX);
            const randomY = Math.floor(Math.random() * maxY);

            button.style.position = 'absolute';
            button.style.left = `${randomX}px`;
            button.style.top = `${randomY}px`;
        }

        function moveMessage(message) {
            setInterval(() => {
                const maxX = window.innerWidth - message.offsetWidth;
                const maxY = window.innerHeight - message.offsetHeight;

                const randomX = Math.floor(Math.random() * maxX);
                const randomY = Math.floor(Math.random() * maxY);

                message.style.left = `${randomX}px`;
                message.style.top = `${randomY}px`;
            }, 3000);
        }
    </script>
</body>
</html>
