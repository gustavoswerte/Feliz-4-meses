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
            overflow: hidden; /* Para evitar a rolagem quando o botão "Não" se move */
            background-image: url('https://static.vecteezy.com/ti/vetor-gratis/p3/18792888-padrao-de-fundos-de-amor-para-banner-poster-modelos-de-design-de-capa-historias-de-papel-de-parede-de-feed-de-midia-social-conceito-de-saudacao-de-feliz-dia-dos-namorados-gratis-vetor.jpg');
            background-size: cover;
            background-position: center;
        }
        .container {
            text-align: center;
            background: rgba(255, 255, 255, 0.9);
            padding: 2rem;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            border-radius: 10px;
        }
        h1 {
            color: #333;
        }
        button {
            padding: 1rem 2rem;
            margin: 1rem;
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
    </style>
</head>
<body>
    <div class="container">
        <h1>Você aceita ser o amor da minha vida até o infinito e além?</h1>
        <button class="yes" onclick="redirectToLink()">Sim</button>
        <button class="no" onmouseover="moveButton()">Não</button>
    </div>

    <script>
        function redirectToLink() {
            window.location.href = 'https://drive.google.com/file/d/1TNT4pKbUQKKjso0i6aUXo1ysZZOaJcp0/view?usp=sharing';
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
    </script>
</body>
</html>
