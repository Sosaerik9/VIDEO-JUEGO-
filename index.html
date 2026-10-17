<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <title>Tactical Ops & Fixed Weapon Switch</title>

  <!-- Three.js Engine -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>

  <style>
    :root {
      --cs-amber: #fca000;
      --cs-amber-glow: rgba(252, 160, 0, 0.4);
      --cs-dark-overlay: rgba(10, 12, 15, 0.95);
    }

    * { box-sizing: border-box; user-select: none; margin: 0; padding: 0; font-family: 'Tahoma', 'Segoe UI', sans-serif; }
    body, html { width: 100%; height: 100%; overflow: hidden; background: #000; color: #fff; }

    #game-container { width: 100vw; height: 100vh; position: absolute; top: 0; left: 0; z-index: 1; }

    .nvg-active {
      filter: sepia(90%) hue-rotate(40deg) saturate(200%) contrast(140%) brightness(85%);
    }

    /* Crosshair */
    #crosshair {
      position: absolute;
      top: 50%;
      left: 50%;
      width: 12px;
      height: 12px;
      transform: translate(-50%, -50%);
      pointer-events: none;
      z-index: 5;
    }
    #crosshair::before, #crosshair::after {
      content: '';
      position: absolute;
      background: rgba(252, 160, 0, 0.9);
    }
    #crosshair::before { top: 5px; left: -6px; width: 24px; height: 2px; }
    #crosshair::after { top: -6px; left: 5px; width: 2px; height: 24px; }

    /* Screen Overlays */
    .screen-overlay {
      position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: 10;
      display: flex; justify-content: center; align-items: center; background: var(--cs-dark-overlay);
      backdrop-filter: blur(5px);
    }

    .hidden { display: none !important; }

    .panel-box {
      background: rgba(15, 20, 26, 0.96);
      border: 1px solid #3d3d3d;
      border-top: 3px solid var(--cs-amber);
      padding: 30px;
      border-radius: 4px;
      width: 100%;
      max-width: 500px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.9);
      text-align: center;
    }

    h1 {
      font-size: 22px;
      color: var(--cs-amber);
      letter-spacing: 2px;
      margin-bottom: 5px;
      text-transform: uppercase;
    }

    .subtitle {
      font-size: 11px;
      color: #8a9ba8;
      margin-bottom: 20px;
      text-transform: uppercase;
      letter-spacing: 1px;
    }

    .auth-tabs {
      display: flex;
      margin-bottom: 20px;
      border-bottom: 2px solid #2f3640;
    }

    .auth-tab {
      flex: 1;
      padding: 10px;
      background: transparent;
      border: none;
      color: #8a9ba8;
      font-weight: bold;
      cursor: pointer;
      text-transform: uppercase;
      font-size: 12px;
      transition: all 0.2s;
    }

    .auth-tab.active {
      color: var(--cs-amber);
      border-bottom: 2px solid var(--cs-amber);
      margin-bottom: -2px;
    }

    .input-group {
      margin-bottom: 15px;
      text-align: left;
    }

    .input-group label {
      display: block;
      font-size: 11px;
      color: #a4b0be;
      margin-bottom: 5px;
      text-transform: uppercase;
    }

    .input-group input, .input-group select {
      width: 100%;
      padding: 12px 15px;
      background: #11161d;
      border: 1px solid #2f3640;
      border-radius: 3px;
      color: #dcdde1;
      font-size: 14px;
      outline: none;
    }

    .package-option {
      display: flex;
      align-items: center;
      background: #11161d;
      border: 1px solid #2f3640;
      padding: 10px 15px;
      border-radius: 3px;
      margin-bottom: 8px;
      cursor: pointer;
      text-align: left;
      font-size: 13px;
    }

    .package-option input { margin-right: 10px; }

    .btn {
      width: 100%;
      padding: 12px;
      background: var(--cs-amber);
      border: none;
      color: #000;
      font-weight: bold;
      font-size: 14px;
      border-radius: 3px;
      cursor: pointer;
      text-transform: uppercase;
      letter-spacing: 1px;
      margin-top: 10px;
      transition: all 0.2s;
    }
    .btn:hover { background: #ffb733; box-shadow: 0 0 12px var(--cs-amber-glow); }

    .btn-secondary {
      background: transparent;
      border: 1px solid #3d3d3d;
      color: #8a9ba8;
    }
    .btn-secondary:hover { background: rgba(255,255,255,0.05); color: #fff; }

    /* VGUI Team Select */
    .vgui-overlay {
      position: absolute; top: 0; left: 0; width: 100vw; height: 100vh; z-index: 25;
      background: rgba(10, 12, 15, 0.92); display: flex; justify-content: center; align-items: center;
    }
    .vgui-window {
      width: 820px; height: 540px; border: 1px solid #3d3d3d;
      background: rgba(15, 18, 22, 0.96); display: flex; flex-direction: column; padding: 25px;
      box-shadow: 0 0 35px #000; border-top: 3px solid var(--cs-amber);
    }
    .vgui-header {
      display: flex; align-items: center; gap: 12px; color: var(--cs-amber);
      font-size: 20px; font-weight: bold; letter-spacing: 1px;
      border-bottom: 1px solid rgba(252,160,0,0.3); padding-bottom: 12px; margin-bottom: 20px;
    }
    .vgui-body { display: flex; gap: 20px; flex: 1; }
    .vgui-menu-col { width: 320px; display: flex; flex-direction: column; gap: 10px; }
    .vgui-btn {
      background: rgba(30, 35, 40, 0.85); border: 1px solid #444; color: var(--cs-amber);
      padding: 14px; font-size: 13px; font-weight: bold; cursor: pointer; text-align: left;
      transition: all 0.15s; border-left: 4px solid var(--cs-amber);
    }
    .vgui-btn:hover { background: var(--cs-amber); color: #000; box-shadow: 0 0 12px var(--cs-amber-glow); }
    .vgui-info-box {
      flex: 1; border: 1px solid #333; background: rgba(5, 5, 5, 0.8); padding: 18px;
      color: var(--cs-amber); font-family: monospace; font-size: 12px; line-height: 1.6; overflow-y: auto;
    }

    /* MENÚ DE COMPRA F2 */
    #buy-menu-overlay {
      position: absolute; top: 0; left: 0; width: 100vw; height: 100vh; z-index: 30;
      background: rgba(10, 12, 15, 0.85); display: none; justify-content: flex-start; align-items: center; padding-left: 80px;
    }
    .buy-menu-box {
      width: 440px; background: rgba(15, 18, 22, 0.96); border: 1px solid #3d3d3d;
      border-top: 3px solid var(--cs-amber); padding: 20px; box-shadow: 0 0 30px #000;
    }
    .buy-menu-title {
      color: var(--cs-amber); font-size: 18px; font-weight: bold; margin-bottom: 15px;
      border-bottom: 1px solid rgba(252,160,0,0.3); padding-bottom: 8px;
    }
    .buy-category { font-size: 10px; color: #8a9ba8; text-transform: uppercase; margin-bottom: 8px; letter-spacing: 1px; }
    .buy-btn {
      width: 100%; background: rgba(30, 35, 40, 0.8); border: 1px solid #444; color: var(--cs-amber);
      padding: 10px 14px; font-size: 12px; font-weight: bold; cursor: pointer; text-align: left;
      margin-bottom: 6px; border-left: 3px solid var(--cs-amber); transition: all 0.1s;
    }
    .buy-btn:hover { background: var(--cs-amber); color: #000; box-shadow: 0 0 10px var(--cs-amber-glow); }

    /* HUD */
    #hud {
      position: absolute; top: 15px; left: 15px; right: 15px;
      display: flex; justify-content: space-between; align-items: flex-start;
      pointer-events: none; z-index: 6;
    }

    .hud-box {
      background: rgba(15, 22, 30, 0.85);
      border-left: 3px solid var(--cs-amber);
      padding: 10px 15px;
      border-radius: 3px;
    }

    .hud-label { font-size: 10px; color: #8a9ba8; text-transform: uppercase; }
    .hud-value { font-size: 18px; font-weight: bold; color: #dcdde1; }

    #faction-indicator {
      position: absolute; bottom: 25px; left: 20px;
      font-size: 12px; color: var(--cs-amber);
      background: rgba(15,22,30,0.85); padding: 6px 12px;
      border: 1px solid #3d3d3d; pointer-events: none; z-index: 6;
    }

    #reload-msg {
      position: absolute; bottom: 80px; left: 50%; transform: translateX(-50%);
      font-size: 14px; font-weight: bold; color: #ff4757; background: rgba(0,0,0,0.8);
      padding: 6px 15px; border: 1px solid #ff4757; display: none; z-index: 6;
    }

    #click-to-play {
      position: absolute; top: 0; left: 0; width: 100%; height: 100%;
      background: rgba(0,0,0,0.7); display: flex; justify-content: center;
      align-items: center; z-index: 7; cursor: pointer;
      font-size: 18px; font-weight: bold; color: var(--cs-amber); letter-spacing: 2px;
    }
  </style>
</head>
<body>

  <div id="game-container">
    <div id="crosshair" class="hidden"></div>

    <!-- HUD -->
    <div id="hud" class="hidden">
      <div class="hud-box">
        <div class="hud-label">Operador / Arma</div>
        <div id="hud-player" class="hud-value">Player1</div>
        <div id="hud-weapon-name" style="font-size: 11px; color: var(--cs-amber); margin-top:2px;">M4A1 GOLD</div>
      </div>

      <div class="hud-box" style="text-align: center;">
        <div class="hud-label">Salud</div>
        <div id="hud-hp" class="hud-value" style="color: #2ed573;">100%</div>
      </div>

      <div class="hud-box" style="text-align: right;">
        <div class="hud-label">Munición / Bajas</div>
        <div id="hud-ammo" class="hud-value" style="color: var(--cs-amber);">30 / 90</div>
        <div id="hud-score" style="font-size: 12px; color: #dcdde1;">Bajas: 0</div>
      </div>
    </div>

    <div id="reload-msg">¡CARGADOR VACÍO! PRESIONA [F3] O [R] PARA RECARGAR</div>
    <div id="faction-indicator" class="hidden">[N] NVG | [ESC] PAUSA | [F2] COMPRAS | [F3] RECARGAR</div>

    <div id="click-to-play" class="hidden">
      HAZ CLIC PARA TOMAR EL CONTROL DE CÁMARA (360°)
    </div>

    <!-- Screen 1: Auth (Login & Register) -->
    <div id="screen-auth" class="screen-overlay">
      <div class="panel-box">
        <h1>TACTICAL OPS 3D</h1>
        <div class="subtitle">Acceso de Operador CS / MW</div>

        <div class="auth-tabs">
          <button id="tab-register-btn" class="auth-tab active" onclick="switchAuthTab('register')">Registrarse</button>
          <button id="tab-login-btn" class="auth-tab" onclick="switchAuthTab('login')">Ingresar</button>
        </div>

        <form id="form-register" onsubmit="event.preventDefault(); handleRegister();">
          <div class="input-group">
            <label>Nombre de Operador</label>
            <input type="text" id="reg-name" placeholder="Ej. Ghost" required>
          </div>
          <div class="input-group">
            <label>Correo Electrónico</label>
            <input type="email" id="reg-email" placeholder="operador@tactical.com" required>
          </div>
          <button type="submit" class="btn">Entrar al Sistema</button>
        </form>

        <form id="form-login" class="hidden" onsubmit="event.preventDefault(); handleLogin();">
          <div class="input-group">
            <label>Correo Electrónico Registrado</label>
            <input type="email" id="login-email" placeholder="operador@tactical.com" required>
          </div>
          <button type="submit" class="btn">Entrar al Sistema</button>
        </form>
      </div>
    </div>

    <!-- Screen 2: PANEL RESELLER TOP UP -->
    <div id="screen-reseller" class="screen-overlay hidden">
      <div class="panel-box" style="max-width: 520px;">
        <h1>💼 PANEL RESELLER</h1>
        <div class="subtitle">TOP UP CALL OF DUTY MOBILE</div>

        <div style="background: #11161d; border: 1px solid #2f3640; padding: 12px; border-radius: 3px; margin-bottom: 15px; text-align: left;">
          <div style="font-size: 11px; color: #718093;">SALDO DISPONIBLE:</div>
          <div id="reseller-balance" style="font-size: 20px; font-weight: bold; color: #2ed573;">$150.00 USD</div>
        </div>

        <div class="input-group">
          <label>1. Ingresar Datos del Cliente (UID)</label>
          <input type="text" id="reseller-uid" value="678912345678910" placeholder="ID de Usuario (UID)">
        </div>

        <div class="input-group">
          <label>2. Seleccionar Paquete:</label>
          <label class="package-option">
            <input type="radio" name="topup_pkg" value="0.90" onchange="updateTotalCost(0.90)"> ( ) 80 CP ($0.90)
          </label>
          <label class="package-option">
            <input type="radio" name="topup_pkg" value="16.50" checked onchange="updateTotalCost(16.50)"> (*) 2,400 CP ($16.50)
          </label>
          <label class="package-option">
            <input type="radio" name="topup_pkg" value="4.80" onchange="updateTotalCost(4.80)"> ( ) Pase de Batalla ($4.80)
          </label>
        </div>

        <div style="text-align: left; margin: 15px 0; font-size: 14px; color: #dcdde1;">
          Costo Total de tu Saldo: <strong id="total-cost-display" style="color: var(--cs-amber);">$16.50 USD</strong>
        </div>

        <button onclick="processTopUp()" class="btn">🚀 PROCESAR RECARGA INMEDIATA</button>
        <button onclick="openTeamSelect()" class="btn btn-secondary" style="margin-top: 10px;">⚔️ IR A SELECCIÓN DE EQUIPO</button>
      </div>
    </div>

    <!-- Screen 3: SELECCIONAR EQUIPO -->
    <div class="vgui-overlay hidden" id="screen-team-select">
      <div class="vgui-window">
        <div class="vgui-header">
          <span>🎯 SELECCIONAR EQUIPO</span>
        </div>
        <div class="vgui-body">
          <div class="vgui-menu-col">
            <button class="vgui-btn" onclick="selectTeam('T')">1 FUERZAS TERRORISTAS</button>
            <button class="vgui-btn" onclick="selectTeam('CT')">2 FUERZAS ANTITERRORISTAS</button>
            <button class="vgui-btn" onclick="selectTeam('AUTO')">5 ASIGNACIÓN AUTOMÁTICA</button>
            <button class="vgui-btn" onclick="selectTeam('SPEC')">6 ASISTIR COMO ESPECTADOR</button>
          </div>
          <div class="vgui-info-box">
            Assault - Hostage Rescue<br>
            by CryptR (lmuur@dlc.fi)[cite: 3]<br><br>
            Counter-Terrorists: Rescue the hostages. Take out the Terrorists without jeopardizing the hostages[cite: 3].<br><br>
            Terrorists: Prevent Counter-Terrorist force from rescuing hostages[cite: 3].
          </div>
        </div>
      </div>
    </div>

    <!-- Screen 4: MENÚ DE COMPRA F2 -->
    <div id="buy-menu-overlay">
      <div class="buy-menu-box" id="buy-menu-content"></div>
    </div>

    <!-- Screen 5: Pause Menu (ESC) -->
    <div id="screen-pause" class="screen-overlay hidden">
      <div class="panel-box">
        <h1>MENÚ TÁCTICO DE PAUSA</h1>
        <div class="subtitle">Configuración de Misión</div>

        <button onclick="applySettingsAndResume()" class="btn">Continuar Jugando</button>
        <button onclick="openResellerPanel()" class="btn btn-secondary" style="margin-top: 10px;">💼 Abrir Panel Reseller</button>
      </div>
    </div>

    <!-- Screen 6: Game Over -->
    <div id="screen-gameover" class="screen-overlay hidden">
      <div class="panel-box">
        <h1 style="color: #ff4757;">MISIÓN FALLIDA</h1>
        <div class="subtitle">Abatido por fuego hostil</div>
        <button onclick="openTeamSelect()" class="btn" style="margin-top: 20px;">Reiniciar Partida</button>
      </div>
    </div>

  </div>

  <script>
    function getStoredPlayers() {
      return JSON.parse(localStorage.getItem('tactical_ops_v10_db') || '[]');
    }

    function savePlayerToDB(playerData) {
      let players = getStoredPlayers();
      let idx = players.findIndex(p => p.email === playerData.email);
      if (idx >= 0) players[idx] = { ...players[idx], ...playerData };
      else players.push(playerData);
      localStorage.setItem('tactical_ops_v10_db', JSON.stringify(players));
    }

    let currentUser = null;
    let score = 0;
    let playerHP = 100;
    let isPlaying = false;
    let isPaused = false;
    let isBuyMenuOpen = false;
    let isReloading = false;
    let nvgActive = false;
    let playerFaction = 'CT';

    let currentWeapon = {
      name: 'M4A1 GOLD',
      ammo: 30,
      maxAmmo: 30,
      reserve: 90,
      bulletSpeed: 4,
      damage: 1,
      color: 0xfca000
    };

    function switchAuthTab(tab) {
      const regBtn = document.getElementById('tab-register-btn');
      const logBtn = document.getElementById('tab-login-btn');
      const regForm = document.getElementById('form-register');
      const logForm = document.getElementById('form-login');

      if (tab === 'register') {
        regBtn.classList.add('active');
        logBtn.classList.remove('active');
        regForm.classList.remove('hidden');
        logForm.classList.add('hidden');
      } else {
        logBtn.classList.add('active');
        regBtn.classList.remove('active');
        logForm.classList.remove('hidden');
        regForm.classList.add('hidden');
      }
    }

    function handleRegister() {
      const name = document.getElementById('reg-name').value.trim();
      const email = document.getElementById('reg-email').value.trim();
      if (!name || !email) return;

      currentUser = { name, email, faction: 'CT', balance: 150.00, score: 0 };
      savePlayerToDB(currentUser);
      openResellerPanel();
    }

    function handleLogin() {
      const email = document.getElementById('login-email').value.trim();
      if (!email) return;

      const players = getStoredPlayers();
      const found = players.find(p => p.email === email);

      if (found) {
        currentUser = found;
        if (currentUser.balance === undefined) currentUser.balance = 150.00;
        openResellerPanel();
      } else {
        alert("No se encontró cuenta con este correo.");
      }
    }

    function openResellerPanel() {
      if (currentUser) {
        document.getElementById('reseller-balance').innerText = `$${(currentUser.balance || 150).toFixed(2)} USD`;
      }
      showScreen('screen-reseller');
    }

    function updateTotalCost(cost) {
      document.getElementById('total-cost-display').innerText = `$${cost.toFixed(2)} USD`;
    }

    function processTopUp() {
      const uid = document.getElementById('reseller-uid').value.trim();
      if (!uid) { alert("Ingresa el UID."); return; }

      currentUser.balance -= 16.50;
      savePlayerToDB(currentUser);
      document.getElementById('reseller-balance').innerText = `$${currentUser.balance.toFixed(2)} USD`;
      alert(`✅ Recarga procesada para UID ${uid}`);
    }

    function openTeamSelect() { showScreen('screen-team-select'); }

    function selectTeam(team) {
      playerFaction = team === 'AUTO' ? (Math.random() > 0.5 ? 'CT' : 'T') : team;
      startGame();
    }

    // --- MENÚ DE COMPRA F2 ---
    function openBuyMenu(category = 'main') {
      if (!isPlaying && category === 'main') return;
      isBuyMenuOpen = true;
      isPlaying = false;
      document.exitPointerLock();
      document.getElementById('buy-menu-overlay').style.display = 'flex';
      document.getElementById('click-to-play').classList.add('hidden');

      const content = document.getElementById('buy-menu-content');

      if (category === 'main') {
        content.innerHTML = `
          <div class="buy-menu-title">Menú de compra</div>
          <button class="buy-btn" onclick="openBuyMenu('pistols')">1 Pistolas</button>
          <button class="buy-btn" onclick="openBuyMenu('shotguns')">2 Escopetas</button>
          <button class="buy-btn" onclick="openBuyMenu('smgs')">3 Metralletas</button>
          <button class="buy-btn" onclick="openBuyMenu('rifles')">4 Rifles</button>
          <button class="buy-btn" onclick="openBuyMenu('heavy')">5 Ametralladoras pesadas</button>
          <button class="buy-btn" onclick="reloadAmmoSupply()">6 Recargar Munición Total</button>
          <button class="buy-btn" onclick="closeBuyMenu()" style="border-left-color: #ff4757; margin-top: 10px;">0 Cancelar</button>
        `;
      } else if (category === 'pistols') {
        content.innerHTML = `
          <div class="buy-menu-title">Pistolas</div>
          <button class="buy-btn" onclick="selectNewWeapon('Glock 18 Tactical', 20, 60, 3, 1, 0x0984e3)">1. Glock 18 Tactical</button>
          <button class="buy-btn" onclick="selectNewWeapon('Desert Eagle .50', 7, 35, 5, 2, 0xfca000)">2. Desert Eagle .50</button>
          <button class="buy-btn" onclick="openBuyMenu('main')" style="margin-top:10px;">0 Volver</button>
        `;
      } else if (category === 'shotguns') {
        content.innerHTML = `
          <div class="buy-menu-title">Escopetas</div>
          <button class="buy-btn" onclick="selectNewWeapon('SPAS-12 Combat', 8, 32, 4.5, 2.5, 0x636e72)">1. SPAS-12 Combat</button>
          <button class="buy-btn" onclick="openBuyMenu('main')" style="margin-top:10px;">0 Volver</button>
        `;
      } else if (category === 'smgs') {
        content.innerHTML = `
          <div class="buy-menu-title">Metralletas</div>
          <button class="buy-btn" onclick="selectNewWeapon('P90 Cyberpunk', 50, 150, 5, 1, 0x00cec9)">1. P90 Cyberpunk</button>
          <button class="buy-btn" onclick="openBuyMenu('main')" style="margin-top:10px;">0 Volver</button>
        `;
      } else if (category === 'rifles') {
        content.innerHTML = `
          <div class="buy-menu-title">Rifles</div>
          <button class="buy-btn" onclick="selectNewWeapon('M4A1 Gold', 30, 90, 4, 1, 0xfca000)">1. M4A1 Gold</button>
          <button class="buy-btn" onclick="selectNewWeapon('AWP Sniper', 10, 30, 7, 3, 0xff4757)">2. AWP Sniper Letal</button>
          <button class="buy-btn" onclick="openBuyMenu('main')" style="margin-top:10px;">0 Volver</button>
        `;
      } else if (category === 'heavy') {
        content.innerHTML = `
          <div class="buy-menu-title">Ametralladoras</div>
          <button class="buy-btn" onclick="selectNewWeapon('Minigun Vulcan', 100, 300, 6, 2, 0x2ed573)">1. Minigun Vulcan Destroyer</button>
          <button class="buy-btn" onclick="openBuyMenu('main')" style="margin-top:10px;">0 Volver</button>
        `;
      }
    }

    function selectNewWeapon(name, ammo, reserve, speed, damage, color) {
      currentWeapon = { name, ammo, maxAmmo: ammo, reserve, bulletSpeed: speed, damage, color };
      updateHUD();
      closeBuyMenu();
    }

    function reloadAmmoSupply() {
      currentWeapon.ammo = currentWeapon.maxAmmo;
      currentWeapon.reserve += 60;
      updateHUD();
      closeBuyMenu();
    }

    function executeManualReload() {
      if (isReloading || currentWeapon.ammo >= currentWeapon.maxAmmo) return;
      if (currentWeapon.reserve <= 0) return;

      isReloading = true;
      const reloadEl = document.getElementById('reload-msg');
      reloadEl.style.display = 'block';
      reloadEl.innerText = "🔄 RECARGANDO CARTUCHOS...";

      setTimeout(() => {
        let needed = currentWeapon.maxAmmo - currentWeapon.ammo;
        let take = Math.min(needed, currentWeapon.reserve);
        currentWeapon.ammo += take;
        currentWeapon.reserve -= take;
        isReloading = false;
        reloadEl.style.display = 'none';
        updateHUD();
      }, 1000);
    }

    function closeBuyMenu() {
      isBuyMenuOpen = false;
      document.getElementById('buy-menu-overlay').style.display = 'none';
      isPlaying = true;
      // Reactivar control de cámara fluido sin bloqueos
      setTimeout(() => {
        document.body.requestPointerLock();
      }, 50);
    }

    function updateHUD() {
      document.getElementById('hud-weapon-name').innerText = currentWeapon.name;
      document.getElementById('hud-ammo').innerText = `${currentWeapon.ammo} / ${currentWeapon.reserve}`;
      document.getElementById('hud-score').innerText = `Bajas: ${score}`;
    }

    function showScreen(id) {
      document.querySelectorAll('.screen-overlay, .vgui-overlay').forEach(s => s.classList.add('hidden'));
      document.getElementById('buy-menu-overlay').style.display = 'none';
      document.getElementById('hud').classList.add('hidden');
      document.getElementById('crosshair').classList.add('hidden');
      document.getElementById('click-to-play').classList.add('hidden');
      document.getElementById('faction-indicator').classList.add('hidden');
      
      if (id === 'screen-team-select') {
        document.getElementById('screen-team-select').classList.remove('hidden');
      } else if (id) {
        document.getElementById(id).classList.remove('hidden');
      }
    }

    function startGame() {
      isPaused = false;
      isBuyMenuOpen = false;
      showScreen(null);
      document.getElementById('hud').classList.remove('hidden');
      document.getElementById('crosshair').classList.remove('hidden');
      document.getElementById('click-to-play').classList.remove('hidden');
      document.getElementById('faction-indicator').classList.remove('hidden');
      
      document.getElementById('hud-player').innerText = currentUser ? currentUser.name : 'Player1';
      score = 0;
      playerHP = 100;
      updateHUD();

      isPlaying = true;
      resetWorld();
    }

    // Keybindings
    window.addEventListener('keydown', e => {
      if (e.key === 'Escape') {
        if (isBuyMenuOpen) closeBuyMenu();
        else if (isPlaying) openPauseMenu();
      }
      if (e.key === 'F2' || e.key === 'f2') {
        e.preventDefault();
        if (isPlaying) openBuyMenu('main');
      }
      if (e.key === 'F3' || e.key === 'f3' || e.key === 'r' || e.key === 'R') {
        e.preventDefault();
        if (isPlaying && !isBuyMenuOpen) executeManualReload();
      }
    });

    // --- MOTOR 3D & COMBATE ---
    const container = document.getElementById('game-container');
    const scene = new THREE.Scene();
    scene.background = new THREE.Color(0x111622);
    scene.fog = new THREE.FogExp2(0x111622, 0.015);

    const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
    const renderer = new THREE.WebGLRenderer({ antialias: true });
    renderer.setSize(window.innerWidth, window.innerHeight);
    container.appendChild(renderer.domElement);

    scene.add(new THREE.AmbientLight(0xffffff, 0.4));
    const dirLight = new THREE.DirectionalLight(0xb2bec3, 0.7);
    dirLight.position.set(40, 80, 40);
    scene.add(dirLight);

    const floorGeo = new THREE.PlaneGeometry(350, 350);
    const floorMat = new THREE.MeshStandardMaterial({ color: 0x22252a });
    const floor = new THREE.Mesh(floorGeo, floorMat);
    floor.rotation.x = -Math.PI / 2;
    scene.add(floor);

    for (let i = 0; i < 35; i++) {
      const boxGeo = new THREE.BoxGeometry(3, 3, 3);
      const boxMat = new THREE.MeshStandardMaterial({ color: 0x8b5a2b });
      const box = new THREE.Mesh(boxGeo, boxMat);
      box.position.set((Math.random() - 0.5) * 180, 1.5, (Math.random() - 0.5) * 180);
      scene.add(box);
    }

    const weaponGroup = new THREE.Group();
    const gunBodyGeo = new THREE.BoxGeometry(0.12, 0.18, 0.7);
    const gunMat = new THREE.MeshStandardMaterial({ color: 0x2f3640, metalness: 0.8 });
    const gunBody = new THREE.Mesh(gunBodyGeo, gunMat);
    weaponGroup.add(gunBody);

    const barrel = new THREE.Mesh(new THREE.CylinderGeometry(0.025, 0.025, 0.5), gunMat);
    barrel.rotation.x = Math.PI / 2;
    barrel.position.set(0, 0.03, -0.45);
    weaponGroup.add(barrel);

    camera.add(weaponGroup);
    weaponGroup.position.set(0.24, -0.22, -0.5);
    scene.add(camera);

    let moveForward = false, moveBackward = false, moveLeft = false, moveRight = false;
    let yaw = 0, pitch = 0;

    const clickToPlayEl = document.getElementById('click-to-play');
    clickToPlayEl.addEventListener('click', () => {
      if (!isPaused && !isBuyMenuOpen) document.body.requestPointerLock();
    });

    document.addEventListener('pointerlockchange', () => {
      if (document.pointerLockElement === document.body) {
        clickToPlayEl.classList.add('hidden');
      } else if (isPlaying && !isPaused && !isBuyMenuOpen) {
        clickToPlayEl.classList.remove('hidden');
      }
    });

    document.addEventListener('mousemove', (e) => {
      if (document.pointerLockElement === document.body && isPlaying) {
        yaw -= e.movementX * 0.0022;
        pitch -= e.movementY * 0.0022;
        pitch = Math.max(-Math.PI / 2.2, Math.min(Math.PI / 2.2, pitch));
      }
    });

    document.addEventListener('keydown', e => {
      if (isPlaying && !isBuyMenuOpen) {
        if (e.key === 'w' || e.key === 'W') moveForward = true;
        if (e.key === 's' || e.key === 'S') moveBackward = true;
        if (e.key === 'a' || e.key === 'A') moveLeft = true;
        if (e.key === 'd' || e.key === 'D') moveRight = true;
        if (e.key === 'n' || e.key === 'N') {
          nvgActive = !nvgActive;
          document.getElementById('game-container').classList.toggle('nvg-active', nvgActive);
        }
      }
    });

    document.addEventListener('keyup', e => {
      if (e.key === 'w' || e.key === 'W') moveForward = false;
      if (e.key === 's' || e.key === 'S') moveBackward = false;
      if (e.key === 'a' || e.key === 'A') moveLeft = false;
      if (e.key === 'd' || e.key === 'D') moveRight = false;
    });

    const bullets = [];
    const enemyBullets = [];
    const enemies = [];

    // Disparar Jugador
    document.addEventListener('mousedown', (e) => {
      if (document.pointerLockElement === document.body && e.button === 0 && isPlaying && !isReloading && !isBuyMenuOpen) {
        if (currentWeapon.ammo <= 0) {
          const reloadMsg = document.getElementById('reload-msg');
          reloadMsg.style.display = 'block';
          reloadMsg.innerText = "⚠️ ¡CARGADOR VACÍO! PRESIONA [F3] PARA RECARGAR";
          return;
        }

        currentWeapon.ammo--;
        updateHUD();

        const bullet = new THREE.Mesh(
          new THREE.SphereGeometry(0.1),
          new THREE.MeshBasicMaterial({ color: currentWeapon.color })
        );
        bullet.position.copy(camera.position);
        const dir = new THREE.Vector3(0, 0, -1).applyQuaternion(camera.quaternion);

        bullet.userData = { vel: dir.multiplyScalar(currentWeapon.bulletSpeed), life: 80, damage: currentWeapon.damage };
        scene.add(bullet);
        bullets.push(bullet);
        weaponGroup.position.z += 0.05;
      }
    });

    function spawnEnemy() {
      if (!isPlaying || enemies.length >= 10) return;
      const enemy = new THREE.Mesh(
        new THREE.CylinderGeometry(0.8, 0.8, 2.2),
        new THREE.MeshStandardMaterial({ color: playerFaction === 'CT' ? 0xd63031 : 0x0984e3 })
      );
      const angle = Math.random() * Math.PI * 2;
      const dist = 35 + Math.random() * 25;
      enemy.position.set(camera.position.x + Math.cos(angle) * dist, 1.1, camera.position.z + Math.sin(angle) * dist);
      enemy.userData = { hp: 2, shootCooldown: Math.random() * 60 + 30 };
      scene.add(enemy);
      enemies.push(enemy);
    }
    setInterval(spawnEnemy, 2500);

    function resetWorld() {
      camera.position.set(0, 1.7, 0);
      yaw = 0; pitch = 0;
      enemies.forEach(e => scene.remove(e));
      bullets.forEach(b => scene.remove(b));
      enemyBullets.forEach(b => scene.remove(b));
      enemies.length = 0; bullets.length = 0; enemyBullets.length = 0;
    }

    const clock = new THREE.Clock();

    function animate() {
      requestAnimationFrame(animate);

      if (isPlaying) {
        const delta = clock.getDelta();
        camera.quaternion.setFromAxisAngle(new THREE.Vector3(0, 1, 0), yaw);
        camera.quaternion.multiply(new THREE.Quaternion().setFromAxisAngle(new THREE.Vector3(1, 0, 0), pitch));

        const moveDir = new THREE.Vector3();
        if (moveForward) moveDir.z -= 1;
        if (moveBackward) moveDir.z += 1;
        if (moveLeft) moveDir.x -= 1;
        if (moveRight) moveDir.x += 1;
        moveDir.normalize();
        moveDir.applyQuaternion(new THREE.Quaternion().setFromAxisAngle(new THREE.Vector3(0, 1, 0), yaw));

        camera.position.addScaledVector(moveDir, 12 * delta);
        camera.position.y = 1.7;
        weaponGroup.position.z += (-0.5 - weaponGroup.position.z) * 0.1;

        // Actualizar balas del jugador
        for (let i = bullets.length - 1; i >= 0; i--) {
          const b = bullets[i];
          b.position.add(b.userData.vel);
          b.userData.life--;

          for (let j = enemies.length - 1; j >= 0; j--) {
            const e = enemies[j];
            if (b.position.distanceTo(e.position) < 1.6) {
              e.userData.hp -= b.userData.damage;
              scene.remove(b);
              bullets.splice(i, 1);

              if (e.userData.hp <= 0) {
                scene.remove(e);
                enemies.splice(j, 1);
                score += 100;
                updateHUD();
              }
              break;
            }
          }
          if (b.userData.life <= 0) { scene.remove(b); bullets.splice(i, 1); }
        }

        // IA Bots Enemigos
        for (let i = enemies.length - 1; i >= 0; i--) {
          const e = enemies[i];
          const dir = new THREE.Vector3().subVectors(camera.position, e.position);
          dir.y = 0;
          const dist = dir.length();
          dir.normalize();

          if (dist > 12) e.position.addScaledVector(dir, 4 * delta);

          e.userData.shootCooldown--;
          if (e.userData.shootCooldown <= 0 && dist < 35) {
            e.userData.shootCooldown = 90;
            const eb = new THREE.Mesh(new THREE.SphereGeometry(0.08), new THREE.MeshBasicMaterial({ color: 0xff4757 }));
            eb.position.copy(e.position);
            eb.position.y += 0.5;
            eb.userData = { vel: new THREE.Vector3().subVectors(camera.position, e.position).normalize().multiplyScalar(1.5), life: 100 };
            scene.add(eb);
            enemyBullets.push(eb);
          }
        }
      }
      renderer.render(scene, camera);
    }
    animate();

    window.addEventListener('resize', () => {
      camera.aspect = window.innerWidth / window.innerHeight;
      camera.updateProjectionMatrix();
      renderer.setSize(window.innerWidth, window.innerHeight);
    });
  </script>
</body>
</html>
