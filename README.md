
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Midnight Case</title>
    <style>
        :root {
            --bg-color: #050505;
            --text-primary: #d4d4d4;
            --text-accent: #9c0000;
            --font-serif: 'Georgia', serif;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-primary);
            font-family: var(--font-serif);
            overflow-x: hidden;
            background: radial-gradient(circle at center, #150505 0%, #050505 80%);
            min-height: 100vh;
        }

        /* Ambient Fog/Vignette Overlay */
        body::before {
            content: '';
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: max-gradient(rgba(0,0,0,0) 60%, rgba(0,0,0,0.9));
            pointer-events: none;
            z-index: 10;
        }

        /* Seamless click-anywhere curtain to trigger audio bypassed natively */
        #audio-trigger-layer {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            z-index: 9999;
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
            background: rgba(5, 5, 5, 0.98);
            transition: opacity 1.5s ease;
        }

        .prompt-text {
            font-size: 1.5rem;
            letter-spacing: 5px;
            text-transform: uppercase;
            color: #444;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { opacity: 0.3; }
            50% { opacity: 0.8; color: var(--text-accent); }
            100% { opacity: 0.3; }
        }

        /* Main Investigation Container */
        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 60px 20px;
            position: relative;
            z-index: 2;
        }

        .header-title {
            text-align: center;
            font-size: 3.5rem;
            letter-spacing: 8px;
            text-transform: uppercase;
            margin-bottom: 10px;
            color: #fff;
            text-shadow: 0 0 20px rgba(255,255,255,0.1);
        }

        .subtitle {
            text-align: center;
            font-size: 0.9rem;
            letter-spacing: 4px;
            text-transform: uppercase;
            color: var(--text-accent);
            margin-bottom: 80px;
        }

        /* Typewriter text formatting */
        .story-container {
            font-size: 1.25rem;
            line-height: 1.8;
            letter-spacing: 0.5px;
            white-space: pre-line; /* Preserves paragraph formatting */
            border-left: 2px solid #1a1a1a;
            padding-left: 25px;
            margin-bottom: 60px;
        }

        /* Custom Typewriter Cursor Effect */
        .cursor {
            display: inline-block;
            width: 10px;
            height: 1.2rem;
            background-color: var(--text-accent);
            margin-left: 4px;
            animation: blink 0.8s infinite;
            vertical-align: middle;
        }

        @keyframes blink {
            50% { background-color: transparent; }
        }

        /* Crime Scene Image layout styling */
        .evidence-block {
            margin: 40px 0;
            border: 1px solid #1c0505;
            padding: 15px;
            background: #0a0202;
            box-shadow: 0 0 30px rgba(0,0,0,0.8);
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .evidence-block img {
            width: 100%;
            height: auto;
            filter: grayscale(100%) brightness(70%) contrast(130%);
            mix-blend-mode: luminosity;
        }

        /* Input field area */
        .input-panel {
            opacity: 0;
            transition: opacity 2s ease;
            text-align: center;
            margin-top: 50px;
        }

        .input-panel.visible {
            opacity: 1;
        }

        .input-panel h3 {
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 3px;
            color: var(--text-accent);
            margin-bottom: 20px;
        }

        input[type="text"] {
            background: transparent;
            border: none;
            border-bottom: 1px solid #333;
            color: #fff;
            padding: 10px;
            font-size: 1.3rem;
            font-family: var(--font-serif);
            width: 100%;
            max-width: 400px;
            text-align: center;
            outline: none;
            transition: border-color 0.5s;
        }

        input[type="text"]:focus {
            border-color: var(--text-accent);
        }
    </style>
</head>
<body>

    <!-- Invisible trigger mask to fire audio on the very first user interaction natively -->
    <div id="audio-trigger-layer" onclick="initiateScene()">
        <div class="prompt-text">Click anywhere to begin inspection</div>
    </div>

    <!-- Direct raw source path for an atmospheric, ominous drone sound -->
    <audio id="creepyAmbient" loop pre-load="auto">
        <source src="https://assets.mixkit.co/active_storage/sfx/2568/2568-84.wav" type="audio/wav">
    </audio>

    <div class="container">
        <h1 class="header-title">The Midnight Case</h1>
        <div class="subtitle">A Detective Investigation</div>

        <!-- The typewriter script will targets this element to auto generate characters -->
        <div class="story-container" id="typewriter-target"></div>

        <!-- Dynamic Evidence Image Placement -->
        <div class="evidence-block">
            <img src="https://github.com/Kamakshi-weby/lalala/blob/main/622d03f0-8c85-4901-91e1-22853a46c77d.jpg?raw=true" alt="Case File Photo">
        </div>

        <!-- Submission Box -->
        <div class="input-panel" id="verdict-form">
            <h3>Who committed this crime?</h3>
            <input type="text" placeholder="Type the culprit's name..." autocomplete="off">
        </div>
    </div>

    <script>
        // Expanded immersive narrative block text
        const narrativeText = `CASE FILE NO. 1947: THE ASHFORD MANOR MURDER\n\n11:47 PM. The fog was rolling heavy off the harbor, thick enough to swallow a man whole. When the call cracked through the dispatch line, it sounded more like a death rattle than a notice.\n\nVictor Ashford—the city's premier industrial titan—was slumped inside his private quarters. A single cleanly placed bullet wound pierced his silk monogrammed vest. No signs of forced entry. The grandfather clock in the corner had shattered at exactly 11:00 PM, fixed in time.\n\nFour suspects remain isolated inside the main lounge downstairs, wrapped up tightly in their matching alibis and expensive venom:\n\n- ELEANOR ASHFORD (The Widow): Draped completely in black lace. She swears she was inside the conservatory clip-trimming orchids, yet her hands shook violently enough to rattle her porcelain teacup.\n\n- MARCUS CHEN (The Partner): Cold, calculating, eyes like split flint. Claims he was deep in ledger documentation, but the primary financial contract sheet has been neatly ripped from the binder binding.\n\nLook closely at the desk file image below. The clues are screaming inside the dark. Who among them struck the fatal match?`;

        let index = 0;
        const speed = 45; // Speed adjustment in milliseconds per letter typed

        function initiateScene() {
            // Instantly hide overlay curtain
            const curtain = document.getElementById('audio-trigger-layer');
            curtain.style.opacity = '0';
            setTimeout(() => curtain.remove(), 1500);

            // Execute loop soundtrack immediately
            const music = document.getElementById('creepyAmbient');
            music.play().catch(e => console.log("Audio block bypass registered.", e));

            // Run automated typewriter delivery sequence
            typeWriter();
        }

        function typeWriter() {
            if (index < narrativeText.length) {
                const target = document.getElementById("typewriter-target");
                
                // Append next string slice + keep clean flashing cursor block tracking text edge
                target.innerHTML = narrativeText.substring(0, index + 1) + '<span class="cursor"></span>';
                index++;
                setTimeout(typeWriter, speed);
            } else {
                // Remove trailing typing cursor when page sequence achieves complete execution
                document.querySelector('.cursor').remove();
                // Fade-in submission fields smoothly at end of reading event
                document.getElementById('verdict-form').classList.add('visible');
            }
        }
    </script>
</body>
</html>
