<!DOCTYPE html>
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

        <!-- VIEW 1: INTRO & GUIDE (The "Understanding" Phase) -->
        <section id="view-intro" class="animate-fade-in space-y-8">
            
            <!-- Hero Card -->
            <div class="glass-panel p-8 rounded-2xl text-center space-y-4 border-l-4 border-accent">
                <h2 class="font-serif text-4xl text-primary mb-2">Guia de Autopercepção Corporal</h2>
                <p class="text-lg text-textMuted max-w-2xl mx-auto font-light leading-relaxed">
                    Este não é um teste de precisão. É uma <b>ponte visual</b> entre o que você sente internamente e como habita sua imagem externa. Vamos identificar onde a percepção encontra o desejo de bem-estar.
                </p>
                <button onclick="switchTab('map')" class="mt-6 bg-accent text-white px-8 py-3 rounded-full font-bold shadow-lg hover:bg-primary transition-colors transform hover:-translate-y-1">
                    Iniciar Vivência
                </button>
            </div>

            <!-- Preparation Grid -->
            <div class="grid md:grid-cols-2 gap-6">
                <!-- Step 1: Prep -->
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

                <!-- Step 2: Mental Set -->
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

        <!-- VIEW 2: THE MAP (The Interactive Tool) -->
        <section id="view-map" class="hidden space-y-6">
            
            <!-- Patient ID Bar -->
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

            <!-- The Work Area -->
            <div class="grid lg:grid-cols-[1fr_340px_1fr] gap-8 items-start">
                
                <!-- Left: Current Perception -->
                <div class="space-y-4">
                    <div class="bg-primary text-white p-3 rounded-lg text-center shadow-md">
                        <h3 class="font-bold text-sm tracking-wide">PERCEPÇÃO REAL ATUAL</h3>
                        <p class="text-xs opacity-90 font-light italic mt-1">"O que o espelho e o toque dizem hoje?"</p>
                    </div>
                    
                    <!-- Dynamic Input Fields -->
                    <div class="space-y-3" id="current-inputs">
                        <!-- JS generated fields -->
                    </div>
                </div>

                <!-- Center: Body Canvas -->
                <div class="flex flex-col items-center sticky top-24">
                    <div class="bg-white p-1 rounded-lg border border-secondary mb-2 flex gap-2">
                        <button onclick="setGender('female')" class="px-3 py-1 text-xs font-bold rounded hover:bg-secondary/20 transition-colors uppercase text-primary">Feminino</button>
                        <button onclick="setGender('male')" class="px-3 py-1 text-xs font-bold rounded hover:bg-secondary/20 transition-colors uppercase text-primary">Masculino</button>
                    </div>
                    
                    <div class="canvas-wrapper relative cursor-crosshair group" id="canvas-container">
                        <img id="bodyImage" src="https://img.freepik.com/vetores-premium/ilustracao-em-vetor-silhueta-corpo-feminino_681458-122.jpg" class="w-full h-full object-contain p-4 opacity-90 transition-opacity duration-500">
                        <!-- Markers go here -->
                        <canvas id="drawingCanvas" class="absolute top-0 left-0 w-full h-full z-10 pointer-events-none"></canvas>
                        <div id="markers-layer" class="absolute top-0 left-0 w-full h-full z-20"></div>
                        
                        <!-- Hover Instruction -->
                        <div class="absolute bottom-4 left-0 w-full text-center pointer-events-none opacity-0 group-hover:opacity-100 transition-opacity">
                            <span class="bg-white/80 px-2 py-1 rounded text-xs text-primary shadow-sm">Toque para marcar tensão</span>
                        </div>
                    </div>
                    <p class="text-xs text-textMuted mt-2 italic text-center max-w-[250px]">Toque na silhueta para marcar pontos de conflito, dor ou atenção.</p>
                </div>

                <!-- Right: Ideal Perception -->
                <div class="space-y-4">
                    <div class="bg-secondary text-white p-3 rounded-lg text-center shadow-md">
                        <h3 class="font-bold text-sm tracking-wide">PERCEPÇÃO DO IDEAL</h3>
                        <p class="text-xs opacity-90 font-light italic mt-1">"Como gostaria de se sentir leve?"</p>
                    </div>

                    <!-- Dynamic Input Fields -->
                    <div class="space-y-3" id="ideal-inputs">
                        <!-- JS generated fields -->
                    </div>
                </div>
            </div>

            <!-- Action Bar -->
            <div class="fixed bottom-0 left-0 right-0 p-4 bg-white/95 backdrop-blur-md border-t border-secondary/30 flex justify-center gap-3 z-50 shadow-[0_-4px_20px_rgba(0,0,0,0.05)]">
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
        </section>

        <!-- VIEW 3: INSIGHTS & REFLECTION (Chart.js Visualization) -->
        <section id="view-insights" class="hidden animate-fade-in pb-20">
            <div class="glass-panel p-6 rounded-2xl mb-8">
                <h2 class="font-serif text-3xl text-primary mb-4 text-center">Reflexão da Vivência</h2>
                <p class="text-textMuted text-center text-sm mb-8 max-w-lg mx-auto">
                    Abaixo você pode visualizar onde sua atenção está mais concentrada hoje. Observe se há um equilíbrio entre o que você sente (Atual) e o que você deseja (Ideal).
                </p>

                <!-- Chart Container -->
                <div class="bg-white p-4 rounded-xl border border-secondary/20 shadow-sm h-[300px] w-full max-w-2xl mx-auto relative">
                    <canvas id="reflectionChart"></canvas>
                </div>
            </div>

            <div class="bg-primary/5 p-6 rounded-xl border border-primary/20 text-center">
                <h3 class="font-serif text-xl text-primary mb-2">Próximos Passos</h3>
                <p class="text-sm text-textMuted mb-4">
                    Ao observar este mapa, que emoção surge? Alívio? Surpresa? 
                    <br>Leve estas percepções para nossa próxima sessão.
                </p>
            </div>
        </section>

    </main>

    <script>
        // --- DATA & STATE ---
        const state = {
            gender: 'female',
            markers: [], // {x: %, y: %}
            texts: {} // id: string
        };

        const images = {
            female: "https://img.freepik.com/vetores-premium/ilustracao-em-vetor-silhueta-corpo-feminino_681458-122.jpg",
            male: "https://img.freepik.com/vetores-premium/silhueta-de-uma-figura-humana-em-pe_53876-410810.jpg?semt=ais_hybrid&w=740&q=80"
        };

        const bodyParts = [
            { id: 't1', label: 'Cabeça / Rosto', yMin: 0, yMax: 15 },
            { id: 't2', label: 'Pescoço / Ombros', yMin: 15, yMax: 25 },
            { id: 't3', label: 'Tronco / Abdômen', yMin: 25, yMax: 45 },
            { id: 't4', label: 'Braços / Mãos', yMin: 20, yMax: 50 }, // Side approximation
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
            // UI Update
            ['intro', 'map', 'insights'].forEach(t => {
                document.getElementById(`view-${t}`).classList.add('hidden');
                document.getElementById(`nav-${t}`).className = 'tab-inactive pb-2 transition-all';
            });
            
            document.getElementById(`view-${tabId}`).classList.remove('hidden');
            document.getElementById(`nav-${tabId}`).className = 'tab-active pb-2 transition-all';

            // Special actions
            if (tabId === 'insights') updateChart();
        }

        // --- INPUT RENDERING ---
        function renderInputs() {
            const createField = (part, prefix, placeholder) => `
                <div class="field-box group">
                    <label class="group-focus-within:text-accent transition-colors">${part.label}</label>
                    <textarea 
                        id="${prefix}-${part.id}" 
                        placeholder="${placeholder}"
                        oninput="saveText('${prefix}-${part.id}')"
                    ></textarea>
                </div>
            `;

            const currentHTML = bodyParts.map(p => createField(p, 'curr', 'Descreva o formato, volume, sensação...')).join('');
            const idealHTML = bodyParts.map(p => createField(p, 'ideal', 'Como seria o contorno de paz?')).join('');

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
            // Prevent marking if clicking on existing marker
            if(e.target.classList.contains('marker')) return;

            const rect = canvasContainer.getBoundingClientRect();
            const x = ((e.clientX - rect.left) / rect.width) * 100;
            const y = ((e.clientY - rect.top) / rect.height) * 100;

            // Boundary check
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

        // --- CHART.JS VISUALIZATION ---
        let myChart = null;

        function initChart() {
            const ctx = document.getElementById('reflectionChart').getContext('2d');
            
            // Custom plugin to draw background image behind chart if needed, 
            // but simple bar chart is better here.
            
            myChart = new Chart(ctx, {
                type: 'bar',
                data: {
                    labels: bodyParts.map(p => p.label),
                    datasets: [
                        {
                            label: 'Pontos de Tensão (Marcas)',
                            data: [0,0,0,0,0,0],
                            backgroundColor: '#e53e3e',
                            borderRadius: 6,
                        },
                        {
                            label: 'Intensidade do Relato (Caracteres)',
                            data: [0,0,0,0,0,0],
                            backgroundColor: '#7a8f82',
                            borderRadius: 6,
                            yAxisID: 'y1'
                        }
                    ]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    scales: {
                        y: {
                            beginAtZero: true,
                            grid: { display: false },
                            display: false // Hide axis numbers for cleaner look
                        },
                        y1: {
                            display: false,
                            position: 'right',
                            grid: { display: false }
                        },
                        x: {
                            grid: { display: false },
                            ticks: { font: { family: "'Montserrat', sans-serif", size: 10 } }
                        }
                    },
                    plugins: {
                        legend: { position: 'bottom', labels: { font: { family: "'Montserrat', sans-serif" } } },
                        tooltip: {
                            backgroundColor: 'rgba(255,255,255,0.9)',
                            titleColor: '#2d3748',
                            bodyColor: '#718096',
                            borderColor: '#d8c3ae',
                            borderWidth: 1,
                            callbacks: {
                                label: function(context) {
                                    let label = context.dataset.label || '';
                                    if (label) {
                                        label += ': ';
                                    }
                                    if (context.parsed.y !== null) {
                                        label += context.parsed.y;
                                    }
                                    return label;
                                }
                            }
                        }
                    }
                }
            });
        }

        function updateChart() {
            // Count markers per region based on Y coordinate
            const markerCounts = [0, 0, 0, 0, 0, 0];
            state.markers.forEach(m => {
                const y = m.y;
                // Simple logic: mapping markers roughly to body parts based on Y %
                // Head: 0-15, Neck: 15-25, Torso: 25-45, Arms: check X, but simplify to Y for now or mainly Torso/Arms overlap
                // Let's iterate bodyParts config
                bodyParts.forEach((part, idx) => {
                    if(y >= part.yMin && y < part.yMax) {
                        markerCounts[idx]++;
                    }
                });
            });

            // Count text length (intensity of description)
            const textCounts = bodyParts.map(p => {
                const currLen = (document.getElementById(`curr-${p.id}`)?.value || '').length;
                const idealLen = (document.getElementById(`ideal-${p.id}`)?.value || '').length;
                return Math.min((currLen + idealLen) / 10, 10); // Scale down for visual balance
            });

            myChart.data.datasets[0].data = markerCounts;
            myChart.data.datasets[1].data = textCounts;
            myChart.update();
        }

        // --- EXPORT & SEND ---
        function getHtmlContent() {
            // Clone document to make a readonly version
            const docClone = document.documentElement.cloneNode(true);
            
            // Fix inputs
            const name = document.getElementById('patientName').value;
            const date = document.getElementById('dateInput').value;
            docClone.querySelector('#patientName').setAttribute('value', name);
            docClone.querySelector('#dateInput').setAttribute('value', date);
            
            // Fix Textareas
            const areas = document.querySelectorAll('textarea');
            const cloneAreas = docClone.querySelectorAll('textarea');
            areas.forEach((a, i) => {
                cloneAreas[i].innerHTML = a.value; // Store value in HTML
                cloneAreas[i].setAttribute('readonly', true);
            });

            // Fix Markers (Inject them into HTML permanently)
            const markerLayer = docClone.querySelector('#markers-layer');
            markerLayer.innerHTML = ''; // Clear events
            state.markers.forEach(m => {
                const el = document.createElement('div');
                el.className = 'absolute w-6 h-6 bg-alert border-2 border-white rounded-full flex items-center justify-center text-white text-xs font-bold transform -translate-x-1/2 -translate-y-1/2';
                el.style.left = `${m.x}%`;
                el.style.top = `${m.y}%`;
                el.innerHTML = '✕';
                markerLayer.appendChild(el);
            });

            // Ensure correct image
            docClone.querySelector('#bodyImage').src = state.gender === 'female' ? images.female : images.male;

            // Clean up UI for Readonly
            docClone.querySelectorAll('.no-print').forEach(el => el.remove()); // Remove buttons
            docClone.querySelector('#view-intro').remove(); // Remove Intro
            docClone.querySelector('#view-insights').remove(); // Remove Chart section (optional, keeping clean)
            docClone.querySelector('#view-map').classList.remove('hidden'); // Ensure map is visible
            
            // Add Readonly styles
            const style = document.createElement('style');
            style.innerHTML = `
                textarea { border: none; background: transparent; resize: none; overflow: hidden; height: auto; font-weight: 500; color: #000; }
                input { border: none; font-weight: bold; color: #000; }
                .glass-panel { box-shadow: none; border: none; }
                body { padding: 20px; background-image: none; background-color: #fff; }
                .canvas-wrapper { border: 1px solid #ccc; box-shadow: none; }
            `;
            docClone.querySelector('head').appendChild(style);

            return "<!DOCTYPE html>" + docClone.outerHTML;
        }

        function downloadHtml() {
            const name = document.getElementById('patientName').value || "Paciente";
            const htmlContent = getHtmlContent();
            const blob = new Blob([htmlContent], { type: 'text/html' });
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
            const text = encodeURIComponent(
                `Olá, Andrêssa Nobre! 🌿\n\nSou ${name}. Concluí meu Mapa de Autopercepção Corporal.\n\n✅ O arquivo "${filename}" já foi salvo no meu celular/computador.\n\n📍 Estou enviando ele em anexo agora (clicando no clipe 📎 > Documento).`
            );
            
            // Small delay to allow download to start
            setTimeout(() => {
                window.open(`https://wa.me/${phone}?text=${text}`, '_blank');
            }, 1000);
        }
    </script>
</body>
</html>
