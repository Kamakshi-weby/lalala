<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Blackwood Case</title>

    <link rel="stylesheet" href="style.css">

    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700&family=Special+Elite&display=swap"
        rel="stylesheet">
</head>

<body>

    <!-- Background Music -->
    <audio id="bgMusic" loop>
        <source src="piano.mp3" type="audio/mpeg">
    </audio>

    <!-- Flash -->
    <div id="flash"></div>

    <!-- PAGE 1 -->
    <section id="intro">

        <div class="overlay"></div>

        <div class="content">

            <h3>CASE FILE #017</h3>

            <h1>THE BLACKWOOD MURDER</h1>

            <p>
                Three people entered the Blackwood Manor.
                Only two came out.
            </p>

            <button id="startBtn">
                START INVESTIGATION
            </button>

        </div>

    </section>

    <!-- PAGE 2 -->

    <section id="storySection">

        <h2>Detective's Notes</h2>

        <div class="story">

            <p>

                11:47 PM.

                Rain poured endlessly over Blackwood Manor.

                The lights flickered exactly three times before every room went silent.

                The victim, Eleanor Blackwood, was discovered in the library with a knife buried deep in her chest.

                There were no signs of forced entry.

                No fingerprints.

                No footprints.

                The windows were locked from the inside.

                Only four people were inside the mansion.

            </p>

            <br>

            <h3>Suspects</h3>

            <br>

            <b>Arthur</b>

            <p>
                Eleanor's older brother.
                Calm.
                Wealthy.
                Inherits the family estate after her death.
            </p>

            <br>

            <b>Claire</b>

            <p>
                Eleanor's best friend.
                Claimed she never left the dining room.
                However, the maid heard footsteps upstairs.
            </p>

            <br>

            <b>Victor</b>

            <p>
                The family lawyer.
                Recently discovered Eleanor planned to rewrite her will.
            </p>

            <br>

            <b>Mary</b>

            <p>
                The housekeeper.
                Worked there for 27 years.
                Loved Eleanor like her own daughter.
            </p>

            <br>

            <h3>Evidence Found</h3>

            <ul>

                <li>A broken pocket watch stopped at 11:47.</li>

                <li>A muddy footprint leading nowhere.</li>

                <li>A torn photograph missing one face.</li>

                <li>The knife had no fingerprints.</li>

                <li>A burning fireplace despite warm weather.</li>

                <li>A single black feather on the floor.</li>

            </ul>

            <br>

            <h2>
                So...

                Who killed Eleanor?
            </h2>

        </div>

        <div class="choices">

            <button class="suspect" data-name="Arthur">Arthur</button>

            <button class="suspect" data-name="Claire">Claire</button>

            <button class="suspect" data-name="Victor">Victor</button>

            <button class="suspect" data-name="Mary">Mary</button>

        </div>

    </section>

    <!-- Jumpscare -->

    <div id="jumpscare">

        <img src="jumpscare.jpg">

        <div class="jumpText">

            YOU WERE WRONG.

            <br><br>

            THE KILLER HAS BEEN WATCHING YOU.

        </div>

    </div>

    <script src="script.js"></script>

</body>

</html>


*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

html{
    scroll-behavior:smooth;
}

body{
    background:#000;
    color:white;
    font-family:"Special Elite",cursive;
    overflow-x:hidden;
}

/* ---------------- INTRO ---------------- */

#intro{
    height:100vh;
    background:
        linear-gradient(rgba(0,0,0,.65),rgba(0,0,0,.9)),
        url("https://images.unsplash.com/photo-1511497584788-876760111969?q=80&w=1920&auto=format&fit=crop");
    background-size:cover;
    background-position:center;
    display:flex;
    justify-content:center;
    align-items:center;
    position:relative;
}

.overlay{
    position:absolute;
    inset:0;
    background:rgba(0,0,0,.25);
    animation:flicker 6s infinite;
}

.content{
    position:relative;
    z-index:2;
    text-align:center;
    width:85%;
    max-width:900px;
}

.content h3{
    color:#b30000;
    letter-spacing:5px;
    margin-bottom:20px;
    font-size:18px;
}

.content h1{
    font-family:"Cinzel",serif;
    font-size:65px;
    letter-spacing:3px;
    text-shadow:0 0 25px red;
}

.content p{
    margin-top:30px;
    font-size:22px;
    line-height:1.8;
    color:#ddd;
}

#startBtn{
    margin-top:45px;
    padding:18px 45px;
    background:#7b0000;
    border:none;
    color:white;
    cursor:pointer;
    font-size:18px;
    letter-spacing:2px;
    transition:.35s;
}

#startBtn:hover{
    background:#b00000;
    transform:scale(1.06);
    box-shadow:0 0 25px red;
}

/* ---------------- STORY ---------------- */

#storySection{
    display:none;
    min-height:100vh;
    background:#080808;
    padding:80px 12%;
}

