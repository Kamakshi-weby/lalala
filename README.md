
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Whispering Shadow // Case File #773</title>
    <style>
        :root {
            --bg-color: #16191b;
            --panel-color: #222629;
            --accent-gold: #dfb76c;
            --text-light: #e3e4e6;
            --text-muted: #8a9094;
            --crimson: #a93226;
            --font-serif: 'Georgia', serif;
            --font-sans: 'Courier New', Courier, monospace;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-light);
            font-family: var(--font-serif);
            line-height: 1.8;
            letter-spacing: 0.02em;
            overflow-x: hidden;
            background-image: 
                radial-gradient(circle at 70% 20%, rgba(223, 183, 108, 0.03) 0%, transparent 50%),
                radial-gradient(circle at 20% 80%, rgba(169, 50, 38, 0.03) 0%, transparent 40%);
        }

        /* Ambient Audio Control */
        .audio-bar {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background: rgba(22, 25, 27, 0.9);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(223, 183, 108, 0.15);
            padding: 12px 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
        }

        .status-indicator {
            font-family: var(--font-sans);
            font-size: 0.8rem;
            color: var(--accent-gold);
            text-transform: uppercase;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .status-dot {
            width: 6px;
            height: 6px;
            background-color: var(--accent-gold);
            border-radius: 50%;
            animation: pulse 2s infinite;
        }

        .audio-btn {
            background: transparent;
            border: 1px solid var(--accent-gold);
            color: var(--accent-gold);
            padding: 6px 16px;
            font-family: var(--font-sans);
            font-size: 0.75rem;
            cursor: pointer;
            text-transform: uppercase;
            transition: all 0.3s ease;
        }

        .audio-btn:hover {
            background: var(--accent-gold);
            color: var(--bg-color);
        }

        /* Navigation Tabs */
        .nav-container {
            max-width: 900px;
            margin: 100px auto 20px auto;
            display: flex;
            gap: 10px;
            padding: 0 20px;
        }

        .tab-btn {
            background: transparent;
            border: none;
            color: var(--text-muted);
            font-family: var(--font-sans);
            font-size: 0.9rem;
            padding: 10px 20px;
            cursor: pointer;
            border-bottom: 2px solid transparent;
            transition: all 0.3s ease;
        }

        .tab-btn.active {
            color: var(--accent-gold);
            border-bottom: 2px solid var(--accent-gold);
        }

        /* Layout & Pages */
        .main-container {
            max-width: 900px;
            margin: 0 auto 100px auto;
            padding: 20px;
        }

        .page {
            display: none;
            animation: fadeIn 0.6s ease forwards;
        }

        .page.active {
            display: block;
        }

        /* Page 1 Elements: Dossier */
        .profile-section {
            display: grid;
            grid-template-columns: 1fr 1.5fr;
            gap: 40px;
            align-items: start;
            margin-top: 20px;
        }

        @media (max-width: 768px) {
            .profile-section {
                grid-template-columns: 1fr;
            }
        }

        .portrait-frame {
            border: 1px solid rgba(223, 183, 108, 0.2);
            padding: 15px;
            background: var(--panel-color);
            box-shadow: 0 15px 35px rgba(0,0,0,0.3);
            position: relative;
        }

        .portrait-frame::before {
            content: 'EVIDENCE FILE #041';
            position: absolute;
            top: -10px;
            left: 15px;
            background: var(--bg-color);
            padding: 0 8px;
            font-family: var(--font-sans);
            font-size: 0.7rem;
            color: var(--text-muted);
        }

        .portrait-img {
            width: 100%;
            height: auto;
            filter: grayscale(40%) contrast(110%);
            display: block;
            border: 1px solid rgba(0,0,0,0.4);
        }

        .dossier-details h1 {
            font-size: 2.5rem;
            color: var(--text-light);
            font-weight: 400;
            margin-bottom: 5px;
            line-height: 1.2;
        }

        .dossier-subtitle {
            font-family: var(--font-sans);
            color: var(--accent-gold);
            font-size: 0.85rem;
            text-transform: uppercase;
            margin-bottom: 30px;
            display: block;
        }

        .dossier-meta {
            font-family: var(--font-sans);
            font-size: 0.85rem;
            border-top: 1px solid rgba(255,255,255,0.05);
            border-bottom: 1px solid rgba(255,255,255,0.05);
            padding: 15px 0;
            margin-bottom: 30px;
            color: var(--text-muted);
        }

        .dossier-meta div {
            margin-bottom: 5px;
        }

        .dossier-meta strong {
            color: var(--text-light);
        }

        .narrative-p {
            margin-bottom: 20px;
            color: #c8cbcb;
            text-align: justify;
        }

        /* Page 2 Elements: Case File */
        .case-header {
            margin-bottom: 40px;
            border-bottom: 1px solid rgba(223, 183, 108, 0.2);
            padding-bottom: 20px;
        }

        .case-header h2 {
            font-size: 2rem;
            font-weight: 400;
            margin-bottom: 5px;
        }

        .story-block {
            background: rgba(34, 38, 41, 0.4);
            border-left: 2px solid var(--accent-gold);
            padding: 30px;
            margin-bottom: 40px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        /* Interactive Guessing Terminal */
        .terminal-box {
            background: var(--panel-color);
            border: 1px solid rgba(223, 183, 108, 0.2);
            padding: 40px;
            border-radius: 2px;
            margin-top: 50px;
            position: relative;
        }

        .terminal-box h3 {
            font-family: var(--font-sans);
            font-size: 1.1rem;
            color: var(--accent-gold);
            margin-bottom: 20px;
            text-transform: uppercase;
        }

        .input-wrapper {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        @media (max-width: 500px) {
            .input-wrapper {
                flex-direction: column;
            }
        }

        .culprit-input {
            flex: 1;
            background: rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(255, 255, 255, 0.1);
            padding: 15px;
            color: var(--text-light);
            font-family: var(--font-sans);
            font-size: 1rem;
            outline: none;
            transition: border-color 0.3s;
        }

        .culprit-input:focus {
            border-color: var(--accent-gold);
        }

        .submit-btn {
            background: var(--accent-gold);
            color: var(--bg-color);
            border: none;
            padding: 15px 30px;
            font-family: var(--font-sans);
            font-weight: bold;
            font-size: 0.9rem;
            text-transform: uppercase;
            cursor: pointer;
            transition: background 0.3s;
        }

        .submit-btn:hover {
            background: #c5a159;
        }

        .feedback-message {
            margin-top: 20px;
            font-family: var(--font-sans);
            font-size: 0.9rem;
            min-height: 24px;
        }

        .success { color: #52be80; }
        .error { color: var(--crimson); }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes pulse {
            0% { opacity: 0.4; }
            50% { opacity: 1; }
            100% { opacity: 0.4; }
        }
    </style>
</head>
<body>

    <!-- Ambient Sound System & Banner -->
    <div class="audio-bar">
        <div class="status-indicator">
            <div class="status-dot"></div>
            <span id="system-status">System: Ambient Suspense Offline</span>
        </div>
        <button class="audio-btn" id="audio-toggle" onclick="toggleAudio()">Initialize Audio</button>
    </div>

    <!-- Navigation Tabs -->
    <nav class="nav-container">
        <button class="tab-btn active" onclick="switchPage('dossier-page', this)">I. Investigator Profile</button>
        <button class="tab-btn" onclick="switchPage('case-page', this)">II. Active Case File</button>
    </nav>

    <!-- Main Content Housing -->
    <main class="main-container">

        <!-- PAGE 1: DOSSIER & INTRO -->
        <section id="dossier-page" class="page active">
            <div class="profile-section">
                <div class="portrait-frame">
                    <img src="https://github.com/Kamakshi-weby/lalala/blob/main/622d03f0-8c85-4901-91e1-22853a46c77d.jpg?raw=true" alt="Lead Detective Portrait" class="portrait-img">
                </div>
                <div class="dossier-details">
                    <h1>Detective Specialist</h1>
                    <span class="dossier-subtitle">Department of Esoteric & High-Profile Crimes</span>
                    
                    <div class="dossier-meta">
                        <div><strong>Current Assignment:</strong> The Blackwood Manor Heist</div>
                        <div><strong>Status:</strong> Active Investigation</div>
                        <div><strong>Methodology:</strong> Behavioral Analytics & Technical Forensics</div>
                    </div>

                    <p class="narrative-p">
                        Some investigators follow the footprints in the mud; I look for the anomalies in the architecture. Operating within the intersection of shadows and absolute logic, my career has been defined by the cases the city preferred to forget. 
                    </p>
                    <p class="narrative-p">
                        This archive serves as a repository for open investigations. The portrait on the left isn't just an identification card—it's a record of the last remaining specialist willing to look directly into the dark. Turn to the next file when you are ready to examine the evidence.
                    </p>
                </div>
            </div>
        </section>

        <!-- PAGE 2: THE CASE FILE -->
        <section id="case-page" class="page">
            <div class="case-header">
                <h2>Case File #773: The Midnight Sonata</h2>
                <p class="dossier-subtitle">Location: Blackwood Estate // Timeline: 02:40 AM</p>
            </div>

            <div class="story-block">
                <p class="narrative-p">
                    The rain was hitting the stained-glass windows of Blackwood Estate with rhythmic cruelty. Inside, Lord Blackwood lay dead at his study desk, a single glass of untouched vintage wine sitting beside a torn piece of parchment reading: <em>"The debt is collected."</em>
                </p>
                <p class="narrative-p">
                    Three individuals were present in the manor house during the storm, each anchoring an alibi that seemed just a fraction too polished to trust:
                </p>
                <p class="narrative-p">
                    <strong>1. Sterling (The Butler):</strong> Claimed he was in the downstairs wine cellar securing the estate's inventory against the rising damp. Yet, his boots carried traces of fresh white orchid petals—flowers native exclusively to the second-story conservatory balcony overlooking the study window.
                </p>
                <p class="narrative-p">
                    <strong>2. Julian (The Estranged Brother):</strong> Insisted he spent the entire night locked in the west-wing library translating rare classical texts. He possessed no motive, save for a freshly bound bank draft detailing massive gambling debits due by dawn.
                </p>
                <p class="narrative-p">
                    <strong>3. Victoria (The Protege):</strong> Swore she was fast asleep in the guest chambers after taking a heavy dose of sleeping draught. Curiously, her silver pocket watch stopped precisely at 2:42 AM, the exact moment the master clock in the study was smashed during the struggle.
                </p>
            </div>

            <!-- Culprit Submission Terminal -->
            <div class="terminal-box">
                <h3>Deduction Interface</h3>
                <p class="narrative-p" style="font-size: 0.95rem; color: var(--text-muted);">
                    Review the environmental indicators carefully. Who fractured the timeline? Type the name of the true culprit below.
                </p>
                
                <div class="input-wrapper">
                    <input type="text" id="culprit-input" class="culprit-input" placeholder="Type name here (e.g., Sterling, Julian, Victoria)..." autocomplete="off">
                    <button class="submit-btn" onclick="verifyCulprit()">Verify Deduction</button>
                </div>
                
                <div id="feedback" class="feedback-message"></div>
            </div>
        </section>

    </main>

    <script>
        // Page Navigation Logic
        function switchPage(pageId, button) {
            document.querySelectorAll('.page').forEach(page => page.classList.remove('active'));
            document.querySelectorAll('.tab-btn').forEach(btn => btn.classList.remove('active'));
            
            document.getElementById(pageId).classList.add('active');
            button.classList.add('active');
        }

        // Culprit Verification Core
        function verifyCulprit() {
            const input = document.getElementById('culprit-input').value.trim().toLowerCase();
            const feedback = document.getElementById('feedback');

            if (input === 'sterling') {
                feedback.className = "feedback-message success";
                feedback.innerText = "✓ DEDUCTION CORRECT. The orchid petals on the boots exposed the path to the balcony window. Sterling has been detained.";
            } else if (input === 'victoria' || input === 'julian') {
                feedback.className = "feedback-message error";
                feedback.innerText = "✗ INCORRECT. Alibi holds under preliminary pressure. Look closer at the physical tracking clues.";
            } else if (input === "") {
                feedback.className = "feedback-message error";
                feedback.innerText = "⚠ Input terminal empty. Enter a suspect name.";
            } else {
                feedback.className = "feedback-message error";
                feedback.innerText = "✗ UNKNOWN SUBJECT. The suspect must be Sterling, Julian, or Victoria.";
            }
        }

        // Web Audio API Custom Scary Background Synth (Built-in Audio)
        let audioCtx = null;
        let oscillator = null;
        let filter = null;
        let lfo = null;
        let isPlaying = false;

        function initAudioSystem() {
            audioCtx = new (window.AudioContext || window.webkitAudioContext)();
            
            // Create audio modules
            oscillator = audioCtx.createOscillator();
            filter = audioCtx.createBiquadFilter();
            let gainNode = audioCtx.createGain();
            
            // Configure dark moody drone oscillator
            oscillator.type = 'sawtooth';
            oscillator.frequency.setValueAtTime(55, audioCtx.currentTime); // Low A pitch
            
            // Configure scary low-pass sweeping filter
            filter.type = 'lowpass';
            filter.frequency.setValueAtTime(200, audioCtx.currentTime);
            filter.Q.setValueAtTime(5, audioCtx.currentTime);
            
            // LFO to modulate filter to give that eerie movie tension movement
            lfo = audioCtx.createOscillator();
            let lfoGain = audioCtx.createGain();
            lfo.type = 'sine';
            lfo.frequency.setValueAtTime(0.3, audioCtx.currentTime); // Very slow sweep
            lfoGain.gain.setValueAtTime(120, audioCtx.currentTime);
            
            lfo.connect(lfoGain);
            lfoGain.connect(filter.frequency);
            
            // Master Volume setting
            gainNode.gain.setValueAtTime(0.12, audioCtx.currentTime); 
            
            // Connect chain
            oscillator.connect(filter);
            filter.connect(gainNode);
            gainNode.connect(audioCtx.destination);
            
            // Start components
            oscillator.start();
            lfo.start();
        }

        function toggleAudio() {
            const btn = document.getElementById('audio-toggle');
            const status = document.getElementById('system-status');

            if (!isPlaying) {
                if (!audioCtx) {
                    initAudioSystem();
                } else if (audioCtx.state === 'suspended') {
                    audioCtx.resume();
                }
                isPlaying = true;
                btn.innerText = "Mute Ambiance";
                status.innerText = "System: Ambient Tension Active";
            } else {
                if(audioCtx) {
                    audioCtx.suspend();
                }
                isPlaying = false;
                btn.innerText = "Initialize Audio";
                status.innerText = "System: Ambient Suspense Offline";
            }
        }
    </script>
</body>
</html>
