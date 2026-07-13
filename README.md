
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Whispering Echoes | Case 40058</title>
    <style>
        :root {
            --bg-color: #0b0c10;
            --text-color: #c5c6c7;
            --accent-color: #66fcf1;
            --muted-accent: #45a29e;
            --card-bg: rgba(26, 26, 36, 0.4);
            --border-color: rgba(102, 252, 241, 0.15);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            font-family: 'Courier New', Courier, monospace;
            line-height: 1.8;
            overflow-x: hidden;
            position: relative;
        }

        /* Ambient Translucent Background Grid */
        body::before {
            content: "";
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: 
                radial-gradient(circle at 80% 20%, rgba(40, 30, 50, 0.4), transparent 50%),
                radial-gradient(circle at 20% 80%, rgba(15, 32, 39, 0.5), transparent 60%);
            z-index: -2;
        }

        /* Container providing the spacious layout */
        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 120px 40px;
        }

        section {
            margin-bottom: 180px;
            opacity: 0;
            transform: translateY(40px);
            transition: all 1.2s cubic-bezier(0.25, 1, 0.5, 1);
        }

        section.visible {
            opacity: 1;
            transform: translateY(0);
        }

        h1, h2 {
            font-weight: 300;
            letter-spacing: 4px;
            color: #fff;
            text-transform: uppercase;
            margin-bottom: 30px;
        }

        h1 {
            font-size: 2.5rem;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 15px;
        }

        p {
            margin-bottom: 25px;
            font-size: 1.05rem;
            text-align: justify;
        }

        /* Visual Elements & Images */
        .image-wrapper {
            width: 100%;
            height: 450px;
            overflow: hidden;
            border: 1px solid var(--border-color);
            margin: 40px 0;
            position: relative;
            background: rgba(0,0,0,0.2);
        }

        .image-wrapper img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            filter: grayscale(40%) contrast(110%) brightness(80%);
            opacity: 0.85;
            transition: transform 0.8s ease;
        }

        .image-wrapper:hover img {
            transform: scale(1.03);
        }

        /* Profile Layout */
        .profile-grid {
            display: grid;
            grid-template-columns: 1fr 1.5fr;
            gap: 50px;
            align-items: center;
        }

        .profile-img-box {
            height: 400px;
            border: 1px solid var(--border-color);
            overflow: hidden;
        }

        .profile-img-box img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            filter: grayscale(20%) brightness(90%);
        }

        /* Interactive Gameplay Section */
        .case-file {
            background: var(--card-bg);
            backdrop-filter: blur(8px);
            border: 1px solid var(--border-color);
            padding: 50px;
            border-radius: 4px;
        }

        .input-group {
            margin-top: 40px;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        label {
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            color: var(--muted-accent);
        }

        input[type="text"] {
            background: rgba(0, 0, 0, 0.5);
            border: 1px solid var(--border-color);
            padding: 15px 20px;
            color: #fff;
            font-family: inherit;
            font-size: 1.1rem;
            letter-spacing: 2px;
            outline: none;
            transition: border-color 0.3s;
        }

        input[type="text"]:focus {
            border-color: var(--accent-color);
        }

        button {
            background: transparent;
            border: 1px solid var(--accent-color);
            color: var(--accent-color);
            padding: 15px 30px;
            cursor: pointer;
            font-family: inherit;
            text-transform: uppercase;
            letter-spacing: 2px;
            transition: all 0.3s;
            margin-top: 10px;
            align-self: flex-start;
        }

        button:hover {
            background: rgba(102, 252, 241, 0.1);
            box-shadow: 0 0 15px rgba(102, 252, 241, 0.2);
        }

        .feedback {
            margin-top: 25px;
            font-size: 1.1rem;
            min-height: 30px;
            letter-spacing: 1px;
        }

        .correct { color: #2ecc71; }
        .incorrect { color: #e74c3c; }

        @media (max-width: 768px) {
            .profile-grid {
                grid-template-columns: 1fr;
            }
            .container {
                padding: 60px 20px;
            }
            .image-wrapper {
                height: 300px;
            }
        }
    </style>
</head>
<body>

    <!-- Hidden Background Audio Triggered on Interaction -->
    <audio id="bg-audio" loop>
        <source src="scary-piano.mp3" type="audio/mpeg">
    </audio>

    <div class="container">
        
        <!-- Section 1: The Scene -->
        <section class="visible">
            <h1>The Incident</h1>
            <div class="image-wrapper">
                <img src="https://raw.githubusercontent.com/Kamakshi-weby/lalala/main/622d03f0-8c85-4901-91e1-22853a46c77d.jpg" alt="Story Scenario">
            </div>
            <p>It was exactly 3:14 AM when the alarms inside the conservatory went dark. No glass was broken, no perimeter sensors tripped. Yet, by morning, the estate's most prized possession—and its host—had vanished entirely into the cold mist. Only a single note remained, anchored to a key on the grand piano.</p>
        </section>

        <!-- Section 2: The Investigator -->
        <section>
            <h1>The Mind Behind the Case</h1>
            <div class="profile-grid">
                <div class="profile-img-box">
                    <img src="detective.jpg" alt="Investigator Profile">
                </div>
                <div>
                    <h2>Lead Investigator</h2>
                    <p>Known for dissecting crimes others deem supernatural, he approaches chaos with clinical detachment. He doesn't look for clues; he looks for structural errors in the culprit's reality.</p>
                    <p><em>"Every lock is an admission of fear. Every crime is a signature written in panic."</em></p>
                </div>
            </div>
        </section>

        <!-- Section 3: The Chronicle & Solution -->
        <section>
            <h1>Case File: The Last Sonata</h1>
            <div class="case-file">
                <p>Three guests stayed at the manor that evening: <strong>Julian</strong>, the melancholic composer who spent the night drinking down hall; <strong>Elena</strong>, the estranged heiress who claimed she was asleep in the east wing; and <strong>Dr. Vance</strong>, the family physician who arrived unexpectedly before the storm hit.</p>
                <p>The detective discovered that the master clock had been stopped manually via the gear assembly. The delicate gears were coated in a distinct, aromatic oil used exclusively to preserve old medical instruments. Furthermore, a signature melody was left pressed down on the piano keys: E, B, and G-sharp. A clinical chord sequence meant to mimic a flatlining pulse.</p>
                
                <div class="input-group">
                    <label for="culprit-input">Identify the Culprit</label>
                    <input type="text" id="culprit-input" placeholder="Enter name...">
                    <button onclick="verifyCulprit()">Submit Accusation</button>
                    <div id="feedback-field" class="feedback"></div>
                </div>
            </div>
        </section>

    </div>

    <script>
        // Automatic Audio Activation on first User Interaction
        window.addEventListener('click', () => {
            const audio = document.getElementById('bg-audio');
            if(audio.paused) {
                audio.volume = 0.4;
                audio.play().catch(err => console.log("Audio play blocked until interaction."));
            }
        }, { once: true });

        // Scroll Animation Logic
        const sections = document.querySelectorAll('section');
        const observerOptions = {
            root: null,
            threshold: 0.1,
            rootMargin: "0px 0px -100px 0px"
        };

        const sectionObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if(entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        sections.forEach(section => sectionObserver.observe(section));

        // Riddle Logic Validation
        function verifyCulprit() {
            const answer = document.getElementById('culprit-input').value.trim().toLowerCase();
            const feedback = document.getElementById('feedback-field');
            
            if(answer.includes('vance') || answer.includes('doctor')) {
                feedback.className = "feedback correct";
                feedback.innerText = "Correct. The medical oil and structural flatline signature betrayed Dr. Vance.";
            } else {
                feedback.className = "feedback incorrect";
                feedback.innerText = "The shadows remain still. That is not who committed this crime.";
            }
        }
    </script>
</body>
</html>
