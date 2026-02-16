<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Jornada de Autopercepção Corporal | Andrêssa Nobre</title>
    
    <!-- Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,600;1,400&family=Montserrat:wght@300;400;500;600&display=swap" rel="stylesheet">
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Chart.js -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

    <!-- Tailwind Config for Custom Palette -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        primary: '#7a8f82',
                        secondary: '#d8c3ae',
                        accent: '#A0B179',
                        bgPage: '#fdfdfd',
                        textMain: '#2d3748',
                        textMuted: '#718096',
                        alert: '#e53e3e'
                    },
                    fontFamily: {
                        serif: ['"Cormorant Garamond"', 'serif'],
                        sans: ['"Montserrat"', 'sans-serif'],
                    }
                }
            }
        }
    </script>

    <style>
        /* Custom Styles & Utilities */
        body {
            background-image: url('https://i.ibb.co/XfXGk6h/Captura-de-tela-2025-07-21-222243.png');
            background-repeat: no-repeat;
            background-position: center top;
            background-attachment: fixed;
            background-size: 600px;
            background-blend-mode: soft-light;
            background-color: #fdfdfd;
        }
        
        .glass-panel {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(216, 195, 174, 0.3);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.03);
        }

        .tab-active {
            border-bottom: 3px solid #7a8f82;
            color: #7a8f82;
            font-weight: 600;
        }

        .tab-inactive {
            border-bottom: 3px solid transparent;
            color: #718096;
        }

        .tab-inactive:hover {
            color: #7a8f82;
        }

        /* Canvas Container */
        .canvas-wrapper {
            position: relative;
            width: 100%;
            max-width: 320px;
            height: 580px;
            margin: 0 auto;
            border-radius: 24px;
            border: 2px solid #d8c3ae;
            background: white;
            overflow: hidden;
            box-shadow: inset 0 0 20px rgba(0,0,0,0.02);
        }

        /* Custom Scrollbar for Textareas */
        textarea::-webkit-scrollbar {
            width: 6px;
        }
        textarea::-webkit-scrollbar-thumb {
            background-color: #d8c3ae;
            border-radius: 4px;
        }

        /* Specific styles for input boxes to maintain clean layout */
        .field-box label {
            display: block;
            font-size: 0.75rem;
            font-weight: 700;
            color: #7a8f82;
            text-transform: uppercase;
            margin-bottom: 0.25rem;
            letter-spacing: 0.05em;
        }
        .field-box textarea {
            width: 100%;
            min-height: 80px;
            padding: 0.5rem;
            background-color: rgba(255,255,255,0.5);
            border: 1px solid #d8c3ae;
            border-radius: 0.5rem;
            font-size: 0.875rem;
            outline: none;
            transition: all 0.2s;
        }
        .field-box textarea:focus {
            border-color: #7a8f82;
            background-color: #fff;
            box-shadow: 0 0 0 2px rgba(122, 143, 130, 0.1);
        }
    </style>
