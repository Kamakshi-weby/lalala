
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Whispering Canvas | Case File 04</title>
    <style>
        :root {
            --bg-color: #1a1a17;
            --panel-color: #242420;
            --accent-gold: #c5a880;
            --text-light: #e6e6e0;
            --text-muted: #9c9c90;
            --crimson: #8b2626;
            --font-serif: 'Playfair Display', Georgia, serif;
            --font-sans: 'Montserrat', sans-serif;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-light);
            font-family: var(--font-sans);
            line-height: 1.6;
            overflow-x: hidden;
            letter-spacing: 0.05em;
        }

        /* Ambient Background Texture */
        .noir-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 50% 30%, rgba(36, 36, 32, 0.3) 0%, rgba(18, 18, 15, 0.9) 80%);
            pointer-events: none;
            z-index: 10;
        }

        /* Custom Audio Controller Status */
        .audio-bar {
            position: fixed;
            top: 30px;
            right: 40px;
            z-index: 100;
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 0.2em;
            color: var(--accent-gold);
            cursor: pointer;
        }

        .audio-pulse {
            width: 12px;
            height: 12px;
            background-color: var(--accent-gold);
            border-radius: 50%;
            box-shadow: 0 0 8px var(--accent-gold);
            animation: pulse 2s infinite ease-in-out;
        }

        @keyframes pulse {
            0% { transform: scale(0.8); opacity: 0.5; }
            50% { transform: scale(1.2); opacity: 1; }
            100% { transform: scale(0.8); opacity: 0.5; }
        }

        /* Layout Structure */
        header {
            padding: 40px 60px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid rgba(197, 168, 128, 0.15);
            position: relative;
            z-index: 20;
        }

        .logo {
            font-family: var(--font-serif);
            font-size: 1.5rem;
            font-style: italic;
            color: var(--accent-gold);
            text-decoration: none;
        }

        nav {
            display: flex;
            gap: 40px;
        }

        .nav-link {
            color: var(--text-muted);
            text-decoration: none;
            font-size: 0.8rem;
            text-transform: uppercase;
            letter-spacing: 0.25em;
            transition: color 0.3s ease;
            cursor: pointer;
        }

        .nav-link.active, .nav-link:hover {
            color: var(--accent-gold);
        }

        .page-container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 80px 40px;
            position: relative;
            z-index: 20;
        }

        .page {
            display: none;
            animation: fadeIn 0.8s forwards ease;
        }

        .page.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(15px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Page 1: Dossier & Profile */
        .dossier-grid {
            display: grid;
            grid-template-columns: 1.1fr 1.9fr;
            gap: 80px;
            align-items: start;
        }

        .portrait-frame {
            border: 1px solid rgba(197, 168, 128, 0.3);
            padding: 15px;
            background-color: var(--panel-color);
            box-shadow: 0 20px 40px rgba(0,0,0,0.5);
        }

        .portrait-img {
            width: 100%;
            height: auto;
            filter: sepia(0.2) contrast(1.1) brightness(0.9);
            display: block;
        }

        .profile-info {
            font-family: var(--font-serif);
        }

        .stamp-txt {
            font-family: var(--font-sans);
            font-size: 0.75rem;
            color: var(--crimson);
            text-transform: uppercase;
            letter-spacing: 0.3em;
            border: 1px solid var(--crimson);
            padding: 4px 8px;
            display: inline-block;
            margin-bottom: 20px;
            font-weight: bold;
        }

        h1 {
            font-size: 3.5rem;
            font-weight: 400;
            line-height: 1.1;
            margin-bottom: 30px;
            color: var(--text-light);
        }

        .lead-text {
            font-family: var(--font-sans);
            font-size: 1.05rem;
            color: var(--text-muted);
            margin-bottom: 40px;
            line-height: 1.8;
        }

        .meta-table {
            width: 100%;
            border-top: 1px solid rgba(197, 168, 128, 0.2);
            margin-top: 40px;
        }

        .meta-row {
            display: flex;
            padding: 15px 0;
            border-bottom: 1px solid rgba(197, 168, 128, 0.1);
            font-size: 0.9rem;
        }

        .meta-label {
            width: 150px;
            text-transform: uppercase;
            letter-spacing: 0.15em;
            color: var(--accent-gold);
            font-family: var(--font-sans);
            font-size: 0.75rem;
        }

        .meta-val {
            color: var(--text-light);
        }

        /* Page 2: The Narrative */
        .story-layout {
            max-width: 800px;
            margin: 0 auto;
        }

        .story-header {
            text-align: center;
            margin-bottom: 60px;
        }

        .story-body {
            font-family: var(--font-serif);
            font-size: 1.2rem;
            line-height: 2;
            color: #d1d1c7;
        }

        .story-body p {
            margin-bottom: 35px;
            text-align: justify;
        }

        .story-body p::first-letter {
            font-size: 3rem;
            float: left;
            margin-right: 10px;
            line-height: 1;
            color: var(--accent-gold);
            font-family: var(--font-serif);
        }

        .story-body p + p::first-letter {
            font-size: inherit;
            float: none;
            margin-right: 0;
            line-height: inherit;
            color: inherit;
        }

        /* Accusation Interactive Interface */
        .accusation-box {
            background-color: var(--panel-color);
            border: 1px solid rgba(197, 168, 128, 0.25);
            padding: 50px;
            margin-top: 80px;
            text-align: center;
            position: relative;
        }

        .accusation-box h3 {
            font-family: var(--font-serif);
            font-size: 1.8rem;
            color: var(--accent-gold);
            margin-bottom: 15px;
        }

        .input-wrapper {
            margin: 30px auto 20px auto;
            max-width: 400px;
            position: relative;
        }

        .deduction-input {
            width: 100%;
            background: transparent;
            border: none;
            border-bottom: 2px solid rgba(197, 168, 128, 0.4);
            padding: 10px 0;
            color: var(--text-light);
            font-family: var(--font-sans);
            font-size: 1.1rem;
            text-align: center;
            letter-spacing: 0.1em;
            outline: none;
            transition: border-color 0.4s;
        }

        .deduction-input:focus {
            border-color: var(--accent-gold);
        }

        .submit-btn {
            background-color: transparent;
            border: 1px solid var(--accent-gold);
            color: var(--accent-gold);
            padding: 12px 35px;
            font-family: var(--font-sans);
            font-size: 0.8rem;
            text-transform: uppercase;
            letter-spacing: 0.2em;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 15px;
        }

        .submit-btn:hover {
            background-color: var(--accent-gold);
            color: var(--bg-color);
        }

        .verdict-banner {
            margin-top: 25px;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 0.15em;
            font-weight: bold;
            min-height: 24px;
        }

        .text-correct { color: #4b7a4b; }
        .text-incorrect { color: var(--crimson); }

        @media(max-width: 900px) {
            .dossier-grid { grid-template-columns: 1fr; gap: 40px; }
            header { padding: 30px; }
            .page-container { padding: 40px 20px; }
            h1 { font-size: 2.5rem; }
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600&family=Playfair+Display:ital,wght@0,400;0,600;1,400&display=swap" rel="stylesheet">
</head>
<body>

    <div class="noir-overlay"></div>

    <!-- Clickable audio trigger simulating a film track status indicator -->
    <div class="audio-bar" onclick="toggleAudio()">
        <span id="audio-status-text">Audio Calibrating</span>
        <div class="audio-pulse"></div>
    </div>

    <header>
        <a class="logo" href="#">L I N E A G E</a>
        <nav>
            <span class="nav-link active" onclick="switchPage('dossier-page', this)">Dossier 01</span>
            <span class="nav-link" onclick="switchPage('case-page', this)">The Narrative</span>
        </nav>
    </header>

    <div class="page-container">

        <!-- PAGE 1: DETECTIVE PROFILE DEPLOYMENT -->
        <section id="dossier-page" class="page active">
            <div class="dossier-grid">
                <div class="portrait-frame">
                    <img src="https://github.com/Kamakshi-weby/lalala/blob/main/622d03f0-8c85-4901-91e1-22853a46c77d.jpg?raw=true" alt="Primary Investigator Portfolio Asset" class="portrait-img">
                </div>
                <div class="profile-info">
                    <span class="stamp-txt">Active Assignment</span>
                    <h1>The Investigator Blueprint.</h1>
                    <p class="lead-text">
                        Operating from the shadowy thresholds of systemic industry and hidden architectures, we specialize in tracking details others overlook. No errors are left unexamined, and no anomalies remain unmapped. Everything traces back to a signature pattern.
                    </p>

                    <div class="meta-table">
                        <div class="meta-row">
                            <div class="meta-label">Identity Assignment</div>
                            <div class="meta-val">Lead Investigator</div>
                        </div>
                        <div class="meta-row">
                            <div class="meta-label">Operational Style</div>
                            <div class="meta-val">High-Class Minimalist / High Sharpness Noir</div>
                        </div>
                        <div class="meta-row">
                            <div class="meta-label">Focus Parameters</div>
                            <div class="meta-val">Structural Anomalies, Decryption, In-Engine Visual Realism</div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- PAGE 2: NARRATIVE MYSTERY ARCHIVE -->
        <section id="case-page" class="page">
            <div class="story-layout">
                <div class="story-header">
                    <span class="stamp-txt" style="color: var(--accent-gold); border-color: var(--accent-gold);">Exhibits Closed Until Entry</span>
                    <h1 style="font-size: 2.8rem; margin-top: 15px;">The Glass Menagerie Paradox</h1>
                </div>
                
                <div class="story-body">
                    <p>
                        The rain over the manor structure did not fall so much as it layered itself across the tall glass panels of the conservatory library. At exactly 11:42 PM, Lord Sterling’s private alarm array registered an internal break. When I pushed past the cedar double doors, the room was immaculate, save for one distinct structural anomaly: the central display casing was empty, and its reinforced seals had been removed cleanly from the inside track.
                    </p>
                    <p>
                        Three individuals remained inside the estate perimeter after lock protocol was declared. The first was Julian, the curator, whose clothes carried the unmistakable scent of bitter almond oils—a substance commonly used to preserve historical bindings, but equally capable of neutralizing complex electric currents if applied directly to the line feeds. He insisted he was updating catalog archives in the lower vault.
                    </p>
                    <p>
                        The second was Victoria, the estate's structural engineer. Her hands were perfectly clean, but the tailored cuff of her silk coat bore a faint smudge of graphite grease. When questioned, she noted she had been calibrating the boiler lines near the north terrace, far from the library circuit hubs. However, the internal schematics indicated that the north line shared a single utility tunnel with the library's primary structural conduit.
                    </p>
                    <p>
                        Finally, there was Marcus, the private collector who had arrived unannounced at dusk. He sat quietly by the lounge fireplace, his muddy boots resting on a Persian rug. He claimed he had spent the evening completely incapacitated by a sudden fever, never leaving the hearth fire. Yet, tucked beneath the clasp of his left boot heel, a small fragment of green leaf from an exotic orchid—found exclusively within the library conservatory—was still completely fresh, uncrushed by any walk outdoors.
                    </p>
                </div>

                <!-- Open Form Field Component -->
                <div class="accusation-box">
                    <h3>Record Your Verdict</h3>
                    <p style="font-size: 0.85rem; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.1em;">Type the name of the true culprit below</p>
                    
                    <div class="input-wrapper">
                        <input type="text" id="culpritInput" class="deduction-input" placeholder="ENTER NAME...">
                    </div>
                    
                    <button class="submit-btn" onclick="verifyAccusation()">File Official Dossier</button>
                    <div id="verdictOutput" class="verdict-banner"></div>
                </div>
            </div>
        </section>

    </div>

    <script>
        // Page Switching Logic
        function switchPage(pageId, element) {
            document.querySelectorAll('.page').forEach(page => page.classList.remove('active'));
            document.querySelectorAll('.nav-link').forEach(link => link.classList.remove('active'));
            
            document.getElementById(pageId).classList.add('active');
            element.classList.add('active');
            
            window.scrollTo({ top: 0, behavior: 'smooth' });
            initAudioContext(); // Activates or keeps audio running smoothly on interaction
        }

        // Web Audio API Synthesizer - Creates scary, cinematic background tension organically
        let audioCtx = null;
        let isPlaying = false;
        let lowOsc = null;
        let highOsc = null;
        let lowGain = null;
        let highGain = null;

        function initAudioContext() {
            if (audioCtx) return;
            
            audioCtx = new (window.AudioContext || window.webkitAudioContext)();
            
            // Channel Master Configurations
            lowGain = audioCtx.createGain();
            highGain = audioCtx.createGain();
            
            lowGain.gain.setValueAtTime(0.18, audioCtx.currentTime);
            highGain.gain.setValueAtTime(0.03, audioCtx.currentTime);
            
            // Deep, rumbling ambient sub-bass frequency
            lowOsc = audioCtx.createOscillator();
            lowOsc.type = 'sawtooth';
            lowOsc.frequency.setValueAtTime(42, audioCtx.currentTime); // 42Hz tension note
            
            // High pitch cinematic friction tone
            highOsc = audioCtx.createOscillator();
            highOsc.type = 'sine';
            highOsc.frequency.setValueAtTime(880, audioCtx.currentTime); // Dissonant background ring
            
            // High-pass filtering to give it a hollow, scary movie sound stage
            let filter = audioCtx.createBiquadFilter();
            filter.type = 'lowpass';
            filter.frequency.setValueAtTime(120, audioCtx.currentTime);
            
            // Connect pathways
            lowOsc.connect(filter);
            filter.connect(lowGain);
            lowGain.connect(audioCtx.destination);
            
            highOsc.connect(highGain);
            highGain.connect(audioCtx.destination);
            
            lowOsc.start();
            highOsc.start();
            
            // Modulate tones over time to create a living, creeping horror soundtrack
            setInterval(() => {
                if(!isPlaying) return;
                let now = audioCtx.currentTime;
                // Slowly warp frequencies so it feels like a movie score shifting
                lowOsc.frequency.linearRampToValueAtTime(38 + Math.random() * 8, now + 4);
                highOsc.frequency.linearRampToValueAtTime(875 + Math.random() * 10, now + 3);
                highGain.gain.linearRampToValueAtTime(0.01 + Math.random() * 0.03, now + 2);
            }, 4000);

            isPlaying = true;
            document.getElementById('audio-status-text').innerText = "Tension Engine Active";
        }

        function toggleAudio() {
            if (!audioCtx) {
                initAudioContext();
                return;
            }
            if (isPlaying) {
                lowGain.gain.linearRampToValueAtTime(0, audioCtx.currentTime + 0.5);
                highGain.gain.linearRampToValueAtTime(0, audioCtx.currentTime + 0.5);
                document.getElementById('audio-status-text').innerText = "Audio Muted";
                isPlaying = false;
            } else {
                lowGain.gain.linearRampToValueAtTime(0.18, audioCtx.currentTime + 0.5);
                highGain.gain.linearRampToValueAtTime(0.03, audioCtx.currentTime + 0.5);
                document.getElementById('audio-status-text').innerText = "Tension Engine Active";
                isPlaying = true;
            }
        }

        // Automatic audio unlock triggers on user interaction
        window.addEventListener('click', () => {
            if(audioCtx && audioCtx.state === 'suspended') {
                audioCtx.resume();
                isPlaying = true;
                document.getElementById('audio-status-text').innerText = "Tension Engine Active";
            } else if (!audioCtx) {
                initAudioContext();
            }
        });

        // Text Verification System for Case Deduction
        function verifyAccusation() {
            const input = document.getElementById('culpritInput').value.trim().toLowerCase();
            const feedback = document.getElementById('verdictOutput');
            
            if (input === 'marcus') {
                feedback.className = "verdict-banner text-correct";
                feedback.innerText = "Deduction Verified. The orchid trace leaves Marcus completely exposed.";
            } else if (input === 'julian' || input === 'victoria') {
                feedback.className = "verdict-banner text-incorrect";
                feedback.innerText = "Incorrect. Their actions align with architectural limits. Re-examine the timeline.";
            } else {
                feedback.className = "verdict-banner text-incorrect";
                feedback.innerText = "Unknown entity. Focus your file specifically on Julian, Victoria, or Marcus.";
            }
        }
    </script>
</body>
</html>
