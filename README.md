
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CASE FILE // 773</title>
    <style>
        :root {
            --bg-main: #141617;
            --surface-card: #1b1e20;
            --accent-gold: #dfb76c;
            --text-light: #f5f6f7;
            --text-muted: #82898d;
            --crimson-alert: #e74c3c;
            --font-serif: 'Georgia', serif;
            --font-sans: 'Courier New', Courier, monospace;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--bg-main);
            color: var(--text-light);
            font-family: var(--font-serif);
            line-height: 2;
            letter-spacing: 0.02em;
            overflow-x: hidden;
            min-height: 100vh;
        }

        /* Spacious Luxury Grid Framework */
        .editorial-wrapper {
            max-width: 1300px;
            margin: 0 auto;
            padding: 100px 60px;
        }

        /* Minimalist Page Division Header */
        .section-header {
            display: flex;
            justify-content: space-between;
            align-items: baseline;
            margin-bottom: 80px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.08);
            padding-bottom: 20px;
        }

        .section-counter {
            font-family: var(--font-sans);
            font-size: 0.8rem;
            color: var(--accent-gold);
            letter-spacing: 0.3em;
            text-transform: uppercase;
        }

        /* Page Layout 1: The Investigator Introduction */
        .dossier-canvas {
            display: grid;
            grid-template-columns: 450px 1fr;
            gap: 100px;
            align-items: center;
            margin-bottom: 180px;
        }

        @media (max-width: 950px) {
            .dossier-canvas {
                grid-template-columns: 1fr;
                gap: 50px;
                margin-bottom: 100px;
            }
        }

        .portrait-frame {
            background: var(--surface-card);
            padding: 25px;
            border: 1px solid rgba(223, 183, 108, 0.15);
            box-shadow: 0 40px 90px rgba(0, 0, 0, 0.6);
        }

        .portrait-asset {
            width: 100%;
            height: auto;
            display: block;
            filter: grayscale(100%) contrast(110%);
        }

        .prose-block h1 {
            font-size: 3.8rem;
            font-weight: 400;
            line-height: 1.1;
            margin-bottom: 25px;
            letter-spacing: -0.02em;
        }

        .prose-sub {
            font-family: var(--font-sans);
            color: var(--accent-gold);
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 0.25em;
            display: block;
            margin-bottom: 40px;
        }

        .editorial-p {
            font-size: 1.2rem;
            color: #d1d5d8;
            text-align: justify;
            margin-bottom: 30px;
        }

        /* Page Layout 2: The Mighty Impressive Crime Chronicle */
        .chronicle-canvas {
            margin-top: 60px;
        }

        .story-hero-text {
            font-size: 1.5rem;
            line-height: 2.1;
            color: #fff;
            margin-bottom: 60px;
            border-left: 2px solid var(--accent-gold);
            padding-left: 40px;
        }

        .evidence-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 50px;
            margin-bottom: 80px;
        }

        .evidence-card {
            background: var(--surface-card);
            padding: 40px;
            border: 1px solid rgba(255, 255, 255, 0.03);
            box-shadow: 0 20px 50px rgba(0,0,0,0.2);
            transition: border-color 0.4s ease;
        }

        .evidence-card:hover {
            border-color: rgba(223, 183, 108, 0.2);
        }

        .suspect-label {
            font-family: var(--font-sans);
            color: var(--accent-gold);
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 0.1em;
            margin-bottom: 15px;
            display: block;
        }

        /* Classy Text Guessing Area */
        .accusation-bay {
            background: #191b1d;
            border: 1px solid rgba(223, 183, 108, 0.2);
            padding: 60px;
            margin-top: 100px;
        }

        .accusation-bay h3 {
            font-family: var(--font-sans);
            color: var(--text-light);
            font-size: 1.1rem;
            text-transform: uppercase;
            letter-spacing: 0.2em;
            margin-bottom: 20px;
        }

        .input-structure {
            display: flex;
            gap: 20px;
            margin-top: 40px;
        }

        @media (max-width: 650px) {
            .input-structure {
                flex-direction: column;
            }
        }

        .text-field {
            flex: 1;
            background: #0f1011;
            border: 1px solid rgba(255, 255, 255, 0.1);
            padding: 20px 25px;
            color: var(--text-light);
            font-family: var(--font-sans);
            font-size: 1.05rem;
            outline: none;
            letter-spacing: 0.05em;
            transition: border-color 0.4s ease;
        }

        .text-field:focus {
            border-color: var(--accent-gold);
        }

        .submit-trigger {
            background: var(--accent-gold);
            color: #0f1011;
            border: none;
            padding: 0 50px;
            font-family: var(--font-sans);
            font-weight: bold;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 0.15em;
            cursor: pointer;
            transition: background 0.3s ease;
        }

        .submit-trigger:hover {
            background: #ebd19b;
        }

        .output-log {
            margin-top: 30px;
            font-family: var(--font-sans);
            font-size: 0.9rem;
            min-height: 24px;
            letter-spacing: 0.05em;
        }

        .success-log { color: #2ecc71; }
        .error-log { color: var(--crimson-alert); }
    </style>
</head>
<body>

    <!-- Native Hidden Instrumental Soundtrack Engine -->
    <audio id="cinematic-audio" loop>
        <source src="https://assets.mixkit.co/music/preview/mixkit-cinematic-mystery-312.mp3" type="audio/mpeg">
    </audio>

    <div class="editorial-wrapper">

        <!-- ================= PAGE 1 ================= -->
        <header class="section-header">
            <div class="section-counter">I // Investigator Record</div>
        </header>

        <section class="dossier-canvas">
            <div class="portrait-frame">
                <img src="https://github.com/Kamakshi-weby/lalala/blob/main/622d03f0-8c85-4901-91e1-22853a46c77d.jpg?raw=true" alt="Lead Investigator Archival Media" class="portrait-asset">
            </div>
            <div class="prose-block">
                <h1>Lead Specialist</h1>
                <span class="prose-sub">High-Profile Asset Protection // Intelligence Branch</span>
                <p class="editorial-p">
                    Standard field agents follow the physical marks worn directly into the pavement. I don't look down. Instead, my investigations are built on isolating the invisible, systemic structural anomalies left hanging in the room long after a criminal slips away. 
                </p>
                <p class="editorial-p">
                    This open network architecture operates as a completely clean ledger for open profiles. The tracking photograph captured on the left registers the last remaining active analytical consultant in this district willing to challenge perfectly calculated alibis. Scroll downward to break open the active timeline.
                </p>
            </div>
        </section>


        <!-- ================= PAGE 2 ================= -->
        <header class="section-header">
            <div class="section-counter">II // Active Case Chronicle</div>
        </header>

        <section class="chronicle-canvas">
            <div class="story-hero-text">
                The storm pounded against the stained-glass ceiling of Blackwood Estate with calculated violence. Inside the insulated walls of the private study, Lord Blackwood sat frozen forever at his writing desk. Beside his hand sat an untouched glass of vintage red wine and a ragged note warning: "The debt is collected."
            </div>

            <div class="evidence-grid">
                <div class="evidence-card">
                    <span class="suspect-label">Log 01 // Sterling (The Butler)</span>
                    <p class="editorial-p" style="font-size: 1.05rem;">
                        Maintained under intense questioning that he spent the hours of the storm locked away safely in the lower wine cellar to secure historic stock from rising floodwaters. Yet, forensic analysts found microscopic pieces of crushed white orchid petals caught in the seams of his leather boots. These exotic orchids grow exclusively on the second-story conservatory balcony, which sits directly outside the victim's shattered study window.
                    </p>
                </div>

                <div class="evidence-card">
                    <span class="suspect-label">Log 02 // Julian (The Brother)</span>
                    <p class="editorial-p" style="font-size: 1.05rem;">
                        Swore he spent the entire night alone in the opposite library wing translating ancient Greek classical volumes. While he lacks an apparent physical reason for violence, a hidden bank ledger recovered from his quarters exposes an astronomical chain of private gambling debts coming due exactly at sunrise.
                    </p>
                </div>

                <div class="evidence-card">
                    <span class="suspect-label">Log 03 // Victoria (The Protege)</span>
                    <p class="editorial-p" style="font-size: 1.05rem;">
                        Claims she was deeply asleep in the far eastern wing of the estate after taking a medical sedative. Strangely, her personal antique silver watch was discovered completely broken, its gears jammed and frozen at precisely 2:42 AM—the exact minute the primary pendulum clock in the study was smashed during the fatal scuffle.
                    </p>
                </div>
            </div>

            <!-- Interrogation User Typing Input Frame -->
            <div class="accusation-bay">
                <h3>Isolate the Chrono-Contradiction</h3>
                <p class="editorial-p" style="color: var(--text-muted); font-size: 0.95rem; margin-bottom: 0;">
                    One alibi instantly collapses under physical trace tracking. Type the exact name of the true criminal directly into the field below to issue the arrest warrant.
                </p>
                
                <div class="input-structure">
                    <input type="text" id="culprit-name-entry" class="text-field" placeholder="Type culprit's name here (Sterling, Julian, Victoria)..." autocomplete="off">
                    <button class="submit-trigger" onclick="verifyDeduction()">Issue Warrant</button>
                </div>
                
                <div id="log-output-terminal" class="output-log"></div>
            </div>
        </section>

    </div>

    <script>
        // Instrumental Audio Element Target
        const soundtrack = document.getElementById('cinematic-audio');

        // Global watch trigger to play real movie music on first screen interaction
        document.body.addEventListener('click', () => {
            if (soundtrack.paused) {
                soundtrack.volume = 0.40; // Set dynamic movie theater mixing volume
                soundtrack.play().catch(err => console.log("Audio waiting for explicit interaction context."));
            }
        });

        // Open Typing Interrogation Terminal Mechanics
        function verifyDeduction() {
            // Ensure audio kicks in if clicking input button first
            if (soundtrack.paused) {
                soundtrack.volume = 0.40;
                soundtrack.play();
            }

            const inputString = document.getElementById('culprit-name-entry').value.trim().toLowerCase();
            const terminalLog = document.getElementById('log-output-terminal');

            if (inputString === 'sterling') {
                terminalLog.className = "output-log success-log";
                terminalLog.innerText = "✓ WARRANT ISSUED: Sterling has been neutralized. The crushed orchid petals tracked into his boots proved he scaled the balconies to reach the study window.";
            } else if (inputString === 'victoria' || inputString === 'julian') {
                terminalLog.className = "output-log error-log";
                terminalLog.innerText = "✗ ANALYSIS REJECTED: Subject alibi stands up to current forensic constraints. Re-evaluate physical trace materials.";
            } else if (inputString === "") {
                terminalLog.className = "output-log error-log";
                terminalLog.innerText = "⚠ INPUT EXCEPTION: Interrogation entry block cannot be blank.";
            } else {
                terminalLog.className = "output-log error-log";
                terminalLog.innerText = "✗ ACCESS DENIED: Unknown entity. Target must be Sterling, Julian, or Victoria.";
            }
        }
    </script>
</body>
</html>
