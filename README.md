[index.html](https://github.com/user-attachments/files/30688251/index.html)
<!DOCTYPE html>
<html lang="de" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mandala Art | Mandala-Künstler in Deutschland</title>
    <!-- 引入 Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        darkBg: '#0b0f19',
                        cardBg: '#131c2e',
                        accentGold: '#d4af37',
                    }
                }
            }
        }
    </script>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Serif+TC:wght@300;400;600&family=Plus+Jakarta+Sans:wght@300;400;500&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Plus Jakarta Sans', 'Noto Serif TC', serif; background-color: #0b0f19; color: #e2e8f0; }
        .drag-over { border: 2px dashed #d4af37 !important; background-color: rgba(212, 175, 55, 0.1); }
        .editable-price:focus { outline: none; border-bottom: 1px solid #d4af37; background-color: rgba(212, 175, 55, 0.05); }
    </style>
</head>
<body class="bg-darkBg text-slate-100 antialiased selection:bg-accentGold selection:text-darkBg">

    <!-- Navigation -->
    <header class="fixed top-0 left-0 w-full z-50 bg-darkBg/85 backdrop-blur-md border-b border-slate-800">
        <div class="max-w-7xl mx-auto px-6 h-20 flex items-center justify-between">
            <a href="#" class="text-xl tracking-widest font-light uppercase text-slate-100">
                Aura <span class="text-accentGold">Mandala</span>
            </a>
            <nav class="hidden md:flex space-x-8 text-sm tracking-widest uppercase font-light text-slate-300">
                <a href="#gallery" class="hover:text-accentGold transition">Galerie & Shop</a>
                <a href="#about" class="hover:text-accentGold transition">Biografie</a>
                <a href="#contact" class="hover:text-accentGold transition">Kontakt & Auftrag</a>
            </nav>
            <div class="flex items-center space-x-4">
                <span class="text-xs text-slate-400 tracking-wider hidden sm:inline">Berlin / München</span>
                <button id="adminNavBtn" onclick="handleAdminBtnClick()" class="border border-accentGold/50 text-accentGold px-3 py-1 text-xs tracking-widest uppercase hover:bg-accentGold hover:text-darkBg transition duration-300">
                    Admin
                </button>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="min-h-screen flex items-center justify-center relative pt-20 px-6 overflow-hidden">
        <div class="absolute inset-0 opacity-20 pointer-events-none flex items-center justify-center">
            <div class="w-[600px] h-[600px] rounded-full border border-accentGold/30 animate-pulse"></div>
            <div class="absolute w-[400px] h-[400px] rounded-full border border-accentGold/20"></div>
        </div>
        <div class="max-w-4xl mx-auto text-center z-10">
            <span class="text-accentGold tracking-[0.3em] uppercase text-xs md:text-sm block mb-4">Heilige Geometrie & Innerer Kosmos</span>
            <h1 class="text-4xl md:text-6xl font-light tracking-wide mb-6 leading-tight">Entdeckung der visuellen Resonanz der inneren Ordnung</h1>
            <p class="text-slate-400 font-light max-w-xl mx-auto mb-10 text-sm md:text-base leading-relaxed">
                Zeitgenössische Mandala-Kunst in Deutschland. Eine Verbindung östlicher spiritueller Philosophie mit westlicher, präziser Geometrie, um in komplexen Linien ewige Ruhe und Ausgeglichenheit zu finden.
            </p>
            <a href="#gallery" class="inline-block border border-accentGold text-accentGold px-8 py-3 text-xs tracking-[0.2em] uppercase hover:bg-accentGold hover:text-darkBg transition duration-300">
                Werke entdecken
            </a>
        </div>
    </section>

    <!-- Gallery & Shop -->
    <section id="gallery" class="py-28 px-6 max-w-7xl mx-auto">
        <div class="text-center mb-16">
            <h2 class="text-2xl md:text-3xl font-light tracking-widest uppercase mb-3">Ausgewählte Werke</h2>
            <div class="w-12 h-[1px] bg-accentGold mx-auto"></div>
            <div id="adminEditBar" class="hidden mt-4 inline-block bg-accentGold/10 border border-accentGold/30 px-4 py-2 text-xs text-accentGold tracking-wider">
                ⚙️ Admin-Modus entsperrt: Bilder ziehen/ablegen, Preise ändern und Text bearbeiten. Klicken Sie unten auf Speichern!
            </div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-10">
            
            <!-- Artwork 1 -->
            <div class="group bg-cardBg rounded-sm overflow-hidden border border-slate-800/60 hover:border-accentGold/50 transition duration-300">
                <div id="img-container-1" class="aspect-square overflow-hidden bg-slate-900 relative flex items-center justify-center" 
                     ondragover="handleDragOver(event)" ondragleave="handleDragLeave(event)" ondrop="handleDrop(event, '1')">
                    
                    <div id="img-inner-1" class="absolute inset-0 bg-gradient-to-tr from-indigo-950 via-slate-900 to-amber-950 flex items-center justify-center group-hover:scale-105 transition duration-500">
                        <div class="w-48 h-48 rounded-full border border-accentGold/40 flex items-center justify-center rotate-45"><div class="w-32 h-32 rounded-full border border-cyan-500/40 rotate-12"></div></div>
                    </div>
                    <span class="absolute top-4 left-4 bg-darkBg/80 text-xs px-3 py-1 text-accentGold tracking-wider uppercase border border-slate-700 z-10">Original</span>
                    
                    <div class="admin-img-overlay absolute inset-0 bg-black/60 backdrop-blur-xs flex flex-col items-center justify-center opacity-0 hover:opacity-100 transition duration-300 hidden z-20">
                        <label class="cursor-pointer bg-accentGold text-darkBg px-4 py-2 text-xs tracking-widest uppercase font-medium hover:bg-white transition mb-2">
                            Bild auswählen / Hierher ziehen <input type="file" accept="image/*" class="hidden" onchange="handleFileSelect(event, '1')">
                        </label>
                        <span class="text-[10px] text-slate-300">Unterstützt JPG, PNG</span>
                    </div>
                </div>

                <div id="size-control-1" class="admin-size-ctrl p-4 bg-slate-900/60 border-b border-slate-800 space-y-3 hidden">
                    <div class="flex justify-between items-center text-[11px] text-slate-400">
                        <span>Bildanpassung (Fit)</span>
                        <div class="space-x-1">
                            <button onclick="setImageFit('1', 'cover')" id="fit-cover-1" class="px-2 py-0.5 bg-accentGold text-darkBg font-medium text-[10px] rounded">Ausfüllen</button>
                            <button onclick="setImageFit('1', 'contain')" id="fit-contain-1" class="px-2 py-0.5 bg-slate-800 text-slate-300 text-[10px] rounded hover:bg-slate-700">Einpassen</button>
                        </div>
                    </div>
                    <div>
                        <div class="flex justify-between text-[11px] text-slate-400 mb-1">
                            <span>Manuelle Skalierung</span> <span id="scale-val-1">100%</span>
                        </div>
                        <input type="range" min="80" max="150" value="100" class="w-full accent-accentGold" oninput="changeImageScale('1', this.value)">
                    </div>
                </div>

                <div class="p-6">
                    <div class="flex justify-between items-start mb-2">
                        <h3 class="text-lg font-light tracking-wide">Ether Matrix (Äthermatrix)</h3>
                        <span id="price-1" class="text-accentGold font-mono text-sm px-1 rounded transition">€ 1,200</span>
                    </div>
                    <p class="text-xs text-slate-400 font-light mb-4">Acryl, Blattgold, Leinwand • 80x80 cm • 2026</p>
                </div>
            </div>

            <!-- Artwork 2 -->
            <div class="group bg-cardBg rounded-sm overflow-hidden border border-slate-800/60 hover:border-accentGold/50 transition duration-300">
                <div id="img-container-2" class="aspect-square overflow-hidden bg-slate-900 relative flex items-center justify-center" 
                     ondragover="handleDragOver(event)" ondragleave="handleDragLeave(event)" ondrop="handleDrop(event, '2')">
                    
                    <div id="img-inner-2" class="absolute inset-0 bg-gradient-to-tr from-purple-950 via-slate-900 to-slate-950 flex items-center justify-center group-hover:scale-105 transition duration-500">
                        <div class="w-48 h-48 rounded-full border border-purple-400/40 flex items-center justify-center"><div class="w-32 h-32 rounded-full border border-amber-500/40"></div></div>
                    </div>
                    <span class="absolute top-4 left-4 bg-darkBg/80 text-xs px-3 py-1 text-slate-300 tracking-wider uppercase border border-slate-700 z-10">Limitierter Druck</span>
                    
                    <div class="admin-img-overlay absolute inset-0 bg-black/60 backdrop-blur-xs flex flex-col items-center justify-center opacity-0 hover:opacity-100 transition duration-300 hidden z-20">
                        <label class="cursor-pointer bg-accentGold text-darkBg px-4 py-2 text-xs tracking-widest uppercase font-medium hover:bg-white transition mb-2">
                            Bild auswählen / Hierher ziehen <input type="file" accept="image/*" class="hidden" onchange="handleFileSelect(event, '2')">
                        </label>
                    </div>
                </div>

                <div id="size-control-2" class="admin-size-ctrl p-4 bg-slate-900/60 border-b border-slate-800 space-y-3 hidden">
                    <div class="flex justify-between items-center text-[11px] text-slate-400">
                        <span>Bildanpassung (Fit)</span>
                        <div class="space-x-1">
                            <button onclick="setImageFit('2', 'cover')" id="fit-cover-2" class="px-2 py-0.5 bg-accentGold text-darkBg font-medium text-[10px] rounded">Ausfüllen</button>
                            <button onclick="setImageFit('2', 'contain')" id="fit-contain-2" class="px-2 py-0.5 bg-slate-800 text-slate-300 text-[10px] rounded hover:bg-slate-700">Einpassen</button>
                        </div>
                    </div>
                    <div>
                        <div class="flex justify-between text-[11px] text-slate-400 mb-1">
                            <span>Manuelle Skalierung</span> <span id="scale-val-2">100%</span>
                        </div>
                        <input type="range" min="80" max="150" value="100" class="w-full accent-accentGold" oninput="changeImageScale('2', this.value)">
                    </div>
                </div>

                <div class="p-6">
                    <div class="flex justify-between items-start mb-2">
                        <h3 class="text-lg font-light tracking-wide">Cosmic Heart (Kosmisches Herz)</h3>
                        <span id="price-2" class="text-accentGold font-mono text-sm px-1 rounded transition">€ 280</span>
                    </div>
                    <p class="text-xs text-slate-400 font-light mb-4">Fine Art Print (Limitiert auf 50 Stück) • 50x50 cm</p>
                </div>
            </div>

            <!-- Artwork 3 -->
            <div class="group bg-cardBg rounded-sm overflow-hidden border border-slate-800/60 hover:border-accentGold/50 transition duration-300">
                <div id="img-container-3" class="aspect-square overflow-hidden bg-slate-900 relative flex items-center justify-center" 
                     ondragover="handleDragOver(event)" ondragleave="handleDragLeave(event)" ondrop="handleDrop(event, '3')">
                    
                    <div id="img-inner-3" class="absolute inset-0 bg-gradient-to-tr from-slate-950 via-blue-950 to-emerald-950 flex items-center justify-center group-hover:scale-105 transition duration-500">
                        <div class="w-48 h-48 rounded-full border border-emerald-400/40 flex items-center justify-center rotate-12"><div class="w-32 h-32 rounded-full border border-blue-500/40"></div></div>
                    </div>
                    <span class="absolute top-4 left-4 bg-darkBg/80 text-xs px-3 py-1 text-accentGold tracking-wider uppercase border border-slate-700 z-10">Original</span>
                    
                    <div class="admin-img-overlay absolute inset-0 bg-black/60 backdrop-blur-xs flex flex-col items-center justify-center opacity-0 hover:opacity-100 transition duration-300 hidden z-20">
                        <label class="cursor-pointer bg-accentGold text-darkBg px-4 py-2 text-xs tracking-widest uppercase font-medium hover:bg-white transition mb-2">
                            Bild auswählen / Hierher ziehen <input type="file" accept="image/*" class="hidden" onchange="handleFileSelect(event, '3')">
                        </label>
                    </div>
                </div>

                <div id="size-control-3" class="admin-size-ctrl p-4 bg-slate-900/60 border-b border-slate-800 space-y-3 hidden">
                    <div class="flex justify-between items-center text-[11px] text-slate-400">
                        <span>Bildanpassung (Fit)</span>
                        <div class="space-x-1">
                            <button onclick="setImageFit('3', 'cover')" id="fit-cover-3" class="px-2 py-0.5 bg-accentGold text-darkBg font-medium text-[10px] rounded">Ausfüllen</button>
                            <button onclick="setImageFit('3', 'contain')" id="fit-contain-3" class="px-2 py-0.5 bg-slate-800 text-slate-300 text-[10px] rounded hover:bg-slate-700">Einpassen</button>
                        </div>
                    </div>
                    <div>
                        <div class="flex justify-between text-[11px] text-slate-400 mb-1">
                            <span>Manuelle Skalierung</span> <span id="scale-val-3">100%</span>
                        </div>
                        <input type="range" min="80" max="150" value="100" class="w-full accent-accentGold" oninput="changeImageScale('3', this.value)">
                    </div>
                </div>

                <div class="p-6">
                    <div class="flex justify-between items-start mb-2">
                        <h3 class="text-lg font-light tracking-wide">Silent Zero (Absolute Stille)</h3>
                        <span id="price-3" class="text-accentGold font-mono text-sm px-1 rounded transition">€ 1,500</span>
                    </div>
                    <p class="text-xs text-slate-400 font-light mb-4">Acryl, Metallpigmente • 100x100 cm • 2025</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Biography -->
    <section id="about" class="py-28 bg-cardBg/40 border-y border-slate-800/80 px-6 transition">
        <div class="max-w-4xl mx-auto grid grid-cols-1 md:grid-cols-3 gap-12 items-center">
            
            <div class="flex flex-col space-y-3">
                <div id="img-container-portrait" class="aspect-[3/4] bg-slate-800 border border-slate-700 relative flex items-center justify-center overflow-hidden group"
                     ondragover="handleDragOver(event)" ondragleave="handleDragLeave(event)" ondrop="handleDrop(event, 'portrait')">
                    
                    <div id="img-inner-portrait" class="absolute inset-0 flex items-center justify-center text-slate-500 text-xs tracking-widest uppercase bg-slate-900">
                        Künstlerporträt
                    </div>
                    <div class="admin-img-overlay absolute inset-0 bg-black/60 backdrop-blur-xs flex flex-col items-center justify-center opacity-0 hover:opacity-100 transition duration-300 hidden z-20">
                        <label class="cursor-pointer bg-accentGold text-darkBg px-3 py-1.5 text-[10px] tracking-widest uppercase font-medium hover:bg-white transition mb-1">
                            Bild auswählen / Hierher ziehen <input type="file" accept="image/*" class="hidden" onchange="handleFileSelect(event, 'portrait')">
                        </label>
                    </div>
                </div>

                <div id="size-control-portrait" class="admin-size-ctrl p-3 bg-slate-900/80 border border-slate-800 rounded space-y-2 hidden">
                    <div class="flex justify-between items-center text-[10px] text-slate-400">
                        <span>Bildanpassung</span>
                        <div class="space-x-1">
                            <button onclick="setImageFit('portrait', 'cover')" id="fit-cover-portrait" class="px-2 py-0.5 bg-accentGold text-darkBg font-medium text-[9px] rounded">Ausfüllen</button>
                            <button onclick="setImageFit('portrait', 'contain')" id="fit-contain-portrait" class="px-2 py-0.5 bg-slate-800 text-slate-300 text-[9px] rounded hover:bg-slate-700">Einpassen</button>
                        </div>
                    </div>
                    <div>
                        <div class="flex justify-between text-[10px] text-slate-400 mb-1">
                            <span>Skalierung</span> <span id="scale-val-portrait">100%</span>
                        </div>
                        <input type="range" min="80" max="150" value="100" class="w-full accent-accentGold" oninput="changeImageScale('portrait', this.value)">
                    </div>
                </div>
            </div>

            <div class="md:col-span-2">
                <span class="text-accentGold tracking-[0.3em] uppercase text-xs block mb-3">Biografie</span>
                <h2 id="bio-title" class="text-2xl font-light tracking-wide mb-6 rounded transition">Im rationalen Raum Deutschlands die heilige Geometrie des Ostens weben</h2>
                <p id="bio-p1" class="text-slate-300 font-light text-sm leading-relaxed mb-4 rounded transition">Lebt in Deutschland. Der Kern der Arbeit entspringt der Suche nach der zugrunde liegenden Struktur des Lebens. Mandala bedeutet im Sanskrit „Kreis“ und ist auch ein Dialog zwischen dem Mikrokosmos und dem makrokosmischen Geist.</p>
                <p id="bio-p2" class="text-slate-400 font-light text-sm leading-relaxed mb-6 rounded transition">Durch extrem strenge geometrische Symmetrie und feine Pinselstriche werden Energiefelder auf der Leinwand aufgebaut, die den Betrachter zu innerem Frieden führen können. Die Werke wurden in unabhängigen Galerien in Berlin, Frankfurt und anderen Orten ausgestellt.</p>
                <div id="bio-exhibitions" class="text-xs text-accentGold tracking-wider rounded transition">Ausstellungen: Berlin Art Week (2025) • München Design Center (2024)</div>
            </div>
        </div>
    </section>

    <!-- Contact -->
    <section id="contact" class="py-28 px-6 max-w-3xl mx-auto text-center">
        <span class="text-accentGold tracking-[0.3em] uppercase text-xs block mb-3">Kontakt aufnehmen</span>
        <h2 class="text-2xl md:text-3xl font-light tracking-widest uppercase mb-6">Kontakt & Auftrag</h2>
        <p class="text-slate-400 font-light text-sm mb-10">Wenn Sie an Originalgemälden oder limitierten Drucken interessiert sind oder ein individuelles Mandala in Auftrag geben möchten, kontaktieren Sie mich bitte.</p>
        <a href="mailto:contact@auramandala.com" class="inline-block bg-accentGold text-darkBg px-8 py-3 text-xs tracking-[0.2em] uppercase font-medium hover:bg-white transition duration-300">
            E-Mail senden
        </a>
    </section>

    <!-- Firebase Save Button -->
    <div id="savePriceContainer" class="text-center py-12 bg-darkBg border-t border-slate-800 hidden">
        <p id="upload-status" class="text-xs text-slate-400 mb-3 hidden">Bilder werden hochgeladen und Daten gespeichert, bitte warten...</p>
        <button onclick="saveDataToFirebase()" class="bg-accentGold text-darkBg px-8 py-3 text-xs tracking-[0.2em] uppercase font-medium hover:bg-white transition duration-300 shadow-lg">
            Änderungen dauerhaft speichern
        </button>
    </div>

    <!-- Footer -->
    <footer class="py-8 border-t border-slate-800 text-center text-xs text-slate-500">
        <p>&copy; 2026 Aura Mandala. Alle Rechte vorbehalten. Berlin / München.</p>
    </footer>

    <!-- Admin Login Modal -->
    <div id="loginModal" class="fixed inset-0 z-50 flex items-center justify-center bg-black/70 backdrop-blur-sm hidden">
        <div class="bg-cardBg border border-slate-700 p-8 rounded-sm w-full max-w-md relative shadow-2xl">
            <button onclick="toggleLoginModal()" class="absolute top-4 right-4 text-slate-400 hover:text-accentGold text-xl">&times;</button>
            
            <h3 class="text-xl font-light tracking-wide mb-1 text-center">Admin-Portal</h3>
            <p class="text-xs text-slate-400 text-center mb-6 tracking-wider">Administrator-Anmeldung</p>
            
            <form onsubmit="handleAuth(event)" class="space-y-4">
                <div>
                    <label class="block text-xs uppercase tracking-wider text-slate-400 mb-1">Benutzername</label>
                    <input type="text" id="username" required class="w-full bg-slate-900 border border-slate-700 px-4 py-2.5 text-sm text-slate-200 focus:outline-none focus:border-accentGold transition" placeholder="Geben Sie Ihr Konto ein">
                </div>
                <div>
                    <label class="block text-xs uppercase tracking-wider text-slate-400 mb-1">Passwort</label>
                    <input type="password" id="password" required class="w-full bg-slate-900 border border-slate-700 px-4 py-2.5 text-sm text-slate-200 focus:outline-none focus:border-accentGold transition" placeholder="Geben Sie Ihr Passwort ein">
                </div>
                <button type="submit" class="w-full bg-accentGold text-darkBg py-3 text-xs tracking-[0.2em] uppercase font-medium hover:bg-white transition duration-300 mt-2">
                    Anmelden
                </button>
            </form>
        </div>
    </div>

    <!-- 1. JS Logic -->
    <script>
        let isLoggedIn = false;
        window.pendingImages = {};

        function toggleLoginModal() { document.getElementById('loginModal').classList.toggle('hidden'); }
        
        function handleAdminBtnClick() {
            if (isLoggedIn) {
                if (confirm('Wirklich abmelden?')) { isLoggedIn = false; updateAdminUI(); }
            } else { toggleLoginModal(); }
        }

        function handleAuth(event) {
            event.preventDefault();
            isLoggedIn = true;
            toggleLoginModal();
            updateAdminUI();
            alert('✅ Bearbeitungsmodus entsperrt! Sie können nun Bilder ziehen und Text ändern.');
        }

        function updateAdminUI() {
            const elementsToEdit = ['price-1', 'price-2', 'price-3', 'bio-title', 'bio-p1', 'bio-p2', 'bio-exhibitions'];
            const overlays = document.querySelectorAll('.admin-img-overlay');
            const sizeCtrls = document.querySelectorAll('.admin-size-ctrl');

            if (isLoggedIn) {
                document.getElementById('adminEditBar').classList.remove('hidden');
                document.getElementById('savePriceContainer').classList.remove('hidden');
                overlays.forEach(el => el.classList.remove('hidden'));
                sizeCtrls.forEach(el => el.classList.remove('hidden'));
                
                elementsToEdit.forEach(id => {
                    const el = document.getElementById(id);
                    if(el) {
                        el.setAttribute('contenteditable', 'true');
                        el.classList.add('bg-slate-900/80', 'border', 'border-accentGold/40', 'p-1', 'rounded');
                    }
                });
            } else {
                document.getElementById('adminEditBar').classList.add('hidden');
                document.getElementById('savePriceContainer').classList.add('hidden');
                overlays.forEach(el => el.classList.add('hidden'));
                sizeCtrls.forEach(el => el.classList.add('hidden'));
                
                elementsToEdit.forEach(id => {
                    const el = document.getElementById(id);
                    if(el) {
                        el.removeAttribute('contenteditable');
                        el.classList.remove('bg-slate-900/80', 'border', 'border-accentGold/40', 'p-1', 'rounded');
                    }
                });
            }
        }

        function handleFileSelect(event, id) {
            if (event.target.files[0]) displayImage(event.target.files[0], id);
        }
        function handleDragOver(event) { event.preventDefault(); event.currentTarget.classList.add('drag-over'); }
        function handleDragLeave(event) { event.currentTarget.classList.remove('drag-over'); }
        function handleDrop(event, id) {
            event.preventDefault(); event.currentTarget.classList.remove('drag-over');
            if (event.dataTransfer.files[0] && event.dataTransfer.files[0].type.startsWith('image/')) {
                displayImage(event.dataTransfer.files[0], id);
            } else { alert('Bitte ziehen Sie eine gültige Bilddatei (JPG / PNG) hierher'); }
        }

        function displayImage(file, id) {
            const reader = new FileReader();
            reader.onload = function(e) {
                const base64Data = e.target.result;
                const innerContainer = document.getElementById(`img-inner-${id}`);
                innerContainer.className = "absolute inset-0 w-full h-full flex items-center justify-center overflow-hidden transition duration-300 bg-slate-900";
                innerContainer.innerHTML = `<img src="${base64Data}" class="w-full h-full object-cover" id="uploaded-img-${id}" data-fit="cover">`;
                
                window.pendingImages[id] = base64Data;
                
                const rangeInput = document.querySelector(`#size-control-${id} input[type="range"]`);
                if (rangeInput) rangeInput.value = 100;
                const scaleVal = document.getElementById(`scale-val-${id}`);
                if (scaleVal) scaleVal.textContent = '100%';
            }
            reader.readAsDataURL(file);
        }

        function setImageFit(id, fitType) {
            const innerContainer = document.getElementById(`img-inner-${id}`);
            const img = innerContainer.querySelector('img');
            const btnCover = document.getElementById(`fit-cover-${id}`);
            const btnContain = document.getElementById(`fit-contain-${id}`);

            if (img) {
                if (fitType === 'cover') {
                    img.className = "w-full h-full object-cover transition-transform duration-300";
                    btnCover.classList.replace('bg-slate-800', 'bg-accentGold');
                    btnCover.classList.replace('text-slate-300', 'text-darkBg');
                    btnContain.classList.replace('bg-accentGold', 'bg-slate-800');
                    btnContain.classList.replace('text-darkBg', 'text-slate-300');
                } else {
                    img.className = "w-full h-full object-contain transition-transform duration-300";
                    btnContain.classList.replace('bg-slate-800', 'bg-accentGold');
                    btnContain.classList.replace('text-slate-300', 'text-darkBg');
                    btnCover.classList.replace('bg-accentGold', 'bg-slate-800');
                    btnCover.classList.replace('text-darkBg', 'text-slate-300');
                }
            }
        }

        function changeImageScale(id, value) {
            document.getElementById(`scale-val-${id}`).textContent = value + '%';
            const innerContainer = document.getElementById(`img-inner-${id}`);
            const img = innerContainer.querySelector('img');
            if (img) { img.style.transform = `scale(${value / 100})`; } 
            else { innerContainer.style.transform = `scale(${value / 100})`; }
        }
    </script>

    <!-- 2. Firebase Database -->
    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/10.8.0/firebase-app.js";
        import { getFirestore, doc, setDoc, getDoc } from "https://www.gstatic.com/firebasejs/10.8.0/firebase-firestore.js";
        import { getStorage, ref, uploadString, getDownloadURL } from "https://www.gstatic.com/firebasejs/10.8.0/firebase-storage.js";

        const firebaseConfig = {
            apiKey: "AIzaSyCAEAAEswatYgTthGV2FMKr36gf2EC4UNQ",
            authDomain: "aura-mandala.firebaseapp.com",
            projectId: "aura-mandala",
            storageBucket: "aura-mandala.firebasestorage.app",
            messagingSenderId: "505766279978",
            appId: "1:505766279978:web:19711146c54b92101a3c53"
        };

        const app = initializeApp(firebaseConfig);
        const db = getFirestore(app);
        const storage = getStorage(app);

        window.saveDataToFirebase = async function() {
            const statusText = document.getElementById('upload-status');
            statusText.classList.remove('hidden');

            try {
                const imageUrls = {};
                for (const [id, base64] of Object.entries(window.pendingImages)) {
                    const imageRef = ref(storage, `artworks/${id}`);
                    await uploadString(imageRef, base64, 'data_url');
                    imageUrls[`img_${id}`] = await getDownloadURL(imageRef);
                }

                const dataToSave = {
                    price1: document.getElementById('price-1').textContent,
                    price2: document.getElementById('price-2').textContent,
                    price3: document.getElementById('price-3').textContent,
                    bioTitle: document.getElementById('bio-title').textContent,
                    bioP1: document.getElementById('bio-p1').textContent,
                    bioP2: document.getElementById('bio-p2').textContent,
                    bioExh: document.getElementById('bio-exhibitions').textContent,
                    ...imageUrls
                };

                await setDoc(doc(db, "website", "content_de"), dataToSave, { merge: true });
                
                statusText.classList.add('hidden');
                alert("✅ Erfolgreich gespeichert! Daten und Bilder wurden dauerhaft in der Cloud gespeichert.");
                window.pendingImages = {}; 

            } catch (error) {
                statusText.classList.add('hidden');
                console.error(error);
                alert("❌ Speichern fehlgeschlagen! Bitte überprüfen Sie die Firebase Storage-Berechtigungen.");
            }
        };

        window.onload = async function() {
            try {
                // 注意：我把讀取的資料庫路徑改為 content_de，這樣德文版可以獨立儲存
                const docSnap = await getDoc(doc(db, "website", "content_de"));
                if (docSnap.exists()) {
                    const data = docSnap.data();
                    
                    if(data.price1) document.getElementById('price-1').textContent = data.price1;
                    if(data.price2) document.getElementById('price-2').textContent = data.price2;
                    if(data.price3) document.getElementById('price-3').textContent = data.price3;
                    if(data.bioTitle) document.getElementById('bio-title').textContent = data.bioTitle;
                    if(data.bioP1) document.getElementById('bio-p1').textContent = data.bioP1;
                    if(data.bioP2) document.getElementById('bio-p2').textContent = data.bioP2;
                    if(data.bioExh) document.getElementById('bio-exhibitions').textContent = data.bioExh;

                    ['1', '2', '3', 'portrait'].forEach(id => {
                        if(data[`img_${id}`]) {
                            const innerContainer = document.getElementById(`img-inner-${id}`);
                            innerContainer.className = "absolute inset-0 w-full h-full flex items-center justify-center overflow-hidden transition duration-300 bg-slate-900";
                            innerContainer.innerHTML = `<img src="${data[`img_${id}`]}" class="w-full h-full object-cover">`;
                        }
                    });
                }
            } catch (error) {
                console.log("Keine Cloud-Daten gefunden.");
            }
        };
    </script>
</body>
</html>
