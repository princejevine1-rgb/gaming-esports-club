<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Royal E-Sports Club</title>
<style>
* { margin: 0; padding: 0; box-sizing: border-box; font-family: Inter, Arial, sans-serif; }
:root { --gold: #ffc700; --bg: #070707; --text: #f5f5f5; --soft: #1f1f1f; --muted: #b8b8b8; }
body { background: radial-gradient(circle at 20% 10%, #171717 0%, #090909 50%, #040404 100%); color: var(--text); line-height: 1.5; }
.container { width: min(1100px, 92%); margin: 0 auto; }
header { position: sticky; top: 0; z-index: 20; background: rgba(5,5,5,0.85); backdrop-filter: blur(6px); border-bottom: 1px solid #222; }
nav { display: flex; align-items: center; justify-content: center; padding: 16px 0; position: relative; }
.logo { font-size: 1.35rem; letter-spacing: 0.8px; font-weight: 800; color: var(--gold); font-family: Algerian, serif; }
.nav-left { position: absolute; left: 0; display: flex; align-items: center; }
.nav-right { position: absolute; right: 0; display: flex; align-items: center; }
.menu-tab-container { position: relative; }
.menu-tab { border: 1px solid #333; color: #fff; background: #111; border-radius: 8px; padding: 8px 12px; cursor: pointer; font-weight: 600; }
.menu-dropdown { display: none; position: absolute; top: 40px; left: 0; background: #101010; border: 1px solid #2a2a2a; border-radius: 8px; min-width: 180px; padding: 8px; box-shadow: 0 4px 18px rgba(0,0,0,0.35); }
.menu-dropdown a { display: block; color: #f0f0f0; text-decoration: none; margin: 6px 0; padding: 5px 8px; border-radius: 6px; }
.menu-dropdown a:hover { background: #1f1f1f; color: var(--gold); }
.menu-tab-container:hover .menu-dropdown { display: block; }
.menu { display: flex; gap: 18px; }
.menu a { color: #e6e6e6; text-decoration: none; font-size: .95rem; transition: .2s; }
.menu a:hover { color: var(--gold); }
@keyframes zoomInOut { 0% { background-size: 102%; } 50% { background-size: 100%; } 100% { background-size: 102%; } }
.hero { min-height: 80vh; display: grid; place-items: center; text-align: center; padding: 80px 0 60px; background: linear-gradient(to bottom, rgba(0,0,0,.5), rgba(0,0,0,.8)), url('logo.png') center/cover no-repeat fixed; background-size: cover; background-attachment: fixed; animation: zoomInOut 8s ease-in-out infinite; width: 100vw; margin-left: calc(-50vw + 50%); }
.hero h1 { font-size: clamp(2.2rem, 8vw, 4.5rem); letter-spacing: 1px; color: var(--gold); text-shadow: 0 0 18px rgba(255, 199, 0, .3); }
.hero p { margin-top: 12px; font-size: clamp(1rem, 2.2vw, 1.2rem); color: #f0f0f0; max-width: 650px; margin-inline: auto; }
.cta { margin-top: 22px; display: inline-flex; border-radius: 999px; border: 0; background: var(--gold); color: #060606; font-weight: 700; padding: 12px 24px; cursor: pointer; transition: .2s; }
.cta:hover { background: #fff; }
.section { padding: 70px 0; }
.section h2 { text-align: center; color: var(--gold); margin-bottom: 14px; font-size: clamp(1.7rem, 4vw, 2.6rem); font-family: Algerian, serif; font-weight: 900; letter-spacing: 2px; }
.section p { text-align: center; color: #c8c8c8; margin: 0 auto 24px; max-width: 760px; }
.cards { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 18px; }
.card { background: transparent; border: none; padding: 16px; transition: transform .2s; display: flex; flex-direction: column; align-items: center; text-align: center; }
.card img { width: 150px; height: 150px; border-radius: 50%; object-fit: cover; margin-bottom: 12px; }
.card h3 { margin: 0; color: #fff; }
.card small { color: #9a9a9a; display: block; margin-top: 4px; }
.features { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 14px; text-align: left; margin-top: 18px; }
.feature { background: #121212; border: 1px solid #222; border-radius: 10px; padding: 16px; }
.feature h4 { margin-bottom: 8px; color: var(--gold); }
#join .join-card { margin: 0 auto; width: min(620px, 100%); background: #0f0f0f; border: 1px solid #222; border-radius: 12px; padding: 20px; text-align: left; }
#join form { display: grid; gap: 10px; }
#join input, #join textarea { width: 100%; border-radius: 8px; border: 1px solid #2b2b2b; background: #111; color: #fff; padding: 10px; }
#join button { border: 0; background: var(--gold); color: #121212; padding: 11px 16px; border-radius: 8px; font-weight: 700; cursor: pointer; }
footer { padding: 18px 0; background: #0b0b0b; border-top: 1px solid #222; }
.footer-inner { display: flex; flex-wrap: wrap; gap: 8px; justify-content: space-between; align-items: center; }
.social { display: flex; gap: 10px; }
.social a { color: #060606; text-decoration: none; font-size: 0.9rem; background: var(--gold); padding: 10px 18px; border-radius: 999px; font-weight: 700; transition: .2s; }
.social a:hover { background: #fff; }
@media (max-width: 760px) { header { padding: 10px 0; } .menu { gap: 12px; flex-wrap: wrap; justify-content: center; } .section { padding: 50px 0; } }
.hidden { display: none; }
</style>
</head>
<body>
<header>
<div class="container">
<nav>
<div class="nav-left">
<div class="menu-tab-container">
<button class="menu-tab">☰ Menu</button>
<div class="menu-dropdown">
<a href="#home">Home</a>
<a href="#team">Team</a>
<a href="#achievements">Achievements</a>
<a href="#join">Join</a>
<a href="#contact">Contact</a>
</div>
</div>
</div>
<div class="logo">ROYAL E-SPORTS CLUB</div>
<div class="nav-right">
<a href="#home" style="display:flex; align-items:center;">
<img class="top-right-img" src="royal-bg.png" alt="Club Badge" style="width: 46px; height: 46px; border-radius: 999px; object-fit: cover; border: 2px solid #333;">
</a>
</div>
</nav>
</div>
</header>
<main id="home" class="container">
<section class="hero">
<a href="#join" class="cta" style="text-decoration: none;">Become A Royal Member</a>
</section>
<section class="section" id="team">
<h2>CLUB LEAD</h2>
<div class="cards">
<div class="card"><img src="jevine.png" style="width:150px; height:150px; border-radius:50%; object-fit:cover;"><h3>Jevine</h3><small>Founder</small></div>
<div class="card"><img src="messiah.png" style="width:150px; height:150px; border-radius:50%; object-fit:cover;"><h3>Joel</h3><small>Co-Founder</small></div>
<div class="card"><img src="brian.png" style="width:150px; height:150px; border-radius:50%; object-fit:cover;"><h3>Brian</h3><small>Co-Founder</small></div>
<div class="card"><img src="kratos.png" style="width:150px; height:150px; border-radius:50%; object-fit:cover;"><h3>Kratos</h3><small>Co-Founder</small></div>
</div>
</section>
<section class="section" id="achievements">
<h2>Our Achievements</h2>
<p>Every legend starts with a first match. We are building toward greatness.</p>
<div style="margin: 0 auto; max-width: 800px; border: 1px solid #333; background: linear-gradient(145deg, #111, #1d1d1d); border-radius: 14px; padding: 30px; text-align: center;">
<h3 style="font-size: clamp(1.3rem, 4vw, 2rem); color: var(--gold); letter-spacing: 0.8px; margin-bottom: 10px;">WE'RE JUST GETTING STARTED</h3>
<p style="color: #d0d0d0; margin: 0;">Tune in for upcoming tournaments, team growth, and our next big win.</p>
</div>
</section>
<section class="section" id="join">
<h2>Join The Team</h2>

<div class="join-card">
<form action="https://formsubmit.co/infororalesports1@gmail.com" method="POST">
<input type="text" placeholder="Full Name" name="Full Name" required>
<input type="text" placeholder="Player UID (example: ROYAL123)" name="Player UID" required>
<input type="email" placeholder="Email Address" name="Email Address" required>
<select id="game-select" name="Game" required style="width: 100%; border-radius: 8px; border: 1px solid #2b2b2b; background: #111; color: #fff; padding: 10px;">
<option value="Call of Duty Mobile">Call of Duty Mobile</option>
<option value="Blood Strike">Blood Strike</option>
<option value="PUBGM">PUBGM</option>
<option value="Free Fire">Free Fire</option>
<option value="Others">Others (please specify)</option>
</select>
<input type="text" id="other-game-input" placeholder="Specify the game name" name="Other Game" style="width: 100%; border-radius: 8px; border: 1px solid #2b2b2b; background: #111; color: #fff; padding: 10px;" class="hidden">
<textarea rows="4" placeholder="Tell us your rank, region, and why you want to join" name="Message"></textarea>
<input type="hidden" name="_captcha" value="false">
<input type="hidden" name="_next" value="https://yourdomain.com/success.html">
<button type="submit">Apply Now</button>
</form>
<script>
document.getElementById('game-select').addEventListener('change', function() {
  const otherInput = document.getElementById('other-game-input');
  if (this.value === 'Others') {
    otherInput.classList.remove('hidden');
    otherInput.required = true;
  } else {
    otherInput.classList.add('hidden');
    otherInput.required = false;
    otherInput.value = '';
  }
});
</script>
</div>
</section>
</main>
<footer id="contact">
<div class="container footer-inner">
<div><strong>Royal E-Sports Club</strong><br><small>Built for champions.</small></div>
<div class="social"><a href="https://discord.gg/4BSchUsJbb">Discord</a><a href="#">Instagram</a><a href="#">YouTube</a></div>
<div>© 2026 Royal E-Sports Club</div>
</div>
</footer>
</body>
</html>
