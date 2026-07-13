
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>THE SHADOW INDEX // CASE FILE #773</title>
    <style>
        :root {
            --bg-color: #171a1c;
            --panel-color: #24292d;
            --accent-gold: #dfb76c;
            --text-light: #f4f5f6;
            --text-muted: #8c9398;
            --crimson: #d9534f;
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
            line-height: 1.9;
            letter-spacing: 0.03em;
            overflow-x: hidden;
            background-image: 
                linear-gradient(rgba(23, 26, 28, 0.92), rgba(23, 26, 28, 0.92)),
                radial-gradient(circle at 50% 30%, rgba(223, 183, 108, 0.08) 0%, transparent 70%);
        }

        /* Spacious & Classy Header Frame */
        .agency-header {
            max-width: 1100px;
            margin: 0 auto;
            padding: 80px 50px 30px 50px;
            display: flex;
            justify-content: space-between;
            align-items: flex-end;
            border-bottom: 1px solid rgba(223, 183, 108, 0.15);
        }

        .agency-badge {
            font-family: var(--font-sans);
            font-size: 0.85rem;
            color: var(--accent-gold);
            letter-spacing: 0.4em;
            text-transform: uppercase;
            font-weight: bold;
        }

        .navigation-rack {
            display: flex;
            gap: 40px;
        }

        .nav-link {
            background: transparent;
            border: none;
            color: var(--text-muted);
            font-family: var(--font-sans);
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 0.2em;
            cursor: pointer;
            padding-bottom: 8px;
            border-bottom: 2px solid transparent;
            transition: all 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }

        .nav-link.active-tab, .nav-link:hover {
            color: var(--text-light);
            border-bottom: 2px solid var(--accent-gold);
        }

        /* Main Workspace Compartment */
        .workspace-container {
            max-width: 1100px;
            margin: 60px auto 120px auto;
            padding: 0 50px;
        }

        .view-panel {
            display: none;
            animation: cinematicReveal 0.9s cubic-bezier(0.215, 0.610, 0.355, 1.000) forwards;
        }

        .view-panel.active-panel {
            display: block;
        }

        /* Page 1: Elegant Portrait & Profile Layout */
        .dossier-grid {
            display: grid;
            grid-template-columns: 1.1fr 1.4fr;
            gap: 70px;
            align-items: center;
        }

        @media (max-width: 850px) {
            .dossier-grid {
                grid-template-columns: 1fr;
                gap: 50px;
            }
        }

        .exhibit-frame {
            position: relative;
            background: var(--panel-color);
            padding: 24px;
            border: 1px solid rgba(223, 183, 108, 0.2);
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.5);
        }

        .exhibit-frame::before {
            content: "DEPT EVIDENCE BANNER // DO NOT ALTER";
            position: absolute;
            bottom: -30px;
            left: 0;
            font-family: var(--font-sans);
            font-size: 0.65rem;
            color: var(--text-muted);
            letter-spacing: 0.1em;
        }

        .investigator-portrait {
            width: 100%;
            height: auto;
            display: block;
            filter: grayscale(15%) sepia(10%) contrast(105%);
            border: 1px solid rgba(0,0,0,0.3);
        }

        .biography-block h1 {
            font-size: 3.2rem;
            font-weight: 400;
            letter-spacing: -0.01em;
            line-height: 1.1;
            margin-bottom: 15px;
            color: var(--text-light);
        }

        .biography-tagline {
            font-family: var(--font-sans);
            color: var(--accent-gold);
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 0.25em;
            display: block;
            margin-bottom: 45px;
        }

        .dossier-table {
            width: 100%;
            margin-bottom: 45px;
            border-top: 1px solid rgba(223, 183, 108, 0.15);
            border-collapse: collapse;
        }

        .dossier-table td {
            padding: 15px 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
            font-size: 0.95rem;
        }

        .dossier-table td.label {
            font-family: var(--font-sans);
            color: var(--accent-gold);
            text-transform: uppercase;
            font-size: 0.75rem;
            letter-spacing: 0.15em;
            width: 35%;
        }

        .narrative-prose {
            color: #ced2d5;
            text-align: justify;
            font-size: 1.1rem;
            margin-bottom: 30px;
        }

        /* Page 2: Case Mechanics */
        .case-title h2 {
            font-size: 2.6rem;
            font-weight: 400;
            margin-bottom: 10px;
            letter-spacing: -0.01em;
        }

        .case-summary-box {
            background: linear-gradient(90deg, rgba(36, 41, 45, 0.6), transparent);
            border-left: 2px solid var(--accent-gold);
            padding: 45px;
            margin: 50px 0 70px 0;
            box-shadow: 0 15px 40px rgba(0,0,0,0.2);
        }

        .suspect-profile {
            margin-bottom: 35px;
            padding-left: 15px;
            border-left: 1px solid rgba(255,255,255,0.08);
        }

        .suspect-name {
            font-family: var(--font-sans);
            color: var(--accent-gold);
            font-size: 1rem;
            text-transform: uppercase;
            margin-bottom: 8px;
            letter-spacing: 0.05em;
        }

        /* Interactive Anomaly Parser Box */
        .deduction-vault {
            background: var(--panel-color);
            border: 1px solid rgba(223, 183, 108, 0.2);
            padding: 60px;
            box-shadow: 0 25px 50px rgba(0,0,0,0.3);
        }

        .deduction-vault h3 {
            font-family: var(--font-sans);
            font-size: 1.1rem;
            color: var(--accent-gold);
            text-transform: uppercase;
            letter-spacing: 0.25em;
            margin-bottom: 20px;
        }

        .interactive-row {
            display: flex;
            gap: 20px;
            margin-top: 40px;
        }

        @media (max-width: 650px) {
            .interactive-row {
                flex-direction: column;
            }
        }

        .vault-input {
            flex: 1;
            background: #171a1c;
            border: 1px solid rgba(255, 255, 255, 0.1);
            padding: 18px 22px;
            color: var(--text-light);
            font-family: var(--font-sans);
            font-size: 1.05rem;
            outline: none;
            letter-spacing: 0.05em;
            transition: border-color 0.4s ease;
        }

        .vault-input:focus {
            border-color: var(--accent-gold);
        }

        .vault-btn {
            background: var(--accent-gold);
            color: #171a1c;
            border: none;
            padding: 0 45px;
            font-family: var(--font-sans);
            font-weight: bold;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 0.15em;
            cursor: pointer;
            transition: background 0.3s ease;
        }

        .vault-btn:hover {
            background: #f0cb85;
        }

        .console-logs {
            margin-top: 30px;
            font-family: var(--font-sans);
            font-size: 0.9rem;
            letter-spacing: 0.05em;
            min-height: 26px;
        }

        .log-match { color: #52be80; }
        .log-mismatch { color: var(--crimson); }

        @keyframes cinematicReveal {
            from { opacity: 0; transform: translateY(12px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>

    <!-- Classy Modular Identity Banner -->
    <header class="agency-header">
        <div class="agency-badge">CRIMINAL FORENSICS INTELLIGENCE</div>
        <nav class="navigation-rack">
            <button class="nav-link active-tab" onclick="switchTab('dossier-panel', this)">I. Investigator</button>
            <button class="nav-link" onclick="switchTab('case-panel', this)">II. Case Chronicle</button>
        </nav>
    </header>

    <!-- Master Control Engine Container -->
    <main class="workspace-container">

        <!-- PANEL 1: ARCHIVAL INVESTIGATOR RECORD -->
        <section id="dossier-panel" class="view-panel active-panel">
            <div class="dossier-grid">
                <div class="exhibit-frame">
                    <img src="https://github.com/Kamakshi-weby/lalala/blob/main/622d03f0-8c85-4901-91e1-22853a46c77d.jpg?raw=true" alt="Primary Investigator File Record" class="investigator-portrait">
                </div>
                <div class="biography-block">
                    <h1>Special Analyst</h1>
                    <span class="biography-tagline">Department of High-Profile Anomalies</span>
                    
                    <table class="dossier-table">
                        <tr>
                            <td class="label">Current File</td>
                            <td>The Blackwood Estate Asset Dispersion</td>
                        </tr>
                        <tr>
                            <td class="label">Priority Index</td>
                            <td>Alpha Class // Highly Unresolved</td>
                        </tr>
                        <tr>
                            <td class="label">Strategy Vector</td>
                            <td>Chrono-Structural Analysis & Behavioral Forensics</td>
                        </tr>
                    </table>

                    <p class="narrative-prose">
                        Standard field agents follow the physical marks worn into the pavement. I don't. My investigations focus entirely on isolating structural anomalies embedded deep inside an individual's timeline. 
                    </p>
                    <p class="narrative-prose">
                        This open network interface operates as a secure ledger for outstanding case profiles. The tracking asset captured on the left is a remaining timestamp of the final consultant in this district willing to challenge high-profile alibis. Flip to the Case Chronicle tab to decipher the crime scene logs.
                    </p>
                </div>
            </div>
        </section>

        <!-- PANEL 2: ACTIVE SCENE DOSSIER -->
        <section id="case-panel" class="view-panel">
            <div class="case-title">
                <h2>Case File #773: The Midnight Sonata</h2>
                <p class="biography-tagline">Location Vector: Blackwood Perimeter // Timeline Matrix: 02:40 AM</p>
            </div>

            <div class="case-summary-box">
                <p class="narrative-prose" style="font-size: 1.2rem; margin-bottom: 40px; color: #f4f5f6;">
                    The rain storm smashed against the stained-glass roof of Blackwood Estate with brutal intent. Inside the insulated walls of the private study, Lord Blackwood was discovered dead at his writing desk. Beside his hand sat an untouched glass of wine and a ragged note warning: <em>"The debt is collected."</em>
                </p>

                <div class="suspect-profile">
                    <div class="suspect-name">Suspect One // Sterling (The Butler)</div>
                    <p class="narrative-prose">
                        Stated under interrogation that he spent the entire evening working in the subterranean wine vaults to protect old stock from flooding. However, forensics recovered fresh white orchid petal fragments stuck beneath his dress shoes. These specific orchids are grown nowhere else except on the second-floor conservatory balcony that looks straight into the victim's study window.
                    </p>
                </div>

                <div class="suspect-profile">
                    <div class="suspect-name">Suspect Two // Julian (The Estranged Brother)</div>
                    <p class="narrative-prose">
                        Insists he never left the isolated library wing all night, where he was busy translating rare scripts. He shows no apparent motive, except for a newly signed bank statement hidden in his pocket revealing massive gambling losses due to be paid at dawn.
                    </p>
                </div>

                <div class="suspect-profile">
                    <div class="suspect-name">Suspect Three // Victoria (The Protege)</div>
                    <p class="narrative-prose">
                        Claims she was fast asleep in the opposite guest wing after drinking a heavy dose of sleeping medicine. Strangely, her personal antique pocket watch was found completely broken and stopped at exactly 2:42 AM—the exact minute the master wall clock in the study was smashed during the scuffle.
                    </p>
                </div>
            </div>

            <!-- Typing Interface Core Box -->
            <div class="deduction-vault">
                <h3>Isolate The Contradiction</h3>
                <p class="narrative-prose" style="font-size: 0.95rem; color: var(--text-muted); margin-bottom: 0;">
                    One alibi completely breaks under physical tracking. Type the exact name of the real criminal below to lock in the arrest warrant.
                </p>
                
                <div class="interactive-row">
                    <input type="text" id="target-suspect" class="vault-input" placeholder="Type name here (Sterling, Julian, or Victoria)..." autocomplete="off">
                    <button class="vault-btn" onclick="runAnalysis()">Analyze Target</button>
                </div>
                
                <div id="terminal-output" class="console-logs"></div>
            </div>
        </section>

    </main>

    <script>
        // Tab Shifting Engine
        function switchTab(panelId, eventSource) {
            document.querySelectorAll('.view-panel').forEach(p => p.classList.remove('active-panel'));
            document.querySelectorAll('.nav-link').forEach(b => b.classList.remove('active-tab'));
            
            document.getElementById(panelId).classList.add('active-panel');
            eventSource.classList.add('active-tab');
            
            // Fires movie soundtrack automatically on the first user action
            engageCinematicTrack();
        }

        // Direct Text Input Deduction Logic
        function runAnalysis() {
            engageCinematicTrack(); // Audio safety backup trigger
            const playerGuess = document.getElementById('target-suspect').value.trim().toLowerCase();
            const logBox = document.getElementById('terminal-output');

            if (playerGuess === 'sterling') {
                logBox.className = "console-logs log-match";
                logBox.innerText = "✓ CASE LOGGED: Target neutralized. The orchid petals crushed under his boots proved he climbed up to the study balcony window. Sterling has been detained.";
            } else if (playerGuess === 'victoria' || playerGuess === 'julian') {
                logBox.className = "console-logs log-mismatch";
                logBox.innerText = "✗ ANALYSIS FAILED: Subject alibi remains intact. Check the physical trace elements left on their person again.";
            } else if (playerGuess === "") {
                logBox.className = "console-logs log-mismatch";
                logBox.innerText = "⚠ ERRONEOUS ENTRY: Please specify a suspect's name to execute tracking script.";
            } else {
                logBox.className = "console-logs log-mismatch";
                logBox.innerText = "✗ SUBJECT UNKNOWN: Entry must match an verified suspect present at the manor house (Sterling, Julian, or Victoria).";
            }
        }

        /* 
           INBUILT CINEMATIC SOUNDTRACK ENGINE
           Generates a dramatic, high-tension thriller movie score natively using the Web Audio API.
           Starts completely automatically on the user's very first interaction with the web page.
        */
        let soundContext = null;
        let audioNodesList = [];

        function engageCinematicTrack() {
            if (soundContext) return; // Prevent duplicate engines from spawning

            soundContext = new (window.AudioContext || window.webkitAudioContext)();
            
            // LAYER 1: Deep Cinematic Bass Thudding Heartbeat Pulse
            let bassOsc = soundContext.createOscillator();
            let bassGain = soundContext.createGain();
            bassOsc.type = 'triangle';
            bassOsc.frequency.setValueAtTime(45.88, soundContext.currentTime); // Haunting F# Sub Note
            
            bassGain.gain.setValueAtTime(0.01, soundContext.currentTime);
            
            // Loop creates a rhythmic pulsing heartbeat movie cue effect
            setInterval(() => {
                if(soundContext.state !== 'suspended') {
                    bassGain.gain.linearRampToValueAtTime(0.22, soundContext.currentTime + 0.3);
                    bassGain.gain.linearRampToValueAtTime(0.01, soundContext.currentTime + 1.1);
                }
            }, 1400);

            bassOsc.connect(bassGain);
            bassGain.connect(soundContext.destination);
            bassOsc.start();

            // LAYER 2: Detuned Horror Mystery Drone Harmony
            let tensionOscillator = soundContext.createOscillator();
            let lowPassFilter = soundContext.createBiquadFilter();
            let masterVolumeGain = soundContext.createGain();
            
            tensionOscillator.type = 'sawtooth';
            tensionOscillator.frequency.setValueAtTime(68.82, soundContext.currentTime); // C# Minor framework element
            tensionOscillator.detune.setValueAtTime(18, soundContext.currentTime); // Sharp detuning for chilling tension
            
            lowPassFilter.type = 'lowpass';
            lowPassFilter.frequency.setValueAtTime(160, soundContext.currentTime);
            
            // Automatically modulates the low pass filter over time to create a slow cinematic sweeping effect
            let filterModulatorOsc = soundContext.createOscillator();
            let modulatorGainNode = soundContext.createGain();
            filterModulatorOsc.type = 'sine';
            filterModulatorOsc.frequency.setValueAtTime(0.12, soundContext.currentTime); 
            modulatorGainNode.gain.setValueAtTime(75, soundContext.currentTime);
            
            filterModulatorOsc.connect(modulatorGainNode);
            modulatorGainNode.connect(lowPassFilter.frequency);
            
            masterVolumeGain.gain.setValueAtTime(0.05, soundContext.currentTime);
            
            tensionOscillator.connect(lowPassFilter);
            lowPassFilter.connect(masterVolumeGain);
            masterVolumeGain.connect(soundContext.destination);
            
            tensionOscillator.start();
            filterModulatorOsc.start();

            audioNodesList.push(bassOsc, tensionOscillator, filterModulatorOsc);
        }

        // Global watcher to fire up the movie audio tracks instantly on any initial mouse tap
        document.body.addEventListener('click', () => {
            if (soundContext && soundContext.state === 'suspended') {
                soundContext.resume();
            } else {
                engageCinematicTrack();
            }
        }, { once: true });
    </script>
</body>
</html>
