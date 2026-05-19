```html
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Odaklan</title>
    
    <!-- PWA Kurulumu için Gerekli Ayarlar -->
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <meta name="theme-color" content="#1f2937">
    
    <!-- Manifest (Uygulamanın telefondaki adı, ikonu vs. için) -->
    <!-- Not: Gerçek bir PWA için ayrı bir manifest.json dosyası gerekir ancak bu kod tek dosyalık basit bir simülasyondur -->
    <link rel="manifest" href="data:application/manifest+json;base64,eyJuYW1lIjoiT2Rha2xhbiIsInNob3J0X25hbWUiOiJPZGFrbGFuIiwic3RhcnRfdXJsIjoiLiIsImRpc3BsYXkiOiJzdGFuZGFsb25lIiwiYmFja2dyb3VuZF9jb2xvciI6IiMxZjI5MzciLCJ0aGVtZV9jb2xvciI6IiMxZjI5MzciLCJpY29ucyI6W3sic3JjIjoiaHR0cHM6Ly9jZG4tanNkZWxpdnIubmV0L2doL3R3ZW1vamkvdHdlbW9qaUBsYXRlc3QvYXNzZXRzLzUxMng1MTIvMjNmMS5wbmciLCJzaXplcyI6IjUxMng1MTIiLCJ0eXBlIjoiaW1hZ2UvcG5nIn1dfQ==">
    
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    
    <style>
        /* Telefonda seçilmeyi ve dokunma vurgularını engellemek için */
        body {
            -webkit-touch-callout: none;
            -webkit-user-select: none;
            user-select: none;
            -webkit-tap-highlight-color: transparent;
        }
        .transition-colors {
            transition: background-color 0.5s ease, color 0.5s ease;
        }
    </style>
</head>
<body class="bg-gray-900 text-white min-h-screen flex flex-col font-sans transition-colors duration-500" id="body-bg">

    <!-- Telefonda üst bar (Çentik vs) için boşluk bırakma -->
    <div class="h-12 w-full bg-gray-900"></div>

    <div class="flex-1 flex flex-col items-center justify-center p-6 w-full max-w-md mx-auto">
        
        <!-- Uygulama Başlığı -->
        <h1 class="text-3xl font-bold mb-8 text-gray-100 flex justify-center items-center gap-3">
            <i class="fa-solid fa-stopwatch text-red-500"></i> Odaklan
        </h1>

        <!-- Mod Seçici Butonlar -->
        <div class="flex w-full bg-gray-800 p-1 rounded-2xl mb-12 shadow-inner">
            <button id="work-btn" class="flex-1 py-3 rounded-xl font-semibold bg-red-500 text-white shadow-md transition-all" onclick="setMode('work')">
                Çalışma
            </button>
            <button id="break-btn" class="flex-1 py-3 rounded-xl font-semibold text-gray-400 hover:text-white transition-all" onclick="setMode('break')">
                Mola
            </button>
        </div>

        <!-- Zamanlayıcı Ekranı -->
        <div class="py-12 flex justify-center items-center w-64 h-64 rounded-full border-4 border-gray-700 shadow-[0_0_40px_rgba(0,0,0,0.3)] mb-12 relative overflow-hidden">
            <div id="progress-circle" class="absolute inset-0 bg-red-500 opacity-10 transition-all duration-1000 ease-linear" style="height: 0%; bottom: 0; top: auto;"></div>
            <h2 id="timer-display" class="text-7xl font-black tabular-nums tracking-tight relative z-10">25:00</h2>
        </div>

        <!-- Kontrol Butonları -->
        <div class="flex justify-center gap-8">
            <button class="w-16 h-16 rounded-full bg-gray-800 text-gray-400 flex items-center justify-center text-xl shadow-lg active:bg-gray-700" onclick="resetTimer()">
                <i class="fa-solid fa-rotate-right"></i>
            </button>
            
            <button id="start-btn" class="w-20 h-20 rounded-full bg-red-500 text-white flex items-center justify-center text-3xl shadow-[0_10px_20px_rgba(239,68,68,0.3)] active:transform active:scale-95 transition-all" onclick="toggleTimer()">
                <i class="fa-solid fa-play ml-1" id="play-icon"></i>
            </button>
        </div>
        
    </div>

    <!-- Kurulum Bilgisi Modal (Sadece eğitim amaçlı gösterim) -->
    <div id="install-hint" class="fixed bottom-0 left-0 right-0 bg-blue-600 text-white p-4 rounded-t-3xl shadow-2xl transform translate-y-full transition-transform duration-500 z-50">
        <div class="flex justify-between items-start">
            <div>
                <p class="font-bold mb-1">Telefona Kur!</p>
                <p class="text-sm opacity-90">Tarayıcı menüsünden "Ana Ekrana Ekle"yi seçerek bunu bir uygulama gibi kullanabilirsin.</p>
            </div>
            <button onclick="document.getElementById('install-hint').classList.add('translate-y-full')" class="p-2 bg-blue-700 rounded-full">
                <i class="fa-solid fa-xmark"></i>
            </button>
        </div>
    </div>

    <script>
        // İpucunu 2 saniye sonra göster
        setTimeout(() => {
            document.getElementById('install-hint').classList.remove('translate-y-full');
        }, 2000);

        let totalTime = 25 * 60;
        let timeLeft = 25 * 60; 
        let timerId = null;
        let isRunning = false;
        let currentMode = 'work'; 

        const display = document.getElementById('timer-display');
        const startBtn = document.getElementById('start-btn');
        const playIcon = document.getElementById('play-icon');
        const workBtn = document.getElementById('work-btn');
        const breakBtn = document.getElementById('break-btn');
        const progress = document.getElementById('progress-circle');

        function updateDisplay() {
            const minutes = Math.floor(timeLeft / 60);
            const seconds = timeLeft % 60;
            display.textContent = `${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
            
            // İlerleme çubuğunu (arkaplan dolumu) güncelle
            const percentage = ((totalTime - timeLeft) / totalTime) * 100;
            progress.style.height = `${percentage}%`;
        }

        function setMode(mode) {
            currentMode = mode;
            isRunning = false;
            clearInterval(timerId);
            playIcon.classList.remove('fa-pause', 'ml-0');
            playIcon.classList.add('fa-play', 'ml-1');
            
            // Aktif renkleri belirle
            const activeColor = mode === 'work' ? 'bg-red-500' : 'bg-green-500';
            const shadowColor = mode === 'work' ? 'rgba(239,68,68,0.3)' : 'rgba(34,197,94,0.3)';

            startBtn.className = `w-20 h-20 rounded-full ${activeColor} text-white flex items-center justify-center text-3xl shadow-[0_10px_20px_${shadowColor}] active:transform active:scale-95 transition-all`;
            progress.className = `absolute inset-0 ${activeColor} opacity-10 transition-all duration-1000 ease-linear`;

            if (mode === 'work') {
                totalTime = 25 * 60;
                workBtn.className = "flex-1 py-3 rounded-xl font-semibold bg-red-500 text-white shadow-md transition-all";
                breakBtn.className = "flex-1 py-3 rounded-xl font-semibold text-gray-400 hover:text-white transition-all bg-transparent shadow-none";
            } else {
                totalTime = 5 * 60;
                breakBtn.className = "flex-1 py-3 rounded-xl font-semibold bg-green-500 text-white shadow-md transition-all";
                workBtn.className = "flex-1 py-3 rounded-xl font-semibold text-gray-400 hover:text-white transition-all bg-transparent shadow-none";
            }
            timeLeft = totalTime;
            updateDisplay();
        }

        function toggleTimer() {
            if (isRunning) {
                clearInterval(timerId);
                isRunning = false;
                playIcon.classList.remove('fa-pause', 'ml-0');
                playIcon.classList.add('fa-play', 'ml-1');
            } else {
                isRunning = true;
                playIcon.classList.remove('fa-play', 'ml-1');
                playIcon.classList.add('fa-pause', 'ml-0');
                
                timerId = setInterval(() => {
                    timeLeft--;
                    updateDisplay();
                    
                    if (timeLeft <= 0) {
                        clearInterval(timerId);
                        isRunning = false;
                        
                        // Titreşim (Telefonda çalışır)
                        if (navigator.vibrate) {
                            navigator.vibrate([300, 100, 300, 100, 300]);
                        }
                        
                        setTimeout(() => {
                            alert(currentMode === 'work' ? 'Çalışma süresi bitti! Mola zamanı.' : 'Mola bitti! Hadi işe dönelim.');
                            setMode(currentMode === 'work' ? 'break' : 'work');
                        }, 500);
                    }
                }, 1000);
            }
        }

        function resetTimer() {
            setMode(currentMode); 
        }

        updateDisplay();
    </script>
</body>
</html>


```
