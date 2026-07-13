<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>THE CRIMSON 404 DATASTREAM</title>
    <!-- Avant-garde / High-End Design Typography -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Syne:wght@700;800&family=Unbounded:wght@400;700&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --bg-deep: #050508;
            --neon-pink: #ff0055;
            --cyber-cyan: #00f3ff;
            --pure-white: #ffffff;
            --muted-slate: #4a4a5a;
            --text-glow: 0 0 20px rgba(255, 0, 85, 0.6);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--bg-deep);
            color: var(--pure-white);
            font-family: 'Share Tech Mono', monospace;
            overflow-x: hidden;
            line-height: 1.7;
        }

        /* Ambient scanlines over the screen for a raw cinematic look */
        body::before {
            content: " ";
            display: block;
            position: fixed;
            top: 0; left: 0; bottom: 0; right: 0;
            background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.25) 50%), linear-gradient(90deg, rgba(255, 0, 0, 0.06), rgba(0, 255, 0, 0.02), rgba(0, 0, 255, 0.06));
            z-index: 9999;
            background-size: 100% 3px, 6px 100%;
            pointer-events: none;
        }

        /* Immersive Audio Centerpiece Control */
        .audio-trigger {
            position: fixed;
            top: 30px;
            right: 40px;
            z-index: 5000;
            background: rgba(0, 0, 0, 0.9);
            border: 2px solid var(--cyber-cyan);
            padding: 12px 24px;
            color: var(--cyber-cyan);
            font-family: 'Unbounded', sans-serif;
            font-size: 0.75rem;
            letter-spacing: 2px;
            cursor: pointer;
            box-shadow: 0 0 15px rgba(0, 243, 255, 0.3);
            transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .audio-trigger:hover {
            background: var(--cyber-cyan);
            color: var(--bg-deep);
            box-shadow: 0 0 25px var(--cyber-cyan);
            transform: scale(1.05);
        }

        /* Navigation Architecture (2 Pages via display toggling) */
        .viewport {
            min-height: 100vh;
            width: 100vw;
            display: none;
            padding: 100px 8%;
        }

        .viewport.active {
            display: block;
            animation: viewReveal 0.8s cubic-bezier(0.16, 1, 0.3, 1) forwards;
        }

        @keyframes viewReveal {
            from { opacity: 0; transform: scale(0.98); filter: blur(10px); }
            to { opacity: 1; transform: scale(1); filter: blur(0); }
        }

        /* --- PAGE 1: THE DOSSIER INTRO --- */
        .hero-grid {
            display: grid;
            grid-template-columns: 1.1fr 0.9fr;
            gap: 80px;
            align-items: center;
            min-height: 80vh;
        }

        .massive-header {
            font-family: 'Syne', sans-serif;
            font-weight: 800;
            font-size: 5.5rem;
            line-height: 0.95;
            text-transform: uppercase;
            letter-spacing: -3px;
            margin-bottom: 30px;
        }

        .highlight-accent {
            color: var(--neon-pink);
            text-shadow: var(--text-glow);
        }

        .intro-blurb {
            font-size: 1.25rem;
            color: #b0b0cc;
            margin-bottom: 40px;
            max-width: 600px;
        }

        .case-image-holder {
            position: relative;
            border: 4px solid var(--pure-white);
            box-shadow: 0 30px 60px rgba(0,0,0,0.8);
            overflow: hidden;
        }

        .case-image-holder img {
            width: 100%;
            height: auto;
            display: block;
            filter: contrast(115%) brightness(90%);
            transition: transform 0.5s ease;
        }

        .case-image-holder:hover img {
            transform: scale(1.03);
        }

        /* --- PAGE 2: THE UNCONVENTIONAL STORY --- */
        .story-wrapper {
            max-width: 1100px;
            margin: 0 auto;
        }

        .story-meta {
            font-family: 'Unbounded', sans-serif;
            font-size: 0.8rem;
            color: var(--cyber-cyan);
            margin-bottom: 40px;
            letter-spacing: 3px;
            text-transform: uppercase;
        }

        .narrative-columns {
            font-size: 1.25rem;
            color: #e2e2ee;
            text-align: left;
            margin-bottom: 80px;
        }

        .narrative-columns p {
            margin-bottom: 35px;
            position: relative;
            padding-left: 20px;
            border-left: 2px solid var(--muted-slate);
        }

        .narrative-columns strong {
            color: var(--cyber-cyan);
            font-family: 'Unbounded', sans-serif;
            font-size: 1.05rem;
        }

        /* --- IMMERSIVE INTERACTIVE TEXT INPUT DEDUCTION --- */
        .input-terminal-zone {
            background: rgba(10, 10, 15, 0.6);
            border: 2px solid var(--muted-slate);
            padding: 60px;
            position: relative;
            margin-top: 100px;
        }

        .input-terminal-zone::before {
            content: "SECURE INTEL RECOGNITION";
            position: absolute;
            top: -14px;
            left: 40px;
            background: var(--bg-deep);
            padding: 0 15px;
            font-family: 'Unbounded', sans-serif;
            font-size: 0.75rem;
            color: var(--neon-pink);
            letter-spacing: 2px;
        }

        .terminal-prompt-text {
            font-size: 1.5rem;
            margin-bottom: 30px;
            font-family: 'Syne', sans-serif;
        }

        .custom-typing-input {
            width: 100%;
            background: transparent;
            border: none;
            border-bottom: 3px solid var(--pure-white);
            color: var(--cyber-cyan);
            font-family: 'Unbounded', sans-serif;
            font-size: 2rem;
            padding: 15px 0;
            outline: none;
            text-transform: uppercase;
            letter-spacing: 2px;
            transition: border-color 0.3s ease;
        }

        .custom-typing-input:focus {
            border-color: var(--neon-pink);
        }

        .action-button {
            background: transparent;
            border: 2px solid var(--pure-white);
            color: var(--pure-white);
            font-family: 'Unbounded', sans-serif;
            font-size: 0.9rem;
            padding: 18px 45px;
            cursor: pointer;
            margin-top: 40px;
            letter-spacing: 2px;
            text-transform: uppercase;
            transition: all 0.3s;
        }

        .action-button:hover {
            background: var(--pure-white);
            color: var(--bg-deep);
            box-shadow: 0 0 30px rgba(255,255,255,0.4);
        }

        .output-response-matrix {
            margin-top: 40px;
            font-size: 1.3rem;
            color: var(--neon-pink);
            min-height: 60px;
            font-family: 'Share Tech Mono', monospace;
            letter-spacing: 1px;
        }

        .cursor-blink::after {
            content: '█';
            animation: blockBlink 0.8s steps(2) infinite;
        }

        @keyframes blockBlink { 50% { opacity: 0; } }

        @media (max-width: 1024px) {
            .hero-grid { grid-template-columns: 1fr; gap: 40px; }
            .massive-header { font-size: 3.5rem; }
        }
    </style>
</head>
<body>

    <!-- INTERACTIVE BACKGROUND SCARY SOUND ENGINE -->
    <div class="audio-trigger" onclick="handleSoundEngine()">
        SOUND SCENE: <span id="engine-status">OFF</span>
    </div>

    <!-- Web Audio API Custom Horror Synth Generator -->
    <script>
        let audioContext;
        let mainDroneOsc, horrorLfoOsc, structuralGain, dynamicFilter;
        let musicActive = false;

        function initializeHorrorSoundtrack() {
            audioContext = new (window.AudioContext || window.webkitAudioContext)();
            
            // Raw low-frequency drone oscillator
            mainDroneOsc = audioContext.createOscillator();
            mainDroneOsc.type = 'sawtooth';
            mainDroneOsc.frequency.setValueAtTime(48.99, audioContext.currentTime); // Low G key for tension

            // Secondary oscillator creating acoustic clash beats
            horrorLfoOsc = audioContext.createOscillator();
            horrorLfoOsc.type = 'triangle';
            horrorLfoOsc.frequency.setValueAtTime(49.42, audioContext.currentTime); 

            dynamicFilter = audioContext.createBiquadFilter();
            dynamicFilter.type = 'lowpass';
            dynamicFilter.frequency.setValueAtTime(130, audioContext.currentTime);
            dynamicFilter.Q.setValueAtTime(9, audioCtx = audioContext.currentTime);

            structuralGain = audioContext.createGain();
            structuralGain.gain.setValueAtTime(0, audioContext.currentTime); // Initialize silent

            // Routing audio flow graph
            mainDroneOsc.connect(dynamicFilter);
            horrorLfoOsc.connect(dynamicFilter);
            dynamicFilter.connect(structuralGain);
            structuralGain.connect(audioContext.destination);

            mainDroneOsc.start();
            horrorLfoOsc.start();
        }

        function handleSoundEngine() {
            if (!audioContext) initializeHorrorSoundtrack();
            const label = document.getElementById('engine-status');

            if (!musicActive) {
                audioContext.resume();
                structuralGain.gain.setTargetAtTime(0.25, audioContext.currentTime, 0.4);
                label.innerText = "ON (DISSONANT DRONE)";
                label.style.color = "var(--neon-pink)";
                musicActive = true;
            } else {
                structuralGain.gain.setTargetAtTime(0, audioContext.currentTime, 0.2);
                label.innerText = "OFF";
                label.style.color = "var(--cyber-cyan)";
                musicActive = false;
            }
        }
    </script>


    <!-- ================= VIEWPORT PAGE 1: DOSSIER CORE ================= -->
    <section id="view-1" class="viewport active">
        <div class="hero-grid">
            <div>
                <h1 class="massive-header">THE CORRUPTION OF <span class="highlight-accent">ROOM 404</span></h1>
                <p class="intro-blurb">
                    The database has broken down. Lord Harrison was murdered inside a locked room, completely visible from the street layout below. You are looking directly through the terminal grid of the detective sent to recover the files.
                </p>
                <button class="action-button" onclick="changeViewport('view-2')">Deconstruct Evidence File</button>
            </div>
            
            <div class="case-image-holder">
                <!-- Direct GitHub image source integration -->
                <img src="https://github.com/Kamakshi-weby/lalala/blob/main/622d03f0-8c85-4901-91e1-22853a46c77d.jpg?raw=true" alt="Crimson Manor 404 Case Scenario File">
            </div>
        </div>
    </section>


    <!-- ================= VIEWPORT PAGE 2: INTERROGATION CHRONICLES ================= -->
    <section id="view-2" class="viewport">
        <div class="story-wrapper">
            <div class="story-meta">
                <span>FILE PATH: CASE_LOGS // CRIMSON_MANOR_404</span>
                <button class="action-button" style="padding: 6px 16px; margin: 0 0 0 30px; font-size: 0.65rem; vertical-align: middle;" onclick="changeViewport('view-1')">← BACK TO DESK</button>
            </div>

            <div class="narrative-columns">
                <p>
                    <strong>THE TIMELINE BREAK:</strong> The grandfather clock in the study was smashed down at precisely 11:15 PM, freezing the mechanical gear lines in place. Lord Harrison sat perfectly upright in his plush leather chair, staring across the wet pavement toward the cold storefronts. On his desk sat a partially drained crystal tumbler of rare vintage whiskey, a slow-burning cigar on an ash tray, and an old iron typewriter displaying a singular line: <em>"The error code manifests at midnight."</em>
                </p>

                <p>
                    <strong>SUSPECT ONE (JULIAN BLACKWOOD):</strong> The antique merchant running the local bookshop directly across the street layout. Blackwood asserted he was cataloging inventory text books all night long, but a physical sweeping of his private desk revealed his primary inkwells were dry. Furthermore, trace remnants of dark conservatory clay were found stuck to the heels of his leather oxfords.
                </p>

                <p>
                    <strong>SUSPECT TWO (LADY ELEANOR):</strong> Harrison’s sole surviving biological family member. Facing complete removal from the estate distribution ledger, she claimed she stayed sequestered in her room with literary classics. Yet, a physical verification of the locked grandfather clock room revealed a single snapped strand of expensive genuine pearl thread caught inside the primary brass escapement gear.
                </p>

                <p>
                    <strong>SUSPECT THREE (DR. ALISTAIR VANCE):</strong> The attending family clinical physician. He documented his departure from the manor layout hours before the lightning storm peak. However, a forensic chemical verification of the whiskey remnants on the desk showed heavy saturation of a complex nerve blocking agent—a restricted molecule manufactured exclusively for Vance’s diagnostic kit.
                </p>
            </div>

            <!-- KEYBOARD TYPING USER DEDUCTION TERMINAL -->
            <div class="input-terminal-zone">
                <h3 class="terminal-prompt-text">TYPE THE NAME OF THE CULPRIT TO EXECUTE VERDICT INTERCEPT:</h3>
                
                <input type="text" id="suspect-input" class="custom-typing-input" placeholder="Type name here..." autocomplete="off">
                
                <button class="action-button" style="border-color: var(--cyber-cyan); color: var(--cyber-cyan);" onclick="verifyCulpritData()">COMPUTE TARGET INTEL</button>
                
                <div class="output-response-matrix" id="terminal-output-panel"></div>
            </div>
        </div>
    </section>


    <!-- VIEW CONTROL & INTERACTIVE STRING TYPING ENGINE -->
    <script>
        function changeViewport(targetId) {
            document.querySelectorAll('.viewport').forEach(view => view.classList.remove('active'));
            document.getElementById(targetId).classList.add('active');
            window.scrollTo(0,0);
        }

        function verifyCulpritData() {
            const userInput = document.getElementById('suspect-input').value.trim().toLowerCase();
            const outputPanel = document.getElementById('terminal-output-panel');
            
            outputPanel.innerHTML = "";
            outputPanel.classList.add('cursor-blink');

            let resolutionString = "";

            if (userInput.includes("vance") || userInput.includes("alistair")) {
                resolutionString = ">> ACCESS GRANTED. CRIMINAL SEQUENCE CONFIRMED: Dr. Alistair Vance exploited his medical clearance to lace the crystal whiskey tumbler, executing the kill while attempting to utilize Eleanor's inheritance feud as structural misdirection. Datastream cleared.";
            } else if (userInput.includes("blackwood") || userInput.includes("julian")) {
                resolutionString = ">> ANALYSIS FLAGGED: Julian Blackwood was inside the mansion boundary layout stealing historical ledgers, but he lacked the chemical means to poison the target's glass. Re-examine the medical data vectors.";
            } else if (userInput.includes("eleanor") || userInput.includes("lady")) {
                resolutionString = ">> CORRUPTION DETECTED: Lady Eleanor did intentionally damage and jam the grandfather clock mechanism to shift the estimated window of death, but she did not prepare the toxin. Target escaped.";
            } else if (userInput === "") {
                resolutionString = ">> EXCEPTION: Input field empty. Type the name of your calculated suspect into the terminal to parse judgment data.";
            } else {
                resolutionString = ">> UNKNOWN IDENTITY EXCEPTION: The name typed does not match any authenticated profile inside the Crimson 404 security grid. Try analyzing the data file profiles again.";
            }

            // Typewriter aesthetic response generator
            let counter = 0;
            function printStream() {
                if (counter < resolutionString.length) {
                    outputPanel.innerHTML += resolutionString.charAt(counter);
                    counter++;
                    setTimeout(printStream, 25);
                } else {
                    outputPanel.classList.remove('cursor-blink');
                }
            }
            printStream();
        }
    </script>

</body>
</html>
