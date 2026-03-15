<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wedding Shivani & Arpan</title>
    
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Segoe+UI:wght@300;400;600&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>

    <style>
        :root {
            --pastel-pink: #d8a7b1;    
            --pastel-blue: #a3b8c8;
            --gold: #c5a059;
            --light-periwinkle: #f0f4f9;
            --font-serif: 'Playfair Display', serif;
            --font-sans: 'Segoe UI', sans-serif;
            --bg-soft: #fdfaf7;
        }

        body, html {
            margin: 0; padding: 0;
            width: 100%; height: 100%;
            font-family: var(--font-sans);
            background-color: var(--bg-soft);
            overflow: hidden; 
        }

        /* INTRO PAGE */
        #intro-page {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: url('https://premiumelegante.thedigitalyes.com/assets/intro-poster-new-BU7qGwfU.jpg') no-repeat center center;
            background-size: cover; z-index: 2000; cursor: pointer;
            transition: transform 1.2s cubic-bezier(0.7, 0, 0.3, 1);
        }

        /* FLORAL SIDEBARS */
        .floral-side {
            position: fixed; top: 0; width: 20vw; height: 100vh;
            background-image: url('https://boda-maria-carlos.lovable.app/assets/floral-border-J4FzR5M8.png');
            background-repeat: repeat-y; background-size: contain; z-index: 100;
            opacity: 0; transition: opacity 1.5s ease-in; pointer-events: none;
        }
        .floral-left { left: 0; background-position: right center; transform: scaleX(-1); }
        .floral-right { right: 0; background-position: right center; }
        .is-open .floral-side { opacity: 1; }

        #music-control {
            position: fixed; bottom: 25px; right: 25px; z-index: 150;
            background: rgba(255, 255, 255, 0.9); border: 1px solid var(--pastel-pink);
            color: var(--pastel-pink); width: 45px; height: 45px; border-radius: 50%;
            display: none; align-items: center; justify-content: center; cursor: pointer;
            box-shadow: 0 4px 15px rgba(216, 167, 177, 0.3); font-size: 20px;
        }
        .is-open #music-control { display: flex; }

        .scroll-container {
            height: 100vh; overflow-y: scroll; scroll-snap-type: y mandatory;
            display: none; position: relative; z-index: 10;
        }
        .is-open .scroll-container { display: block; }

        section {
            min-height: 100vh; width: 100%; scroll-snap-align: start;
            display: flex; flex-direction: column; justify-content: center;
            align-items: center; text-align: center; padding: 40px 0;
        }

        .content-wrap { width: 95%; max-width: 700px; position: relative; z-index: 15; }

        /* WELCOME BOX */
        .welcome-box {
            background-color: var(--light-periwinkle);
            padding: 50px 40px; border-radius: 4px;
            box-shadow: 0 15px 40px rgba(0,0,0,0.04); margin: 0 auto;
            max-width: 480px; position: relative;
            border-top: 2px solid var(--gold); border-bottom: 2px solid var(--gold);
        }

        .ganesha-img {
            width: 100px; 
            margin-top: 20px; 
            mix-blend-mode: multiply; 
            opacity: 0.9;
        }

        /* ITINERARY STYLING */
        .events-grid {
            display: grid; grid-template-columns: 1fr 1fr; gap: 20px;
            margin-top: 30px; text-align: left;
        }
        .event-card {
            background: white; padding: 20px; border-radius: 8px;
            border-left: 3px solid var(--gold);
            box-shadow: 0 5px 15px rgba(0,0,0,0.03);
            display: flex; flex-direction: column;
        }
        .event-date { font-family: var(--font-serif); color: var(--gold); font-size: 0.9rem; margin-bottom: 5px; }
        .event-name { font-family: var(--font-serif); color: var(--pastel-pink); font-size: 1.3rem; margin-bottom: 8px; }
        .event-detail { font-size: 0.85rem; color: #666; margin: 3px 0; min-height: 2.5em; }
        
        .maps-btn {
            display: inline-block;
            margin-top: 15px;
            padding: 8px 12px;
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: var(--gold);
            text-decoration: none;
            border: 1px solid var(--gold);
            border-radius: 4px;
            transition: all 0.3s ease;
            text-align: center;
            font-weight: 600;
        }
        .maps-btn:hover {
            background: var(--gold);
            color: white;
        }

        /* TYPOGRAPHY */
        .welcome-title, .venue-title { 
            font-family: var(--font-serif); font-weight: 400; font-size: 2.5rem; 
            color: var(--pastel-pink); margin-bottom: 20px; 
        }

        .is-open #intro-page { transform: translateY(-100%); }

        @media (max-width: 768px) {
            .events-grid { grid-template-columns: 1fr; }
            .content-wrap { width: 85%; }
            section { height: auto; min-height: 100vh; }
        }
    </style>
</head>
<body id="page-body">

    <div id="intro-page" onclick="openLetter()"></div>
    <div id="music-control" onclick="toggleMusic()">♪</div>
    
    <audio id="wedding-audio" loop>
        <source src="https://raw.githubusercontent.com/ishvni19/Wedding-invite/main/jashn_e_bahara_instr.mp3" type="audio/mpeg">
    </audio>

    <div class="floral-side floral-left"></div>
    <div class="floral-side floral-right"></div>

    <div class="scroll-container">
        <section>
            <div class="content-wrap">
                <p style="letter-spacing: 8px; font-size: 11px; color: var(--pastel-blue); margin-bottom: 25px;">THE WEDDING OF</p>
                <div style="font-family: var(--font-serif); font-size: clamp(2.2rem, 7vw, 3.5rem); color: var(--pastel-pink); text-transform: uppercase; letter-spacing: 6px;">
                    <div>Shivani</div>
                    <span style="font-size: 0.6em; display: block; margin: 10px 0; font-style: italic; color: var(--pastel-blue); text-transform: lowercase;">and</span>
                    <div>Arpan</div>
                </div>
                <div style="font-family: var(--font-serif); font-size: 1.5rem; color: var(--pastel-blue); margin-top: 20px; font-style: italic;">May 2026</div>
            </div>
        </section>

        <section>
            <div class="content-wrap">
                <div class="welcome-box">
                    <h1 class="welcome-title">Welcome!</h1>
                    <p style="font-size: 1.15rem; line-height: 1.8; color: #555; text-wrap: balance;">
                        Together with joyful hearts, the Sutrave and Tapdiya families warmly invite you to celebrate the beautiful union of their children, <strong>Shivani and Arpan</strong>. We look forward to sharing this unforgettable moment with our most special people.
                    </p>
                    <img src="https://t3.ftcdn.net/jpg/16/00/52/30/360_F_1600523058_2OBMnlklgR0P7S20ZbgRwK8WMvLvvg65.jpg" class="ganesha-img" alt="Ganesha">
                </div>
            </div>
        </section>

        <section>
            <div class="content-wrap">
                <h2 class="welcome-title">The Itinerary</h2>
                <div class="events-grid">
                    <div class="event-card">
                        <div class="event-date">6th May | 10:00 AM</div>
                        <div class="event-name">The Carnival</div>
                        <div class="event-detail">📍 Lakshmi Vihar Phase-1, Hyderabad</div>
                        <a href="https://maps.app.goo.gl/roDnZc4eDrALiWsQ9" target="_blank" class="maps-btn">View on Maps</a>
                    </div>
                    <div class="event-card">
                        <div class="event-date">6th May | 5:00 PM onwards</div>
                        <div class="event-name">Engagement & Sangeet</div>
                        <div class="event-detail">📍 Sri Convention Center, Hyderabad</div>
                        <a href="https://maps.app.goo.gl/6yXBLZ42Ls6XhGUu6" target="_blank" class="maps-btn">View on Maps</a>
                    </div>
                    <div class="event-card">
                        <div class="event-date">7th May | 10:30 AM</div>
                        <div class="event-name">The Wedding</div>
                        <div class="event-detail">📍 Sri Convention Center, Hyderabad</div>
                        <a href="https://maps.app.goo.gl/6yXBLZ42Ls6XhGUu6" target="_blank" class="maps-btn">View on Maps</a>
                    </div>
                    <div class="event-card">
                        <div class="event-date">9th May | 6:30 PM</div>
                        <div class="event-name">The Reception</div>
                        <div class="event-detail">📍 Sagar Lawns, Aurangabad</div>
                        <a href="https://maps.app.goo.gl/dktrr4VmMripQ6wSA" target="_blank" class="maps-btn">View on Maps</a>
                    </div>
                </div>
            </div>
        </section>

        <section>
            <div class="content-wrap">
                <h2 class="welcome-title" style="font-style: italic;">Counting Down to the Celebration...</h2>
                <div id="timer" class="countdown" style="display: flex; justify-content: center; gap: 10px;">
                    <div class="time-box" style="background: #fff; padding: 15px 5px; border-radius: 10px; min-width: 70px; border: 1px solid rgba(216, 167, 177, 0.2);">
                        <span class="val" id="days" style="font-size: 1.8rem; color: var(--pastel-pink); font-family: var(--font-serif);">00</span><br>
                        <span style="font-size: 9px; text-transform: uppercase; color: var(--pastel-purple); letter-spacing: 1px;">Days</span>
                    </div>
                    <div class="time-box" style="background: #fff; padding: 15px 5px; border-radius: 10px; min-width: 70px; border: 1px solid rgba(216, 167, 177, 0.2);">
                        <span class="val" id="hours" style="font-size: 1.8rem; color: var(--pastel-pink); font-family: var(--font-serif);">00</span><br>
                        <span style="font-size: 9px; text-transform: uppercase; color: var(--pastel-purple); letter-spacing: 1px;">Hrs</span>
                    </div>
                    <div class="time-box" style="background: #fff; padding: 15px 5px; border-radius: 10px; min-width: 70px; border: 1px solid rgba(216, 167, 177, 0.2);">
                        <span class="val" id="minutes" style="font-size: 1.8rem; color: var(--pastel-pink); font-family: var(--font-serif);">00</span><br>
                        <span style="font-size: 9px; text-transform: uppercase; color: var(--pastel-purple); letter-spacing: 1px;">Min</span>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <script>
        const audio = document.getElementById('wedding-audio');
        let isPlaying = false;

        function openLetter() {
            document.getElementById('page-body').classList.add('is-open');
            audio.play().then(() => { 
                isPlaying = true; 
                document.getElementById('music-control').innerText = '♪'; 
            }).catch(e => {
                console.log("Autoplay prevented. User needs to interact with the page first.");
            });
            confetti({ particleCount: 150, spread: 70, origin: { y: 0.6 }, colors: ['#d8a7b1', '#a3b8c8', '#c5a059'] });
        }

        function toggleMusic() {
            const btn = document.getElementById('music-control');
            if (isPlaying) { audio.pause(); btn.innerText = '🔇'; } 
            else { audio.play(); btn.innerText = '♪'; }
            isPlaying = !isPlaying;
        }

        const targetDate = new Date("May 06, 2026 10:00:00").getTime();
        setInterval(function() {
            const now = new Date().getTime();
            const d = targetDate - now;
            if (d > 0) {
                document.getElementById("days").innerText = String(Math.floor(d / (1000 * 60 * 60 * 24))).padStart(2, '0');
                document.getElementById("hours").innerText = String(Math.floor((d % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60))).padStart(2, '0');
                document.getElementById("minutes").innerText = String(Math.floor((d % (1000 * 60 * 60)) / (1000 * 60))).padStart(2, '0');
            }
        }, 1000);
    </script>
</body>
</html>
