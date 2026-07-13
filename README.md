
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>THE SHADOW INDEX // CASE 773</title>
    <style>
        :root {
            --bg-color: #0f1112;
            --desk-surface: #191c1e;
            --accent-gold: #dfb76c;
            --ink-black: #08090a;
            --text-clean: #e1e4e6;
            --text-dark: #222;
            --text-muted: #6c7275;
            --crimson: #962d22;
            --font-serif: 'Georgia', serif;
            --font-mono: 'Courier New', Courier, monospace;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-clean);
            font-family: var(--font-serif);
            overflow-x: hidden;
            letter-spacing: 0.02em;
            background-image: radial-gradient(circle at 50% 40%, #1a1e20 0%, var(--bg-color) 80%);
            min-height: 100vh;
        }

        /* Minimalist Navigation Frame */
        .workspace-header {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 60px 40px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .brand-mark {
            font-family: var(--font-mono);
            font-size: 0.75rem;
            color: var(--accent-gold);
            letter-spacing: 0.5em;
            text-transform: uppercase;
        }

        .switch-board {
            display: flex;
            gap: 50px;
        }

        .switch-tab {
            background: transparent;
            border: none;
            color: var(--text-muted);
            font-family: var(--font-mono);
            font-size: 0.8rem;
            text-transform: uppercase;
            letter-spacing: 0.2em;
            cursor: pointer;
            padding: 10px 0;
            position: relative;
            transition: color 0.4s ease;
        }

        .switch-tab::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 1px;
            background-color: var(--accent-gold);
            transition: width 0.4s ease;
        }

        .switch-tab.active-state {
            color: #fff;
        }

        .switch-tab.active-state::after {
            width: 100%;
        }

        /* Screen Display Assembly */
        .canvas-container {
            max-width: 1200px;
            margin: 0 auto 150px auto;
            padding: 0 40px;
        }

        .desk-view {
            display: none;
            animation: cinematicSlideIn 1s cubic-bezier(0.16, 1, 0.3, 1) forwards;
        }

        .desk-view.active-state {
            display: block;
        }

        /* Concept 1: The Sleuth Dossier Asymmetry */
        .dossier-layout {
            display: flex;
            gap: 80px;
            align-items: center;
            justify-content: space-between;
        }

        @media (max-width: 900px) {
            .dossier-layout {
                flex-direction: column;
                gap: 40px;
            }
        }

        .portrait-frame {
            flex-shrink: 0;
            width: 400px;
            max-width: 100%;
            background: var(--desk-surface);
            padding: 30px;
            border-top: 3px solid var(--accent-gold);
            box-shadow: 0 40px 80px rgba(0,0,0,0.6);
        }

        .portrait-img {
            width: 100%;
            height: auto;
            display: block;
            filter: grayscale(100%) contrast(115%);
        }

        .profile-narrative {
            max-width: 600px;
        }

        .profile-narrative h1 {
            font-size: 3.5rem;
            font-weight: 400;
            line-height: 1.1;
            margin-bottom: 20px;
            color: #fff;
        }

        .subtitle-spec {
            font-family: var(--font-mono);
            color: var(--accent-gold);
            font-size: 0.8rem;
            text-transform: uppercase;
            letter-spacing: 0.3em;
            display: block;
            margin-bottom: 40px;
        }

        .editorial-text {
            font-size: 1.15rem;
            line-height: 2;
            color: #cdd1d4;
            text-align: justify;
            margin-bottom: 30px;
        }

        /* Concept 2: The Physical File Folder Concept */
        .case-folder {
            background: #e6e2da;
            color: var(--text-dark);
            padding: 80px;
            box-shadow: 0 50px 100px rgba(0,0,0,0.7);
            position: relative;
            border-radius: 4px;
        }

        @media (max-width: 768px) {
            .case-folder { padding: 40px; }
        }

        .folder-tab-label {
            position: absolute;
            top: -35px;
            left: 0;
            background: #e6e2da;
            padding: 8px 30px;
            font-family: var(--font-mono);
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 0.15em;
            border-radius: 4px 4px 0 0;
        }

        .folder-title-block {
            border-bottom: 2px solid var(--text-dark);
            padding-bottom: 30px;
            margin-bottom: 50px;
        }

        .folder-title-block h2 {
            font-size: 2.8rem;
            font-weight: 400;
            letter-spacing: -0.01em;
        }

        .chronicle-stream {
            margin-bottom: 60px;
        }

        .statement-card {
            margin-bottom: 45px;
            border-left: 3px solid var(--crimson);
            padding-left: 25px;
        }

        .suspect-header {
            font-family: var(--font-mono);
            font-size: 0.9rem;
            text-transform: uppercase;
            font-weight: bold;
            margin-bottom: 10px;
            letter-spacing: 0.05em;
            color: var(--crimson);
        }

        .folder-prose {
            font-size: 1.1rem;
            line-height: 1.9;
            text-align: justify;
            color: #333;
        }

        /* Text Interrogation Box */
        .interrogation-console {
            background: var(--ink-black);
            padding: 50px;
            color: var(--text-clean);
            margin-top: 60px;
        }

        .interrogation-console h3 {
            font-family: var(--font-mono);
            color: var(--accent-gold);
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 0.2em;
            margin-bottom: 15px;
        }

        .control-row {
            display: flex;
            gap: 20px;
            margin-top: 35px;
        }

        @media (max-width: 600px) {
            .control-row { flex-direction: column; }
        }

        .verdict-input {
            flex: 1;
            background: #131517;
            border: 1px solid rgba(255, 255, 255, 0.08);
            padding: 18px;
            color: var(--text-clean);
            font-family: var(--font-mono);
            font-size: 1rem;
            outline: none;
            letter-spacing: 0.05em;
            transition: border-color 0.4s ease;
        }

        .verdict-input:focus {
            border-color: var(--accent-gold);
        }

        .execute-btn {
            background: var(--accent-gold);
            color: var(--ink-black);
            border: none;
            padding: 0 40px;
            font-family: var(--font-mono);
            font-weight: bold;
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 0.15em;
            cursor: pointer;
            transition: background 0.3s ease;
        }

        .execute-btn:hover {
            background: #f1cd89;
        }

        .status-output {
            margin-top: 25px;
            font-family: var(--font-mono);
            font-size: 0.85rem;
            min-height: 24px;
        }

        .match { color: #2ecc71; }
        .mismatch { color: #e74c3c; }

        @keyframes cinematicSlideIn {
            from { opacity: 0; transform: translateY(20px); filter: blur(5px); }
            to { opacity: 1; transform: translateY(0); filter: blur(0); }
        }
    </style>
</head>
<body>

    <!-- Minimal Workspace Header Frame -->
    <header class="workspace-header">
        <div class="brand-mark">INVESTIGATIVE UNIT ARCHIVE</div>
        <nav class="switch-board">
            <button class="switch-tab active-state" onclick="toggleView('dossier-view', this)">I. Profile Overview</button>
            <button class="switch-tab" onclick="toggleView('case-view', this)">II. Case Chronicle</button>
        </nav>
    </header>

    <!-- Master Screen Matrix -->
    <main class="canvas-container">

        <!-- VIEW 1: THE INVESTIGATOR PROFILE -->
        <section id="dossier-view" class="desk-view active-state">
            <div class="dossier-layout">
                <div class="portrait-frame">
                    <img src="https://github.com/Kamakshi-weby/lalala/blob/main/622d03f0-8c85-4901-91e1-22853a46c77d.jpg?raw=true" alt="Investigator Photographic Record" class="portrait-img">
                </div>
                <div class="profile-narrative">
                    <h1>Lead Specialist</h1>
                    <span class="subtitle-spec">Special Operations // Threat Classification</span>
                    <p class="editorial-text">
                        Most detectives track the heavy footprints pressed deep into the dirt. I don't look down. Instead, my investigations are built on isolating the invisible, systemic structural anomalies left hanging in the room long after a criminal slips away. 
                    </p>
                    <p class="editorial-text">
                        This open framework acts as a secure repository for unsolved high-profile assets. The image on the left registers the last active analytical consultant in this district willing to challenge perfectly calculated alibis. Shift over to the Case Chronicle tab to break open the timeline.
                    </p>
                </div>
            </div>
        </section>

        <!-- VIEW 2: THE PHYSICAL MANILA FILE FOLDER -->
        <section id="case-view" class="desk-view">
            <div class="case-folder">
                <div class="folder-tab-label">CLASSIFIED CASE FILE #773</div>
                
                <div class="folder-title-block">
                    <h2>The Midnight Sonata</h2>
                    <p class="subtitle-spec" style="color: #555; margin-bottom: 0; margin-top: 5px;">Incident Location: Blackwood Estate // Timeline Peak: 02:40 AM</p>
                </div>

                <div class="chronicle-stream">
                    <p class="folder-prose" style="font-size: 1.25rem; font-weight: bold; margin-bottom: 40px; color: #111;">
                        The storm pounded against the stained-glass ceiling of Blackwood Estate with calculated violence. Inside the master study, Lord Blackwood sat dead at his writing desk, a freshly poured, untouched glass of red wine resting beside a torn shred of stationary that read: <em>"The debt is collected."</em>
                    </p>

                    <div class="statement-card">
                        <div class="suspect-header">Alibi Statement 01 // Sterling (The Butler)</div>
                        <p class="folder-prose">
                            Maintained under intense questioning that he spent the hours of the storm locked away in the lower wine cellar to secure historic stock from rising floodwaters. Yet, forensic analysts found microscopic pieces of crushed white orchid petals caught in the seams of his leather boots. These exotic orchids grow exclusively on the second-story conservatory balcony, which sits directly outside the victim's shattered study window.
                        </p>
                    </div>

                    <div class="statement-card">
                        <div class="suspect-header">Alibi Statement 02 // Julian (The Brother)</div>
                        <p class="folder-prose">
                            Swore he spent the entire night alone in the opposite library wing translating ancient Greek classical volumes. While he lacks an apparent reason for violence, a hidden bank ledger recovered from his quarters exposes an astronomical chain of private gambling debts coming due at sunrise.
                        </p>
                    </div>

                    <div class="statement-card">
                        <div class="suspect-header">Alibi Statement 03 // Victoria (The Protege)</div>
                        <p class="folder-prose">
                            Claims she was deeply asleep in the far eastern wing of the estate after taking a medical sedative. Strangely, her personal antique silver watch was discovered completely broken, its gears jammed and frozen at precisely 2:42 AM—the exact minute the primary pendulum clock in the study was smashed during the fatal scuffle.
                        </p>
                    </div>
                </div>

                <!-- Dark Interrogation Terminal Module -->
                <div class="interrogation-console">
                    <h3>Isolate the Chrono-Contradiction</h3>
                    <p class="folder-prose" style="color: var(--text-muted); font-size: 0.95rem;">
                        One alibi instantly collapses under physical trace tracking. Type the name of the true criminal directly into the field below to issue the arrest warrant.
                    </p>
                    
                    <div class="control-row">
                        <input type="text" id="suspect-entry" class="verdict-input" placeholder="Enter target name (Sterling, Julian, or Victoria)..." autocomplete="off">
                        <button class="execute-btn" onclick="analyzeVerdict()">Issue Warrant</button>
                    </div>
                    
                    <div id="console-feedback" class="status-output"></div>
                </div>
            </div>
        </section>

    </main>

    <script>
        // Smooth Tab Navigation Script
        function toggleView(targetPanel, buttonSource) {
            document.querySelectorAll('.desk-view').forEach(v => v.classList.remove('active-state'));
            document.querySelectorAll('.switch-tab').forEach(t => t.classList.remove('active-state'));
            
            document.getElementById(targetPanel).classList.add('active-state');
            buttonSource.classList.add('active-state');
            
            // Trigger soundtrack framework instantly on user tab shifting
            playDramatics();
        }

        // Interrogation Text Core Logic
        function analyzeVerdict() {
            playDramatics(); // Security catch to start audio if not already running
            const userVerdict = document.getElementById('suspect-entry').value.trim().toLowerCase();
            const consoleOutput = document.getElementById('console-feedback');

            if (userVerdict === 'sterling') {
                consoleOutput.className = "status-output match";
                consoleOutput.innerText = "✓ WARRANT ISSUED: Sterling has been neutralized. The crushed orchid petals tracked into his boots proved he scaled the balconies to reach the study window.";
            } else if (userVerdict === 'victoria' || userVerdict === 'julian') {
                consoleOutput.className = "status-output mismatch";
                consoleOutput.innerText = "✗ ANALYSIS REJECTED: Subject alibi stands up to current forensic constraints. Re-evaluate physical trace materials.";
            } else if (userVerdict === "") {
                consoleOutput.className = "status-output mismatch";
                consoleOutput.innerText = "⚠ INPUT EXCEPTION: Interrogation entry block cannot be blank.";
            } else {
                consoleOutput.className = "status-output mismatch";
                consoleOutput.innerText = "✗ ACCESS DENIED: Unknown entity. Target must be Sterling, Julian, or Victoria.";
            }
        }

        /* 
           ADVANCED DRAMATIC SCENE SCORE ENGINE
           Generates a multi-layered, classical 3-note dramatic movie progression dynamically using native Web Audio API oscillators.
           No continuous synth hums or background noise loops. Runs automatically on first user click.
        */
        let movieAudioCtx = null;

        function playDramatics() {
            if (movieAudioCtx) return; // Prevent duplicate music instances

            movieAudioCtx = new (window.AudioContext || window.webkitAudioContext)();
            
            // Sequence Timing Loop - Plays a dramatic structural loop every 4.5 seconds
            function triggerScoreSequence() {
                if (!movieAudioCtx || movieAudioCtx.state === 'suspended') return;

                let now = movieAudioCtx.currentTime;

                // --- LAYER 1: Deep Cinematic Low-End Boom (Orchestral Sub Strike) ---
                let subOsc = movieAudioCtx.createOscillator();
                let subGain = movieAudioCtx.createGain();
                subOsc.type = 'triangle';
                subOsc.frequency.setValueAtTime(36.71, now); // Low D Orchestral Base Note
                
                subGain.gain.setValueAtTime(0.0, now);
                subGain.gain.linearRampToValueAtTime(0.40, now + 0.1);
                subGain.gain.exponentialRampToValueAtTime(0.001, now + 2.5);
                
                subOsc.connect(subGain);
                subGain.connect(movieAudioCtx.destination);
                subOsc.start(now);
                subOsc.stop(now + 2.6);

                // --- LAYER 2: Eerie High-Tension 3-Note Melodic Chime Motif ---
                // Note A (Starts immediately)
                playChimeNote(220.00, now, 1.8); 
                // Note Bb (Plays at 1.2 seconds later for a shocking minor second clash)
                playChimeNote(233.08, now + 1.2, 1.6); 
                // Note D (Plays at 2.4 seconds later to settle into complete mystery)
                playChimeNote(293.66, now + 2.4, 1.8);
            }

            // Core synth architecture for the melodic tension strings/chimes
            function playChimeNote(freq, startTime, duration) {
                let osc = movieAudioCtx.createOscillator();
                let gain = movieAudioCtx.createGain();
                
                osc.type = 'sine';
                osc.frequency.setValueAtTime(freq, startTime);
                
                // Add minor detune over time to build movie suspense vibrato
                osc.detune.setValueAtTime(0, startTime);
                osc.detune.linearRampToValueAtTime(12, startTime + duration);

                gain.gain.setValueAtTime(0.0, startTime);
                gain.gain.linearRampToValueAtTime(0.07, startTime + 0.2);
                gain.gain.exponentialRampToValueAtTime(0.001, startTime + duration);

                osc.connect(gain);
                gain.connect(movieAudioCtx.destination);
                
                osc.start(startTime);
                osc.stop(startTime + duration + 0.1);
            }

            // Fire first dramatic cue immediately and set up the cycle loop
            triggerScoreSequence();
            setInterval(triggerScoreSequence, 5500);
        }

        // Global watchdog trigger to instantly initialize the custom script audio upon screen tap
        document.body.addEventListener('click', () => {
            if (movieAudioCtx && movieAudioCtx.state === 'suspended') {
                movieAudioCtx.resume();
            } else {
                playDramatics();
            }
        }, { once: true });
    </script>
</body>
</html>