#storySection h2{
    text-align:center;
    font-family:"Cinzel",serif;
    margin-bottom:40px;
    font-size:42px;
    color:#d4d4d4;
}

.story{
    max-width:900px;
    margin:auto;
    font-size:20px;
    line-height:2;
    color:#d2d2d2;
}

.story h3{
    color:#b50000;
    margin-top:40px;
}

.story ul{
    margin-left:30px;
    margin-top:15px;
}

.story li{
    margin-bottom:12px;
}

/* ---------------- BUTTONS ---------------- */

.choices{
    margin-top:70px;
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:20px;
    max-width:700px;
    margin-left:auto;
    margin-right:auto;
}

.suspect{
    padding:18px;
    background:#111;
    border:1px solid #444;
    color:white;
    font-size:18px;
    cursor:pointer;
    transition:.3s;
}

.suspect:hover{
    background:#8a0000;
    transform:scale(1.05);
}

/* ---------------- JUMPSCARE ---------------- */

#jumpscare{
    position:fixed;
    inset:0;
    background:black;
    display:none;
    justify-content:center;
    align-items:center;
    flex-direction:column;
    z-index:9999;
}

#jumpscare img{
    width:100%;
    height:100%;
    object-fit:cover;
    animation:shake .15s infinite;
}

.jumpText{
    position:absolute;
    color:white;
    text-align:center;
    font-size:45px;
    font-family:"Cinzel",serif;
    text-shadow:0 0 30px red;
    animation:blink .25s infinite;
}

/* ---------------- FLASH ---------------- */

#flash{
    position:fixed;
    inset:0;
    background:white;
    opacity:0;
    pointer-events:none;
    z-index:9998;
}

/* ---------------- ANIMATIONS ---------------- */

@keyframes flicker{

0%,100%{
opacity:.25;
}

15%{
opacity:.4;
}

28%{
opacity:.18;
}

40%{
opacity:.35;
}

65%{
opacity:.22;
}

80%{
opacity:.4;
}

}

@keyframes blink{

0%,100%{
opacity:1;
}

50%{
opacity:.2;
}

}

@keyframes shake{

0%{
transform:translate(4px,2px);
}

25%{
transform:translate(-4px,-3px);
}

50%{
transform:translate(3px,-2px);
}

75%{
transform:translate(-3px,3px);
}

100%{
transform:translate(4px,-3px);
}

}

/* ---------------- MOBILE ---------------- */

@media(max-width:768px){

.content h1{
font-size:42px;
}

.content p{
font-size:18px;
}

.story{
font-size:17px;
}

.choices{
grid-template-columns:1fr;
}

.jumpText{
font-size:28px;
}

}

// ---------- ELEMENTS ----------

const startBtn = document.getElementById("startBtn");
const intro = document.getElementById("intro");
const story = document.getElementById("storySection");

const flash = document.getElementById("flash");
const music = document.getElementById("bgMusic");

const suspects = document.querySelectorAll(".suspect");
const jumpscare = document.getElementById("jumpscare");

// ---------- START MUSIC ----------

// Browsers often block autoplay.
// This tries to play immediately and retries after the first click.

window.addEventListener("load", () => {
    music.volume = 0.35;

    music.play().catch(() => {

        document.addEventListener("click", () => {
            music.play();
        }, { once: true });

    });
});

// ---------- START INVESTIGATION ----------

startBtn.addEventListener("click", () => {

    intro.style.display = "none";
    story.style.display = "block";

    window.scrollTo({
        top: 0,
        behavior: "smooth"
    });

});

// ---------- CHOOSING A SUSPECT ----------

suspects.forEach(button => {

    button.addEventListener("click", () => {

        const answer = button.dataset.name;

        flash.style.transition = ".15s";
        flash.style.opacity = "1";

        setTimeout(() => {
            flash.style.opacity = "0";
        }, 150);

        setTimeout(() => {

            let message = "";

            switch(answer){

                case "Arthur":
                    message =
                    "Arthur had the strongest motive... but the watch in his pocket stopped an hour earlier. Someone wanted you to suspect him.";
                    break;

                case "Claire":
                    message =
                    "Claire lied about where she was... but she never entered the library.";
                    break;

                case "Victor":
                    message =
                    "Victor would gain money... yet he was already leaving Blackwood forever.";
                    break;

                case "Mary":
                    message =
                    "Mary loved Eleanor... or so everyone believed.";
                    break;

            }

            alert(message);

        },500);

        // ---------- JUMPSCARE ----------

        setTimeout(() => {

            music.pause();

            jumpscare.style.display = "flex";

            // OPTIONAL SCREAM SOUND

            const scream = new Audio("scream.mp3");
            scream.volume = 1;
            scream.play().catch(()=>{});

            document.body.style.overflow = "hidden";

        },2500);

    });

});
