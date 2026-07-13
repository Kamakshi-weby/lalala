
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>THE CRIMSON 404 // CASE FILE</title>
    <!-- Google Fonts for Ultra-Aesthetic Noir Typography -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Special+Elite&family=Syne:wght@400;700;800&family=Courier+Prime:ital,wght@0,400;0,700;1,400&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --bg-dark: #0a0a0c;
            --neon-red: #ff2a2a;
            --neon-glow: rgba(255, 42, 42, 0.6);
            --paper-white: #e2daf0;
            --muted-gray: #64646e;
            --panel-bg: rgba(14, 14, 18, 0.85);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--bg-dark);
            color: var(--paper-white);
            font-family: 'Courier Prime', monospace;
            overflow-x: hidden;
            line-height: 1.8;
        }

        /* Ambient Rain/Crackle Layer */
        .ambient-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: radial-gradient(circle at 50% 50%, transparent 20%, rgba(0,0,0,0.8) 100%);
            pointer-events: none;
            z-index: 10;
        }

        /* Custom Audio Control Hub */
        .audio-hub {
            position: fixed;
            top: 30px;
            right: 40px;
            z-index: 100;
            display: flex;
            align-items: center;
            gap: 12px;
            background: rgba(0, 0, 0, 0.6);
            padding: 10px 20px;
            border: 1px solid var(--neon-red);
            border-radius: 4px;
            box-shadow: 0 0 15px var(--neon-glow);
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .audio-hub:hover {
            background: var(--neon-red);
            color: var(--bg-dark);
        }

        .audio-pulse {
            width: 8px;
            height: 8px;
            background-color: var(--neon-red);
            border-radius: 50%;
            animation: pulse 1.5s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(0.8); opacity: 0.5; }
            50% { transform: scale(1.3); opacity: 1; box-shadow: 0 0 10px var(--neon-red); }
            100% { transform: scale(0.8); opacity: 0.5; }
        }

        /* Navigation / Page Architecture */
        .page {
            min-height: 100vh;
            width: 100vw;
            padding: 80px 10%;
            display: none;
            position: absolute;
            top: 0;
            left: 0;
        }

        .page.active {
            display: block;
            animation: fadeIn 1.2s ease-in-out forwards;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* PAGE 1: DOCKET & INTRO */
        .hero-layout {
            display: grid;
            grid-template-columns: 1.2fr 1fr;
            gap: 60px;
            align-items: center;
            margin-top: 40px;
        }

        .case-title {
            font-family: 'Syne', sans-serif;
            font-weight: 800;
            font-size: 4.5rem;
            line-height: 1.1;
            text-transform: uppercase;
            letter-spacing: -2px;
            color: #fff;
            margin-bottom: 20px;
        }

        .crimson-text {
            color: var(--neon-red);
            text-shadow: 0 0 20px var(--neon-glow);
            font-family: 'Special Elite', cursive;
        }

        .detective-image-container {
            position: relative;
            border: 1px solid rgba(255,255,255,0.1);
            padding: 15px;
            background: #111;
            box-shadow: 0 25px 50px rgba(0,0,0,0.6);
        }

        .detective-image {
            width: 100%;
            height: auto;
            filter: grayscale(20%) contrast(110%);
            display: block;
        }

        .stamp-overlay {
            position: absolute;
            bottom: -20px;
            right: -20px;
            background: transparent;
            border: 3px double var(--neon-red);
            color: var(--neon-red);
            font-family: 'Special Elite', cursive;
            padding: 5px 15px;
            font-size: 1.2rem;
            transform: rotate(-8deg);
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .profile-docket {
            background: var(--panel-bg);
            border-left: 3px solid var(--neon-red);
            padding: 40px;
            margin-top: 40px;
        }

        .docket-header {
            font-family: 'Special Elite', cursive;
            font-size: 1.4rem;
            color: var(--neon-red);
            margin-bottom: 20px;
            letter-spacing: 1px;
        }

        .docket-row {
            display: flex;
            margin-bottom: 12px;
            border-bottom: 1px dashed rgba(255,255,255,0.05);
            padding-bottom: 6px;
        }

        .docket-label {
            width: 140px;
            color: var(--muted-gray);
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* PAGE 2: THE CASE FILE STORY */
        .story-container {
            max-width: 900px;
            margin: 0 auto;
            padding: 40px 0;
        }

        .story-header {
            text-align: center;
            margin-bottom: 80px;
        }

        .story-header h2 {
            font-family: 'Syne', sans-serif;
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 10px;
        }

        .story-body {
            font-size: 1.15rem;
            text-align: justify;
            color: #d1ced6;
        }

        .story-paragraph {
            margin-bottom: 35px;
            text-indent: 40px;
        }

        /* Interactive Guessing Terminal */
        .deduction-box {
            background: #0f0f13;
            border: 1px solid rgba(255, 255, 255, 0.1);
            padding: 50px;
            margin-top: 80px;
            text-align: center;
            position: relative;
        }

        .deduction-box::before {
            content: 'CRIMINAL IDENTIFICATION TERMINAL';
            position: absolute;
            top: -12px;
            left: 30px;
            background: var(--bg-dark);
            padding: 0 10px;
            font-size: 0.75rem;
            color: var(--neon-red);
            letter-spacing: 2px;
        }

        .suspect-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            margin: 40px 0;
        }

        .suspect-card {
            border: 1px solid var(--muted-gray);
            padding: 25px;
            background: rgba(255,255,255,0.02);
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .suspect-card:hover {
            border-color: var(--neon-red);
            box-shadow: 0 0 15px rgba(255, 42, 42, 0.2);
            transform: translateY(-4px);
        }

        .suspect-card.selected {
            border-color: var(--neon-red);
            background: rgba(255, 42, 42, 0.1);
            box-shadow: 0 0 25px var(--neon-glow);
        }

        .suspect-name {
            font-family: 'Special Elite', cursive;
            font-size: 1.2rem;
            margin-bottom: 8px;
        }

        .suspect-role {
            font-size: 0.8rem;
            color: var(--muted-gray);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* Buttons & Interactions */
        .btn {
            background: transparent;
            border: 1px solid var(--paper-white);
            color: var(--paper-white);
            padding: 15px 35px;
            font-family: 'Courier Prime', monospace;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 20px;
        }

        .btn:hover {
            background: var(--paper-white);
            color: var(--bg-dark);
            box-shadow: 0 0 20px rgba(255,255,255,0.3);
        }

        .btn-primary {
            border-color: var(--neon-red);
            color: var(--neon-red);
        }

        .btn-primary:hover {
            background: var(--neon-red);
            color: #fff;
            box-shadow: 0 0 25px var(--neon-glow);
        }

        /* Result Display Overlay */
        #result-display {
            margin-top: 30px;
            font-family: 'Special Elite', cursive;
            font-size: 1.3rem;
            min-height: 40px;
        }

        .typewriter-cursor::after {
            content: '█';
            animation: blink 0.8s infinite;
        }

        @keyframes blink {
            50% { opacity: 0; }
        }
    </style>
</head>
<body>

    <div class="ambient-overlay"></div>

    <!-- Background Sound Controller -->
    <div class="audio-hub" onclick="toggleAudio()">
        <div class="audio-pulse" id="pulse-indicator"></div>
        <span id="audio-text" style="font-size: 0.75rem; letter-spacing: 1px;">AMBience: OFF</span>
    </div>

    <!-- Web Audio API Synthesizer (Generates scary horror drone live without needing external MP3 asset links!) -->
    <script>
        let audioCtx;
        let oscillator, lowOsc, filter, gainNode;
        let isPlaying = false;

        function initAudio() {
            audioCtx = new (window.AudioContext || window.webkitAudioContext)();
            
            // Primary tense cinematic drone pitch
            oscillator = audioCtx.createOscillator();
            oscillator.type = 'sawtooth';
            oscillator.frequency.setValueAtTime(55, audioCtx.currentTime); // Low A

            // Detuned secondary layer for a discordant horror dynamic
            lowOsc = audioCtx.createOscillator();
            lowOsc.type = 'triangle';
            lowOsc.frequency.setValueAtTime(55.8, audioCtx.currentTime); // LFO style clash

            // Deep horror movie low pass filter cutoff
            filter = audioCtx.createBiquadFilter();
            filter.type = 'lowpass';
            filter.frequency.setValueAtTime(180, audioCtx.currentTime);
            filter.Q.setValueAtTime(8, audioCtx.currentTime);

            gainNode = audioCtx.createGain();
            gainNode.gain.setValueAtTime(0.15, audioCtx.currentTime); // Smooth low background setting

            // Connections
            oscillator.connect(filter);
            lowOsc.connect(filter);
            filter.connect(gainNode);
            gainNode.connect(audioCtx.destination);

            oscillator.start();
            lowOsc.start();
        }

        function toggleAudio() {
            if (!audioCtx) initAudio();
            
            if (!isPlaying) {
                audioCtx.resume();
                gainNode.gain.setTargetAtTime(0.18, audioCtx.currentTime, 0.5);
                document.getElementById('audio-text').innerText = 'AMBIENCE: LURKING';
                document.getElementById('pulse-indicator').style.animationPlayState = 'running';
                isPlaying = true;
            } else {
                gainNode.gain.setTargetAtTime(0, audioCtx.currentTime, 0.3);
                document.getElementById('audio-text').innerText = 'AMBIENCE: MUTED';
                document.getElementById('pulse-indicator').style.animationPlayState = 'paused';
                isPlaying = false;
            }
        }
    </script>


    <!-- ================= PAGE 1: DETECTIVE PROFILE & MISSION INTRO ================= -->
    <section id="page-1" class="page active">
        <div class="hero-layout">
            
            <div>
                <p style="text-transform: uppercase; letter-spacing: 4px; color: var(--muted-gray); font-size: 0.8rem; margin-bottom: 10px;">// CRIME FILES DEPARTMENT</p>
                <h1 class="case-title">THE CASE OF <br><span class="crimson-text">CRIMSON MANOR 404</span></h1>
                
                <p style="font-size: 1.1rem; margin-bottom: 30px; color: #a5a2b0;">
                    The neon sign flickered through the heavy downpour outside my window. Arkham Occult Bookshop was dark, but Room 404 across the street remained brilliantly illuminated. Lord Harrison was dead, cold for three hours, and the killer left nothing behind but an unanswered riddle on a typewriter.
                </p>

                <button class="btn btn-primary" onclick="switchPage('page-2')">Open Full Case File →</button>

                <div class="profile-docket">
                    <div class="docket-header">DETECTIVE ON SCENE PROFILE</div>
                    <div class="docket-row">
                        <span class="docket-label">OPERATIVE:</span>
                        <span>As Assigned / The Mind in the Shadows</span>
                    </div>
                    <div class="docket-row">
                        <span class="docket-label">JURISDICTION:</span>
                        <span>Arkham District, Sector 404</span>
                    </div>
                    <div class="docket-row">
                        <span class="docket-label">METHODOLOGY:</span>
                        <span>Abductive Logic, Dark Psychometrics, Midnight Inspection</span>
                    </div>
                </div>
            </div>

            <div class="detective-image-container">
                <!-- Expects 'detective.jpg' locally in your repo -->
                <img src="detective.jpg" alt="Detective investigating neon Crimson Manor file" class="detective-image">
                <div class="stamp-overlay">CASE RE-OPENED</div>
            </div>

        </div>
    </section>


    <!-- ================= PAGE 2: THE DETECTIVE STORY & INTERACTIVE INTERROGATION ================= -->
    <section id="page-2" class="page">
        <div class="story-container">
            
            <div class="story-header">
                <p style="color: var(--neon-red); font-family: 'Special Elite', cursive; letter-spacing: 2px;">CONFIDENTIAL DOCUMENT // DO NOT DISTRIBUTE</p>
                <h2>THE CHRONICLE OF THE LATE LORD HARRISON</h2>
                <button class="btn" style="padding: 6px 15px; font-size: 0.75rem;" onclick="switchPage('page-1')">← Return to Main Desk</button>
            </div>

            <div class="story-body">
                <p class="story-paragraph">
                    The grandfather clock struck midnight when I breached the heavy oak doors of Crimson Manor. The air inside smelled of expensive scotch, rain-dampened coats, and the undeniable copper tang of freshly spilled blood. Lord Harrison sat upright at his walnut desk, staring forward with blank eyes. In front of him sat a glass of rare whiskey, an unlit cigar glowing faintly from an ember tray, and a mechanical typewriter with a single line stamped across the parchment: <em style="color: var(--neon-red);">"The clock strikes four, the error is made, the currency of blood is paid."</em>
                </p>

                <p class="story-paragraph">
                    Three individuals were discovered within the manor grounds immediately after the alarm was raised, each possessing an undeniable reason to see the old billionaire silenced. My task was simple yet agonizing: sit under the flicker of the red neon light, dissect their narratives, and point out the mastermind behind the 404 conspiracy before dawn.
                </p>

                <p class="story-paragraph">
                    First was <strong>Julian Blackwood</strong>, the disgruntled antique dealer who ran the Arkham Occult Bookshop downstairs. He claimed he was updating his shop ledgers until midnight. Yet, when I checked his desk across the street, his inkwell was entirely dry, and his boots carried traces of fresh mud matching the rare soil from Crimson Manor's private conservatory garden.
                </p>

                <p class="story-paragraph">
                    Next stood <strong>Lady Eleanor</strong>, the estranged niece facing total disinheritance in Harrison's updated will. She swore on her honor she stayed locked away inside her room reading classics. However, a broken string from her pearl necklace lay caught inside the mechanism of the antique grandfather clock—a clock that had been abruptly jammed to stop exactly at 11:15 PM.
                </p>

                <p class="story-paragraph">
                    Finally, there was <strong>Dr. Alistair Vance</strong>, the personal physician who regularly administered Harrison's daily heart treatments. Vance was calm, claiming he had left the mansion long before the storm peaked. But on the victim's desk stood that half-finished glass of whiskey; my analysis kit confirmed traces of an advanced alkaloid toxin—a chemical only available within Vance's restricted private cabinet.
                </p>
            </div>

            <!-- Interrogation Guessing Game Box -->
            <div class="deduction-box">
                <h3>THE FINAL VERDICT IS YOURS</h3>
                <p style="color: var(--muted-gray); font-size: 0.9rem; margin-top: 5px;">Review the evidence carefully. Who rigged Crimson Manor 404?</p>
                
                <div class="suspect-grid">
                    <div class="suspect-card" onclick="selectSuspect(this, 'Julian Blackwood')">
                        <div class="suspect-name">Julian Blackwood</div>
                        <div class="suspect-role">The Bookkeeper</div>
                    </div>
                    <div class="suspect-card" onclick="selectSuspect(this, 'Lady Eleanor')">
                        <div class="suspect-name">Lady Eleanor</div>
                        <div class="suspect-role">The Disinherited Heir</div>
                    </div>
                    <div class="suspect-card" onclick="selectSuspect(this, 'Dr. Alistair Vance')">
                        <div class="suspect-name">Dr. Alistair Vance</div>
                        <div class="suspect-role">The Trusted Physician</div>
                    </div>
                </div>

                <button class="btn btn-primary" onclick="submitDeduction()">Lock in Guess</button>
                <div id="result-display"></div>
            </div>

        </div>
    </section>

    <!-- Page Transition Logic -->
    <script>
        let chosenSuspect = "";

        function switchPage(pageId) {
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById(pageId).classList.add('active');
            window.scrollTo(0,0);
        }

        function selectSuspect(element, name) {
            document.querySelectorAll('.suspect-card').forEach(card => {
                card.classList.remove('selected');
            });
            element.classList.add('selected');
            chosenSuspect = name;
        }

        function submitDeduction() {
            const display = document.getElementById('result-display');
            display.className = "typewriter-cursor";
            display.innerHTML = "";
            
            if (!chosenSuspect) {
                display.innerHTML = "SYSTEM ERROR: Select a suspect from the case file grid.";
                return;
            }

            let responseText = "";
            if (chosenSuspect === "Dr. Alistair Vance") {
                responseText = "CASE SOLVED. Vance used his medical access to clear Harrison's heart while framing the scene. You saw through the shadow metrics.";
            } else if (chosenSuspect === "Julian Blackwood") {
                responseText = "INSUFFICIENT PROOF. Blackwood was stealing rare books from the study, but he didn't orchestrate the fatal glass. The real killer escapes.";
            } else {
                responseText = "MISDIRECTION. Lady Eleanor broke her pearls attempting to alter the timeline of death, but she wasn't the source of the lethal dosage. Look closer.";
            }

            // Simple typewriter reveal animation
            let i = 0;
            function typeWriter() {
                if (i < responseText.length) {
                    display.innerHTML += responseText.charAt(i);
                    i++;
                    setTimeout(typeWriter, 40);
                } else {
                    display.className = ""; // Remove blinking cursor when done
                }
            }
            typeWriter();
        }
    </script>
</body>
</html>
