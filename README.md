
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Midnight Case - A Detective Investigation</title>
    <style>
        :root {
            --bg-color: #0b0b0b;
            --text-primary: #e0e0e0;
            --text-accent: #8b0000; /* Deep Red */
            --font-serif: 'Georgia', serif;
            --font-sans: 'Arial', sans-serif;
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
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Fade-in Animation for Text */
        .fade-in-text {
            opacity: 0;
            transform: translateY(20px);
            animation: fadeInUp 2s forwards;
        }

        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Sections Layout */
        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        section {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 60px 20px;
            border-bottom: 1px solid #1a1a1a;
        }

        /* Landing Page Section */
        #landing {
            background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.95)), 
                        url('https://github.com/Kamakshi-weby/lalala/blob/main/622d03f0-8c85-4901-91e1-22853a46c77d.jpg?raw=true') no-repeat center center;
            background-size: cover;
        }

        h1 {
            font-size: 3.5rem;
            letter-spacing: 6px;
            text-transform: uppercase;
            font-weight: 300;
            margin-bottom: 10px;
        }

        .subtitle {
            font-family: var(--font-sans);
            color: var(--text-accent);
            letter-spacing: 4px;
            font-size: 0.9rem;
            text-transform: uppercase;
            margin-bottom: 40px;
        }

        .btn {
            background: transparent;
            color: var(--text-primary);
            border: 1px solid var(--text-accent);
            padding: 15px 40px;
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-bottom: 20px;
        }

        .btn:hover {
            background-color: var(--text-accent);
            box-shadow: 0 0 15px rgba(139, 0, 0, 0.6);
        }

        .warning-text {
            font-family: var(--font-sans);
            font-size: 0.75rem;
            color: #555;
            letter-spacing: 1px;
        }

        /* Story & Case Sections */
        .case-number {
            color: var(--text-accent);
            font-family: var(--font-sans);
            font-size: 0.8rem;
            letter-spacing: 3px;
            text-transform: uppercase;
            margin-bottom: 15px;
        }

        h2 {
            font-size: 2.5rem;
            margin-bottom: 30px;
            font-weight: 400;
        }

        p {
            font-size: 1.1rem;
            max-width: 700px;
            color: #b0b0b0;
            margin-bottom: 25px;
            text-align: left;
        }

        /* Layout with Image side-by-side */
        .content-wrap {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            width: 100%;
            gap: 40px;
            margin-top: 30px;
        }

        .text-block {
            flex: 1;
            min-width: 300px;
        }

        .img-block {
            flex: 1;
            min-width: 300px;
            border: 1px solid #222;
            padding: 10px;
            background-color: #111;
        }

        .img-block img {
            width: 100%;
            height: auto;
            filter: grayscale(100%) contrast(120%);
            display: block;
        }

        /* Verdict Form */
        .verdict-box {
            border: 1px solid #222;
            padding: 40px;
            background-color: #0d0d0d;
            width: 100%;
            max-width: 500px;
            margin-top: 30px;
        }

        input[type="text"] {
            width: 100%;
            background: transparent;
            border: none;
            border-bottom: 1px solid var(--text-accent);
            color: #fff;
            padding: 10px;
            font-size: 1.2rem;
            font-family: var(--font-serif);
            margin-bottom: 30px;
            text-align: center;
            outline: none;
        }

        /* Content initially hidden until "Enter" is clicked */
        #main-investigation {
            display: none;
        }
    </style>
</head>
<body>

    <!-- Background Audio Component -->
    <!-- Replace the src with your desired creepy piano audio URL stream or file path -->
    <audio id="creepyPiano" loop>
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
    </audio>

    <!-- LANDING PAGE -->
    <section id="landing">
        <div class="fade-in-text">
            <h1>The Midnight Case</h1>
            <div class="subtitle">A Detective Investigation</div>
            <button class="btn" onclick="startInvestigation()">Enter Investigation</button>
            <div class="warning-text">⚠️ WARNING: Audio will play</div>
        </div>
    </section>

    <!-- MAIN WEBSITE CONTENT -->
    <div id="main-investigation">
        
        <!-- SECTION 1: THE MIDNIGHT MURDER -->
        <section class="container">
            <div class="content-wrap">
                <div class="text-block">
                    <div class="case-number">Case File No. 1947</div>
                    <h2>The Midnight Murder</h2>
                    <p>When shadows dance at midnight and secrets whisper through the fog, only one detective dares to uncover the truth lurking in the darkness.</p>
                </div>
                <div class="img-block">
                    <!-- Embedded the requested image layout -->
                    <img src="https://github.com/Kamakshi-weby/lalala/blob/main/622d03f0-8c85-4901-91e1-22853a46c77d.jpg?raw=true" alt="Detective Scene">
                </div>
            </div>
        </section>

        <!-- SECTION 2: THE CASE UNFOLDS -->
        <section class="container">
            <div class="case-number">The Investigation</div>
            <h2>The Case Unfolds</h2>
            <p><strong>11:47 PM.</strong> The call came through like a death knell. A body discovered at the Ashford Manor—Victor Ashford, the wealthy industrialist, found dead in his study. Single gunshot wound to the chest. Time of death: approximately 11:00 PM.</p>
            <p>When I arrived, the manor was thick with tension and expensive perfume. Four people remained in the house, each with their own secrets, their own motives.</p>
        </section>

        <!-- SECTION 3: THE SUSPECTS -->
        <section class="container">
            <div class="case-number">The Suspects</div>
            <div style="text-align: left; width: 100%;">
                <p><strong style="color: var(--text-accent);">Eleanor Ashford (The Widow):</strong> Cool, composed, draped in black silk. Her alibi: she was in the conservatory, tending to her orchids. But her hands trembled when she poured her tea.</p>
                <p><strong style="color: var(--text-accent);">Marcus Chen (The Business Partner):</strong> Sharp suit, sharper tongue. He claimed he was in the library reviewing contracts. Documents scattered across the desk confirmed his story—but one page was missing.</p>
            </div>
        </section>

        <!-- SECTION 4: THE VERDICT -->
        <section class="container">
            <h2>Your Verdict</h2>
            <p style="text-align: center;">You've seen the evidence. You've heard the testimonies. Now, Detective, who do you believe committed this heinous crime?</p>
            
            <div class="verdict-box">
                <div class="case-number" style="margin-bottom: 5px;">Type the Culprit's Name</div>
                <input type="text" placeholder="Enter name..." id="culpritInput">
                <button class="btn" style="width: 100%; margin-bottom: 0;" onclick="submitVerdict()">Submit Verdict</button>
            </div>
        </section>
    </div>

    <script>
        function startInvestigation() {
            // Play the creepy background music loop
            const audio = document.getElementById('creepyPiano');
            audio.play().catch(function(error) {
                console.log("Audio play blocked or encountered an issue: ", error);
            });

            // Hide landing page smoothly and show the game content
            document.getElementById('landing').style.display = 'none';
            
            const mainContent = document.getElementById('main-investigation');
            mainContent.style.display = 'block';
            
            // Scroll smoothly to the top of the content
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function submitVerdict() {
            const name = document.getElementById('culpritInput').value;
            if(name.trim() !== "") {
                alert("Verdict received, Detective. Case file updated with suspect: " + name);
            } else {
                alert("Please enter a suspect's name.");
            }
        }
    </script>
</body>
</html>
