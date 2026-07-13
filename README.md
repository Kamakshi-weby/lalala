
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>THE CRIMSON 404: GLITCH IN THE VOID // OFFICIAL CASE TERMINAL</title>
    <!-- Modern Gothic & Monospace Typography -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Crimson+Pro:ital,wght@0,300;0,600;1,300&family=Share+Tech+Mono&family=Syne:wght@400;700;800&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --bg-void: #000000;
            --terminal-green: #00ff00;
            --neon-pink: #ff1aff;
            --glitch-cyan: #00ffff;
            --blood-red: #8b0000;
            --text-main: #f0f0f0;
            --text-muted: #666;
            --glow-green: 0 0 10px rgba(0, 255, 0, 0.7);
            --glow-pink: 0 0 20px rgba(255, 26, 255, 0.6);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            scrollbar-width: thin;
            scrollbar-color: var(--neon-pink) var(--bg-void);
        }

        body {
            background-color: var(--bg-void);
            color: var(--text-main);
            font-family: 'Share Tech Mono', monospace;
            overflow-x: hidden;
            line-height: 1.6;
            cursor: crosshair;
        }

        /* --- THE CRAZY STATIC & SCANLINE OVERLAYS --- */
        .scanlines {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: linear-gradient(
                to bottom,
                rgba(255, 255, 255, 0) 50%,
                rgba(0, 0, 0, 0.2) 50%
            );
            background-size: 100% 4px;
            z-index: 1000;
            pointer-events: none;
            opacity: 0.15;
        }

        .ambient-noise {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUh4振动声音数据'); /* Encoded static data */
            opacity: 0.05;
            z-index: 999;
            pointer-events: none;
            animation: noise 0.2s steps(4) infinite;
        }

        @keyframes noise {
            0% { transform: translate(0,0) }
            25% { transform: translate(1%,1%) }
            50% { transform: translate(-1%,-1%) }
            75% { transform: translate(1%,-1%) }
            100% { transform: translate(-1%,1%) }
        }

        /* --- THE VISUAL BACKGROUND (Your generated image) --- */
        .main-background {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background: url('image_28b49d.jpg') no-repeat center center/cover;
            filter: grayscale(100%) contrast(150%) brightness(50%);
            mix-blend-mode: color-burn; /* Vibe shift: Dark and gritty */
            opacity: 0.3;
            z-index: -1;
            transform: scale(1.1); /* Prevents edge bleed during animation */
            animation: kenBurns 60s ease-in-out infinite;
        }

        @keyframes kenBurns {
            0% { transform: scale(1.1) translate(0, 0) }
            50% { transform: scale(1.05) translate(-1%, 1%) }
            100% { transform: scale(1.1) translate(0, 0) }
        }

        /* --- SOUND & UI CONTROLS --- */
        .ui-hub {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 2000;
            background: rgba(0, 0, 0, 0.8);
            border: 1px solid var(--terminal-green);
            padding: 10px 20px;
            box-shadow: var(--glow-green);
            color: var(--terminal-green);
            cursor: pointer;
            transition: all 0.3s;
        }

        .ui-hub:hover {
            box-shadow: 0 0 30px var(--neon-pink);
            border-color: var(--neon-pink);
            color: var(--neon-pink);
        }

        /* --- GENERAL PAGE STRUCTURE --- */
        .page {
            min-height: 100vh;
            display: none;
            position: relative;
            z-index: 100;
        }

        .page.active {
            display: block;
            animation: terminalDecode 1s steps(20) forwards;
        }

        @keyframes terminalDecode {
            from { opacity: 0; transform: translateY(10px) }
            to { opacity: 1; transform: translateY(0) }
        }

        /* --- PAGE 1: DECODING/INTRO --- */
        .hero-section {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            padding: 0 10%;
        }

        .decode-container {
            text-align: center;
            max-width: 800px;
        }

        .status-header {
            color: var(--terminal-green);
            font-size: 1rem;
            margin-bottom: 30px;
            text-transform: uppercase;
            letter-spacing: 5px;
            text-shadow: var(--glow-green);
        }

        .title-crimson {
            font-family: 'Syne', sans-serif;
            font-weight: 800;
            font-size: 5rem;
            text-transform: uppercase;
            letter-spacing: -2px;
            color: transparent;
            -webkit-text-stroke: 1px var(--neon-pink);
            margin-bottom: 20px;
            position: relative;
            animation: titlePulse 4s ease-in-out infinite;
        }

        .title-crimson::after {
            content: "CRIMSON 404";
            position: absolute;
            top: 0;
            left: 0;
            color: #fff;
            text-shadow: var(--glow-pink);
            clip-path: inset(0 100% 0 0); /* Used for reveal effect */
        }

        @keyframes titlePulse {
            0%, 100% { filter: brightness(1) }
            50% { filter: brightness(1.3) }
        }

        .story-intro-text {
            color: var(--text-muted);
            font-size: 1.1rem;
            margin-bottom: 50px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        /* --- PAGE 2: MAIN CASE FILE --- */
        .file-section {
            padding: 80px 15% 150px 15%;
            max-width: 1600px;
            margin: 0 auto;
        }

        .file-header {
            border-bottom: 1px solid rgba(255, 26, 255, 0.2);
            padding-bottom: 40px;
            margin-bottom: 80px;
            text-align: right;
        }

        .classification {
            font-size: 1.2rem;
            color: var(--blood-red);
            font-family: 'Crimson Pro', serif;
            font-style: italic;
            letter-spacing: 2px;
        }

        .story-content {
            font-family: 'Crimson Pro', serif;
            font-size: 1.6rem;
            font-weight: 300;
            letter-spacing: 0.05rem;
            text-align: justify;
            columns: 2;
            column-gap: 80px;
        }

        .story-content strong {
            color: #fff;
            font-weight: 600;
        }

        .story-content a {
            color: var(--neon-pink);
            text-decoration: none;
            border-bottom: 1px dashed var(--neon-pink);
        }

        .story-content p {
            margin-bottom: 2rem;
            text-indent: 2rem;
        }

        /* --- DEDUCTION / ENDING TERMINAL --- */
        .deduction-terminal {
            margin-top: 150px;
            padding: 50px;
            background: #050505;
            border: 1px solid var(--terminal-green);
            box-shadow: 0 0 50px rgba(0, 255, 0, 0.1);
            max-width: 900px;
            margin-left: auto;
            margin-right: auto;
            text-align: center;
        }

        .term-title {
            color: var(--terminal-green);
            font-size: 1.4rem;
            letter-spacing: 3px;
            text-transform: uppercase;
            margin-bottom: 40px;
        }

        .suspect-selection {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            margin-bottom: 50px;
        }

        .suspect-btn {
            background: transparent;
            border: 1px solid var(--text-muted);
            color: var(--text-muted);
            padding: 20px;
            text-transform: uppercase;
            font-family: 'Share Tech Mono', monospace;
            cursor: pointer;
            transition: all 0.2s;
        }

        .suspect-btn:hover {
            border-color: var(--neon-pink);
            color: var(--neon-pink);
            background: rgba(255, 26, 255, 0.05);
            box-shadow: var(--glow-pink);
        }

        .suspect-btn.selected {
            background: var(--neon-pink);
            color: #000;
            border-color: var(--neon-pink);
            box-shadow: var(--glow-pink);
        }

        .submit-btn {
            background: transparent;
            border: 2px solid var(--terminal-green);
            color: var(--terminal-green);
            padding: 15px 40px;
            font-size: 1rem;
            text-transform: uppercase;
            font-family: 'Share Tech Mono', monospace;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: var(--glow-green);
        }

        .submit-btn:hover {
            background: var(--terminal-green);
            color: #000;
        }

        .result-display {
            margin-top: 50px;
            color: #fff;
            min-height: 50px;
            font-size: 1.1rem;
        }

        .cursor::after {
            content: '█';
            animation: blink 0.8s infinite;
        }

        @keyframes blink {
            50% { opacity: 0; }
        }

        /* --- RESPONSIVE FIXES --- */
        @media (max-width: 1200px) {
            .story-content { columns: 1; text-align: left; }
            .title-crimson { font-size: 3.5rem; }
        }
    </style>
</head>
<body>

    <!-- OVERLAYS -->
    <div class="scanlines"></div>
    <div class="ambient-noise"></div>
    <div class="main-background"></div>

    <!-- UI: SOUND CONTROL -->
    <div class="ui-hub" onclick="toggleDissonanceAudio()">
        SYS // AUDIO: <span id="audio-status">OFF</span>
    </div>


    <!-- ================= PAGE 1: DECODING ================= -->
    <section id="page-1" class="page active">
        <div class="hero-section">
            <div class="decode-container">
                <p class="status-header">/// ESTABLISHING SECURE CONNECTION ///</p>
                <h1 class="title-crimson">CRIMSON 404</h1>
                <p class="story-intro-text">
                    [Awaiting Subject Input] — You are the designated Operative. Your visual cortex has been synchronized with the memories of the detective from Image 28b49d.jpg. Lord Harrison is deceased. Room 404 is a glitch in reality. Proceed to decipher the corrupted data stream.
                </p>
                <button class="submit-btn" onclick="navigateToPage('page-2')">INITIALIZE CASE FILE DECODE</button>
            </div>
        </div>
    </section>


    <!-- ================= PAGE 2: CASE FILE ================= -->
    <section id="page-2" class="page">
        <div class="file-section">
            <div class="file-header">
                <button class="submit-btn" style="padding: 5px 15px; font-size: 0.7rem;" onclick="navigateToPage('page-1')">← RETURN TO TERMINAL</button>
                <p class="classification">Classification: COSMIC BLACK // EYES ONLY</p>
                <p style="font-size: 0.8rem; color: var(--text-muted);">Timestamp: [CORRUPTED]</p>
            </div>

            <div class="story-content">
                <p>It was never about the whiskey. I knew that the moment my consciousness stabilized inside Image 28b49d.jpg. The neon sign outside Room 404 was bleeding onto the desk, its red luminescence shifting reality in ways my standard logic circuits struggled to compute. I wasn’t just a detective; I was a data-siphon, and Crimson Manor was a corrupted hard drive.</p>

                <p>Lord Harrison sat at the walnut desk, his vital signs flat for exactly 4.04 hours. The glass of high-end scotch stood next to his lifeless hand, unlit cigar near the edge, and the <strong style="color:var(--neon-pink)">typewriter jammed on a single repeated phrase: ERR_LOG_000.</strong></p>

                <p>Three entities were detected in the immediate grid. They all had motive. My analysis needed precision.</p>

                <p>Operative <a href="#blackwood">Julian Blackwood</a> was found first, in the downstairs library. His boots were covered in the unique red clay found only in the Manor’s sealed conservatory garden. He swore he hadn’t left the library all evening, yet his inkwell was dry, and a freshly broken string on the rare <strong style="color:var(--neon-pink)">grandfather clock was found jammed into his pocket.</strong></p>

                <p>Operative <a href="#eleanor">Lady Eleanor</a> stood in the drawing room, nursing a minor scrape on her forearm. She was the primary heir but facing disinheritance in a revised will. She claimed ignorance, but my thermal analysis detected an anomalous temperature drop near the safe, and a <strong style="color:var(--neon-pink)">single, antique whiskey stone was missing</strong> from the set in the victim’s cabinet.</p>

                <p>Operative <a href="#vance">Dr. Alistair Vance</a>, the personal physician, was the calmest. His presence was routine. He claimed he had left the Manor long before the system failure. Yet, I tracked <strong style="color:var(--neon-pink)">residual trace compounds of an advanced, unregistrable nerve toxin</strong> inside his leather medical bag, perfectly matching the substance discovered in the residual whiskey sample on the desk.</p>

                <p>The system was glitching. One of these three individuals did not belong in this timeline. The final deduction is now mandatory. Who corrupted the data flow of Crimson 404?</p>
            </div>

            <!-- DEDUCTION TERMINAL -->
            <div class="deduction-terminal">
                <p class="term-title">INPUT REQUIRED: IDENTIFY SUSPECT 000</p>
                <div class="suspect-selection">
                    <button class="suspect-btn" id="s1" onclick="selectSuspect('Julian Blackwood', 's1')">Julian Blackwood</button>
                    <button class="suspect-btn" id="s2" onclick="selectSuspect('Lady Eleanor', 's2')">Lady Eleanor</button>
                    <button class="suspect-btn" id="s3" onclick="selectSuspect('Dr. Alistair Vance', 's3')">Dr. Alistair Vance</button>
                </div>
                <button class="submit-btn" onclick="submitFinalDeduction()">EXECUTE FINAL LOGIC</button>
                <div class="result-display" id="display-area"></div>
            </div>

        </div>
    </section>

    <!-- AUTOMATED AUDIO ENGINE (Requires User Interaction) -->
    <script>
        let audioCtx;
        let mainDrone;
        let lfo;
        let gainNode;
        let filterNode;
        let isPlaying = false;

        function initDissonanceAudio() {
            // Context
            audioCtx = new (window.AudioContext || window.webkitAudioContext)();
            
            // Nodes
            mainDrone = audioCtx.createOscillator();
            mainDrone.type = 'sawtooth';
            mainDrone.frequency.setValueAtTime(55, audioCtx.currentTime); // Low A (Tense bass)

            lfo = audioCtx.createOscillator();
            lfo.type = 'triangle';
            lfo.frequency.setValueAtTime(0.3, audioCtx.currentTime); // 0.3 Hz Slow throb

            gainNode = audioCtx.createGain();
            gainNode.gain.setValueAtTime(0, audioCtx.currentTime); // Start silent

            filterNode = audioCtx.createBiquadFilter();
            filterNode.type = 'lowpass';
            filterNode.frequency.setValueAtTime(150, audioCtx.currentTime); // Deep, muffled sound
            filterNode.Q.setValueAtTime(5, audioCtx.currentTime); // Resonance

            // Connections
            // LFO controls the filter frequency (Makes the sound 'breathe' eerie)
            let lfoGain = audioCtx.createGain();
            lfoGain.gain.setValueAtTime(50, audioCtx.currentTime); // Range of the throb
            lfo.connect(lfoGain);
            lfoGain.connect(filterNode.frequency);

            mainDrone.connect(filterNode);
            filterNode.connect(gainNode);
            gainNode.connect(audioCtx.destination);

            // Start oscs
            mainDrone.start();
            lfo.start();
        }

        function toggleDissonanceAudio() {
            if (!audioCtx) initDissonanceAudio();
            const statusLabel = document.getElementById('audio-status');

            if (!isPlaying) {
                // Smooth fade in
                gainNode.gain.setTargetAtTime(0.2, audioCtx.currentTime, 0.5);
                statusLabel.innerText = "ACTIVATED (Dissonant Drone)";
                statusLabel.style.color = "var(--neon-pink)";
                isPlaying = true;
            } else {
                // Smooth fade out
                gainNode.gain.setTargetAtTime(0, audioCtx.currentTime, 0.3);
                statusLabel.innerText = "OFF";
                statusLabel.style.color = "var(--terminal-green)";
                isPlaying = false;
            }
        }
    </script>

    <!-- NAVIGATION & DEDUCTION LOGIC -->
    <script>
        let selectedSuspectName = "";

        function navigateToPage(pageId) {
            document.querySelectorAll('.page').forEach(page => page.classList.remove('active'));
            document.getElementById(pageId).classList.add('active');
            window.scrollTo(0,0);
        }

        function selectSuspect(name, btnId) {
            document.querySelectorAll('.suspect-btn').forEach(btn => btn.classList.remove('selected'));
            document.getElementById(btnId).classList.add('selected');
            selectedSuspectName = name;
        }

        function submitFinalDeduction() {
            const display = document.getElementById('display-area');
            display.innerHTML = "";
            display.classList.add('cursor');

            if (!selectedSuspectName) {
                responseText = "SYS_ERROR: Select suspect ID before submission.";
            } else if (selectedSuspectName === "Dr. Alistair Vance") {
                responseText = "// LOGIC CHECK: Dr. Vance used his medical clearance to introduce the toxin. He assumed the standard investigation would check the glass first and miss the trace compounds in his case. You identified the data error. Case Solved.";
            } else if (selectedSuspectName === "Julian Blackwood") {
                responseText = "// ERROR: Blackwood was attempting to steal Lord Harrison's private ledgers to frame the disinherited niece. He is guilty of espionage, but not murder. Look closer at the biochemical evidence.";
            } else {
                responseText = "// DATA INCONSISTENCY: Lady Eleanor did attempt to tamper with thegrandfather clock to confuse the investigation, but she lacked access to the toxic compound that neutralized the victim. Re-analyze the suspects.";
            }

            let i = 0;
            function typeWriter() {
                if (i < responseText.length) {
                    display.innerHTML += responseText.charAt(i);
                    i++;
                    setTimeout(typeWriter, 30);
                } else {
                    display.classList.remove('cursor');
                }
            }
            typeWriter();
        }
    </script>

</body>
</html>
