# central-scheme-mcq-mock-test-<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>POLAI EDUCATION HUB - Mock Test</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>

    <style>
        body {
            font-family: 'Inter', sans-serif;
            transition: background 0.3s, color 0.3s;
        }
        .animated-bg {
            background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
            background-size: 400% 400%;
            animation: gradient 15s ease infinite;
        }
        .animated-bg-dark {
            background: linear-gradient(-45deg, #0f172a, #1e1b4b, #111827, #0f172a);
            background-size: 400% 400%;
            animation: gradient 15s ease infinite;
        }
        @keyframes gradient {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        .glass {
            background: rgba(255, 255, 255, 0.75);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.25);
        }
        .dark .glass {
            background: rgba(15, 23, 42, 0.65);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        /* Custom scrollbar */
        ::-webkit-scrollbar { width: 6px; height: 6px; }
        ::-webkit-scrollbar-track { background: transparent; }
        ::-webkit-scrollbar-thumb { background: rgba(156, 163, 175, 0.5); border-radius: 4px; }
    </style>
</head>
<body class="animated-bg min-h-screen text-slate-800 antialiased flex flex-col transition-colors duration-300" id="body-theme">

    <header class="glass sticky top-0 z-50 shadow-sm px-4 py-3 border-b border-white/20 transition-all">
        <div class="max-w-7xl mx-auto flex flex-col sm:flex-row items-center justify-between gap-4">
            <div class="flex items-center gap-3">
                <div class="w-12 h-12 bg-gradient-to-tr from-red-500 to-orange-500 rounded-full flex items-center justify-center text-white font-bold text-xl shadow-lg border-2 border-white">
                    PEH
                </div>
                <div>
                    <h1 class="text-xl font-bold bg-gradient-to-r from-slate-900 to-indigo-9ments dark:from-white dark:to-slate-300 bg-clip-text text-transparent tracking-tight">
                        POLAI EDUCATION HUB
                    </h1>
                    <div class="flex items-center gap-2 mt-0.5">
                        <span class="bg-red-500 text-white text-[10px] font-semibold px-2 py-0.5 rounded-full shadow-sm animate-pulse">LIVE</span>
                        <span class="text-xs font-medium text-slate-500 dark:text-slate-400" id="lbl-badge">Testbook Premium Interface</span>
                    </div>
                </div>
            </div>
            
            <div class="flex items-center gap-3 flex-wrap justify-center">
                <a href="https://www.youtube.com/@Polaieducationhub" target="_blank" class="bg-red-600 hover:bg-red-700 text-white text-sm font-semibold px-4 py-2 rounded-xl flex items-center gap-2 transition transform hover:scale-105 shadow-md">
                    <i class="fab fa-youtube text-lg"></i> <span id="btn-subscribe">Subscribe</span>
                </a>
                
                <button id="lang-toggle" onclick="toggleLanguage()" class="px-3 py-2 rounded-xl border border-slate-300 dark:border-slate-700 bg-white/50 dark:bg-slate-800/50 text-xs font-bold tracking-wider hover:bg-slate-100 dark:hover:bg-slate-700 transition">
                    ODIA / EN
                </button>

                <button onclick="toggleTheme()" class="w-10 h-10 rounded-xl bg-white/50 dark:bg-slate-800/50 flex items-center justify-center text-lg shadow-sm border border-slate-300 dark:border-slate-700 hover:bg-slate-100 dark:hover:bg-slate-700 transition">
                    <i id="theme-icon" class="fas fa-moon text-slate-700 dark:text-yellow-400"></i>
                </button>
            </div>
        </div>
    </header>

    <main class="flex-grow max-w-7xl w-full mx-auto p-4 flex flex-col lg:flex-row gap-6 items-stretch">
        
        <div class="flex-grow lg:w-3/4 flex flex-col gap-4">
            
            <div class="glass rounded-2xl p-4 flex flex-col sm:flex-row sm:items-center justify-between gap-4 shadow-xl">
                <div>
                    <h2 class="text-lg font-bold text-slate-900 dark:text-white uppercase tracking-wide" id="lbl-exam-title">
                        CENTRAL SCHEME 2026 MCQ TEST
                    </h2>
                    <p class="text-xs text-slate-500 dark:text-slate-400" id="lbl-sub-info">Total Questions: 15 | Positive: +1.0 | Negative: -0.0</p>
                </div>
                <div class="flex items-center gap-3 bg-indigo-500/10 dark:bg-indigo-400/10 px-4 py-2 rounded-xl border border-indigo-500/20 self-start sm:self-center">
                    <i class="far fa-clock text-indigo-600 dark:text-indigo-400 text-lg animate-pulse"></i>
                    <span class="font-mono text-lg font-bold text-indigo-700 dark:text-indigo-300" id="timer-display">15:00</span>
                </div>
            </div>

            <div class="w-full bg-slate-200/50 dark:bg-slate-700/50 rounded-full h-2.5 overflow-hidden shadow-inner">
                <div id="progress-bar" class="bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500 h-2.5 rounded-full transition-all duration-300" style="width: 0%"></div>
            </div>

            <div id="start-screen" class="glass rounded-2xl p-6 sm:p-8 text-center shadow-2xl flex flex-col items-center justify-center min-h-[400px]">
                <div class="w-20 h-20 bg-indigo-500/10 text-indigo-600 dark:text-indigo-400 rounded-full flex items-center justify-center text-4xl mb-4">
                    <i class="fas fa-file-alt"></i>
                </div>
                <h3 class="text-2xl font-bold mb-2 dark:text-white" id="lbl-welcome">Ready to start the Mock Test?</h3>
                <p class="text-slate-600 dark:text-slate-300 max-w-md text-sm mb-6" id="lbl-instructions">
                    Enhance your preparation with our real-time Testbook interface exam dashboard. Instant response feedback with review status is supported.
                </p>
                <button onclick="startQuiz()" class="px-8 py-3 bg-gradient-to-r from-indigo-600 to-purple-600 hover:from-indigo-700 hover:to-purple-700 text-white font-semibold rounded-xl shadow-lg transform hover:-translate-y-0.5 transition cursor-pointer">
                    <span id="btn-start">Start Test Now</span> <i class="fas fa-arrow-right ml-2"></i>
                </button>
            </div>

            <div id="quiz-card" class="glass rounded-2xl p-6 shadow-2xl flex-grow hidden flex-col justify-between min-h-[400px]">
                <div>
                    <div class="flex justify-between items-center border-b border-slate-200 dark:border-slate-700 pb-3 mb-5">
                        <span class="text-xs font-semibold px-3 py-1 bg-slate-200 dark:bg-slate-700 text-slate-700 dark:text-slate-300 rounded-md" id="q-number-badge">Question 1 of 15</span>
                        <span class="text-xs text-indigo-600 dark:text-indigo-400 font-medium cursor-pointer" onclick="clearResponse()"><i class="fas fa-undo mr-1"></i> Clear Response</span>
                    </div>

                    <h3 id="question-text" class="text-base sm:text-lg font-semibold text-slate-900 dark:text-white leading-relaxed mb-6">
                        Loading Question...
                    </h3>

                    <div class="space-y-3" id="options-container">
                        </div>
                </div>

                <div class="flex justify-between items-center mt-8 pt-4 border-t border-slate-200 dark:border-slate-700 gap-3">
                    <button id="btn-prev" onclick="prevQuestion()" class="px-4 py-2.5 bg-slate-200 dark:bg-slate-700 hover:bg-slate-300 dark:hover:bg-slate-600 text-slate-700 dark:text-white font-medium rounded-xl transition text-sm flex items-center gap-2 disabled:opacity-40 disabled:cursor-not-allowed">
                        <i class="fas fa-chevron-left"></i> <span id="lbl-prev">Previous</span>
                    </button>
                    
                    <button id="btn-mark" onclick="markForReview()" class="px-4 py-2.5 bg-amber-500/10 text-amber-600 dark:text-amber-400 border border-amber-500/20 hover:bg-amber-500/20 font-medium rounded-xl transition text-sm flex items-center gap-2">
                        <i class="fas fa-bookmark"></i> <span id="lbl-mark">Mark Review</span>
                    </button>

                    <button id="btn-next" onclick="nextQuestion()" class="px-5 py-2.5 bg-indigo-600 hover:bg-indigo-700 text-white font-medium rounded-xl transition text-sm flex items-center gap-2">
                        <span id="lbl-next-save">Save & Next</span> <i class="fas fa-chevron-right"></i>
                    </button>
                </div>
            </div>

            <div id="result-screen" class="glass rounded-2xl p-6 sm:p-8 shadow-2xl hidden text-center flex-col items-center">
                <div class="w-20 h-20 bg-green-500/10 text-green-500 rounded-full flex items-center justify-center text-4xl mb-4 animate-bounce">
                    <i class="fas fa-trophy"></i>
                </div>
                <h3 class="text-2xl font-bold text-slate-900 dark:text-white mb-1" id="lbl-congrats">Test Successfully Completed!</h3>
                <p class="text-sm text-slate-500 dark:text-slate-400 mb-6" id="lbl-result-sub">Analysis report and performance scorecard generation</p>

                <div class="grid grid-cols-2 sm:grid-cols-4 gap-4 w-full max-w-2xl mb-8">
                    <div class="p-4 bg-white/40 dark:bg-slate-800/40 rounded-xl border border-white/20">
                        <div class="text-2xl font-black text-indigo-600 dark:text-indigo-400" id="res-score">0/15</div>
                        <div class="text-xs text-slate-500 dark:text-slate-400 mt-1" id="lbl-res-score">Your Score</div>
                    </div>
                    <div class="p-4 bg-white/40 dark:bg-slate-800/40 rounded-xl border border-white/20">
                        <div class="text-2xl font-black text-green-500" id="res-correct">0</div>
                        <div class="text-xs text-slate-500 dark:text-slate-400 mt-1" id="lbl-res-acc">Correct</div>
                    </div>
                    <div class="p-4 bg-white/40 dark:bg-slate-800/40 rounded-xl border border-white/20">
                        <div class="text-2xl font-black text-red-500" id="res-wrong">0</div>
                        <div class="text-xs text-slate-500 dark:text-slate-400 mt-1" id="lbl-res-wrong">Wrong</div>
                    </div>
                    <div class="p-4 bg-white/40 dark:bg-slate-800/40 rounded-xl border border-white/20">
                        <div class="text-2xl font-black text-amber-500" id="res-rank">#1</div>
                        <div class="text-xs text-slate-500 dark:text-slate-400 mt-1" id="lbl-res-rank">Rank</div>
                    </div>
                </div>

                <div class="flex flex-wrap gap-4 justify-center mb-8">
                    <button onclick="downloadCertificate()" class="px-5 py-2.5 bg-gradient-to-r from-emerald-500 to-green-600 hover:from-emerald-600 hover:to-green-700 text-white text-sm font-semibold rounded-xl shadow-md transition flex items-center gap-2 cursor-pointer">
                        <i class="fas fa-file-certificate"></i> <span id="btn-cert">Download Certificate</span>
                    </button>
                    <button onclick="shareScore()" class="px-5 py-2.5 bg-blue-500 hover:bg-blue-600 text-white text-sm font-semibold rounded-xl shadow-md transition flex items-center gap-2 cursor-pointer">
                        <i class="fas fa-share-alt"></i> <span id="btn-share">Share Score</span>
                    </button>
                    <button onclick="window.location.reload()" class="px-5 py-2.5 bg-slate-600 hover:bg-slate-700 text-white text-sm font-semibold rounded-xl shadow-md transition flex items-center gap-2 cursor-pointer">
                        <i class="fas fa-redo"></i> <span id="btn-restart">Retake Test</span>
                    </button>
                </div>

                <div class="w-full max-w-md border-t border-slate-200 dark:border-slate-700 pt-6">
                    <p class="text-xs font-semibold uppercase tracking-wider text-slate-400 mb-3" id="lbl-join-community">Join our community for regular test updates</p>
                    <div class="flex flex-col sm:flex-row gap-3 justify-center">
                        <a href="https://www.youtube.com/@Polaieducationhub" target="_blank" class="flex-1 bg-red-500/10 hover:bg-red-500/20 text-red-600 dark:text-red-400 border border-red-500/20 text-xs font-bold py-2.5 px-4 rounded-xl flex items-center justify-center gap-2 transition">
                            <i class="fab fa-youtube text-base"></i> YouTube Channel
                        </a>
                        <a href="https://t.me/" target="_blank" class="flex-1 bg-sky-500/10 hover:bg-sky-500/20 text-sky-600 dark:text-sky-400 border border-sky-500/20 text-xs font-bold py-2.5 px-4 rounded-xl flex items-center justify-center gap-2 transition">
                            <i class="fab fa-telegram-plane text-base"></i> Join Telegram
                        </a>
                    </div>
                </div>

                <div class="w-full text-left mt-8 border-t border-slate-200 dark:border-slate-700 pt-6">
                    <h4 class="text-lg font-bold text-slate-900 dark:text-white mb-4 flex items-center gap-2">
                        <i class="fas fa-spell-check text-indigo-500"></i> <span id="lbl-review-title">Detailed Answer Key & Solutions</span>
                    </h4>
                    <div id="detailed-solutions" class="space-y-4">
                        </div>
                </div>
            </div>
        </div>

        <div class="lg:w-1/4 flex flex-col gap-4">
            <div class="glass rounded-2xl p-4 shadow-xl flex flex-col justify-between h-full min-h-[300px]">
                <div>
                    <h3 class="text-sm font-bold text-slate-900 dark:text-white uppercase tracking-wider mb-3 pb-2 border-b border-slate-200 dark:border-slate-700" id="lbl-palette">
                        Question Palette
                    </h3>
                    
                    <div class="grid grid-cols-2 gap-2 text-[11px] font-medium text-slate-600 dark:text-slate-400 mb-4 bg-slate-500/5 p-2 rounded-xl">
                        <div class="flex items-center gap-1.5"><span class="w-3 h-3 bg-slate-200 dark:bg-slate-700 rounded border border-slate-300"></span> <span id="ind-unvisited">Unvisited</span></div>
                        <div class="flex items-center gap-1.5"><span class="w-3 h-3 bg-emerald-500 rounded"></span> <span id="ind-answered">Answered</span></div>
                        <div class="flex items-center gap-1.5"><span class="w-3 h-3 bg-amber-500 rounded"></span> <span id="ind-review">Review</span></div>
                        <div class="flex items-center gap-1.5"><span class="w-3 h-3 bg-indigo-500 rounded"></span> <span id="ind-current">Current</span></div>
                    </div>

                    <div class="grid grid-cols-5 gap-2" id="palette-matrix">
                        </div>
                </div>

                <div class="mt-6 pt-4 border-t border-slate-200 dark:border-slate-700">
                    <button id="btn-submit-exam" onclick="submitQuiz()" class="w-full py-2.5 bg-emerald-600 hover:bg-emerald-700 text-white font-semibold text-sm rounded-xl shadow-lg transition flex items-center justify-center gap-2 cursor-pointer hidden">
                        <i class="fas fa-check-double"></i> <span id="lbl-submit-test">Submit Exam</span>
                    </button>
                </div>
            </div>

            <div class="glass rounded-2xl p-4 shadow-xl">
                <h3 class="text-sm font-bold text-slate-900 dark:text-white uppercase tracking-wider mb-3 flex items-center gap-2" id="lbl-leaderboard">
                    <i class="fas fa-award text-amber-500"></i> Top Rankers (Live)
                </h3>
                <div class="space-y-2 text-xs">
                    <div class="flex justify-between items-center bg-amber-500/10 p-2 rounded-lg border border-amber-500/20">
                        <span class="font-semibold text-slate-800 dark:text-slate-200">🥇 1. Subhasmita Rout</span>
                        <span class="font-mono font-bold text-amber-600">15.0 / 15</span>
                    </div>
                    <div class="flex justify-between items-center bg-slate-500/5 p-2 rounded-lg">
                        <span class="text-slate-700 dark:text-slate-300">🥈 2. Manoj Kumar Naik</span>
                        <span class="font-mono text-slate-600 dark:text-slate-400">14.0 / 15</span>
                    </div>
                    <div class="flex justify-between items-center bg-slate-500/5 p-2 rounded-lg">
                        <span class="text-slate-700 dark:text-slate-300">🥉 3. Priya Ranjan Das</span>
                        <span class="font-mono text-slate-600 dark:text-slate-400">13.0 / 15</span>
                    </div>
                </div>
            </div>
        </div>
    </main>

    <footer class="mt-auto glass border-t border-white/20 py-4 text-center text-xs text-slate-500 dark:text-slate-400 shadow-inner">
        <p class="font-semibold text-slate-700 dark:text-slate-300">Powered By POLAI EDUCATION HUB</p>
        <p class="mt-0.5" id="lbl-foot-sub">Subscribe For More MCQs & Study Materials</p>
    </footer>

    <audio id="snd-click" src="https://assets.mixkit.co/active_storage/sfx/2568/2568-84.wav" preload="auto"></audio>
    <audio id="snd-success" src="https://assets.mixkit.co/active_storage/sfx/1435/1435-84.wav" preload="auto"></audio>

    <script>
        // DATA MODEL & SYSTEM CONTROLS
        let currentLang = 'EN';
        let currentIdx = 0;
        let timerInstance = null;
        let timeLeft = 900; // 15 mins
        let userResponses = Array(15).fill(null);
        let reviewStatus = Array(15).fill(false);
        let quizActive = false;

        const questionsData = [
            {
                q_en: "Which Act Is Replaced By The Viksit Bharat–Guarantee for Rozgar & Ajeevika Mission (Gramin) Bill, 2025?",
                q_or: "ବିକସିତ ଭାରତ-ଗ୍ୟାରେଣ୍ଟି ଫର୍ ରୋଜଗାର ଏବଂ ଆଜୀବିକା ମିଶନ (ଗ୍ରାମୀଣ) ବିଲ୍, ୨୦୨୫ ଦ୍ୱାରା କେଉଁ ଅଧିନିୟମ ବଦଳାଯାଇଛି?",
                opts_en: ["MGNREGA", "National Food Security Act", "Right to Education Act", "Forest Rights Act"],
                opts_or: ["MGNREGA", "ଜାତୀୟ ଖାଦ୍ୟ ସୁରକ୍ଷା ଅଧିନିୟମ", "ଶିକ୍ଷା ଅଧିକାର ଅଧିନିୟମ", "ଜଙ୍ଗଲ ଅଧିକାର ଅଧିନିୟମ"],
                correct: 0
            },
            {
                q_en: "PM RAHAT Scheme Is Related To Which Of The Following?",
                q_or: "ପିଏମ୍ ରାହତ (PM RAHAT) ଯୋଜନା ନିମ୍ନଲିଖିତ ମଧ୍ୟରୁ କାହା ସହିତ ଜଡିତ?",
                opts_en: ["Agriculture Insurance", "Rural Housing", "Education Support", "Road Accident Treatment"],
                opts_or: ["କୃଷି ବୀମା", "ଗ୍ରାମୀଣ ଗୃହ ନିର୍ମାଣ", "ଶିକ୍ଷା ସହାୟତା", "ସଡକ ଦୁର୍ଘଟଣା ଚିକିତ୍ସା"],
                correct: 3
            },
            {
                q_en: "SATHEE App Has Been Launched By Which Ministry?",
                q_or: "SATHEE ଆପ୍ କେଉଁ ମନ୍ତ୍ରାଳୟ ଦ୍ୱାରା ଆରମ୍ଭ କରାଯାଇଛି?",
                opts_en: ["Ministry of Education", "Ministry of IT", "Ministry of Science", "Ministry of Skill Development"],
                opts_or: ["ଶିକ୍ଷା ମନ୍ତ୍ରାଳୟ", "ଆଇଟି ମନ୍ତ୍ରାଳୟ", "ବିଜ୍ଞାନ ମନ୍ତ୍ରାଳୟ", "ଦକ୍ଷତା ବିକାଶ ମନ୍ତ୍ରାଳୟ"],
                correct: 0
            },
            {
                q_en: "The BHAVYA Scheme Has Been Approved With An Outlay Of?",
                q_or: "ଭବ୍ୟ (BHAVYA) ଯୋଜନା କେତେ ବ୍ୟୟବରାଦ ସହିତ ଅନୁମୋଦିତ ହୋଇଛି?",
                opts_en: ["₹33,660 Crore", "₹23,500 Crore", "₹45,000 Crore", "₹12,000 Crore"],
                opts_or: ["₹୩୩,୬୬୦ କୋଟି", "₹୨୩,୫୦୦ କୋଟି", "₹୪୫,୦୦୦ କୋଟି", "₹୧୨,୦୦୦ କୋଟି"],
                correct: 0
            },
            {
                q_en: "PRARAMBH 2026 Campaign Educates Citizens About Which Act?",
                q_or: "PRARAMBH 2026 ଅଭିଯାନ ନାଗରିକମାନଙ୍କୁ କେଉଁ ଆକ୍ଟ ବିଷୟରେ ଶିକ୍ଷା ଦିଏ?",
                opts_en: ["GST Act", "Income Tax Act 2025", "Companies Act", "Banking Regulation Act"],
                opts_or: ["GST ଆକ୍ଟ", "ଆୟକର ଅଧିନିୟମ ୨୦୨୫", "କମ୍ପାନୀ ଆକ୍ଟ", "ବ୍ୟାଙ୍କିଙ୍ଗ୍ ନିୟନ୍ତ୍ରଣ ଆକ୍ଟ"],
                correct: 1
            },
            {
                q_en: "Jal Jeevan Mission 2.0 Has Been Extended Till?",
                q_or: "ଜଳ ଜୀବନ ମିଶନ ୨.୦ କେଉଁ ବର୍ଷ ପର୍ଯ୍ୟନ୍ତ ବୃଦ୍ଧି କରାଯାଇଛି?",
                opts_en: ["2026", "2030", "2028", "2025"],
                opts_or: ["୨୦୨୬", "୨୦୩୦", "୨୦୨୮", "୨୦୨୫"],
                correct: 2
            },
            {
                q_en: "DHRUVA Platform Has Been Launched By?",
                q_or: "DHRUVA ପ୍ଲାଟଫର୍ମ କାହା ଦ୍ୱାରା ଲଞ୍ଚ କରାଯାଇଛି?",
                opts_en: ["Department of Posts", "Ministry of Electronics & IT", "NITI Aayog", "RBI"],
                opts_or: ["ଡାକ ବିଭାଗ", "ଇଲେକ୍ଟ୍ରୋନିକ୍ସ ଏବଂ ଆଇଟି ମନ୍ତ୍ରାଳୟ", "ନୀତି ଆୟୋଗ", "RBI"],
                correct: 0
            },
            {
                q_en: "How Many Airports Will Be Developed Under UDAN 2.0?",
                q_or: "ଉଡାନ ୨.୦ (UDAN 2.0) ଅଧୀନରେ କେତେ ବିମାନବନ୍ଦର ବିକଶିତ ହେବ?",
                opts_en: ["100", "50", "200", "75"],
                opts_or: ["୧୦୦", "୫୦", "୨୦୦", "୭୫"],
                correct: 0
            },
            {
                q_en: "Him-CONNECT Initiative Was Announced By?",
                q_or: "ହିମ୍-କନେକ୍ଟ (Him-CONNECT) ପଦକ୍ଷେପ କାହା ଦ୍ୱାରା ଘୋଷଣା କରାଯାଇଥିଲା?",
                opts_en: ["Ministry of Jal Shakti", "MoEFCC", "Ministry of Earth Sciences", "NITI Aayog"],
                opts_or: ["ଜଳ ଶକ୍ତି ମନ୍ତ୍ରାଳୟ", "MoEFCC (ପରିବେଶ ମନ୍ତ୍ରାଳୟ)", "ପୃଥିବୀ ବିଜ୍ଞାନ ମନ୍ତ୍ରାଳୟ", "ନୀତି ଆୟୋଗ"],
                correct: 1
            },
            {
                q_en: "When Was PMGSY Launched?",
                q_or: "PMGSY (ପ୍ରଧାନମନ୍ତ୍ରୀ ଗ୍ରାମ ସଡ଼କ ଯୋଜନା) କେବେ ଆରମ୍ଭ ହୋଇଥିଲା?",
                opts_en: ["2000", "2011", "2017", "2019"],
                opts_or: ["୨୦୦୦", "୨୦୧୧", "୨୦୧୭", "୨୦୧୯"],
                correct: 0
            },
            {
                q_en: "Which Initiative Was Launched To End Child Marriage?",
                q_or: "ବାଲ୍ୟ ବିବାହ ସମାପ୍ତ କରିବା ପାଇଁ କେଉଁ ପଦକ୍ଷେପ ଆରମ୍ଭ କରାଯାଇଥିଲା?",
                opts_en: ["Beti Bachao Beti Padhao", "Poshan Abhiyaan", "Bal Vivah Mukt Bharat", "Mission Shakti"],
                opts_or: ["ବେଟି ବଚାଓ ବେଟି ପଢାଓ", "ପୋଷଣ ଅଭିଯାନ", "ବାଲ୍ ବିବାହ ମୁକ୍ତ ଭାରତ", "ମିଶନ ଶକ୍ତି"],
                correct: 2
            },
            {
                q_en: "Which Scheme Modernizes 1000 ITIs?",
                q_or: "କେଉଁ ଯୋଜନା ୧୦୦୦ଟି ITI କୁ ଆଧୁନିକୀକରଣ କରେ?",
                opts_en: ["PMKVY", "PM-SETU", "Skill India Mission", "Digital Bharat"],
                opts_or: ["PMKVY", "PM-SETU", "ସ୍କିଲ୍ ଇଣ୍ଡିଆ ମିଶନ", "ଡିଜିଟାଲ୍ ଭାରତ"],
                correct: 1
            },
            {
                q_en: "Dalhan Aatmanirbharta Mission Outlay?",
                q_or: "ଦାଲ୍‌ହାନ ଆତ୍ମନିର୍ଭରତା ମିଶନର ବ୍ୟୟବରାଦ କେତେ?",
                opts_en: ["₹11,440 Crore", "₹10,000 Crore", "₹12,500 Crore", "₹9,800 Crore"],
                opts_or: ["₹୧୧,୪୪୦ କୋଟି", "₹୧୦,୦୦୦ କୋଟି", "₹୧୨,୫୦୦ କୋଟି", "₹୯,୮୦୦ କୋଟି"],
                correct: 0
            },
            {
                q_en: "We Rise Initiative Launched By?",
                q_or: "ଉଇ ରାଇଜ୍ (We Rise) ପଦକ୍ଷେପ କାହା ଦ୍ୱାରା ଆରମ୍ଭ କରାଯାଇଛି?",
                opts_en: ["UNICEF", "World Bank", "Ministry of Education", "NITI Aayog"],
                opts_or: ["UNICEF", "ବିଶ୍ୱ ବ୍ୟାଙ୍କ", "ଶିକ୍ଷା ମନ୍ତ୍ରାଳୟ", "ନୀତି ଆୟୋଗ"],
                correct: 3
            },
            {
                q_en: "VISHWAS Scheme Was Launched By?",
                q_or: "ବିଶ୍ୱାସ (VISHWAS) ଯୋଜନା କାହା ଦ୍ୱାରା ଲଞ୍ଚ କରାଯାଇଥିଲା?",
                opts_en: ["Labour Ministry", "Finance Ministry", "Home Ministry", "Corporate Affairs Ministry"],
                opts_or: ["ଶ୍ରମ ମନ୍ତ୍ରାଳୟ", "ଅର୍ଥ ମନ୍ତ୍ରାଳୟ", "ଗୃହ ମନ୍ତ୍ରାଳୟ", "କର୍ପୋରେଟ୍ ବ୍ୟାପାର ମନ୍ତ୍ରାଳୟ"],
                correct: 0
            }
        ];

        // LOCALIZATION DICTIONARY
        const uiText = {
            EN: {
                badge: "Testbook Premium Interface", subscribe: "Subscribe", welcome: "Ready to start the Mock Test?",
                instructions: "Enhance your preparation with our real-time Testbook interface exam dashboard. Instant response feedback with review status is supported.",
                start: "Start Test Now", prev: "Previous", mark: "Mark Review", next: "Save & Next",
                palette: "Question Palette", unvisited: "Unvisited", answered: "Answered", review: "Review",
                current: "Current", submit: "Submit Exam", congrats: "Test Successfully Completed!",
                subinfo: "Total Questions: 15 | Positive: +1.0 | Negative: -0.0",
                resub: "Analysis report and performance scorecard generation", score: "Your Score", acc: "Correct",
                wrong: "Wrong", rank: "Rank", cert: "Download Certificate", share: "Share Score", restart: "Retake Test",
                com: "Join our community for regular test updates", sol: "Detailed Answer Key & Solutions"
            },
            ODIA: {
                badge: "ଟେଷ୍ଟବୁକ୍ ପ୍ରିମିୟମ୍ ଇଣ୍ଟରଫେସ୍", subscribe: "ସବସ୍କ୍ରାଇବ୍", welcome: "ମକ୍ ଟେଷ୍ଟ ଆରମ୍ଭ କରିବାକୁ ପ୍ରସ୍ତୁତ କି?",
                instructions: "ଆମର ପ୍ରକୃତ ସମୟର ଟେଷ୍ଟବୁକ୍ ଇଣ୍ଟରଫେସ୍ ପରୀକ୍ଷା ଡ୍ୟାସବୋର୍ଡ ସହିତ ଆପଣଙ୍କର ପ୍ରସ୍ତୁତିକୁ ବଢାନ୍ତୁ। ତୁରନ୍ତ ଉତ୍ତର ପ୍ରତିକ୍ରିୟା ଏବଂ ସମୀକ୍ଷା ସ୍ଥିତି ସମର୍ଥିତ।",
                start: "ଏବେ ଟେଷ୍ଟ ଦିଅନ୍ତୁ", prev: "ପୂର୍ବବର୍ତ୍ତୀ", mark: "ସମୀକ୍ଷା ଚିହ୍ନଟ", next: "ରଖନ୍ତୁ ଓ ଆଗକୁ ଯାଆନ୍ତୁ",
                palette: "ପ୍ରଶ୍ନ ପାଲେଟ୍", unvisited: "ଅନାଲୋଚିତ", answered: "ଉତ୍ତର ଦିଆଯାଇଛି", review: "ସମୀକ୍ଷା",
                current: "ଚଳିତ ପ୍ରଶ୍ନ", submit: "ପରୀକ୍ଷା ସବମିଟ୍ କରନ୍ତୁ", congrats: "ଟେଷ୍ଟ ସଫଳତାର ସହିତ ସମାପ୍ତ ହେଲା!",
                subinfo: "ମୋଟ ପ୍ରଶ୍ନ: ୧୫ | ପଜିଟିଭ୍: +୧.୦ | ନେଗେଟିଭ୍: -୦.୦",
                resub: "ବିଶ୍ଳେଷଣ ରିପୋର୍ଟ ଏବଂ ପ୍ରଦର୍ଶନ ସ୍କୋରକାର୍ଡ ପ୍ରସ୍ତୁତି", score: "ଆପଣଙ୍କ ସ୍କୋର", acc: "ଠିକ୍ ଉତ୍ତର",
                wrong: "ଭୁଲ୍ ଉତ୍ତର", rank: "ରାଙ୍କ", cert: "ପ୍ରମାଣପତ୍ର ଡାଉନଲୋଡ୍", share: "ସ୍କୋର ସେୟାର କରନ୍ତୁ", restart: "ପୁନର୍ବାର ଚେଷ୍ଟା",
                com: "ନିୟମିତ ଟେଷ୍ଟ ଅପଡେଟ୍ ପାଇଁ ଆମ କମ୍ୟୁନିଟିରେ ଯୋଗ ଦିଅନ୍ତୁ", sol: "ବିସ୍ତୃତ ଉତ୍ତର ଏବଂ ସମାଧାନ"
            }
        };

        // AUDIO DRIVERS
        function playSnd(id) {
            const a = document.getElementById(id);
            if(a) { a.currentTime = 0; a.play().catch(()=>{}); }
        }

        // INTERFACE MECHANICS & THEMING
        function toggleTheme() {
            document.documentElement.classList.toggle('dark');
            const bg = document.getElementById('body-theme');
            const icon = document.getElementById('theme-icon');
            if(document.documentElement.classList.contains('dark')) {
                bg.className = "animated-bg-dark min-h-screen text-slate-100 antialiased flex flex-col transition-colors duration-300";
                icon.className = "fas fa-sun text-yellow-400";
            } else {
                bg.className = "animated-bg min-h-screen text-slate-800 antialiased flex flex-col transition-colors duration-300";
                icon.className = "fas fa-moon text-slate-700";
            }
        }

        function toggleLanguage() {
            currentLang = currentLang === 'EN' ? 'ODIA' : 'EN';
            applyLocalization();
            if(quizActive) renderQuestion();
        }

        function applyLocalization() {
            const tr = uiText[currentLang];
            document.getElementById('lbl-badge').innerText = tr.badge;
            document.getElementById('btn-subscribe').innerText = tr.subscribe;
            document.getElementById('lbl-sub-info').innerText = tr.subinfo;
            document.getElementById('lbl-welcome').innerText = tr.welcome;
            document.getElementById('lbl-instructions').innerText = tr.instructions;
            document.getElementById('btn-start').innerText = tr.start;
            document.getElementById('lbl-prev').innerText = tr.prev;
            document.getElementById('lbl-mark').innerText = tr.mark;
            document.getElementById('lbl-next-save').innerText = tr.next;
            document.getElementById('lbl-palette').innerText = tr.palette;
            document.getElementById('ind-unvisited').innerText = tr.unvisited;
            document.getElementById('ind-answered').innerText = tr.answered;
            document.getElementById('ind-review').innerText = tr.review;
            document.getElementById('ind-current').innerText = tr.current;
            document.getElementById('lbl-submit-test').innerText = tr.submit;
            document.getElementById('lbl-congrats').innerText = tr.congrats;
            document.getElementById('lbl-result-sub').innerText = tr.resub;
            document.getElementById('lbl-res-score').innerText = tr.score;
            document.getElementById('lbl-res-acc').innerText = tr.acc;
            document.getElementById('lbl-res-wrong').innerText = tr.wrong;
            document.getElementById('lbl-res-rank').innerText = tr.rank;
            document.getElementById('btn-cert').innerText = tr.cert;
            document.getElementById('btn-share').innerText = tr.share;
            document.getElementById('btn-restart').innerText = tr.restart;
            document.getElementById('lbl-join-community').innerText = tr.com;
            document.getElementById('lbl-review-title').innerText = tr.sol;
        }

        // INITIAL PALETTE GENERATION
        function generatePalette() {
            const container = document.getElementById('palette-matrix');
            container.innerHTML = '';
            for(let i=0; i<15; i++) {
                const btn = document.createElement('button');
                btn.id = `palette-btn-${i}`;
                btn.className = "w-10 h-10 font-bold rounded-xl text-xs border border-slate-300 dark:border-slate-600 bg-white/40 dark:bg-slate-800/40 text-slate-700 dark:text-slate-300 flex items-center justify-center transition shadow-sm cursor-not-allowed";
                btn.innerText = i+1;
                btn.onclick = () => { if(quizActive) jumpToQuestion(i); };
                container.appendChild(btn);
            }
        }

        // QUIZ ENGINE ENGINE
        function startQuiz() {
            playSnd('snd-click');
            quizActive = true;
            document.getElementById('start-screen').classList.add('hidden');
            document.getElementById('quiz-card').classList.remove('hidden');
            document.getElementById('btn-submit-exam').classList.remove('hidden');
            
            // Enable palette operations
            for(let i=0; i<15; i++) {
                document.getElementById(`palette-btn-${i}`).classList.remove('cursor-not-allowed');
            }
            
            startTimer();
            renderQuestion();
            updatePaletteUI();
        }

        function startTimer() {
            timerInstance = setInterval(() => {
                if(timeLeft <= 0) {
                    clearInterval(timerInstance);
                    submitQuiz();
                } else {
                    timeLeft--;
                    let m = Math.floor(timeLeft / 60);
                    let s = timeLeft % 60;
                    document.getElementById('timer-display').innerText = `${m.toString().padStart(2,'0')}:${s.toString().padStart(2,'0')}`;
                }
            }, 1000);
        }

        function renderQuestion() {
            const q = questionsData[currentIdx];
            document.getElementById('q-number-badge').innerText = currentLang === 'EN' ? `Question ${currentIdx + 1} of 15` : `ପ୍ରଶ୍ନ ${currentIdx + 1} / ୧୫`;
            document.getElementById('question-text').innerText = currentLang === 'EN' ? q.q_en : q.q_or;

            const optsBox = document.getElementById('options-container');
            optsBox.innerHTML = '';

            const alpha = ['A', 'B', 'C', 'D'];
            const optionsList = currentLang === 'EN' ? q.opts_en : q.opts_or;

            optionsList.forEach((opt, idx) => {
                const isSelected = userResponses[currentIdx] === idx;
                const row = document.createElement('div');
                row.onclick = () => selectOption(idx);
                row.className = `p-3.5 rounded-xl border flex items-center gap-3 cursor-pointer transition transform hover:scale-[1.01] shadow-sm ${
                    isSelected 
                    ? 'bg-indigo-600/10 border-indigo-500 dark:border-indigo-400 text-indigo-700 dark:text-indigo-300 font-medium' 
                    : 'bg-white/50 dark:bg-slate-800/50 border-slate-200 dark:border-slate-700 text-slate-700 dark:text-slate-300 hover:bg-white/80 dark:hover:bg-slate-700/80'
                }`;
                row.innerHTML = `
                    <span class="w-7 h-7 rounded-lg flex items-center justify-center text-xs font-bold shadow-inner ${
                        isSelected ? 'bg-indigo-600 text-white' : 'bg-slate-200 dark:bg-slate-700 text-slate-600 dark:text-slate-400'
                    }">${alpha[idx]}</span>
                    <span class="text-sm">${opt}</span>
                `;
                optsBox.appendChild(row);
            });

            // Adjust navigation state
            document.getElementById('btn-prev').disabled = currentIdx === 0;
            document.getElementById('btn-next').innerHTML = currentIdx === 14 
                ? `${currentLang==='EN'?'Finish':'ସମାପ୍ତ'} <i class="fas fa-check-circle ml-1"></i>` 
                : `${currentLang==='EN'?'Save & Next':'ରଖନ୍ତୁ ଓ ଆଗକୁ'} <i class="fas fa-chevron-right ml-1"></i>`;

            // Progress estimation
            const progression = ((currentIdx + 1) / 15) * 100;
            document.getElementById('progress-bar').style.width = `${progression}%`;
            
            updatePaletteUI();
        }

        function selectOption(idx) {
            playSnd('snd-click');
            userResponses[currentIdx] = idx;
            renderQuestion();
        }

        function clearResponse() {
            playSnd('snd-click');
            userResponses[currentIdx] = null;
            renderQuestion();
        }

        function markForReview() {
            playSnd('snd-click');
            reviewStatus[currentIdx] = !reviewStatus[currentIdx];
            updatePaletteUI();
        }

        function nextQuestion() {
            if(currentIdx < 14) {
                currentIdx++;
                renderQuestion();
            } else {
                submitQuiz();
            }
        }

        function prevQuestion() {
            if(currentIdx > 0) {
                currentIdx--;
                renderQuestion();
            }
        }

        function jumpToQuestion(i) {
            playSnd('snd-click');
            currentIdx = i;
            renderQuestion();
        }

        function updatePaletteUI() {
            for(let i=0; i<15; i++) {
                const btn = document.getElementById(`palette-btn-${i}`);
                if(!btn) continue;
                
                // Base structure styles resetting
                btn.className = "w-10 h-10 font-bold rounded-xl text-xs flex items-center justify-center transition shadow-sm ";

                if(i === currentIdx) {
                    btn.className += "bg-indigo-600 text-white ring-4 ring-indigo-500/30 scale-105 border-indigo-600 z-10";
                } else if(reviewStatus[i]) {
                    btn.className += "bg-amber-500 text-white border-amber-500";
                } else if(userResponses[i] !== null) {
                    btn.className += "bg-emerald-500 text-white border-emerald-500";
                } else {
                    btn.className += "bg-white/40 dark:bg-slate-800/40 border-slate-300 dark:border-slate-600 text-slate-700 dark:text-slate-300";
                }
            }
        }

        // SCORE CALCULATION & SUBMISSION PRODUCER
        function submitQuiz() {
            clearInterval(timerInstance);
            quizActive = false;
            playSnd('snd-success');
            
            document.getElementById('quiz-card').classList.add('hidden');
            document.getElementById('btn-submit-exam').classList.add('hidden');
            document.getElementById('result-screen').classList.remove('hidden');

            // Metrics formulation
            let correctCount = 0;
            let wrongCount = 0;

            userResponses.forEach((ans, idx) => {
                if(ans !== null) {
                    if(ans === questionsData[idx].correct) correctCount++;
                    else wrongCount++;
                }
            });

            const scoreObtained = correctCount; // +1.0 per correct, 0 negative

            document.getElementById('res-score').innerText = `${scoreObtained}/15`;
            document.getElementById('res-correct').innerText = correctCount;
            document.getElementById('res-wrong').innerText = wrongCount;
            
            // Dynamic generation of rank profiles based on points
            let estimatedRank = scoreObtained === 15 ? 1 : (16 - scoreObtained);
            document.getElementById('res-rank').innerText = `#${estimatedRank}`;

            // Trigger Confetti Celebrations
            confetti({ particleCount: 150, spread: 80, origin: { y: 0.6 } });

            renderDetailedSolutions();
        }

        // SOLUTION GENERATOR (LAST ME ANSWER SHOW)
        function renderDetailedSolutions() {
            const container = document.getElementById('detailed-solutions');
            container.innerHTML = '';
            const alpha = ['A', 'B', 'C', 'D'];

            questionsData.forEach((q, idx) => {
                const isCorrect = userResponses[idx] === q.correct;
                const hasAnswered = userResponses[idx] !== null;
                
                const card = document.createElement('div');
                card.className = "p-4 bg-white/50 dark:bg-slate-800/50 rounded-xl border border-slate-200 dark:border-slate-700 shadow-sm space-y-2";
                
                let answerStatusHTML = '';
                if(!hasAnswered) {
                    answerStatusHTML = `<span class="text-xs font-semibold px-2 py-0.5 bg-slate-200 dark:bg-slate-700 text-slate-600 dark:text-slate-400 rounded">Unanswered</span>`;
                } else if(isCorrect) {
                    answerStatusHTML = `<span class="text-xs font-semibold px-2 py-0.5 bg-green-500/20 text-green-600 rounded">Correct</span>`;
                } else {
                    answerStatusHTML = `<span class="text-xs font-semibold px-2 py-0.5 bg-red-500/20 text-red-600 rounded">Incorrect</span>`;
                }

                const optionsList = currentLang === 'EN' ? q.opts_en : q.opts_or;

                card.innerHTML = `
                    <div class="flex items-start justify-between gap-3">
                        <h5 class="text-sm font-bold text-slate-800 dark:text-slate-200">Q${idx+1}. ${currentLang==='EN'?q.q_en:q.q_or}</h5>
                        ${answerStatusHTML}
                    </div>
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-2 text-xs pt-1">
                        ${optionsList.map((o, i) => `
                            <div class="p-2 rounded-lg border ${
                                i === q.correct 
                                ? 'bg-green-500/10 border-green-500/30 text-green-700 dark:text-green-400 font-medium' 
                                : (userResponses[idx] === i ? 'bg-red-500/10 border-red-500/30 text-red-700 dark:text-red-400' : 'bg-slate-100/50 dark:bg-slate-900/50 border-transparent text-slate-600 dark:text-slate-400')
                            }">
                                ${alpha[i]}. ${o}
                            </div>
                        `).join('')}
                    </div>
                    <div class="text-[11px] text-indigo-600 dark:text-indigo-400 font-medium bg-indigo-500/5 p-2 rounded-lg mt-1">
                        <i class="fas fa-info-circle mr-1"></i> <strong>Correct Answer: Option ${alpha[q.correct]}</strong> (${optionsList[q.correct]})
                    </div>
                `;
                container.appendChild(card);
            });
        }

        // HTML5 CANVAS DYNAMIC CERTIFICATE GENERATION
        function downloadCertificate() {
            const canvas = document.createElement('canvas');
            canvas.width = 800;
            canvas.height = 600;
            const ctx = canvas.getContext('2d');

            // Draw Background Gradients
            const grad = ctx.createLinearGradient(0, 0, 800, 600);
            grad.addColorStop(0, '#ffffff');
            grad.addColorStop(1, '#f1f5f9');
            ctx.fillStyle = grad;
            ctx.fillRect(0, 0, 800, 600);

            // Vintage Borders
            ctx.strokeStyle = '#4f46e5';
            ctx.lineWidth = 10;
            ctx.strokeRect(20, 20, 760, 560);
            ctx.strokeStyle = '#f59e0b';
            ctx.lineWidth = 2;
            ctx.strokeRect(30, 30, 740, 540);

            // Header Elements
            ctx.textAlign = 'center';
            ctx.fillStyle = '#1e1b4b';
            ctx.font = 'bold 32px Inter, sans-serif';
            ctx.fillText('POLAI EDUCATION HUB', 400, 100);

            ctx.fillStyle = '#64748b';
            ctx.font = '600 14px Inter, sans-serif';
            ctx.fillText('CERTIFICATE OF ACCOMPLISHMENT', 400, 140);

            // Body Context
            ctx.fillStyle = '#334155';
            ctx.font = 'italic 18px Inter, sans-serif';
            ctx.fillText('This is proudly awarded to an elite aspirant for completing the', 400, 220);

            ctx.fillStyle = '#4f46e5';
            ctx.font = 'bold 24px Inter, sans-serif';
            ctx.fillText('CENTRAL SCHEME 2026 MCQ TEST', 400, 270);

            // Metrics Output
            let scr = document.getElementById('res-score').innerText;
            ctx.fillStyle = '#0f172a';
            ctx.font = '500 18px Inter, sans-serif';
            ctx.fillText(`Securing a commendable score of ${scr} Questions`, 400, 330);

            // Signatures & Branding Endorsements
            ctx.fillStyle = '#94a3b8';
            ctx.fillText('________________________', 400, 440);
            ctx.fillStyle = '#4f46e5';
            ctx.font = 'bold 16px Inter, sans-serif';
            ctx.fillText('Authorized Examination Wing', 400, 465);

            ctx.fillStyle = '#f59e0b';
            ctx.font = 'bold 12px Inter, sans-serif';
            ctx.fillText('Verified E-Certificate', 400, 520);

            // Trigger Download File Pipeline
            const image = canvas.toDataURL("image/png");
            const link = document.createElement('a');
            link.download = 'Polai_Education_Hub_Certificate.png';
            link.href = image;
            link.click();
        }

        // SOCIAL WEB SHARE API
        function shareScore() {
            let scr = document.getElementById('res-score').innerText;
            const text = `I scored ${scr} in the Central Scheme 2026 MCQ Mock Test on POLAI EDUCATION HUB! Prepare and take your test now.`;
            if (navigator.share) {
                navigator.share({ title: 'Mock Test Results', text: text, url: window.location.href }).catch(()=>{});
            } else {
                navigator.clipboard.writeText(text);
                alert('Score details copied to clipboard!');
            }
        }

        // WINDOW DRIVER BOOTSTRAP
        window.onload = () => {
            generatePalette();
            applyLocalization();
        };
    </script>
</body>
</html>
