<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Choose Your Aura</title>
<style>
  body { 
    font-family: Arial, sans-serif; 
    background: #87CEEB; /* Sky Blue background */
    margin:0; padding:0; 
  }

  .top-details { 
    background: #fff; 
    color: #000; 
    text-align:center; 
    padding:10px 0; 
    font-size:16px; 
    font-weight:bold; 
    animation: pulse 3s infinite;
  }

  @keyframes pulse {
    0%,100%{transform:scale(1);}
    50%{transform:scale(1.05);}
  }

  .main-container{
    background: transparent; 
    padding:0 0 40px 0;
    margin: 0 auto;
  }

  .top-bar { 
    background: #87CEEB; 
    color:white; 
    padding:10px 20px; 
    font-size:18px; 
    display:flex; 
    gap:10px; 
    box-shadow: 0 2px 10px rgba(0,0,0,0.3);
  }

  .top-bar button { 
    color:white; font-weight:bold; padding:6px 12px; border-radius:10px; 
    background: #fff; 
    border:none; cursor:pointer; transition: all 0.3s;
    box-shadow: 0 0 5px #FFD700, 0 0 10px #FFFF00; /* subtle glow */
    animation: glowButton 2s infinite alternate;
  }

  .top-bar button:hover { 
    background: #00BFFF; 
    transform: scale(1.1) rotate(5deg);
    box-shadow: 0 0 15px #FFD700, 0 0 25px #FFFF00, 0 0 35px #FFD700;
  }

  @keyframes glowButton {
    0% { box-shadow: 0 0 5px #FFD700, 0 0 10px #FFFF00; }
    50% { box-shadow: 0 0 10px #FFD700, 0 0 20px #FFFF00; }
    100% { box-shadow: 0 0 5px #FFD700, 0 0 10px #FFFF00; }
  }

  header { 
    background: #fff; 
    color:#000; 
    padding:40px 20px; 
    text-align:center; 
    line-height:1.2; 
  }

  .animated-title {
    font-size: 48px;
    font-weight: bold;
    background: linear-gradient(90deg, red, white, blue, white);
    background-size: 300% 100%;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    animation: fireIceGlow 5s linear infinite, lightningGlow 2s infinite alternate;
    display: inline-block;
    text-shadow: 0 0 10px rgba(255,255,255,0.5), 0 0 20px rgba(0,191,255,0.3);
  }

  @keyframes fireIceGlow {
    0% { background-position: 0% 0%; }
    25% { background-position: 50% 0%; }
    50% { background-position: 100% 0%; }
    75% { background-position: 50% 0%; }
    100% { background-position: 0% 0%; }
  }

  @keyframes lightningGlow {
    0% { text-shadow: 0 0 5px #fff, 0 0 10px #00BFFF; }
    50% { text-shadow: 0 0 20px #fff, 0 0 30px #00BFFF; }
    100% { text-shadow: 0 0 5px #fff, 0 0 10px #00BFFF; }
  }

  .sub-header { font-size:22px; font-weight:normal; margin-top:5px; color:#000; }

  .container { max-width:900px; margin:40px auto; padding:0 20px; }

  .card { 
    background: #fff; 
    padding:20px; 
    margin-bottom:25px; 
    border-radius:20px; 
    box-shadow: 0 8px 20px rgba(0,0,0,0.3); 
    color:#000; 
    transition: transform 0.5s, box-shadow 0.5s, opacity 1s;
    opacity: 0;
    animation: glowCard 2s infinite alternate;
  }

  .card.visible { opacity: 1; }

  .card:hover { transform: scale(1.05); box-shadow: 0 12px 25px rgba(0,0,0,0.5); }

  .card h2 { color:#87CEEB; margin-top:0; text-shadow: 1px 1px 2px #fff; }

  .editable { min-height:80px; padding:10px; border-radius:10px; background: rgba(255,255,255,0.7); border:1px solid #87CEEB; color:#000; }

  .button { 
    display:inline-block; 
    background: #87CEEB; 
    color:white; 
    padding:10px 25px; 
    margin-top:10px; 
    border:none; 
    border-radius:10px; 
    cursor:pointer; 
    font-weight:bold; 
    text-align:center; 
    text-decoration:none; 
    transition: all 0.3s;
    box-shadow: 0 0 5px #FFD700, 0 0 10px #FFFF00; /* subtle yellow glow */
    animation: glowButton 2s infinite alternate;
  }

  .button:hover { 
    background:#00BFFF; 
    color:#fff;
    transform: scale(1.1) rotate(5deg);
    box-shadow: 0 0 15px #FFD700, 0 0 25px #FFFF00, 0 0 35px #FFD700; /* stronger glow on hover */
  }

  @keyframes glowCard {
    0% { box-shadow: 0 0 10px #FFD700; }
    50% { box-shadow: 0 0 20px #FFFF00; }
    100% { box-shadow: 0 0 10px #FFD700; }
  }

  #modal { display:none; position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.6); justify-content:center; align-items:center; }
  #modal-content-container { 
    background:#fff; 
    padding:30px; 
    border-radius:20px; 
    max-width:600px; 
    width:90%; 
    position:relative; 
    max-height:80%; 
    overflow-y:auto; 
    color: #000;
  }
  #modal-close { position:absolute; top:10px; right:15px; font-size:20px; cursor:pointer; color:#ff3333; }
</style>
</head>
<body>

<div class="top-details">
  🚀 Welcome to Choose Your Aura! Latest update 0.0.1 coming in February. 🌟 Join the community, explore aura types, check weekly challenges, and discover secrets! 🎉
</div>

<div class="main-container">

  <div class="top-bar">
    <button onclick="openHomeModal()">Home</button>
  </div>

  <header>
    <span class="animated-title">Choose Your Aura</span>
    <div class="sub-header">Updates & News</div>
  </header>

  <div class="container">
    <!-- Latest Updates -->
    <div class="card">
      <h2>Latest Updates ⚡</h2>
      <div class="editable">
        <p>Version 0.0.1 released!</p>
        <ul>
          <li>Minor bug fixes</li>
          <li>Improved aura visuals</li>
          <li>Performance improvements</li>
        </ul>
      </div>
      <button class="button" onclick="openModal('latest')">See Latest</button>
    </div>

    <!-- News -->
    <div class="card">
      <h2>News 📰</h2>
      <div class="editable">
        <p>New feature announcements coming soon!</p>
        <ul>
          <li>Community events planned</li>
          <li>Special rewards for players</li>
          <li>Developer Q&A scheduled</li>
        </ul>
      </div>
      <button class="button" onclick="openModal('news')">See News</button>
    </div>

    <!-- Events -->
    <div class="card">
      <h2>Events 🎉</h2>
      <div class="editable">
        <p>Upcoming game events:</p>
        <ul>
          <li>Weekly aura challenges</li>
          <li>Special holiday events</li>
          <li>Competitions with rewards</li>
        </ul>
      </div>
      <button class="button" onclick="openModal('events')">See Events</button>
    </div>

    <!-- Updates -->
    <div class="card">
      <h2>Updates 🔄</h2>
      <div class="editable">
        <p>Planned updates for next versions:</p>
        <ul>
          <li>New levels and maps</li>
          <li>Enhanced aura effects</li>
          <li>Bug fixes and optimizations</li>
        </ul>
      </div>
      <button class="button" onclick="openModal('updates')">See Updates</button>
    </div>

    <!-- Coming -->
    <div class="card">
      <h2>Coming 🎯</h2>
      <div class="editable">
        <p><strong>The update 0.0.1</strong> will come in <em>February</em>.</p>
        <p>Features included:</p>
        <ul>
          <li>New map area</li>
          <li>Special aura effects</li>
          <li>Bug fixes from previous version</li>
        </ul>
        <p>Stay tuned for more news and tips! 🌟</p>
      </div>
      <button class="button" onclick="openModal('coming')">See Coming</button>
    </div>
  </div>
</div>

<!-- Hidden Home content -->
<div id="home-content" style="display:none; color:#000; animation: glowCard 2s infinite alternate;">
  <h2>Welcome to Choose Your Aura 🌟</h2>
  <p>On the Home page you can:</p>
  <ul>
    <li>✨ Discover your unique aura in the game world.</li>
    <li>📰 Check all latest updates and news.</li>
    <li>🎉 View upcoming events and special updates.</li>
    <li>💡 Learn tips and tricks for aura powers.</li>
    <li>🌟 Explore aura types: Fire, Ice, Lightning.</li>
    <li>🎮 Participate in weekly challenges and earn rewards.</li>
    <li>📢 Connect with the community and share achievements.</li>
    <li>🗺️ Unlock new maps and explore hidden secrets.</li>
    <li>🔥❄️⚡ Experiment with aura combinations and effects.</li>
  </ul>
  <p>Explore, play, and enjoy your aura adventure! 🚀</p>
</div>

<!-- Modal -->
<div id="modal">
  <div id="modal-content-container">
    <span id="modal-close" onclick="closeModal()">×</span>
    <h2 id="modal-title"></h2>
    <div id="modal-text"></div>
  </div>
</div>

<script>
const cards = document.querySelectorAll('.card');
window.addEventListener('scroll', () => {
  const triggerBottom = window.innerHeight / 5 * 4;
  cards.forEach(card => {
    const cardTop = card.getBoundingClientRect().top;
    if(cardTop < triggerBottom){
      card.classList.add('visible');
    }
  });
});

function openModal(section){
  let title='', content='';
  if(section==='latest'){title='Latest Updates'; content=document.querySelector('.card:nth-child(1) .editable').innerHTML;}
  else if(section==='news'){title='News'; content=document.querySelector('.card:nth-child(2) .editable').innerHTML;}
  else if(section==='events'){title='Events'; content=document.querySelector('.card:nth-child(3) .editable').innerHTML;}
  else if(section==='updates'){title='Updates'; content=document.querySelector('.card:nth-child(4) .editable').innerHTML;}
  else if(section==='coming'){title='Coming'; content=document.querySelector('.card:nth-child(5) .editable').innerHTML;}
  document.getElementById('modal-title').innerHTML=title;
  document.getElementById('modal-text').innerHTML=content;
  document.getElementById('modal').style.display='flex';
}

function openHomeModal(){
  document.getElementById('modal-title').innerHTML="Home";
  document.getElementById('modal-text').innerHTML=document.getElementById('home-content').innerHTML;
  document.getElementById('modal').style.display='flex';
}

function closeModal(){document.getElementById('modal').style.display='none';}
</script>

</body>
</html>

