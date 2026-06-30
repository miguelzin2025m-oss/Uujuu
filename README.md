```html
<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MegaStore Ultra - Produtos do Futuro</title>
    <!-- Tailwind CSS para estilização moderna -->
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* Animações e efeitos de distorção visual (Glitch) */
        @keyframes tremura {
            0% { transform: translate(2px, 1px) rotate(0deg); }
            10% { transform: translate(-1px, -2px) rotate(-1deg); }
            20% { transform: translate(-3px, 0px) rotate(1deg); }
            30% { transform: translate(0px, 2px) rotate(0deg); }
            40% { transform: translate(1px, -1px) rotate(1deg); }
            50% { transform: translate(-1px, 2px) rotate(-1deg); }
            60% { transform: translate(-3px, 1px) rotate(0deg); }
            70% { transform: translate(2px, 1px) rotate(-1deg); }
            80% { transform: translate(-1px, -1px) rotate(1deg); }
            90% { transform: translate(2px, 2px) rotate(0deg); }
            100% { transform: translate(1px, -2px) rotate(-1deg); }
        }

        .efeito-terramoto {
            animation: tremura 0.1s infinite;
        }

        /* Efeito de ecrã danificado retro */
        .linhas-tv {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.15) 50%);
            background-size: 100% 4px;
            z-index: 9999;
            pointer-events: none;
        }

        /* Elementos afetados pela física bugada */
        .elemento-fisico {
            position: absolute !important;
            transition: transform 0.2s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            pointer-events: auto;
        }

        /* Cursor esquisito de bug */
        .cursor-bugado {
            cursor: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='40' height='40' style='font-size: 30px;'><text y='30'>👾</text></svg>"), auto !important;
        }

        /* Janela retro flutuante */
        .janela-erro-retro {
            position: absolute;
            width: 300px;
            background: #dfdfdf;
            border: 2px solid #ffffff;
            box-shadow: 4px 4px 0px #000000;
            font-family: 'Courier New', Courier, monospace;
            z-index: 999;
        }

        .barra-titulo-retro {
            background: linear-gradient(90deg, #000080, #1084d0);
            color: white;
            font-weight: bold;
            font-size: 13px;
            padding: 3px 6px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        /* Efeito Matrix de fundo no final */
        .chuva-matrix {
            background-color: black;
            color: #0f0;
            font-family: monospace;
            overflow: hidden;
        }
    </style>
</head>
<body class="bg-zinc-950 text-zinc-100 min-h-screen relative overflow-x-hidden transition-all duration-300">

    <!-- Linhas de varrimento de monitor antigo -->
    <div class="linhas-tv"></div>

    <!-- Barra Superior de Diagnóstico Bizarro -->
    <div id="painel-diagnostico" class="bg-red-600 text-white text-center py-2 px-4 font-mono text-xs hidden z-50 relative">
        [ALERTA DE ANOMALIA] DETECTADOS <span id="contador-cliques" class="font-bold underline">0</span> IMPACTOS ESTÉTICOS NO MONITOR!
    </div>

    <!-- Painel Lateral: O Feiómetro -->
    <div id="feiometro-container" class="fixed right-4 top-20 bg-zinc-900 border border-zinc-800 p-4 rounded-xl shadow-2xl z-40 w-64 transition-transform duration-500 translate-x-80">
        <div class="flex items-center justify-between mb-2">
            <span class="text-xs font-mono text-red-500 uppercase tracking-widest">Detector de Feiura</span>
            <span class="text-xs" id="feio-percentagem">0%</span>
        </div>
        <div class="w-full bg-zinc-800 rounded-full h-3 overflow-hidden">
            <div id="feio-progresso-bar" class="bg-gradient-to-r from-yellow-500 to-red-600 h-full w-0 transition-all duration-300"></div>
        </div>
        <p id="feio-status" class="text-[10px] text-zinc-400 mt-2 font-mono">Status: Utilizador tolerável.</p>
    </div>

    <!-- Estrutura Principal da Loja Virtual -->
    <div id="loja-principal" class="transition-all duration-500">
        
        <!-- Cabeçalho de Luxo -->
        <header class="border-b border-zinc-800 bg-zinc-950/80 backdrop-blur sticky top-0 z-30">
            <div class="max-w-7xl mx-auto px-6 py-4 flex justify-between items-center">
                <div class="flex items-center space-x-3">
                    <span class="text-3xl animate-bounce">⚡</span>
                    <span class="text-xl font-black tracking-widest bg-gradient-to-r from-cyan-400 to-purple-500 bg-clip-text text-transparent">MEGASTORE</span>
                </div>
                <div class="flex items-center space-x-6 text-sm text-zinc-400">
                    <span class="hover:text-white cursor-pointer transition">Nanotecnologia</span>
                    <span class="hover:text-white cursor-pointer transition">Física Quântica</span>
                    <span class="hover:text-white cursor-pointer transition">Biogenética</span>
                </div>
                <div>
                    <button class="bg-cyan-500 hover:bg-cyan-400 text-black font-bold px-4 py-2 rounded-lg text-xs tracking-wider uppercase transition">
                        Carrinho (0)
                    </button>
                </div>
            </div>
        </header>

        <!-- Banner com Slogan Irónico -->
        <section class="max-w-7xl mx-auto px-6 pt-12 pb-6">
            <div class="bg-gradient-to-br from-purple-900/40 via-zinc-900 to-cyan-950/30 border border-zinc-800 rounded-3xl p-8 md:p-12 text-center relative overflow-hidden">
                <div class="absolute -right-10 -top-10 w-40 h-40 bg-purple-500/10 blur-3xl rounded-full"></div>
                <div class="absolute -left-10 -bottom-10 w-40 h-40 bg-cyan-500/10 blur-3xl rounded-full"></div>
                
                <span class="bg-zinc-800 text-cyan-400 text-[10px] font-bold tracking-widest px-3 py-1 rounded-full uppercase">Sorteio de Natal Antecipado</span>
                <h1 class="text-4xl md:text-6xl font-extrabold tracking-tight mt-6 mb-4 text-white">
                    Seja Bem-vindo à <span class="bg-gradient-to-r from-cyan-400 to-emerald-400 bg-clip-text text-transparent">Perfeição</span>
                </h1>
                <p class="text-zinc-400 max-w-xl mx-auto text-sm md:text-base">
                    Nossos algoritmos premium ajustam os preços com base na inteligência e elegância de quem navega. Desfrute!
                </p>
            </div>
        </section>

        <!-- Vitrine de Produtos -->
        <main class="max-w-7xl mx-auto px-6 py-12">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8" id="grade-produtos">
                
                <!-- Produto 1 -->
                <div class="bg-zinc-900 border border-zinc-800 rounded-2xl p-6 flex flex-col justify-between hover:border-zinc-700 transition duration-300 cartao-produto relative overflow-hidden">
                    <div>
                        <div class="bg-zinc-950 rounded-xl aspect-square flex items-center justify-center text-7xl mb-6 border border-zinc-800/50">
                            🧬
                        </div>
                        <h2 class="text-lg font-bold text-white mb-2 titulo-produto">Modificador de ADN Estético</h2>
                        <p class="text-xs text-zinc-400 mb-6">Altera a sua estrutura genética em tempo real para corrigir imperfeições faciais críticas.</p>
                    </div>
                    <div>
                        <div class="flex justify-between items-end mb-6">
                            <div>
                                <span class="text-[10px] text-zinc-500 uppercase font-mono block">Preço Base</span>
                                <span class="text-xl font-bold text-cyan-400">999.00 EUR</span>
                            </div>
                            <span class="text-xs text-emerald-400 font-bold">Em Stock</span>
                        </div>
                        <button class="botao-comprar w-full bg-zinc-100 hover:bg-white text-zinc-950 font-bold py-3 px-4 rounded-xl text-xs uppercase tracking-wider transition-all duration-200">
                            Comprar Agora
                        </button>
                    </div>
                </div>

                <!-- Produto 2 -->
                <div class="bg-zinc-900 border border-zinc-800 rounded-2xl p-6 flex flex-col justify-between hover:border-zinc-700 transition duration-300 cartao-produto relative overflow-hidden">
                    <div>
                        <div class="bg-zinc-950 rounded-xl aspect-square flex items-center justify-center text-7xl mb-6 border border-zinc-800/50">
                            🕶️
                        </div>
                        <h2 class="text-lg font-bold text-white mb-2 titulo-produto">Óculos de Filtro de Beleza</h2>
                        <p class="text-xs text-zinc-400 mb-6">Filtra a aparência de todas as pessoas ao seu redor. Recomendável usar ao olhar-se ao espelho.</p>
                    </div>
                    <div>
                        <div class="flex justify-between items-end mb-6">
                            <div>
                                <span class="text-[10px] text-zinc-500 uppercase font-mono block">Preço Base</span>
                                <span class="text-xl font-bold text-cyan-400">149.00 EUR</span>
                            </div>
                            <span class="text-xs text-emerald-400 font-bold">Em Stock</span>
                        </div>
                        <button class="botao-comprar w-full bg-zinc-100 hover:bg-white text-zinc-950 font-bold py-3 px-4 rounded-xl text-xs uppercase tracking-wider transition-all duration-200">
                            Comprar Agora
                        </button>
                    </div>
                </div>

                <!-- Produto 3 -->
                <div class="bg-zinc-900 border border-zinc-800 rounded-2xl p-6 flex flex-col justify-between hover:border-zinc-700 transition duration-300 cartao-produto relative overflow-hidden">
                    <div>
                        <div class="bg-zinc-950 rounded-xl aspect-square flex items-center justify-center text-7xl mb-6 border border-zinc-800/50">
                            🧠
                        </div>
                        <h2 class="text-lg font-bold text-white mb-2 titulo-produto">Implante de Autoestima Virtual</h2>
                        <p class="text-xs text-zinc-400 mb-6">Microchip quântico instalado no cérebro para fazê-lo acreditar que é extremamente atraente.</p>
                    </div>
                    <div>
                        <div class="flex justify-between items-end mb-6">
                            <div>
                                <span class="text-[10px] text-zinc-500 uppercase font-mono block">Preço Base</span>
                                <span class="text-xl font-bold text-cyan-400">4,500.00 EUR</span>
                            </div>
                            <span class="text-xs text-emerald-400 font-bold">Em Stock</span>
                        </div>
                        <button class="botao-comprar w-full bg-zinc-100 hover:bg-white text-zinc-950 font-bold py-3 px-4 rounded-xl text-xs uppercase tracking-wider transition-all duration-200">
                            Comprar Agora
                        </button>
                    </div>
                </div>

            </div>
        </main>
    </div>

    <!-- Caixa de Chat de Suporte Assustada (Troll) -->
    <div id="chat-suporte" class="fixed bottom-6 right-6 w-80 bg-zinc-900 border border-zinc-800 rounded-2xl shadow-2xl overflow-hidden z-50 transition-all duration-300 translate-y-96">
        <div class="bg-purple-600 p-4 flex justify-between items-center text-sm font-bold">
            <div class="flex items-center space-x-2">
                <span class="w-2.5 h-2.5 bg-emerald-400 rounded-full animate-ping"></span>
                <span>Assistente Virtual</span>
            </div>
            <button onclick="fecharChat()" class="text-white hover:text-red-300">✕</button>
        </div>
        <div class="p-4 h-48 overflow-y-auto space-y-3 text-xs font-mono" id="mensagens-chat">
            <div class="bg-zinc-950 p-2 rounded-lg text-zinc-400">[Suporte]: Olá! Estou aqui para otimizar as suas compras futuristas.</div>
        </div>
    </div>

    <!-- TELA DE COLAPSO TOTAL (ERRO DE FEIURA) -->
    <div id="bsod-final" class="fixed inset-0 bg-blue-800 text-white font-mono p-6 md:p-24 hidden z-50 overflow-hidden select-none">
        <div class="max-w-4xl mx-auto space-y-6">
            <div class="bg-red-600 text-white px-4 py-2 font-black inline-block mb-4 text-xl tracking-wider uppercase animate-pulse">
                🛑 ALERTA CRÍTICO DE SISTEMA 🛑
            </div>
            <h1 class="text-2xl md:text-4xl font-extrabold uppercase tracking-wide text-yellow-400">
                CRASH TOTAL DO SERVIDOR DE RENDERIZAÇÃO
            </h1>
            
            <p class="text-lg md:text-xl text-zinc-200">
                Uma anomalia estética severa sobrecarregou a placa gráfica quântica da nossa loja. A beleza dos nossos servidores recusou-se a processar a sua imagem facial.
            </p>
            
            <div class="space-y-3 text-sm md:text-base border-t border-blue-500 pt-6">
                <p class="font-bold text-yellow-300 uppercase tracking-widest">Detalhes do Erro:</p>
                <p class="bg-blue-950 p-3 rounded border border-blue-400 text-red-300 font-bold text-lg">
                    CÓDIGO: esse site caiu devido a sua feiura
                </p>
                <p>Módulo de Falha: <span class="text-cyan-300 font-mono">espelho_quebrado.sys</span></p>
                <p>Sugestão Técnica: Tente fazer login de máscara ou mude de rosto e volte mais tarde.</p>
            </div>

            <div class="pt-8">
                <button onclick="reiniciarTroll()" class="bg-yellow-400 text-black font-extrabold px-8 py-4 rounded-xl hover:bg-white transition-colors duration-200 shadow-lg text-sm tracking-wider uppercase">
                    Reiniciar Sistema (Com Maquilhagem) 💄
                </button>
            </div>
        </div>
    </div>

    <!-- Lógica de Simulação de Bugs e Efeitos Comediográficos -->
    <script>
        let clicks = 0;
        const cliquesMaximos = 12; // Número de cliques antes da tela azul final
        let audioCtx = null;
        let chatIniciado = false;

        // Gerador de Ruído e Efeitos Sonoros Retro de Bug (Web Audio API)
        function somDeErro(tipo = 'sine', freq = 300, duracao = 0.1) {
            try {
                if (!audioCtx) {
                    audioCtx = new (window.AudioContext || window.webkitAudioContext)();
                }
                const osc = audioCtx.createOscillator();
                const gain = audioCtx.createGain();
                
                osc.type = tipo;
                osc.frequency.setValueAtTime(freq, audioCtx.currentTime);
                if (tipo === 'sawtooth' || tipo === 'square') {
                    // Efeito de queda de tom dramática
                    osc.frequency.exponentialRampToValueAtTime(50, audioCtx.currentTime + duracao);
                }
                
                gain.gain.setValueAtTime(0.15, audioCtx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + duracao);
                
                osc.connect(gain);
                gain.connect(audioCtx.destination);
                
                osc.start();
                osc.stop(audioCtx.currentTime + duracao);
            } catch(erro) {
                // Previne falhas se o navegador bloquear o áudio
            }
        }

        // Os botões começam a fugir do rato de forma hilariante
        const botoesComprar = document.querySelectorAll('.botao-comprar');
        botoesComprar.forEach(botao => {
            botao.addEventListener('mouseover', () => {
                if (clicks >= 2) {
                    somDeErro('square', 450, 0.15);
                    const limiteX = Math.random() * 260 - 130;
                    const limiteY = Math.random() * 120 - 60;
                    botao.style.transform = `translate(${limiteX}px, ${limiteY}px) rotate(${Math.random() * 30 - 15}deg)`;
                    
                    // Altera o texto de forma cómica
                    botao.innerText = "NÃO ME CLIQUES!";
                    botao.style.backgroundColor = "#ef4444";
                    botao.style.color = "#ffffff";
                }
            });
        });

        // Clique Global para detonar bugs progressivos
        document.addEventListener('click', (evento) => {
            // Ignorar o botão de recomeçar
            if (evento.target.closest('button') && evento.target.textContent.includes('Reiniciar')) return;

            clicks++;
            
            // Ativa o painel de alerta
            const painel = document.getElementById('painel-diagnostico');
            painel.classList.remove('hidden');
            document.getElementById('contador-cliques').innerText = clicks;

            // Altera o cursor e faz barulho de glitch
            document.body.classList.add('cursor-bugado');
            somDeErro(clicks % 2 === 0 ? 'sawtooth' : 'triangle', 200 + (clicks * 60), 0.2);

            // Bug 1: Tremura temporária no ecrã
            document.body.classList.add('efeito-terramoto');
            setTimeout(() => {
                if (clicks < cliquesMaximos) {
                    document.body.classList.remove('efeito-terramoto');
                }
            }, 250);

            // Bug 2: Ativação do "Feiómetro"
            const feiometro = document.getElementById('feiometro-container');
            if (clicks === 2) {
                feiometro.classList.remove('translate-x-80');
            }

            // Atualiza barra do Feiómetro
            if (clicks >= 2 && clicks < cliquesMaximos) {
                const percentagem = Math.min((clicks / (cliquesMaximos - 1)) * 100, 100);
                document.getElementById('feio-percentagem').innerText = `${Math.round(percentagem)}%`;
                document.getElementById('feio-progresso-bar').style.width = `${percentagem}%`;
                
                const statusLabel = document.getElementById('feio-status');
                if (percentagem > 80) {
                    statusLabel.innerText = "Status: PERIGO DE EXPLOSÃO VISUAL!!";
                    statusLabel.classList.add('text-red-500', 'animate-pulse');
                } else if (percentagem > 50) {
                    statusLabel.innerText = "Status: Feiura acima do limite do CSS.";
                    statusLabel.classList.add('text-yellow-500');
                } else if (percentagem > 25) {
                    statusLabel.innerText = "Status: Beleza severamente questionável.";
                }
            }

            // Bug 3: Mudança de cores berrantes ao clicar
            if (clicks >= 3) {
                const coresGlitch = ['#450a0a', '#1e1b4b', '#062f4f', '#160d2b', '#111827'];
                document.body.style.backgroundColor = coresGlitch[Math.floor(Math.random() * coresGlitch.length)];
            }

            // Bug 4: O Chat de suporte abre-se sozinho, desespera-se com a aparência e fecha-se!
            if (clicks === 4 && !chatIniciado) {
                chatIniciado = true;
                const chat = document.getElementById('chat-suporte');
                chat.classList.remove('translate-y-96');
                
                setTimeout(() => {
                    adicionarMensagemChat("Assistente", "A analisar o seu perfil pela câmara...");
                    somDeErro('sine', 800, 0.3);
                }, 1000);

                setTimeout(() => {
                    adicionarMensagemChat("Assistente", "MEU DEUS DO CÉU! QUE CARA É ESSA?!! 😱");
                    somDeErro('sawtooth', 1200, 0.5);
                }, 2500);

                setTimeout(() => {
                    adicionarMensagemChat("Assistente", "A fechar o chat para proteger a minha inteligência!");
                    somDeErro('square', 100, 0.4);
                }, 4000);

                setTimeout(() => {
                    fecharChat();
                }, 5500);
            }

            // Bug 5: Espalhar caixas de erro do Windows 98 na posição do clique
            if (clicks >= 5 && clicks < cliquesMaximos) {
                criarErroRetro(evento.clientX, evento.clientY);
            }

            // Bug 6: Escorregar produtos e títulos (Zalgo/Bug)
            if (clicks >= 7) {
                distorcerTextos();
            }

            // Bug 7: Deixar a página de pernas para o ar e virar tudo de lado
            if (clicks === 9) {
                document.getElementById('loja-principal').style.transform = "rotate(180deg) scale(0.9)";
            }

            // Bug 8: Ativar gravidade louca, fazendo com que os produtos caiam
            if (clicks === 10) {
                document.getElementById('loja-principal').style.transform = "rotate(0deg)";
                derrubarProdutos();
            }

            // Colapso Total e Crash Estético Final
            if (clicks >= cliquesMaximos) {
                colapsoGeral();
            }
        });

        // Adicionar texto no chat do troll
        function adicionarMensagemChat(autor, texto) {
            const container = document.getElementById('mensagens-chat');
            const msg = document.createElement('div');
            msg.className = "bg-zinc-950 p-2 rounded-lg text-zinc-100";
            msg.innerHTML = `<span class="text-purple-400 font-bold">[${autor}]:</span> ${texto}`;
            container.appendChild(msg);
            container.scrollTop = container.scrollHeight;
        }

        // Esconder o chat de suporte
        function fecharChat() {
            document.getElementById('chat-suporte').classList.add('translate-y-96');
        }

        // Cria caixas de diálogo estilo Windows 98 irritantes
        function criarErroRetro(x, y) {
            const janela = document.createElement('div');
            janela.className = 'janela-erro-retro';
            janela.style.left = `${x - 120}px`;
            janela.style.top = `${y - 50}px`;

            const piadasFeio = [
                "Anomalia Visual Crítica na webcam virtual.",
                "Ecrã partindo devido a altos níveis de feiura.",
                "Filtro de decência facial falhou miseravelmente.",
                "O espelho do código CSS quebrou.",
                "O browser sugere cirurgia plástica urgente.",
                "Erro 666: Impossível formatar esse rosto.",
                "Recomendamos o uso de um capacete de motociclista."
            ];

            const mensagemAleatoria = piadasFeio[Math.floor(Math.random() * piadasFeio.length)];

            janela.innerHTML = `
                <div class="barra-titulo-retro">
                    <span>X_FATAL_ERROR.EXE</span>
                    <button class="bg-[#dfdfdf] text-black font-bold border border-white px-1 hover:bg-red-500 hover:text-white" onclick="this.closest('.janela-erro-retro').remove()">X</button>
                </div>
                <div class="p-3 text-black text-xs space-y-3">
                    <p class="font-bold flex items-center gap-2">⚠️ <span class="text-red-600">BEAUTY_FAIL_DETECTED</span></p>
                    <p>${mensagemAleatoria}</p>
                    <div class="text-right">
                        <button class="bg-[#dfdfdf] text-black font-bold border-2 border-white border-b-black border-r-black px-4 py-1 hover:bg-zinc-300" onclick="this.closest('.janela-erro-retro').remove()">Ok</button>
                    </div>
                </div>
            `;
            document.body.appendChild(janela);
        }

        // Transforma títulos em mensagens hilariantes sobre feiura
        function distorcerTextos() {
            const titulos = document.querySelectorAll('.titulo-produto');
            const frasesDistorcidas = [
                "CATASTRÓFE VISUAL",
                "ERRO_DE_BELEZA_101",
                "FALHA ESTÉTICA EXTREMA",
                "CÉREBRO DERRETENDO",
                "SOCORRO QUE SUSTO! 🙀",
                "BUG DE FEIO CRÍTICO"
            ];
            titulos.forEach((titulo, i) => {
                if (Math.random() > 0.4) {
                    titulo.innerText = frasesDistorcidas[Math.floor(Math.random() * frasesDistorcidas.length)];
                    titulo.style.color = "#f43f5e";
                    titulo.style.fontFamily = "monospace";
                }
            });
        }

        // Derruba os cartões com gravidade quântica falsa
        function derrubarProdutos() {
            const cartoes = document.querySelectorAll('.cartao-produto');
            cartoes.forEach((cartao, index) => {
                cartao.classList.add('elemento-fisico');
                const rotacao = Math.random() * 360;
                cartao.style.transform = `translateY(450px) rotate(${rotacao}deg) scale(0.65)`;
                cartao.style.transition = `all ${1.2 + (index * 0.1)}s cubic-bezier(0.175, 0.885, 0.32, 1.275)`;
            });
        }

        // O clímax do bug: Desencadeia o Blue Screen of Death com a mensagem perfeita
        function colapsoGeral() {
            somDeErro('sawtooth', 80, 2.0);
            
            // Remove quaisquer janelas pop-up antigas de erro
            document.querySelectorAll('.janela-erro-retro').forEach(el => el.remove());
            
            // Oculta tudo menos a tela azul
            document.getElementById('loja-principal').style.display = 'none';
            document.getElementById('painel-diagnostico').style.display = 'none';
            document.getElementById('feiometro-container').style.display = 'none';
            
            const bsod = document.getElementById('bsod-final');
            bsod.classList.remove('hidden');
            document.body.style.backgroundColor = '#1e40af'; // Azul escuro
            document.body.classList.add('efeito-terramoto');
        }

        // Botão de auto-cura para repetir a experiência divertida
        function reiniciarTroll() {
            clicks = 0;
            chatIniciado = false;
            
            document.body.classList.remove('efeito-terramoto', 'cursor-bugado');
            document.body.style.backgroundColor = '';
            
            // Ocultar ecrã de crash
            document.getElementById('bsod-final').classList.add('hidden');
            
            // Restaurar tudo o resto
            const loja = document.getElementById('loja-principal');
            loja.style.display = 'block';
            loja.style.transform = 'none';
            
            // Restaurar cartões de produtos
            document.querySelectorAll('.cartao-produto').forEach(cartao => {
                cartao.classList.remove('elemento-fisico');
                cartao.style.transform = 'none';
                cartao.style.transition = '';
            });

            // Reverter botões fujões
            botoesComprar.forEach(botao => {
                botao.style.transform = 'none';
                botao.style.backgroundColor = '';
                botao.style.color = '';
                botao.innerText = "Comprar Agora";
            });

            // Resetar títulos de produtos
            const titulosOriginais = [
                "Modificador de ADN Estético",
                "Óculos de Filtro de Beleza",
                "Implante de Autoestima Virtual"
            ];
            document.querySelectorAll('.titulo-produto').forEach((titulo, i) => {
                titulo.innerText = titulosOriginais[i];
                titulo.style.color = '';
                titulo.style.fontFamily = '';
            });

            // Resetar Feiómetro
            document.getElementById('feio-percentagem').innerText = '0%';
            document.getElementById('feio-progresso-bar').style.width = '0%';
            document.getElementById('feio-status').innerText = 'Status: Utilizador tolerável.';
            document.getElementById('feio-status').className = 'text-[10px] text-zinc-400 mt-2 font-mono';
            document.getElementById('feiometro-container').classList.add('translate-x-80');

            // Ocultar barra superior
            document.getElementById('painel-diagnostico').classList.add('hidden');
        }
    </script>
</body>
</html>

```