</head>
<body class="text-textMain font-sans antialiased min-h-screen flex flex-col">

    <!-- Header -->
    <header class="w-full glass-panel sticky top-0 z-50">
        <div class="max-w-6xl mx-auto px-4 py-4 flex flex-col md:flex-row justify-between items-center gap-4">
            <div class="text-center md:text-left">
                <h1 class="font-serif text-3xl text-primary font-bold tracking-wide">Andrêssa Nobre Alves</h1>
                <p class="text-xs font-bold text-secondary tracking-[0.2em] uppercase">Psicóloga | CRP: 11/23627</p>
            </div>
            
            <!-- Navigation -->
            <nav class="flex gap-6 text-sm uppercase tracking-wider">
                <button onclick="switchTab('intro')" id="nav-intro" class="tab-active pb-2 transition-all">Guia</button>
                <button onclick="switchTab('map')" id="nav-map" class="tab-inactive pb-2 transition-all">Vivência</button>
                <button onclick="switchTab('insights')" id="nav-insights" class="tab-inactive pb-2 transition-all">Reflexão</button>
            </nav>
        </div>
    </header>

    <!-- Main Content Area -->
    <main class="flex-grow max-w-6xl mx-auto w-full p-4 md:p-8">

        <!-- VIEW 1: INTRO & GUIDE -->
        <section id="view-intro" class="animate-fade-in space-y-8">
            <div class="glass-panel p-8 rounded-2xl text-center space-y-4 border-l-4 border-accent">
                <h2 class="font-serif text-4xl text-primary mb-2">Guia de Autopercepção Corporal</h2>
                <p class="text-lg text-textMuted max-w-2xl mx-auto font-light leading-relaxed">
                    Este não é um teste de precisão. É uma <b>ponte visual</b> entre o que você sente internamente e como habita sua imagem externa. Vamos identificar onde a percepção encontra o desejo de bem-estar.
                </p>
                <button onclick="switchTab('map')" class="mt-6 bg-accent text-white px-8 py-3 rounded-full font-bold shadow-lg hover:bg-primary transition-colors transform hover:-translate-y-1">
                    Iniciar Vivência
                </button>
            </div>

            <div class="grid md:grid-cols-2 gap-6">
                <div class="bg-white p-6 rounded-xl shadow-sm border border-secondary/20">
                    <div class="w-10 h-10 bg-primary/10 rounded-full flex items-center justify-center mb-4 text-primary text-xl">🌿</div>
                    <h3 class="font-serif text-2xl text-primary mb-2">Preparando o Ambiente</h3>
                    <ul class="space-y-3 text-sm text-textMuted">
                        <li class="flex items-start gap-2">
                            <span class="text-accent text-lg">•</span>
                            <span><b>Pausa:</b> Reserve 15 minutos sem pressa.</span>
                        </li>
                        <li class="flex items-start gap-2">
                            <span class="text-accent text-lg">•</span>
                            <span><b>Conexão:</b> Antes de começar, feche os olhos e faça 3 respirações profundas.</span>
                        </li>
                        <li class="flex items-start gap-2">
                            <span class="text-accent text-lg">•</span>
                            <span><b>Escaneamento:</b> Sinta seu corpo do topo da cabeça à ponta dos pés.</span>
                        </li>
                    </ul>
                </div>

                <div class="bg-white p-6 rounded-xl shadow-sm border border-secondary/20">
                    <div class="w-10 h-10 bg-secondary/10 rounded-full flex items-center justify-center mb-4 text-secondary text-xl">✨</div>
                    <h3 class="font-serif text-2xl text-primary mb-2">Dicas de Ouro</h3>
                    <ul class="space-y-3 text-sm text-textMuted">
                        <li class="flex items-start gap-2">
                            <span class="text-secondary text-lg">♥</span>
                            <span><b>Sem Julgamentos:</b> Use termos como "apertado", "leve", "pesado" em vez de críticas.</span>
                        </li>
                        <li class="flex items-start gap-2">
                            <span class="text-secondary text-lg">♥</span>
                            <span><b>Dinâmica:</b> Se hoje sente de um jeito e amanhã de outro, tudo bem. O corpo muda.</span>
                        </li>
                        <li class="flex items-start gap-2">
                            <span class="text-secondary text-lg">♥</span>
                            <span><b>Segurança:</b> Este é um espaço protegido pelo sigilo profissional.</span>
                        </li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- VIEW 2: THE MAP -->
        <section id="view-map" class="hidden space-y-6">
            <div class="glass-panel p-4 rounded-xl flex flex-col md:flex-row gap-4 items-center justify-between">
                <div class="flex-grow w-full md:w-auto">
                    <label class="block text-xs font-bold text-primary uppercase mb-1">Seu Nome</label>
                    <input type="text" id="patientName" placeholder="Como prefere ser chamado(a)?" class="w-full bg-transparent border-b-2 border-secondary focus:border-primary outline-none py-1 text-lg">
                </div>
                <div class="w-full md:w-48">
                    <label class="block text-xs font-bold text-primary uppercase mb-1">Data</label>
                    <input type="date" id="dateInput" class="w-full bg-transparent border-b-2 border-secondary outline-none py-1">
                </div>
            </div>

            <div class="grid lg:grid-cols-[1fr_340px_1fr] gap-8 items-start">
                <div class="space-y-4">
                    <div class="bg-primary text-white p-3 rounded-lg text-center shadow-md">
                        <h3 class="font-bold text-sm tracking-wide uppercase">Percepção Real Atual</h3>
                    </div>
                    <div class="space-y-3" id="current-inputs"></div>
                </div>

                <div class="flex flex-col items-center sticky top-24">
                    <div class="bg-white p-1 rounded-lg border border-secondary mb-2 flex gap-2">
                        <button onclick="setGender('female')" class="px-3 py-1 text-xs font-bold rounded hover:bg-secondary/20 transition-colors uppercase text-primary">Feminino</button>
                        <button onclick="setGender('male')" class="px-3 py-1 text-xs font-bold rounded hover:bg-secondary/20 transition-colors uppercase text-primary">Masculino</button>
                    </div>
                    
                    <div class="canvas-wrapper relative cursor-crosshair group" id="canvas-container">
                        <img id="bodyImage" src="https://img.freepik.com/vetores-premium/ilustracao-em-vetor-silhueta-corpo-feminino_681458-122.jpg" class="w-full h-full object-contain p-4 opacity-90 transition-opacity duration-500">
                        <div id="markers-layer" class="absolute top-0 left-0 w-full h-full z-20"></div>
                        <div class="absolute bottom-4 left-0 w-full text-center pointer-events-none opacity-0 group-hover:opacity-100 transition-opacity">
                            <span class="bg-white/80 px-2 py-1 rounded text-xs text-primary shadow-sm">Toque para marcar tensão</span>
                        </div>
                    </div>
                    <p class="text-xs text-textMuted mt-2 italic text-center max-w-[250px]">Clique na silhueta para marcar pontos de conflito ou atenção.</p>
                </div>

                <div class="space-y-4">
                    <div class="bg-secondary text-white p-3 rounded-lg text-center shadow-md">
                        <h3 class="font-bold text-sm tracking-wide uppercase">Percepção do Ideal</h3>
                    </div>
                    <div class="space-y-3" id="ideal-inputs"></div>
                </div>
            </div>
        </section>

        <!-- VIEW 3: INSIGHTS & REFLECTION -->
        <section id="view-insights" class="hidden animate-fade-in pb-32">
            <div class="glass-panel p-6 rounded-2xl mb-8">
                <h2 class="font-serif text-3xl text-primary mb-4 text-center">Reflexão da Vivência</h2>
                <p class="text-textMuted text-center text-sm mb-8 max-w-lg mx-auto">
                    Visualize onde sua atenção se concentra hoje. Compare a densidade das marcas de tensão com a profundidade do seu relato escrito.
                </p>

                <div class="bg-white p-4 rounded-xl border border-secondary/20 shadow-sm h-[350px] w-full max-w-2xl mx-auto relative mb-8">
                    <canvas id="reflectionChart"></canvas>
                </div>

                <div class="bg-primary/5 p-6 rounded-xl border border-primary/20 text-center max-w-2xl mx-auto">
                    <h3 class="font-serif text-xl text-primary mb-2">Análise Final</h3>
                    <p class="text-sm text-textMuted mb-6 leading-relaxed">
                        Ao observar o gráfico e o mapa, que emoções surgem? Há áreas silenciosas que merecem voz ou áreas sobrecarregadas que pedem descanso? Guarde estas percepções para a nossa próxima sessão.
                    </p>
                    
                    <!-- Whatsapp Button also here in Insights -->
                    <div class="flex flex-col sm:flex-row justify-center gap-3">
                         <button onclick="sendToWhatsapp()" class="px-8 py-3 rounded-xl text-sm font-bold text-white bg-[#25d366] hover:bg-opacity-90 transition-all shadow-lg flex items-center justify-center gap-2 transform hover:scale-105">
                            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24"><path d="M.057 24l1.687-6.163c-1.041-1.804-1.588-3.849-1.587-5.946.003-6.556 5.338-11.891 11.893-11.891 3.181.001 6.167 1.24 8.413 3.488 2.245 2.248 3.481 5.236 3.48 8.414-.003 6.557-5.338 11.892-11.893 11.892-1.99-.001-3.951-.5-5.688-1.448l-6.305 1.654zm6.597-3.807c1.676.995 3.276 1.591 5.392 1.592 5.448 0 9.886-4.434 9.889-9.885.002-5.462-4.415-9.89-9.881-9.892-5.452 0-9.887 4.434-9.889 9.884-.001 2.225.651 3.891 1.746 5.634l-.999 3.648 3.742-.981zm11.387-5.464c-.074-.124-.272-.198-.57-.347-.297-.149-1.758-.868-2.031-.967-.272-.099-.47-.149-.669.149-.198.297-.768.967-.941 1.165-.173.198-.347.223-.644.074-.297-.149-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.297-.347.446-.521.151-.172.2-.296.3-.495.099-.198.05-.372-.025-.521-.075-.148-.669-1.611-.916-2.206-.242-.579-.487-.501-.669-.51l-.57-.01c-.198 0-.52.074-.792.372-.272.297-1.04 1.017-1.04 2.481 0 1.466 1.065 2.875 1.213 3.074.149.198 2.095 3.2 5.076 4.487.709.306 1.263.489 1.694.626.712.226 1.36.194 1.872.118.571-.085 1.758-.719 2.006-1.413.248-.695.248-1.29.173-1.414z"/></svg>
                            <span>ENVIAR RESULTADOS P/ PSI</span>
                        </button>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- Global Floating Action Bar (Map View) -->
    <div id="action-bar" class="hidden fixed bottom-0 left-0 right-0 p-4 bg-white/95 backdrop-blur-md border-t border-secondary/30 flex justify-center gap-3 z-50 shadow-[0_-4px_20px_rgba(0,0,0,0.05)]">
        <button onclick="clearMap()" class="px-6 py-2 rounded-xl text-xs font-bold text-textMuted bg-gray-100 hover:bg-gray-200 transition-colors">
            LIMPAR
        </button>
        <button onclick="switchTab('insights')" class="px-6 py-2 rounded-xl text-xs font-bold text-white bg-primary hover:bg-opacity-90 transition-colors shadow-lg">
            VER ANÁLISE
        </button>
        <button onclick="sendToWhatsapp()" class="px-6 py-2 rounded-xl text-xs font-bold text-white bg-[#25d366] hover:bg-opacity-90 transition-colors shadow-lg flex items-center gap-2">
            <span>ENVIAR P/ PSI</span>
            <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24"><path d="M.057 24l1.687-6.163c-1.041-1.804-1.588-3.849-1.587-5.946.003-6.556 5.338-11.891 11.893-11.891 3.181.001 6.167 1.24 8.413 3.488 2.245 2.248 3.481 5.236 3.48 8.414-.003 6.557-5.338 11.892-11.893 11.892-1.99-.001-3.951-.5-5.688-1.448l-6.305 1.654zm6.597-3.807c1.676.995 3.276 1.591 5.392 1.592 5.448 0 9.886-4.434 9.889-9.885.002-5.462-4.415-9.89-9.881-9.892-5.452 0-9.887 4.434-9.889 9.884-.001 2.225.651 3.891 1.746 5.634l-.999 3.648 3.742-.981zm11.387-5.464c-.074-.124-.272-.198-.57-.347-.297-.149-1.758-.868-2.031-.967-.272-.099-.47-.149-.669.149-.198.297-.768.967-.941 1.165-.173.198-.347.223-.644.074-.297-.149-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.297-.347.446-.521.151-.172.2-.296.3-.495.099-.198.05-.372-.025-.521-.075-.148-.669-1.611-.916-2.206-.242-.579-.487-.501-.669-.51l-.57-.01c-.198 0-.52.074-.792.372-.272.297-1.04 1.017-1.04 2.481 0 1.466 1.065 2.875 1.213 3.074.149.198 2.095 3.2 5.076 4.487.709.306 1.263.489 1.694.626.712.226 1.36.194 1.872.118.571-.085 1.758-.719 2.006-1.413.248-.695.248-1.29.173-1.414z"/></svg>
        </button>
    </div>

    <script>
        // --- DATA & STATE ---
        const state = {
            gender: 'female',
            markers: [], 
            texts: {} 
        };

        const images = {
            female: "https://img.freepik.com/vetores-premium/ilustracao-em-vetor-silhueta-corpo-feminino_681458-122.jpg",
            male: "https://img.freepik.com/vetores-premium/silhueta-de-uma-figura-humana-em-pe_53876-410810.jpg?semt=ais_hybrid&w=740&q=80"
        };

        const bodyParts = [
            { id: 't1', label: 'Cabeça / Rosto', yMin: 0, yMax: 15 },
            { id: 't2', label: 'Pescoço / Ombros', yMin: 15, yMax: 25 },
            { id: 't3', label: 'Tronco / Abdômen', yMin: 25, yMax: 45 },
            { id: 't4', label: 'Braços / Mãos', yMin: 20, yMax: 50 },
            { id: 't5', label: 'Quadril / Coxas', yMin: 45, yMax: 65 },
            { id: 't6', label: 'Pernas / Pés', yMin: 65, yMax: 100 }
        ];

        // --- INIT ---
        document.addEventListener('DOMContentLoaded', () => {
            renderInputs();
            document.getElementById('dateInput').valueAsDate = new Date();
            initChart();
        });

        // --- NAVIGATION ---
        function switchTab(tabId) {
            ['intro', 'map', 'insights'].forEach(t => {
                document.getElementById(`view-${t}`).classList.add('hidden');
                document.getElementById(`nav-${t}`).className = 'tab-inactive pb-2 transition-all';
            });
            
            document.getElementById(`view-${tabId}`).classList.remove('hidden');
            document.getElementById(`nav-${tabId}`).className = 'tab-active pb-2 transition-all';

            // Action bar visibility
            const actionBar = document.getElementById('action-bar');
            if (tabId === 'map') {
                actionBar.classList.remove('hidden');
            } else {
                actionBar.classList.add('hidden');
            }

            if (tabId === 'insights') updateChart();
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // --- INPUT RENDERING ---
        function renderInputs() {
            const createField = (part, prefix, placeholder) => `
                <div class="field-box group">
                    <label>${part.label}</label>
                    <textarea 
                        id="${prefix}-${part.id}" 
                        placeholder="${placeholder}"
                        oninput="saveText('${prefix}-${part.id}')"
                    ></textarea>
                </div>
            `;

            const currentHTML = bodyParts.map(p => createField(p, 'curr', 'Formato, volume, peso ou sensação...')).join('');
            const idealHTML = bodyParts.map(p => createField(p, 'ideal', 'Como gostaria que este contorno fosse?')).join('');

            document.getElementById('current-inputs').innerHTML = currentHTML;
            document.getElementById('ideal-inputs').innerHTML = idealHTML;
        }

        function saveText(id) {
            state.texts[id] = document.getElementById(id).value;
        }

        // --- BODY MAP LOGIC ---
        function setGender(g) {
            if(state.markers.length > 0 && !confirm("Mudar a silhueta apagará as marcas. Continuar?")) return;
            state.gender = g;
            state.markers = [];
            document.getElementById('bodyImage').src = images[g];
            renderMarkers();
        }

        const canvasContainer = document.getElementById('canvas-container');
        canvasContainer.addEventListener('click', (e) => {
            if(e.target.classList.contains('marker')) return;
            const rect = canvasContainer.getBoundingClientRect();
            const x = ((e.clientX - rect.left) / rect.width) * 100;
            const y = ((e.clientY - rect.top) / rect.height) * 100;
            if(x >= 0 && x <= 100 && y >= 0 && y <= 100) {
                state.markers.push({x, y});
                renderMarkers();
            }
        });

        function renderMarkers() {
            const layer = document.getElementById('markers-layer');
            layer.innerHTML = '';
            state.markers.forEach((m, index) => {
                const el = document.createElement('div');
                el.className = 'absolute w-6 h-6 bg-alert border-2 border-white rounded-full flex items-center justify-center text-white text-xs font-bold cursor-pointer shadow-md transform -translate-x-1/2 -translate-y-1/2 hover:scale-110 transition-transform marker';
                el.style.left = `${m.x}%`;
                el.style.top = `${m.y}%`;
                el.innerHTML = '✕';
                el.onclick = (e) => {
                    e.stopPropagation();
                    state.markers.splice(index, 1);
                    renderMarkers();
                };
                layer.appendChild(el);
            });
        }

        function clearMap() {
            if(confirm("Deseja limpar todo o mapa e textos?")) {
                state.markers = [];
                renderMarkers();
                document.querySelectorAll('textarea').forEach(t => t.value = '');
                state.texts = {};
            }
        }

        // --- CHART.JS ---
        let myChart = null;
        function initChart() {
            const ctx = document.getElementById('reflectionChart').getContext('2d');
            myChart = new Chart(ctx, {
                type: 'bar',
                data: {
                    labels: bodyParts.map(p => p.label),
                    datasets: [
                        {
                            label: 'Pontos de Tensão',
                            data: [0,0,0,0,0,0],
                            backgroundColor: '#e53e3e',
                            borderRadius: 4,
                        },
                        {
                            label: 'Intensidade Descritiva',
                            data: [0,0,0,0,0,0],
                            backgroundColor: '#7a8f82',
                            borderRadius: 4,
                            yAxisID: 'y1'
                        }
                    ]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    scales: {
                        y: { beginAtZero: true, display: false },
                        y1: { display: false, position: 'right' },
                        x: { grid: { display: false }, ticks: { font: { family: "'Montserrat'", size: 10 } } }
                    },
                    plugins: {
                        legend: { position: 'bottom', labels: { font: { family: "'Montserrat'", size: 11 } } },
                        tooltip: { backgroundColor: '#fff', titleColor: '#2d3748', bodyColor: '#718096', borderColor: '#d8c3ae', borderWidth: 1 }
                    }
                }
            });
        }

        function updateChart() {
            const markerCounts = [0, 0, 0, 0, 0, 0];
            state.markers.forEach(m => {
                bodyParts.forEach((part, idx) => {
                    if(m.y >= part.yMin && m.y < part.yMax) markerCounts[idx]++;
                });
            });
            const textCounts = bodyParts.map(p => {
                const len = (document.getElementById(`curr-${p.id}`)?.value || '').length + (document.getElementById(`ideal-${p.id}`)?.value || '').length;
                return Math.min(len / 10, 15); 
            });
            myChart.data.datasets[0].data = markerCounts;
            myChart.data.datasets[1].data = textCounts;
            myChart.update();
        }

        // --- EXPORT ---
        function getHtmlContent() {
            const docClone = document.documentElement.cloneNode(true);
            const name = document.getElementById('patientName').value;
            const date = document.getElementById('dateInput').value;
            docClone.querySelector('#patientName').setAttribute('value', name);
            docClone.querySelector('#dateInput').setAttribute('value', date);
            
            const areas = document.querySelectorAll('textarea');
            const cloneAreas = docClone.querySelectorAll('textarea');
            areas.forEach((a, i) => {
                cloneAreas[i].innerHTML = a.value;
                cloneAreas[i].setAttribute('readonly', true);
            });

            const markerLayer = docClone.querySelector('#markers-layer');
            markerLayer.innerHTML = '';
            state.markers.forEach(m => {
                const el = document.createElement('div');
                el.className = 'absolute w-6 h-6 bg-alert border-2 border-white rounded-full flex items-center justify-center text-white text-xs font-bold transform -translate-x-1/2 -translate-y-1/2';
                el.style.left = `${m.x}%`; el.style.top = `${m.y}%`;
                el.innerHTML = '✕';
                markerLayer.appendChild(el);
            });

            docClone.querySelector('#bodyImage').src = state.gender === 'female' ? images.female : images.male;
            docClone.querySelectorAll('nav, button, #action-bar, #view-intro, #view-insights').forEach(el => el.remove());
            docClone.querySelector('#view-map').classList.remove('hidden');
            
            const style = document.createElement('style');
            style.innerHTML = `textarea { border:none; background:transparent; resize:none; font-weight:500; } body { background:#fff; padding:20px; }`;
            docClone.querySelector('head').appendChild(style);
            return "<!DOCTYPE html>" + docClone.outerHTML;
        }

        function downloadHtml() {
            const name = document.getElementById('patientName').value || "Paciente";
            const blob = new Blob([getHtmlContent()], { type: 'text/html' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = `Mapa_Corporal_${name.replace(/\s+/g, '_')}.html`;
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
            return a.download;
        }

        function sendToWhatsapp() {
            const name = document.getElementById('patientName').value || "Paciente";
            const filename = downloadHtml();
            const phone = "5585992844168";
            const text = encodeURIComponent(`Olá, Andrêssa! Sou ${name}. Concluí meu Mapa de Autopercepção Corporal.\nArquivo salvo: ${filename}\n\nEstou enviando em anexo (📎 > Documento).`);
            setTimeout(() => { window.open(`https://wa.me/${phone}?text=${text}`, '_blank'); }, 1000);
        }
    </script>
</body>
</html>
