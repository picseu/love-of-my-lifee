# love-of-my-lifee
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Um pacto especial...</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@600;800&display=swap');

        body {
            margin: 0;
            padding: 0;
            background-color: #050505;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            font-family: 'Cinzel', serif;
            overflow: hidden;
        }

        .app-container {
            width: 360px;
            height: 700px;
            background: linear-gradient(180deg, #1c1c1c, #000000);
            border-radius: 40px;
            box-shadow: 0 10px 40px rgba(139, 0, 0, 0.4);
            position: relative;
            overflow: hidden;
            border: 8px solid #2a0000;
            display: flex;
            flex-direction: column;
            align-items: center;
            color: #e0e0e0;
            text-align: center;
        }

        .tela {
            display: none;
            width: 100%;
            height: 100%;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px;
            box-sizing: border-box;
            position: absolute;
        }

        .active {
            display: flex;
            animation: fadeIn 1s ease-in-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; filter: blur(5px); transform: scale(0.95); }
            to { opacity: 1; filter: blur(0); transform: scale(1); }
        }

        .emoji-grande {
            font-size: 80px;
            margin-bottom: 20px;
            filter: drop-shadow(0 4px 8px rgba(0,0,0,0.8));
        }

        h1 {
            font-size: 24px;
            margin-bottom: 30px;
            text-shadow: 2px 2px 4px rgba(139,0,0,0.5);
            letter-spacing: 1px;
        }

        .btn-container {
            display: flex;
            gap: 20px;
            width: 100%;
            justify-content: center;
            position: relative;
            height: 60px;
        }

        button {
            padding: 15px 30px;
            font-size: 18px;
            font-weight: bold;
            border: 1px solid #4a0000;
            border-radius: 10px;
            cursor: pointer;
            font-family: 'Cinzel', serif;
            box-shadow: 0 4px 10px rgba(0,0,0,0.5);
            transition: all 0.3s ease;
        }

        button:active {
            transform: scale(0.95);
        }

        .btn-sim {
            background-color: #5c0000;
            color: #fff;
            z-index: 2;
        }
        
        .btn-sim:hover {
            background-color: #8a0000;
            box-shadow: 0 0 15px rgba(139, 0, 0, 0.8);
        }

        .btn-nao {
            background-color: #111;
            color: #777;
            position: absolute; 
            z-index: 3;
            border: 1px solid #333;
        }

        .opcoes-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            width: 100%;
        }

        .btn-opcao {
            background-color: rgba(20, 20, 20, 0.8);
            color: #ccc;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 15px;
            border-radius: 10px;
            font-size: 16px;
            border: 1px solid #3a0000;
        }

        .btn-opcao:hover {
            background-color: #3a0000;
            color: white;
            border-color: #8a0000;
        }

        .btn-opcao span {
            font-size: 30px;
            margin-bottom: 5px;
        }

        /* Elementos flutuantes no fundo */
        .decor {
            position: absolute;
            font-size: 24px;
            opacity: 0.3;
            animation: float 6s linear infinite;
            z-index: 0;
            filter: grayscale(0.5);
        }

        @keyframes float {
            0% { transform: translateY(700px) scale(0.5) rotate(0deg); opacity: 0.8; }
            100% { transform: translateY(-100px) scale(1.2) rotate(20deg); opacity: 0; }
        }
    </style>
</head>
<body>

    <div class="app-container">
        <!-- Decorações Góticas -->
        <div class="decor" style="left: 15%; animation-duration: 4s;">🦇</div>
        <div class="decor" style="left: 50%; animation-duration: 7s; font-size: 30px;">🕸️</div>
        <div class="decor" style="left: 80%; animation-duration: 5s;">🥀</div>
        <div class="decor" style="left: 30%; animation-duration: 6s; animation-delay: 2s;">🖤</div>

        <div id="tela1" class="tela active">
            <div class="emoji-grande">🦇</div>
            <h1>Você quer ser o "tismo" do meu "au"?</h1>
            
            <div class="btn-container">
                <button class="btn-sim" onclick="mudarTela('tela2')">SIM</button>
                <button id="btn-nao" class="btn-nao">NÃO</button>
            </div>
        </div>

        <div id="tela2" class="tela">
            <div class="emoji-grande">🧛🏻‍♂️</div>
            <h1>O pacto foi selado! 🖤<br><br>Para celebrar nas sombras, o que vamos devorar hoje?</h1>
            
            <div class="opcoes-grid">
                <button class="btn-opcao" onclick="mudarTela('tela3')"><span>🍣</span> Sushi</button>
                <button class="btn-opcao" onclick="mudarTela('tela3')"><span>🍕</span> Pizza</button>
                <button class="btn-opcao" onclick="mudarTela('tela3')"><span>🍔</span> Hambúrguer</button>
                <button class="btn-opcao" onclick="mudarTela('tela3')"><span>🍷</span> Sang... digo, Vinho</button>
            </div>
        </div>

        <div id="tela3" class="tela">
            <div class="emoji-grande">🖤🥀</div>
            <h1>Fechado!</h1>
            <p style="font-size: 18px; color: #aaa;">Surgirei na sua porta mais tarde.<br>Nossos hiperfocos agora habitam a mesma escuridão! 🥰</p>
        </div>
    </div>

    <script>
        // Lógica do botão fujão
        const btnNao = document.getElementById('btn-nao');
        const btnSim = document.querySelector('.btn-sim');
        
        btnNao.style.right = '0';

        function moverBotao() {
            const container = document.querySelector('.btn-container');
            const containerRect = container.getBoundingClientRect();
            const btnRect = btnNao.getBoundingClientRect();

            const maxX = 250; 
            const maxY = 300; 
            const minX = -100;
            const minY = -200;

            const randomX = Math.floor(Math.random() * (maxX - minX + 1)) + minX;
            const randomY = Math.floor(Math.random() * (maxY - minY + 1)) + minY;

            btnNao.style.transform = `translate(${randomX}px, ${randomY}px)`;
        }

        btnNao.addEventListener('mouseover', moverBotao);
        btnNao.addEventListener('touchstart', function(e) {
            e.preventDefault(); 
            moverBotao();
        });

        function mudarTela(proximaTelaId) {
            const telaAtual = document.querySelector('.active');
            telaAtual.classList.remove('active');

            const proximaTela = document.getElementById(proximaTelaId);
            proximaTela.classList.add('active');
        }
    </script>
</body>
</html>
