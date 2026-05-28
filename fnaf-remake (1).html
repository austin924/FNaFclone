<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Five Nights at Freddy's - 3D</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Share+Tech+Mono&display=swap');
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { background: #000; overflow: hidden; font-family: 'Share Tech Mono', 'Courier New', monospace; }
        #canvas { display: block; }

        /* ---- HUD ---- */
        #hud { position: fixed; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: 10; }

        #time-display {
            position: absolute; top: 18px; left: 50%; transform: translateX(-50%);
            color: #ffe0b0; font-size: 32px; font-weight: bold;
            text-shadow: 0 0 12px #ff8800, 0 0 30px #ff4400;
            letter-spacing: 2px;
        }
        #night-display {
            position: absolute; top: 58px; left: 50%; transform: translateX(-50%);
            color: #aaa8c0; font-size: 15px; letter-spacing: 3px; text-transform: uppercase;
        }

        /* Power */
        #power-wrap {
            position: absolute; bottom: 70px; left: 20px;
        }
        #power-label { color: #aaffaa; font-size: 13px; margin-bottom: 5px; text-shadow: 0 0 8px #00ff00; }
        #power-bar-container {
            width: 220px; height: 16px; background: #0a0a0a;
            border: 1px solid #334433; border-radius: 3px; overflow: hidden;
        }
        #power-bar {
            height: 100%; width: 100%; background: #00ff44;
            transition: width 0.4s, background 0.4s;
            box-shadow: 0 0 8px currentColor;
        }
        #power-display { color: #aaffaa; font-size: 13px; margin-top: 4px; }

        /* Door/Light buttons */
        #left-controls, #right-controls {
            position: absolute; top: 50%; transform: translateY(-50%);
            pointer-events: all; display: flex; flex-direction: column; gap: 8px;
        }
        #left-controls { left: 18px; }
        #right-controls { right: 18px; }

        .door-btn, .light-btn {
            background: rgba(10,10,20,0.85);
            border: 1px solid #445566;
            color: #99aacc; padding: 10px 14px;
            font-size: 12px; cursor: pointer; border-radius: 6px;
            font-family: inherit; text-transform: uppercase; letter-spacing: 1px;
            min-width: 100px; transition: all 0.15s;
            backdrop-filter: blur(4px);
            box-shadow: 0 2px 8px rgba(0,0,0,0.5);
        }
        .door-btn:hover { border-color: #ff6644; color: #ffaa88; background: rgba(40,10,10,0.9); }
        .light-btn:hover { border-color: #ffee44; color: #ffee88; background: rgba(30,30,10,0.9); }
        .door-btn.active { background: rgba(60,5,5,0.95); border-color: #ff3300; color: #ff8877; box-shadow: 0 0 12px #ff330055; }
        .light-btn.active { background: rgba(40,40,5,0.95); border-color: #ffee00; color: #ffee88; box-shadow: 0 0 12px #ffee0055; }

        .btn-icon { display: block; font-size: 18px; margin-bottom: 2px; }
        .btn-label { display: block; font-size: 10px; }

        /* Camera tab at bottom */
        #cam-tab:hover { background: rgba(10,25,55,0.98) !important; border-color: #66aaff !important; box-shadow: 0 -5px 28px #0055aaaa !important; }

        /* Map rooms */
        .map-room { position:absolute;border:1px solid #1a4422;background:rgba(0,18,10,0.75);color:#44aa66;font-size:9px;text-align:center;cursor:pointer;display:flex;align-items:center;justify-content:center;flex-direction:column;transition:all 0.15s;border-radius:2px;padding:2px;line-height:1.3; }
        .map-room:hover { border-color:#44ff88;background:rgba(0,35,18,0.9); }
        .map-room.map-active { border-color:#00ff88!important;background:rgba(0,70,38,0.95)!important;box-shadow:0 0 8px #00ff8866 inset,0 0 6px #00ff88;color:#00ffaa!important; }
        .map-room .mrn { font-size:10px;font-weight:bold;display:block;color:#66ff99; }
        .map-room.map-active .mrn { color:#00ffcc; }

        /* ---- CAMERA OVERLAY ---- */
        #camera-overlay {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,5,10,0.96); z-index: 20;
            display: none; flex-direction: column;
            align-items: center; justify-content: flex-start;
            padding: 12px 0; overflow-y: auto;
        }
        #camera-overlay.visible { display: flex; }

        #cam-header {
            width: 100%; max-width: 960px; padding: 0 16px;
            display: flex; align-items: center; justify-content: space-between;
            margin-bottom: 12px;
        }
        #camera-title {
            color: #00ff88; font-size: 16px; letter-spacing: 3px;
            text-shadow: 0 0 10px #00ff88;
        }
        #close-cameras {
            background: rgba(30,30,50,0.9); border: 1px solid #445566;
            color: #aabbcc; padding: 8px 20px;
            cursor: pointer; font-family: inherit; border-radius: 5px;
            font-size: 13px; letter-spacing: 1px; transition: all 0.2s;
        }
        #close-cameras:hover { border-color: #88aacc; color: #fff; }

        /* Camera main layout: big preview + grid */
        #cam-main {
            width: 100%; max-width: 960px; padding: 0 16px;
            display: flex; gap: 16px; align-items: flex-start;
        }

        /* Big preview */
        #cam-preview-wrap {
            flex: 1; min-width: 0;
            border: 2px solid #224433; border-radius: 6px;
            background: #000; overflow: hidden;
            position: relative;
        }
        #cam-preview {
            width: 100%; display: block;
            image-rendering: pixelated;
        }
        #cam-preview-label {
            position: absolute; bottom: 8px; left: 10px;
            color: #00ff88; font-size: 12px;
            text-shadow: 0 0 6px #00ff88;
        }

        /* Camera grid */
        #camera-grid {
            display: grid; grid-template-columns: repeat(3, 1fr);
            gap: 8px; width: 280px; flex-shrink: 0;
        }
        .cam-button {
            background: rgba(5,12,20,0.9); border: 1px solid #223344;
            color: #8899aa; padding: 10px 6px;
            cursor: pointer; font-family: inherit;
            font-size: 11px; text-align: center;
            transition: all 0.15s; border-radius: 5px;
            line-height: 1.4;
        }
        .cam-button:hover { background: rgba(10,20,35,0.95); border-color: #446688; color: #aaccee; }
        .cam-button.active { background: rgba(0,25,15,0.95); border-color: #00ff88; color: #00ffaa; box-shadow: 0 0 8px #00ff8844; }
        .cam-name { font-size: 11px; font-weight: bold; display: block; }
        .cam-room { font-size: 10px; color: #556677; display: block; margin-top: 1px; }
        .cam-status { display: block; font-size: 10px; margin-top: 4px; padding: 2px 4px; border-radius: 2px; }
        .cam-status.clear { color: #44ff88; }
        .cam-status.alert { color: #ff4444; background: rgba(255,0,0,0.1); animation: alertBlink 0.6s infinite; }

        @keyframes alertBlink { 0%,100%{opacity:1} 50%{opacity:0.4} }

        /* ---- START SCREEN ---- */
        #start-screen {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            z-index: 100; display: flex; flex-direction: column;
            align-items: center; justify-content: center;
            overflow: hidden;
        }
        #menu-bg-canvas {
            position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            z-index: 0;
        }
        .menu-content {
            position: relative; z-index: 2;
            display: flex; flex-direction: column; align-items: center;
        }
        #start-screen h1 {
            color: #ff6600; font-size: clamp(22px, 5vw, 64px); text-align: center;
            text-shadow: 0 0 20px #ff3300, 0 0 60px #ff6600aa, 0 0 120px #ff000055;
            margin-bottom: 6px; letter-spacing: 5px; animation: flicker 4s infinite;
            font-family: inherit; line-height: 1.1;
        }
        .subtitle {
            color: #aa8855; font-size: 13px; margin-bottom: 44px; letter-spacing: 4px;
            text-shadow: 0 0 10px #884400;
        }
        .night-select-label { color: #556677; font-size: 12px; margin-bottom: 12px; letter-spacing: 3px; }
        #start-btn {
            background: linear-gradient(180deg, rgba(80,30,0,0.6) 0%, rgba(40,10,0,0.8) 100%);
            border: 2px solid #ff6600; color: #ff9933; padding: 15px 60px; font-size: 21px; cursor: pointer;
            font-family: inherit; text-transform: uppercase; letter-spacing: 4px;
            transition: all 0.3s; margin-top: 22px; border-radius: 3px;
            box-shadow: 0 0 20px #ff440066, inset 0 0 20px rgba(255,80,0,0.1);
        }
        #start-btn:hover {
            background: linear-gradient(180deg, #ff6600 0%, #cc3300 100%);
            color: #000; box-shadow: 0 0 50px #ff6600cc, 0 0 100px #ff330066;
            transform: scale(1.04);
        }
        .night-btn {
            background: rgba(10,5,0,0.7); border: 1px solid #443322;
            color: #665544; padding: 7px 18px; font-size: 13px; cursor: pointer;
            font-family: inherit; margin: 4px; transition: all 0.2s; border-radius: 3px;
            letter-spacing: 1px;
        }
        .night-btn:hover, .night-btn.selected {
            border-color: #ff7733; color: #ffaa66;
            background: rgba(80,30,0,0.5);
            box-shadow: 0 0 10px #ff440033;
        }
        .keys-hint { color: #2a2010; font-size: 11px; margin-top: 28px; letter-spacing: 1px; }

        #freddy-logo { width: 120px; height: 120px; margin-bottom: 24px; filter: drop-shadow(0 0 25px #ff8800aa); animation: logoFloat 3s ease-in-out infinite; }
        @keyframes logoFloat { 0%,100%{transform:translateY(0)} 50%{transform:translateY(-8px)} }

        /* ---- DEATH SCREEN ---- */
        #death-screen {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            z-index: 100; display: none; flex-direction: column;
            align-items: center; justify-content: center;
            overflow: hidden;
        }
        #death-bg-canvas {
            position: absolute; top: 0; left: 0; width: 100%; height: 100%;
            z-index: 0;
        }
        #death-screen.visible { display: flex; animation: deathReveal 0.5s ease-out; }
        @keyframes deathReveal { from{opacity:0;transform:scale(1.1)} to{opacity:1;transform:scale(1)} }
        .death-content { position: relative; z-index: 2; text-align: center; }
        #death-message {
            color: #ff1111; font-size: clamp(30px, 6vw, 70px); text-align: center;
            text-shadow: 0 0 40px #ff0000, 0 0 80px #880000, 0 0 160px #440000;
            animation: deathPulse 1.5s infinite; margin-bottom: 12px; letter-spacing: 4px;
        }
        #death-sub { color: #885533; font-size: 17px; margin-bottom: 8px; letter-spacing: 2px; }
        #death-killer { color: #ffaa44; font-size: 24px; margin-bottom: 14px; text-shadow: 0 0 15px #ff6600; }
        #death-quote { color: #552222; font-size: 13px; margin-bottom: 40px; font-style: italic; letter-spacing: 1px; }
        .death-btn {
            background: rgba(0,0,0,0.7); padding: 12px 42px;
            font-size: 16px; cursor: pointer; font-family: inherit;
            text-transform: uppercase; letter-spacing: 2px; transition: all 0.3s; margin: 8px;
            border-radius: 3px;
        }
        #retry-btn { border: 2px solid #ff2200; color: #ff5533; box-shadow: 0 0 12px #ff220044; }
        #retry-btn:hover { background: #ff2200; color: #000; box-shadow: 0 0 30px #ff2200; transform: scale(1.05); }
        #menu-btn-death { border: 2px solid #334455; color: #556677; }
        #menu-btn-death:hover { background: #334455; color: #aabbcc; }

        /* ---- WIN SCREEN ---- */
        #win-screen {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: radial-gradient(ellipse, #0a1a00 0%, #000 80%);
            z-index: 100; display: none; flex-direction: column;
            align-items: center; justify-content: center;
        }
        #win-screen.visible { display: flex; }
        #win-message {
            color: #aaff44; font-size: clamp(26px, 5vw, 52px); text-align: center;
            text-shadow: 0 0 30px #88ff00; margin-bottom: 16px; letter-spacing: 2px;
        }
        #win-sub { color: #668844; font-size: 17px; margin-bottom: 50px; }
        .win-btn {
            background: transparent; padding: 12px 42px;
            font-size: 16px; cursor: pointer; font-family: inherit;
            text-transform: uppercase; letter-spacing: 2px; transition: all 0.3s;
            margin: 8px; border-radius: 4px;
        }
        #next-btn { border: 2px solid #aaff44; color: #aaff44; }
        #next-btn:hover { background: #aaff44; color: #000; box-shadow: 0 0 25px #aaff4499; }
        #menu-btn-win { border: 2px solid #445566; color: #556677; }
        #menu-btn-win:hover { background: #445566; color: #fff; }

        /* ---- JUMPSCARE ---- */
        #jumpscare {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: #000; z-index: 90; display: none;
            align-items: center; justify-content: center;
            overflow: hidden;
        }
        #jumpscare.visible { display: flex; }
        #jumpscare-canvas { width: 100%; height: 100%; position: absolute; top: 0; left: 0; }
        #jumpscare-face { font-size: 0px; position: absolute; }

        /* ---- OVERLAYS ---- */
        #noise-overlay {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            pointer-events: none; z-index: 5; opacity: 0;
            background: repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(0,0,0,0.06) 2px, rgba(0,0,0,0.06) 4px);
        }
        #vignette {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            pointer-events: none; z-index: 4;
            background: radial-gradient(ellipse at center, transparent 35%, rgba(0,0,0,0.75) 100%);
        }

        /* ---- ALERT ---- */
        #alert-box {
            position: fixed; top: 80px; left: 50%; transform: translateX(-50%);
            background: rgba(180,0,0,0.92); color: #fff;
            padding: 9px 24px; border-radius: 5px; font-size: 14px;
            z-index: 50; display: none; letter-spacing: 1px;
            box-shadow: 0 0 20px #ff000066; border: 1px solid #ff3300;
        }
        #alert-box.visible { display: block; animation: alertPulse 0.45s ease-in-out infinite; }

        /* ---- NIGHT COMPLETE ---- */
        #night-complete {
            position: fixed; top: 50%; left: 50%; transform: translate(-50%,-50%);
            color: #aaff44; font-size: clamp(24px, 4vw, 44px);
            text-shadow: 0 0 30px #88ff00; z-index: 80; display: none;
            text-align: center; letter-spacing: 2px;
        }
        #night-complete.visible { display: block; animation: fadeInOut 4s forwards; }

        /* ---- ANIMATIONS ---- */
        @keyframes flicker {
            0%,100%{opacity:1} 91%{opacity:1} 92%{opacity:0.2} 93%{opacity:1} 95%{opacity:0.6} 96%{opacity:1}
        }
        @keyframes deathPulse { 0%,100%{opacity:1} 50%{opacity:0.35} }
        @keyframes jsAnim {
            0%{transform:scale(1) rotate(-4deg) translate(-3px,2px)}
            50%{transform:scale(1.08) rotate(4deg) translate(3px,-2px)}
            100%{transform:scale(1) rotate(-4deg) translate(-3px,2px)}
        }
        @keyframes alertPulse { 0%,100%{opacity:1} 50%{opacity:0.65} }
        @keyframes fadeInOut { 0%{opacity:0} 15%{opacity:1} 70%{opacity:1} 100%{opacity:0} }
    </style>
</head>
<body>
<canvas id="canvas"></canvas>
<div id="noise-overlay"></div>
<div id="vignette"></div>

<!-- HUD -->
<div id="hud">
    <div id="time-display">12 AM</div>
    <div id="night-display">Night 1</div>

    <div id="power-wrap">
        <div id="power-label">⚡ POWER REMAINING</div>
        <div id="power-bar-container"><div id="power-bar"></div></div>
        <div id="power-display">100%</div>
    </div>

    <div id="left-controls">
        <button class="door-btn" id="left-door-btn" onclick="toggleDoor('left')">
            <span class="btn-icon">🚪</span><span class="btn-label">Left Door [Q]</span>
        </button>
        <button class="light-btn" id="left-light-btn" onclick="toggleLight('left')">
            <span class="btn-icon">💡</span><span class="btn-label">Left Light [A]</span>
        </button>
    </div>
    <div id="right-controls">
        <button class="door-btn" id="right-door-btn" onclick="toggleDoor('right')">
            <span class="btn-icon">🚪</span><span class="btn-label">Right Door [E]</span>
        </button>
        <button class="light-btn" id="right-light-btn" onclick="toggleLight('right')">
            <span class="btn-icon">💡</span><span class="btn-label">Right Light [D]</span>
        </button>
    </div>

    <div id="cam-tab-wrap" style="position:absolute;bottom:0;left:50%;transform:translateX(-50%);pointer-events:all;display:flex;flex-direction:column;align-items:center;">
        <div id="cam-tab" onclick="openCameras()" style="background:rgba(5,12,24,0.93);border:2px solid #336699;border-bottom:none;color:#88ccff;width:200px;height:44px;cursor:pointer;font-family:inherit;font-size:13px;display:flex;align-items:center;justify-content:center;gap:10px;letter-spacing:1px;border-radius:10px 10px 0 0;box-shadow:0 -4px 18px #003366aa;transition:all 0.2s;">
            <span>📷 CAMERAS [C]</span>
            <span style="font-size:17px;animation:camBounce 1.4s infinite">⌄⌄</span>
        </div>
    </div>
    <style>@keyframes camBounce{0%,100%{transform:translateY(0)}50%{transform:translateY(-4px)}}</style>
</div>

<!-- Camera Overlay -->
<div id="camera-overlay">
    <div id="cam-header">
        <div id="camera-title">◉ SECURITY MONITOR — ACTIVE FEED</div>
        <button id="close-cameras" onclick="closeCameras()">▼ CLOSE MONITOR [C]</button>
    </div>
    <div id="cam-main">
        <!-- Big live preview (canvas) -->
        <div id="cam-preview-wrap">
            <canvas id="cam-preview-canvas" style="width:100%;height:100%;display:block;image-rendering:pixelated;"></canvas>
            <div id="cam-preview-label">CAM 1A – Show Stage</div>
        </div>
        <!-- Right panel: map + grid -->
        <div style="display:flex;flex-direction:column;gap:10px;width:300px;flex-shrink:0;">
        <!-- FNAF1-style MAP -->
        <div id="cam-map" style="width:100%;height:200px;position:relative;background:#010a06;border:1px solid #1a3322;border-radius:4px;overflow:hidden;font-family:inherit;">
            <div class="map-room" id="map-0" onclick="selectCamera(0)" style="left:2%;top:2%;width:22%;height:36%"><span class="mrn">1A</span>Stage</div>
            <div class="map-room" id="map-1" onclick="selectCamera(1)" style="left:26%;top:2%;width:22%;height:36%"><span class="mrn">1B</span>Dining</div>
            <div class="map-room" id="map-2" onclick="selectCamera(2)" style="left:50%;top:2%;width:22%;height:36%"><span class="mrn">1C</span>Pirates</div>
            <div class="map-room" id="map-8" onclick="selectCamera(8)" style="right:2%;top:2%;width:20%;height:36%"><span class="mrn">5</span>Bkstg</div>
            <div class="map-room" id="map-3" onclick="selectCamera(3)" style="left:2%;top:42%;width:20%;height:26%"><span class="mrn">2A</span>W.Hall</div>
            <div class="map-room" id="map-4" onclick="selectCamera(4)" style="left:2%;top:72%;width:20%;height:25%"><span class="mrn">2B</span>W.Cor</div>
            <div class="map-room" id="map-5" onclick="selectCamera(5)" style="left:38%;top:42%;width:22%;height:26%"><span class="mrn">3</span>Supply</div>
            <div class="map-room" id="map-6" onclick="selectCamera(6)" style="right:2%;top:42%;width:20%;height:26%"><span class="mrn">4A</span>E.Hall</div>
            <div class="map-room" id="map-7" onclick="selectCamera(7)" style="right:2%;top:72%;width:20%;height:25%"><span class="mrn">4B</span>E.Cor</div>
            <div style="position:absolute;bottom:15px;left:50%;transform:translateX(-50%);background:rgba(60,20,0,0.7);border:1px solid #ff6600;padding:2px 10px;color:#ff9900;font-size:8px;border-radius:2px;white-space:nowrap;">OFFICE</div>
            <div style="position:absolute;bottom:4px;left:50%;transform:translateX(-50%);color:#ff4400;font-size:7px;white-space:nowrap;">▼ YOU ARE HERE ▼</div>
        </div>
        <!-- Camera selector grid -->
        <div id="camera-grid">
            <div class="cam-button" onclick="selectCamera(0)" id="cam-0">
                <span class="cam-name">CAM 1A</span><span class="cam-room">Show Stage</span>
                <span class="cam-status clear" id="cam-status-0">CLEAR</span>
            </div>
            <div class="cam-button" onclick="selectCamera(1)" id="cam-1">
                <span class="cam-name">CAM 1B</span><span class="cam-room">Dining Area</span>
                <span class="cam-status clear" id="cam-status-1">CLEAR</span>
            </div>
            <div class="cam-button" onclick="selectCamera(2)" id="cam-2">
                <span class="cam-name">CAM 1C</span><span class="cam-room">Pirate Cove</span>
                <span class="cam-status clear" id="cam-status-2">CLEAR</span>
            </div>
            <div class="cam-button" onclick="selectCamera(3)" id="cam-3">
                <span class="cam-name">CAM 2A</span><span class="cam-room">West Hall</span>
                <span class="cam-status clear" id="cam-status-3">CLEAR</span>
            </div>
            <div class="cam-button" onclick="selectCamera(4)" id="cam-4">
                <span class="cam-name">CAM 2B</span><span class="cam-room">W. Corner</span>
                <span class="cam-status clear" id="cam-status-4">CLEAR</span>
            </div>
            <div class="cam-button" onclick="selectCamera(5)" id="cam-5">
                <span class="cam-name">CAM 3</span><span class="cam-room">Supply</span>
                <span class="cam-status clear" id="cam-status-5">CLEAR</span>
            </div>
            <div class="cam-button" onclick="selectCamera(6)" id="cam-6">
                <span class="cam-name">CAM 4A</span><span class="cam-room">East Hall</span>
                <span class="cam-status clear" id="cam-status-6">CLEAR</span>
            </div>
            <div class="cam-button" onclick="selectCamera(7)" id="cam-7">
                <span class="cam-name">CAM 4B</span><span class="cam-room">E. Corner</span>
                <span class="cam-status clear" id="cam-status-7">CLEAR</span>
            </div>
            <div class="cam-button" onclick="selectCamera(8)" id="cam-8">
                <span class="cam-name">CAM 5</span><span class="cam-room">Backstage</span>
                <span class="cam-status clear" id="cam-status-8">CLEAR</span>
            </div>
        </div>
        </div><!-- end right panel -->
    </div>
</div>

<!-- Start Screen -->
<div id="start-screen">
<canvas id="menu-bg-canvas"></canvas>
<div class="menu-content">
    <svg id="freddy-logo" viewBox="0 0 120 120">
        <circle cx="60" cy="45" r="36" fill="#4a2a00" stroke="#ff6600" stroke-width="2"/>
        <circle cx="60" cy="45" r="29" fill="#6b3a00"/>
        <circle cx="48" cy="40" r="9" fill="#fff"/>
        <circle cx="72" cy="40" r="9" fill="#fff"/>
        <circle cx="50" cy="41" r="5" fill="#1a0a00"/>
        <circle cx="74" cy="41" r="5" fill="#1a0a00"/>
        <circle cx="48.5" cy="39.5" r="2" fill="#fff" opacity="0.6"/>
        <circle cx="72.5" cy="39.5" r="2" fill="#fff" opacity="0.6"/>
        <circle cx="60" cy="51" r="4" fill="#3a1800"/>
        <path d="M 46 60 Q 60 73 74 60" stroke="#2a0e00" stroke-width="3" fill="none" stroke-linecap="round"/>
        <rect x="33" y="9" width="54" height="9" fill="#2a1200" stroke="#ff6600" stroke-width="1" rx="1"/>
        <rect x="40" y="0" width="40" height="13" fill="#2a1200" stroke="#ff8800" stroke-width="1" rx="1"/>
        <circle cx="23" cy="47" r="11" fill="#4a2a00"/>
        <circle cx="97" cy="47" r="11" fill="#4a2a00"/>
        <circle cx="23" cy="47" r="5" fill="#ff6600" opacity="0.4"/>
        <circle cx="97" cy="47" r="5" fill="#ff6600" opacity="0.4"/>
        <polygon points="49,83 60,91 71,83 60,75" fill="#ff6600"/>
        <rect x="57" y="91" width="6" height="8" fill="#884400"/>
    </svg>
    <h1>FIVE NIGHTS AT<br>FREDDY'S</h1>
    <div class="subtitle">3D SECURITY OFFICE — SURVIVE UNTIL 6 AM</div>
    <div class="night-select-label">SELECT NIGHT</div>
    <div>
        <button class="night-btn selected" onclick="selectNight(1)" id="night-1-btn">Night 1</button>
        <button class="night-btn" onclick="selectNight(2)" id="night-2-btn">Night 2</button>
        <button class="night-btn" onclick="selectNight(3)" id="night-3-btn">Night 3</button>
        <button class="night-btn" onclick="selectNight(4)" id="night-4-btn">Night 4</button>
        <button class="night-btn" onclick="selectNight(5)" id="night-5-btn">Night 5</button>
    </div>
    <button id="start-btn" onclick="startGame()">▶ START NIGHT</button>
    <div class="keys-hint">Mouse: Look around &nbsp;|&nbsp; Q/E: Doors &nbsp;|&nbsp; A/D: Lights &nbsp;|&nbsp; C: Cameras</div>
</div>
</div>

<!-- Jumpscare -->
<div id="jumpscare">
    <canvas id="jumpscare-canvas"></canvas>
    <div id="jumpscare-face"></div>
</div>

<!-- Death Screen -->
<div id="death-screen">
<canvas id="death-bg-canvas"></canvas>
<div class="death-content">
    <div id="death-message">☠ IT'S ME ☠</div>
    <div id="death-sub">You couldn't survive the night...</div>
    <div id="death-killer">Caught by: <span id="killer-name">Freddy</span></div>
    <div id="death-quote">"The show must go on..."</div>
    <button id="retry-btn" class="death-btn" onclick="retryGame()">↺ RETRY NIGHT</button>
    <button id="menu-btn-death" class="death-btn" onclick="goToMenu()">⌂ MAIN MENU</button>
</div>
</div>

<!-- Win Screen -->
<div id="win-screen">
    <div id="win-message">🌅 6 AM<br>YOU SURVIVED!</div>
    <div id="win-sub">Night complete!</div>
    <button id="next-btn" class="win-btn" onclick="nextNight()">NEXT NIGHT ▶</button>
    <button id="menu-btn-win" class="win-btn" onclick="goToMenu()">⌂ MAIN MENU</button>
</div>

<!-- Alert -->
<div id="alert-box"></div>

<!-- Night Complete Banner -->
<div id="night-complete"></div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script>
// ============================================================
// FNAF 3D - Full Game Logic (v2 - Brighter + Camera Monitor)
// ============================================================

let scene, camera, renderer, clock;
let gameRunning = false;
let gameOver = false;
let currentNight = 1;
let selectedNight = 1;
let cameraOpen = false;
let activeCamIndex = 0;
let power = 100;
let nightHour = 0;
let nightDuration = 360;
let nightTimer = 0;
let lookAngle = 0;
let lookTarget = 0;

let doors = { left: false, right: false };
let lights = { left: false, right: false };

const AI_LEVELS = {
    1: [0, 1, 1, 0],
    2: [2, 2, 2, 1],
    3: [3, 3, 2, 2],
    4: [4, 4, 3, 3],
    5: [4, 4, 4, 4]
};

const LOCATIONS = {
    STAGE: 'stage', DINING: 'dining', BACKSTAGE: 'backstage',
    SUPPLY: 'supply', PIRATE_COVE: 'pirate_cove',
    WEST_HALL: 'west_hall', WEST_CORNER: 'west_corner',
    EAST_HALL: 'east_hall', EAST_CORNER: 'east_corner',
    LEFT_DOOR: 'left_door', RIGHT_DOOR: 'right_door', OFFICE: 'office'
};

const CAM_LOCATIONS = [
    LOCATIONS.STAGE, LOCATIONS.DINING, LOCATIONS.PIRATE_COVE,
    LOCATIONS.WEST_HALL, LOCATIONS.WEST_CORNER, LOCATIONS.SUPPLY,
    LOCATIONS.EAST_HALL, LOCATIONS.EAST_CORNER, LOCATIONS.BACKSTAGE
];

const CAM_NAMES = [
    'CAM 1A – Show Stage', 'CAM 1B – Dining Area', 'CAM 1C – Pirate Cove',
    'CAM 2A – W. Hall', 'CAM 2B – W. Corner', 'CAM 3 – Supply Closet',
    'CAM 4A – E. Hall', 'CAM 4B – E. Corner', 'CAM 5 – Backstage'
];

const FREDDY_PATH = [LOCATIONS.STAGE, LOCATIONS.DINING, LOCATIONS.BACKSTAGE, LOCATIONS.EAST_HALL, LOCATIONS.EAST_CORNER, LOCATIONS.OFFICE];
const BONNIE_PATH = [LOCATIONS.STAGE, LOCATIONS.DINING, LOCATIONS.WEST_HALL, LOCATIONS.WEST_CORNER, LOCATIONS.LEFT_DOOR, LOCATIONS.OFFICE];
const CHICA_PATH  = [LOCATIONS.STAGE, LOCATIONS.DINING, LOCATIONS.EAST_HALL, LOCATIONS.EAST_CORNER, LOCATIONS.RIGHT_DOOR, LOCATIONS.OFFICE];
const FOXY_STAGES = ['hidden', 'peek1', 'peek2', 'peek3', 'running', LOCATIONS.LEFT_DOOR, LOCATIONS.OFFICE];

let animatronics = {};
let officeGroup;
let leftDoorObj, rightDoorObj;
let leftLightObj, rightLightObj;
let animModels = {};

// Canvas-based camera monitor renderer
let camCanvas, camCtx;

// Room background colors for each camera
const CAM_BG_COLORS = {
    [LOCATIONS.STAGE]:       { bg: '#1a0a2e', floor: '#2a1040', accent: '#6633aa' },
    [LOCATIONS.DINING]:      { bg: '#0d1a0d', floor: '#142814', accent: '#336633' },
    [LOCATIONS.PIRATE_COVE]: { bg: '#1a0800', floor: '#2a1200', accent: '#cc4400' },
    [LOCATIONS.WEST_HALL]:   { bg: '#0a0a14', floor: '#111120', accent: '#334466' },
    [LOCATIONS.WEST_CORNER]: { bg: '#0a0a14', floor: '#111120', accent: '#223355' },
    [LOCATIONS.SUPPLY]:      { bg: '#141414', floor: '#1a1a1a', accent: '#444444' },
    [LOCATIONS.EAST_HALL]:   { bg: '#140a0a', floor: '#201010', accent: '#664433' },
    [LOCATIONS.EAST_CORNER]: { bg: '#140a0a', floor: '#201010', accent: '#553322' },
    [LOCATIONS.BACKSTAGE]:   { bg: '#0a0a0a', floor: '#111111', accent: '#333333' },
};

// Animatronic visual config for 2D camera drawing
const ANIM_DRAW = {
    freddy: { bodyColor: '#8B4513', hatColor: '#3a1800', eyeColor: '#fff', accent: '#ff8800', name: 'FREDDY' },
    bonnie: { bodyColor: '#5a0d8a', hatColor: '#3a0060', eyeColor: '#ff00ff', accent: '#aa44ff', name: 'BONNIE' },
    chica:  { bodyColor: '#ccaa00', hatColor: '#886600', eyeColor: '#fff', accent: '#ffdd00', name: 'CHICA'  },
    foxy:   { bodyColor: '#cc3300', hatColor: '#881100', eyeColor: '#ff8800', accent: '#ff4400', name: 'FOXY'  },
};

// ---- AUDIO ----
let audioCtx = null;
function getAudioCtx() {
    if (!audioCtx) audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    return audioCtx;
}
function playBeep(freq=440, duration=0.1, type='square', vol=0.15) {
    try {
        const ctx = getAudioCtx();
        const osc = ctx.createOscillator();
        const gain = ctx.createGain();
        osc.connect(gain); gain.connect(ctx.destination);
        osc.type = type; osc.frequency.value = freq;
        gain.gain.setValueAtTime(vol, ctx.currentTime);
        gain.gain.exponentialRampToValueAtTime(0.001, ctx.currentTime + duration);
        osc.start(); osc.stop(ctx.currentTime + duration);
    } catch(e) {}
}
function playDoorSound() { playBeep(120, 0.4, 'sawtooth', 0.2); playBeep(90, 0.5, 'sawtooth', 0.1); }
function playLightSound() { playBeep(900, 0.06, 'sine'); }
function playCameraSound() { playBeep(1400, 0.07, 'sine', 0.1); playBeep(1000, 0.05, 'sine', 0.08); }
function playAlertSound() { for(let i=0;i<3;i++) setTimeout(()=>playBeep(880,0.15,'square',0.2), i*200); }
function playJumpscareSound() {
    try {
        const ctx = getAudioCtx();
        for (let i = 0; i < 8; i++) {
            setTimeout(() => {
                const osc = ctx.createOscillator();
                const gain = ctx.createGain();
                osc.connect(gain); gain.connect(ctx.destination);
                osc.type = 'sawtooth';
                osc.frequency.value = 60 + Math.random() * 600;
                gain.gain.setValueAtTime(0.5, ctx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.001, ctx.currentTime + 0.4);
                osc.start(); osc.stop(ctx.currentTime + 0.4);
            }, i * 50);
        }
    } catch(e) {}
}
function play6amSound() {
    [523,659,784,1046,1318].forEach((f,i) => setTimeout(()=>playBeep(f,0.5,'sine',0.2), i*180));
}

// ---- INIT ANIMATRONICS ----
function initAnimatronics() {
    const levels = AI_LEVELS[currentNight];
    animatronics = {
        freddy: { name:'Freddy Fazbear', level:levels[0], path:FREDDY_PATH, pathIndex:0, location:LOCATIONS.STAGE, moveTimer:0, moveInterval:Math.max(5,20-levels[0]*2) },
        bonnie: { name:'Bonnie',         level:levels[1], path:BONNIE_PATH, pathIndex:0, location:LOCATIONS.STAGE, moveTimer:0, moveInterval:Math.max(4,15-levels[1]*2) },
        chica:  { name:'Chica',          level:levels[2], path:CHICA_PATH,  pathIndex:0, location:LOCATIONS.STAGE, moveTimer:0, moveInterval:Math.max(4,15-levels[2]*2) },
        foxy:   { name:'Foxy', level: currentNight===1 ? 0 : levels[3], path:FOXY_STAGES, pathIndex:0, location:'hidden', moveTimer:0, moveInterval:Math.max(6,25-levels[3]*3), foxyStage:0, night1Activated: false },
    };
}

// ---- THREE.JS SETUP ----
function initThree() {
    scene = new THREE.Scene();
    scene.background = new THREE.Color(0x1e1e1e);
    scene.fog = new THREE.Fog(0x1a1a1a, 10, 38);

    camera = new THREE.PerspectiveCamera(80, window.innerWidth / window.innerHeight, 0.1, 100);
    camera.position.set(0, 1.72, 0.5);
    camera.rotation.order = 'YXZ';
    camera.rotation.x = -0.14; // tilt down to see the front desk

    renderer = new THREE.WebGLRenderer({ canvas: document.getElementById('canvas'), antialias: true });
    renderer.setSize(window.innerWidth, window.innerHeight);
    renderer.setPixelRatio(window.devicePixelRatio);
    renderer.shadowMap.enabled = true;
    renderer.shadowMap.type = THREE.PCFSoftShadowMap;
    renderer.toneMapping = THREE.ACESFilmicToneMapping;
    renderer.toneMappingExposure = 1.4;

    clock = new THREE.Clock();

    // Camera monitor canvas (offscreen, used as texture)
    camCanvas = document.createElement('canvas');
    camCanvas.width = 512; camCanvas.height = 320;
    camCtx = camCanvas.getContext('2d');

    buildOffice();
    buildAnimatronicModels();

    window.addEventListener('resize', onResize);
    document.addEventListener('mousemove', onMouseMove);
}

function onResize() {
    camera.aspect = window.innerWidth / window.innerHeight;
    camera.updateProjectionMatrix();
    renderer.setSize(window.innerWidth, window.innerHeight);
}
function onMouseMove(e) {
    if (!gameRunning || cameraOpen) return;
    const norm = (e.clientX / window.innerWidth - 0.5) * 2;
    lookTarget = norm * 0.75;
}

// ---- TEXTURE HELPERS ----
function makeWallTexture() {
    const c = document.createElement('canvas'); c.width = 512; c.height = 512;
    const ctx = c.getContext('2d');
    // Dark gray base
    ctx.fillStyle = '#3a3a3a'; ctx.fillRect(0,0,512,512);
    // Subtle vertical panel lines
    ctx.strokeStyle = 'rgba(0,0,0,0.35)'; ctx.lineWidth = 2;
    for(let x=0; x<512; x+=64){ ctx.beginPath(); ctx.moveTo(x,0); ctx.lineTo(x,512); ctx.stroke(); }
    // Horizontal divider stripe at mid-height (like FNAF office wainscoting)
    ctx.fillStyle = '#2a2a2a'; ctx.fillRect(0, 220, 512, 12);
    ctx.fillStyle = '#444444'; ctx.fillRect(0, 232, 512, 4);
    // Lower wall slightly darker
    ctx.fillStyle = 'rgba(0,0,0,0.18)'; ctx.fillRect(0,236,512,276);
    // Grime/scuff marks
    for(let i=0;i<50;i++){
        const gx=Math.random()*512, gy=Math.random()*512;
        const gr = ctx.createRadialGradient(gx,gy,0,gx,gy,20+Math.random()*35);
        gr.addColorStop(0,'rgba(0,0,0,0.1)'); gr.addColorStop(1,'rgba(0,0,0,0)');
        ctx.fillStyle=gr; ctx.fillRect(0,0,512,512);
    }
    return new THREE.CanvasTexture(c);
}

function makeFloorTexture() {
    const c = document.createElement('canvas'); c.width = 512; c.height = 512;
    const ctx = c.getContext('2d');
    // Classic FNAF black & white checkerboard
    const tS = 64;
    for(let r=0;r<8;r++){
        for(let col=0;col<8;col++){
            const isWhite = (r+col)%2===0;
            ctx.fillStyle = isWhite ? '#d8d8d8' : '#1a1a1a';
            ctx.fillRect(col*tS, r*tS, tS, tS);
            // Grout lines
            ctx.strokeStyle = isWhite ? '#aaaaaa' : '#0a0a0a';
            ctx.lineWidth = 2;
            ctx.strokeRect(col*tS+1, r*tS+1, tS-2, tS-2);
            // Shine on white tiles
            if(isWhite){
                ctx.fillStyle = 'rgba(255,255,255,0.18)';
                ctx.fillRect(col*tS+4, r*tS+4, tS/3, tS/3);
            }
            // Scuffs on black tiles
            if(!isWhite && Math.random()<0.4){
                ctx.fillStyle = 'rgba(60,60,60,0.4)';
                ctx.fillRect(col*tS+Math.random()*40, r*tS+Math.random()*40, 8+Math.random()*20, 2+Math.random()*4);
            }
        }
    }
    const tex = new THREE.CanvasTexture(c);
    tex.wrapS=tex.wrapT=THREE.RepeatWrapping;
    tex.repeat.set(4,4);
    return tex;
}

function makeCelebrateBanner() {
    // Full poster with all 3 animatronics + CELEBRATE! text
    const c = document.createElement('canvas'); c.width = 512; c.height = 384;
    const ctx = c.getContext('2d');
    // Poster background
    ctx.fillStyle='#e8e0c8'; ctx.fillRect(0,0,512,384);
    // Top banner
    const bg = ctx.createLinearGradient(0,0,0,80);
    bg.addColorStop(0,'#2a6a22'); bg.addColorStop(1,'#1a4a18');
    ctx.fillStyle=bg; ctx.fillRect(0,0,512,80);
    ctx.fillStyle='rgba(255,255,100,0.6)';
    for(let i=0;i<18;i++){ctx.beginPath();ctx.arc(Math.random()*512,Math.random()*80,2+Math.random()*3,0,Math.PI*2);ctx.fill();}
    // CELEBRATE! text
    ctx.font='bold 66px Impact,Arial Black'; ctx.textAlign='center'; ctx.textBaseline='middle';
    ctx.fillStyle='rgba(0,0,0,0.45)'; ctx.fillText('CELEBRATE!',258,42);
    const tg=ctx.createLinearGradient(0,10,0,72); tg.addColorStop(0,'#ffff44'); tg.addColorStop(0.5,'#ffcc00'); tg.addColorStop(1,'#ff8800');
    ctx.fillStyle=tg; ctx.fillText('CELEBRATE!',256,40);
    ctx.strokeStyle='rgba(0,0,0,0.5)'; ctx.lineWidth=2; ctx.strokeText('CELEBRATE!',256,40);
    // Draw 3 animatronics
    function drawMini(name,cx,cy,scale){
        const colors={freddy:{body:'#8B4513',hat:'#3a1800',eye:'#fff',accent:'#ff8800'},bonnie:{body:'#5a0d8a',hat:'#3a0060',eye:'#ff88ff',accent:'#aa44ff'},chica:{body:'#ccaa00',hat:'#886600',eye:'#fff',accent:'#ffdd00'}};
        const cfg=colors[name]; const s=scale;
        const bW=50*s,bH=62*s,hW=46*s,hH=46*s;
        ctx.fillStyle=cfg.body; ctx.beginPath(); ctx.roundRect(cx-bW/2,cy-bH,bW,bH,4); ctx.fill();
        ctx.fillStyle='rgba(220,195,145,0.7)'; ctx.beginPath(); ctx.ellipse(cx,cy-bH*0.45,bW*0.28,bH*0.32,0,0,Math.PI*2); ctx.fill();
        const headY=cy-bH-hH*0.5;
        ctx.fillStyle=cfg.body; ctx.beginPath(); ctx.roundRect(cx-hW/2,headY-hH/2,hW,hH,4); ctx.fill();
        if(name==='freddy'||name==='bonnie'){ctx.fillStyle=cfg.hat;ctx.fillRect(cx-hW*0.55,headY-hH/2-8*s,hW*1.1,7*s);ctx.fillRect(cx-hW*0.28,headY-hH/2-30*s,hW*0.56,24*s);}
        if(name==='chica'){ctx.fillStyle='#ffcc00';ctx.beginPath();ctx.ellipse(cx,headY+hH*0.15,hW*0.2,hH*0.15,0,0,Math.PI*2);ctx.fill();}
        [[cx-hW*0.22,headY-2*s],[cx+hW*0.22,headY-2*s]].forEach(([ex,ey])=>{ctx.fillStyle='#fff';ctx.beginPath();ctx.arc(ex,ey,7*s,0,Math.PI*2);ctx.fill();ctx.fillStyle='#333';ctx.beginPath();ctx.arc(ex,ey,4*s,0,Math.PI*2);ctx.fill();});
        if(name==='freddy'){ctx.fillStyle='#cc0000';ctx.beginPath();ctx.moveTo(cx-9*s,cy-bH*0.85);ctx.lineTo(cx,cy-bH*0.78);ctx.lineTo(cx+9*s,cy-bH*0.85);ctx.lineTo(cx,cy-bH*0.92);ctx.closePath();ctx.fill();}
        ctx.fillStyle=cfg.accent; ctx.font=`bold ${Math.round(12*s)}px monospace`; ctx.textAlign='center'; ctx.fillText(name.toUpperCase(),cx,cy+14*s);
    }
    drawMini('bonnie',100,280,0.78);
    drawMini('freddy',256,275,0.9);
    drawMini('chica',412,280,0.78);
    ctx.fillStyle='#4a2800'; ctx.font='bold 14px monospace'; ctx.textAlign='center';
    ctx.fillText("FREDDY FAZBEAR'S PIZZA",256,348);
    ctx.font='11px monospace'; ctx.fillStyle='#664422'; ctx.fillText('Where fantasy and fun come to life!',256,365);
    ctx.strokeStyle='#8B4513'; ctx.lineWidth=6; ctx.strokeRect(3,3,506,378);
    ctx.strokeStyle='#ffcc00'; ctx.lineWidth=2; ctx.strokeRect(9,9,494,366);
    return new THREE.CanvasTexture(c);
}

function makeFreddyPoster() {
    const c = document.createElement('canvas'); c.width = 256; c.height = 320;
    const ctx = c.getContext('2d');
    // Background
    const bg = ctx.createLinearGradient(0,0,0,320);
    bg.addColorStop(0,'#1a0800'); bg.addColorStop(1,'#3a1800');
    ctx.fillStyle=bg; ctx.fillRect(0,0,256,320);
    // Draw Freddy face
    ctx.fillStyle='#8B4513'; ctx.beginPath(); ctx.arc(128,140,75,0,Math.PI*2); ctx.fill();
    // Snout
    ctx.fillStyle='#7a3810'; ctx.beginPath(); ctx.arc(128,160,30,0,Math.PI*2); ctx.fill();
    // Eyes
    [[100,120],[156,120]].forEach(([ex,ey])=>{
        ctx.fillStyle='#fff'; ctx.beginPath(); ctx.arc(ex,ey,16,0,Math.PI*2); ctx.fill();
        ctx.fillStyle='#111'; ctx.beginPath(); ctx.arc(ex,ey,9,0,Math.PI*2); ctx.fill();
        ctx.fillStyle='rgba(255,255,255,0.6)'; ctx.beginPath(); ctx.arc(ex-4,ey-4,4,0,Math.PI*2); ctx.fill();
    });
    // Top hat brim
    ctx.fillStyle='#1a0a00'; ctx.fillRect(80,55,96,12); // brim
    ctx.fillRect(95,10,66,50); // top
    ctx.strokeStyle='#4a2800'; ctx.lineWidth=2; ctx.strokeRect(95,10,66,50);
    // Smile
    ctx.strokeStyle='#3a1800'; ctx.lineWidth=4;
    ctx.beginPath(); ctx.arc(128,168,18,0,Math.PI); ctx.stroke();
    // Title text
    ctx.fillStyle='#ff8800'; ctx.font='bold 18px monospace';
    ctx.textAlign='center'; ctx.fillText("FREDDY'S", 128, 240);
    ctx.font='14px monospace'; ctx.fillStyle='#cc6600';
    ctx.fillText("FAZBEAR PIZZA", 128, 260);
    // Border
    ctx.strokeStyle='#ff6600'; ctx.lineWidth=4; ctx.strokeRect(4,4,248,312);
    return new THREE.CanvasTexture(c);
}

function makeDoorTexture() {
    const c = document.createElement('canvas'); c.width = 128; c.height = 512;
    const ctx = c.getContext('2d');
    // Metal door base
    const bg = ctx.createLinearGradient(0,0,128,0);
    bg.addColorStop(0,'#404858'); bg.addColorStop(0.5,'#5a6878'); bg.addColorStop(1,'#404858');
    ctx.fillStyle=bg; ctx.fillRect(0,0,128,512);
    // Panel lines
    ctx.strokeStyle='rgba(0,0,0,0.4)'; ctx.lineWidth=2;
    [120, 240, 360].forEach(y=>{
        ctx.beginPath(); ctx.moveTo(10,y); ctx.lineTo(118,y); ctx.stroke();
    });
    // Rivets
    ctx.fillStyle='#303844';
    [[15,15],[113,15],[15,497],[113,497]].forEach(([rx,ry])=>{
        ctx.beginPath(); ctx.arc(rx,ry,4,0,Math.PI*2); ctx.fill();
    });
    // Warning stripes at bottom
    for(let i=0; i<8; i++){
        ctx.fillStyle = i%2===0 ? '#ffcc00' : '#222';
        ctx.fillRect(0, 448+i*8, 128, 8);
    }
    return new THREE.CanvasTexture(c);
}

function makeCeilingTexture() {
    const c = document.createElement('canvas'); c.width=256; c.height=256;
    const ctx = c.getContext('2d');
    // Dark gray ceiling
    ctx.fillStyle='#2e2e2e'; ctx.fillRect(0,0,256,256);
    // Ceiling tile grid lines
    ctx.strokeStyle='rgba(0,0,0,0.55)'; ctx.lineWidth=2;
    for(let i=0;i<256;i+=64){
        ctx.beginPath(); ctx.moveTo(i,0); ctx.lineTo(i,256); ctx.stroke();
        ctx.beginPath(); ctx.moveTo(0,i); ctx.lineTo(256,i); ctx.stroke();
    }
    // Subtle inner tile shading
    for(let r=0;r<4;r++) for(let col=0;col<4;col++){
        ctx.fillStyle='rgba(255,255,255,0.03)';
        ctx.fillRect(col*64+2, r*64+2, 60, 60);
    }
    // Water stain spots
    for(let i=0;i<8;i++){
        const gx=Math.random()*256, gy=Math.random()*256;
        const gr=ctx.createRadialGradient(gx,gy,0,gx,gy,8+Math.random()*18);
        gr.addColorStop(0,'rgba(0,0,0,0.18)'); gr.addColorStop(1,'rgba(0,0,0,0)');
        ctx.fillStyle=gr; ctx.fillRect(0,0,256,256);
    }
    const t = new THREE.CanvasTexture(c); t.wrapS=t.wrapT=THREE.RepeatWrapping; t.repeat.set(4,4); return t;
}

// ---- BUILD OFFICE ----
function buildOffice() {
    officeGroup = new THREE.Group();
    scene.add(officeGroup);

    // Pre-build textures
    const wallTex = makeWallTexture();
    wallTex.wrapS = wallTex.wrapT = THREE.RepeatWrapping;
    wallTex.repeat.set(3, 1.5);
    const floorTex = makeFloorTexture();
    const ceilTex = makeCeilingTexture();
    const celebTex = makeCelebrateBanner();
    const freddyTex = makeFreddyPoster();
    const doorTex = makeDoorTexture();

    // === DIM LAMP LIGHTING (FNAF1 atmosphere) ===
    const ambientLight = new THREE.AmbientLight(0xffe8cc, 0.3);
    scene.add(ambientLight);
    // Single desk lamp - warm dim glow from above
    const overhead = new THREE.PointLight(0xffd060, 2.2, 11);
    overhead.position.set(0, 3.4, 0.8);
    overhead.castShadow = true;
    scene.add(overhead);
    // Subtle hallway glows
    const leftHallLight = new THREE.PointLight(0xffcc77, 0.7, 8);
    leftHallLight.position.set(-4, 2.5, -2);
    scene.add(leftHallLight);
    const rightHallLight = new THREE.PointLight(0xffcc77, 0.7, 8);
    rightHallLight.position.set(4, 2.5, -2);
    scene.add(rightHallLight);
    // Monitor glow
    const monitorGlow = new THREE.PointLight(0x5577aa, 1.6, 5);
    monitorGlow.position.set(0, 1.8, 1.0);
    scene.add(monitorGlow);
    // Desk lamp object hanging from ceiling
    const lampShadeGeo = new THREE.CylinderGeometry(0.32, 0.52, 0.36, 12, 1, true);
    const lampShadeMat = new THREE.MeshStandardMaterial({color:0x886644,roughness:0.8,side:THREE.DoubleSide,emissive:0x221100,emissiveIntensity:0.3});
    const lampShadeObj = new THREE.Mesh(lampShadeGeo, lampShadeMat);
    lampShadeObj.position.set(0, 3.32, 0.8); officeGroup.add(lampShadeObj);
    const lampBulb = new THREE.Mesh(new THREE.SphereGeometry(0.09,8,8), new THREE.MeshBasicMaterial({color:0xffeeaa}));
    lampBulb.position.set(0, 3.46, 0.8); officeGroup.add(lampBulb);
    const lampCordPts = [new THREE.Vector3(0,3.8,0.8), new THREE.Vector3(0,3.65,0.8)];
    officeGroup.add(new THREE.Line(new THREE.BufferGeometry().setFromPoints(lampCordPts), new THREE.LineBasicMaterial({color:0x222222})));

    // Door button glow lights
    leftLightObj = new THREE.PointLight(0xffee88, 0, 6);
    leftLightObj.position.set(-4.5, 2.2, -0.5);
    scene.add(leftLightObj);

    rightLightObj = new THREE.PointLight(0xffee88, 0, 6);
    rightLightObj.position.set(4.5, 2.2, -0.5);
    scene.add(rightLightObj);

    // === FLOOR ===
    const floorGeo = new THREE.PlaneGeometry(14, 12);
    const floorMat = new THREE.MeshStandardMaterial({ map: floorTex, roughness: 0.7, metalness: 0.05 });
    const floor = new THREE.Mesh(floorGeo, floorMat);
    floor.rotation.x = -Math.PI/2; floor.receiveShadow = true;
    officeGroup.add(floor);

    // === CEILING ===
    const ceilGeo = new THREE.PlaneGeometry(16, 14);
    const ceilMat = new THREE.MeshStandardMaterial({ map: ceilTex, roughness: 1 });
    const ceil = new THREE.Mesh(ceilGeo, ceilMat);
    ceil.rotation.x = Math.PI/2; ceil.position.y = 3.8;
    officeGroup.add(ceil);

    // Ceiling light fixture - glowing
    const fixtureGeo = new THREE.BoxGeometry(3.0, 0.1, 0.7);
    const fixtureMat = new THREE.MeshStandardMaterial({ color: 0xffffff, emissive: 0xffffee, emissiveIntensity: 2.5 });
    const fixture = new THREE.Mesh(fixtureGeo, fixtureMat);
    fixture.position.set(0, 3.72, -1);
    officeGroup.add(fixture);
    const fixture2 = new THREE.Mesh(new THREE.BoxGeometry(3.0, 0.1, 0.7), fixtureMat.clone());
    fixture2.position.set(0, 3.72, 1.5);
    officeGroup.add(fixture2);

    // === WALLS ===
    const wallMat = new THREE.MeshStandardMaterial({ map: wallTex, roughness: 0.85 });

    // Back wall
    const backWall = new THREE.Mesh(new THREE.BoxGeometry(14, 4.2, 0.2), wallMat);
    backWall.position.set(0, 2.1, -6); officeGroup.add(backWall);

    // Left wall
    const lwTex = makeWallTexture(); lwTex.wrapS=lwTex.wrapT=THREE.RepeatWrapping; lwTex.repeat.set(2,1);
    const leftWall = new THREE.Mesh(new THREE.BoxGeometry(0.2, 4.2, 12), new THREE.MeshStandardMaterial({map:lwTex,roughness:0.85}));
    leftWall.position.set(-7, 2.1, 0); officeGroup.add(leftWall);

    // Right wall
    const rwTex = makeWallTexture(); rwTex.wrapS=rwTex.wrapT=THREE.RepeatWrapping; rwTex.repeat.set(2,1);
    const rightWall = new THREE.Mesh(new THREE.BoxGeometry(0.2, 4.2, 12), new THREE.MeshStandardMaterial({map:rwTex,roughness:0.85}));
    rightWall.position.set(7, 2.1, 0); officeGroup.add(rightWall);

    // === WINDOWS (left and right walls - see outside night sky) ===
    (function(){
        const wc = document.createElement('canvas'); wc.width=256; wc.height=256;
        const wctx = wc.getContext('2d');
        const sky=wctx.createLinearGradient(0,0,0,256); sky.addColorStop(0,'#050a15'); sky.addColorStop(0.7,'#091225'); sky.addColorStop(1,'#121c32');
        wctx.fillStyle=sky; wctx.fillRect(0,0,256,256);
        for(let i=0;i<90;i++){const sx=Math.random()*256,sy=Math.random()*175; const br=Math.random(); wctx.fillStyle=`rgba(255,255,${Math.round(200+Math.random()*55)},${0.4+br*0.6})`; wctx.beginPath(); wctx.arc(sx,sy,0.4+Math.random()*1.4,0,Math.PI*2); wctx.fill();}
        // Moon
        wctx.fillStyle='rgba(240,240,200,0.88)'; wctx.beginPath(); wctx.arc(195,45,18,0,Math.PI*2); wctx.fill();
        wctx.fillStyle='rgba(200,200,160,0.3)'; wctx.beginPath(); wctx.arc(200,40,18,0,Math.PI*2); wctx.fill();
        // Ground silhouette
        wctx.fillStyle='#040805'; wctx.fillRect(0,188,256,68);
        for(let t=0;t<9;t++){const tx=t*32+Math.random()*18,th=28+Math.random()*48; wctx.fillStyle='#020503'; wctx.beginPath(); wctx.moveTo(tx,188); wctx.lineTo(tx+7,188-th); wctx.lineTo(tx+14,188); wctx.closePath(); wctx.fill(); wctx.beginPath(); wctx.moveTo(tx-3,188-th*0.5); wctx.lineTo(tx+7,188-th*0.82); wctx.lineTo(tx+17,188-th*0.5); wctx.closePath(); wctx.fill();}
        const winTex = new THREE.CanvasTexture(wc);
        const winMat = new THREE.MeshBasicMaterial({map:winTex});
        // Left window - on interior face of left wall
        const lWin=new THREE.Mesh(new THREE.PlaneGeometry(2.4,1.4),winMat.clone());
        lWin.position.set(-6.88,2.4,-1.8); lWin.rotation.y=Math.PI/2; officeGroup.add(lWin);
        // Right window - on interior face of right wall
        const rWin=new THREE.Mesh(new THREE.PlaneGeometry(2.4,1.4),winMat.clone());
        rWin.position.set(6.88,2.4,-1.8); rWin.rotation.y=-Math.PI/2; officeGroup.add(rWin);
        // Window frames - inside the wall surface
        const frameMat=new THREE.MeshStandardMaterial({color:0x6a5030,roughness:0.7});
        [-6.88,6.88].forEach((wx,side)=>{
            const wy=2.4,wz=-1.8;
            const ry=side===0?Math.PI/2:-Math.PI/2;
            // Top frame bar
            const topBar=new THREE.Mesh(new THREE.BoxGeometry(2.6,0.09,0.12),frameMat);
            topBar.position.set(wx,wy+0.76,wz); topBar.rotation.y=ry; officeGroup.add(topBar);
            // Bottom frame bar
            const botBar=new THREE.Mesh(new THREE.BoxGeometry(2.6,0.09,0.12),frameMat);
            botBar.position.set(wx,wy-0.76,wz); botBar.rotation.y=ry; officeGroup.add(botBar);
            // Left side bar
            const lBar=new THREE.Mesh(new THREE.BoxGeometry(0.09,1.6,0.12),frameMat);
            lBar.position.set(wx,wy,wz-1.25); lBar.rotation.y=ry; officeGroup.add(lBar);
            // Right side bar
            const rBar=new THREE.Mesh(new THREE.BoxGeometry(0.09,1.6,0.12),frameMat);
            rBar.position.set(wx,wy,wz+1.25); rBar.rotation.y=ry; officeGroup.add(rBar);
            // Center divider
            const cBar=new THREE.Mesh(new THREE.BoxGeometry(0.06,1.6,0.08),frameMat);
            cBar.position.set(wx,wy,wz); cBar.rotation.y=ry; officeGroup.add(cBar);
        });
        // Subtle moonlight glow from windows
        const moonGlow1=new THREE.PointLight(0x8899cc,0.4,6); moonGlow1.position.set(-6.5,2.4,-1.8); scene.add(moonGlow1);
        const moonGlow2=new THREE.PointLight(0x8899cc,0.4,6); moonGlow2.position.set(6.5,2.4,-1.8); scene.add(moonGlow2);
    })();

    // === CELEBRATE! BANNER ===
    const bannerGeo = new THREE.PlaneGeometry(4.2, 3.1);
    const bannerMat = new THREE.MeshStandardMaterial({ map: celebTex, roughness: 0.9, emissive: 0xffff00, emissiveIntensity: 0.05 });
    const banner = new THREE.Mesh(bannerGeo, bannerMat);
    banner.position.set(0, 2.55, -5.88); officeGroup.add(banner);

    // === FREDDY POSTER ===
    const posterGeo = new THREE.PlaneGeometry(1.4, 1.8);
    const posterMat = new THREE.MeshStandardMaterial({ map: freddyTex, roughness: 0.8 });
    const poster = new THREE.Mesh(posterGeo, posterMat);
    poster.position.set(-3.5, 2.3, -5.88); officeGroup.add(poster);
    // Poster frame
    const frameGeo = new THREE.BoxGeometry(1.5, 1.95, 0.05);
    const frameMat = new THREE.MeshStandardMaterial({ color: 0x4a3820, roughness: 0.6 });
    const frame = new THREE.Mesh(frameGeo, frameMat);
    frame.position.set(-3.5, 2.3, -5.95); officeGroup.add(frame);

    // === FNAF LOGO POSTER (right side) ===
    addColorPoster(3.5, 2.3, -5.88, '#001a0a', '#00ff44', 'FAZBEAR\nENTERT.');

    // === VARIOUS WALL DECORATIONS ===
    // Party streamers/balloons drawn on back wall
    addWallBalloons(-5, 1.5, -5.87);
    addWallBalloons(5, 1.5, -5.87);
    addWallBalloons(1.5, 1.8, -5.87);
    addWallBalloons(-1.5, 1.8, -5.87);

    // === DESK - BLACK with spiderwebs ===
    const deskTopMat = new THREE.MeshStandardMaterial({ color: 0x0a0a0a, roughness: 0.55, metalness: 0.25 });
    const deskTop = new THREE.Mesh(new THREE.BoxGeometry(5.5, 0.12, 1.4), deskTopMat);
    deskTop.position.set(0, 0.94, 1.8); deskTop.castShadow = true; officeGroup.add(deskTop);
    const deskFront = new THREE.Mesh(new THREE.BoxGeometry(5.5, 0.95, 0.08), new THREE.MeshStandardMaterial({color:0x080808,roughness:0.8}));
    deskFront.position.set(0, 0.475, 1.12); officeGroup.add(deskFront);
    const trimMat = new THREE.MeshStandardMaterial({ color: 0x222222, roughness: 0.3, metalness: 0.6 });
    const trim = new THREE.Mesh(new THREE.BoxGeometry(5.6, 0.04, 0.04), trimMat);
    trim.position.set(0, 0.88, 1.12); officeGroup.add(trim);
    const legMat = new THREE.MeshStandardMaterial({ color: 0x0d0d0d });
    [[-2.4, 1.1], [2.4, 1.1], [-2.4, 2.4], [2.4, 2.4]].forEach(([x, z]) => {
        const leg = new THREE.Mesh(new THREE.BoxGeometry(0.12, 0.94, 0.12), legMat);
        leg.position.set(x, 0.47, z); officeGroup.add(leg);
    });
    // Spiderwebs under desk corners
    function makeSpiderwebCanvas() {
        const wc = document.createElement('canvas'); wc.width=256; wc.height=128;
        const wctx = wc.getContext('2d');
        wctx.strokeStyle='rgba(200,200,200,0.4)'; wctx.lineWidth=0.9;
        [[64,20],[192,30],[128,15]].forEach(([cx,cy])=>{
            const r=38+Math.random()*15;
            for(let a=0;a<12;a++){const angle=a/12*Math.PI*2; wctx.beginPath(); wctx.moveTo(cx,cy); wctx.lineTo(cx+Math.cos(angle)*r,cy+Math.sin(angle)*r); wctx.stroke();}
            for(let ri=1;ri<=5;ri++){wctx.beginPath(); for(let a=0;a<13;a++){const angle=a/12*Math.PI*2,rr=ri*r/5; if(a===0) wctx.moveTo(cx+Math.cos(angle)*rr,cy+Math.sin(angle)*rr); else wctx.lineTo(cx+Math.cos(angle)*rr,cy+Math.sin(angle)*rr);} wctx.stroke();}
        });
        return wc;
    }
    const webTex = new THREE.CanvasTexture(makeSpiderwebCanvas());
    const webMat = new THREE.MeshBasicMaterial({map:webTex,transparent:true,opacity:0.65,side:THREE.DoubleSide});
    [[-2.1,0.55,1.5],[2.1,0.55,1.5],[-2.1,0.55,2.1],[2.1,0.55,2.1]].forEach(([wx,wy,wz])=>{
        const web=new THREE.Mesh(new THREE.PlaneGeometry(0.9,0.5),webMat.clone());
        web.position.set(wx,wy,wz); web.rotation.x=0.35; officeGroup.add(web);
    });
    const bigWeb=new THREE.Mesh(new THREE.PlaneGeometry(1.6,0.65),webMat.clone());
    bigWeb.position.set(-2.2,0.58,1.25); bigWeb.rotation.x=0.55; bigWeb.rotation.z=0.15; officeGroup.add(bigWeb);

    // === MONITOR ===
    const monBodyMat = new THREE.MeshStandardMaterial({ color: 0x1a1a1a, roughness: 0.4, metalness: 0.5 });
    const monBody = new THREE.Mesh(new THREE.BoxGeometry(2.2, 1.4, 0.14), monBodyMat);
    monBody.position.set(0, 1.7, 1.48); officeGroup.add(monBody);

    // Screen bezel - slightly rounded look
    const bezelMat = new THREE.MeshStandardMaterial({ color: 0x111111, roughness: 0.3 });
    const bezel = new THREE.Mesh(new THREE.BoxGeometry(2.1, 1.3, 0.04), bezelMat);
    bezel.position.set(0, 1.7, 1.42); officeGroup.add(bezel);

    // Monitor screen with live camera texture
    const screenGeo = new THREE.PlaneGeometry(1.95, 1.15);
    const camTexture = new THREE.CanvasTexture(camCanvas);
    camTexture.needsUpdate = true;
    const screenMat = new THREE.MeshBasicMaterial({ map: camTexture });
    const screen = new THREE.Mesh(screenGeo, screenMat);
    screen.position.set(0, 1.7, 1.42);
    officeGroup.add(screen);
    officeGroup.userData.camTexture = camTexture;
    officeGroup.userData.camScreen = screen;

    // Monitor stand
    const standMat = new THREE.MeshStandardMaterial({ color: 0x151515, roughness: 0.3, metalness: 0.6 });
    const stand = new THREE.Mesh(new THREE.BoxGeometry(0.06, 0.35, 0.06), standMat);
    stand.position.set(0, 1.02, 1.48); officeGroup.add(stand);
    const standBase = new THREE.Mesh(new THREE.BoxGeometry(0.55, 0.04, 0.3), standMat);
    standBase.position.set(0, 0.85, 1.48); officeGroup.add(standBase);

    // === DESK ITEMS ===
    // Red/white striped Fazband soda cup
    (function() {
        const dc = document.createElement('canvas'); dc.width=32; dc.height=64;
        const dctx = dc.getContext('2d');
        for(let i=0;i<8;i++){dctx.fillStyle=i%2===0?'#cc0000':'#ffffff';dctx.fillRect(0,i*8,32,8);}
        dctx.fillStyle='#aaaaaa'; dctx.fillRect(0,0,32,8);
        dctx.fillStyle='#ffdd00'; dctx.beginPath(); dctx.arc(16,32,6,0,Math.PI*2); dctx.fill();
        dctx.fillStyle='#cc0000'; dctx.font='bold 7px sans-serif'; dctx.textAlign='center'; dctx.fillText('FP',16,35);
        const drinkTex = new THREE.CanvasTexture(dc);
        const drink = new THREE.Mesh(new THREE.CylinderGeometry(0.07,0.065,0.28,12), new THREE.MeshStandardMaterial({map:drinkTex,roughness:0.5}));
        drink.position.set(2.0, 0.97, 1.65); officeGroup.add(drink);
        // Straw
        const straw = new THREE.Mesh(new THREE.CylinderGeometry(0.008,0.008,0.35,6), new THREE.MeshStandardMaterial({color:0xff2222}));
        straw.position.set(2.05,1.10,1.60); straw.rotation.z=0.15; officeGroup.add(straw);
    })();
    // Carl the Cupcake
    (function() {
        const cc = document.createElement('canvas'); cc.width=64; cc.height=80;
        const cctx = cc.getContext('2d');
        for(let i=0;i<4;i++){cctx.fillStyle=i%2===0?'#cc0000':'#ffffff';cctx.fillRect(i*16,44,16,36);}
        cctx.fillStyle='#d4a060'; cctx.beginPath(); cctx.roundRect(6,30,52,28,4); cctx.fill();
        cctx.fillStyle='#ffaabb'; cctx.beginPath(); cctx.arc(32,28,22,Math.PI,0); cctx.closePath(); cctx.fill();
        cctx.fillStyle='#ffe0e8'; cctx.beginPath(); cctx.arc(32,30,14,Math.PI,0); cctx.closePath(); cctx.fill();
        cctx.fillStyle='#fff0a0'; cctx.fillRect(28,10,8,20);
        cctx.fillStyle='#ff6600'; cctx.beginPath(); cctx.ellipse(32,8,4,7,0,0,Math.PI*2); cctx.fill();
        cctx.fillStyle='#ffff00'; cctx.beginPath(); cctx.ellipse(32,9,2,4,0,0,Math.PI*2); cctx.fill();
        // Carl eyes
        cctx.fillStyle='#fff'; cctx.beginPath(); cctx.ellipse(24,26,4,5,0,0,Math.PI*2); cctx.fill();
        cctx.fillStyle='#fff'; cctx.beginPath(); cctx.ellipse(40,26,4,5,0,0,Math.PI*2); cctx.fill();
        cctx.fillStyle='#000'; cctx.beginPath(); cctx.arc(24,27,2,0,Math.PI*2); cctx.fill();
        cctx.fillStyle='#000'; cctx.beginPath(); cctx.arc(40,27,2,0,Math.PI*2); cctx.fill();
        cctx.fillStyle='rgba(255,255,255,0.7)'; cctx.beginPath(); cctx.arc(23,25,1,0,Math.PI*2); cctx.fill();
        cctx.fillStyle='rgba(255,255,255,0.7)'; cctx.beginPath(); cctx.arc(39,25,1,0,Math.PI*2); cctx.fill();
        const cupcakeTex = new THREE.CanvasTexture(cc);
        const cupcake = new THREE.Mesh(new THREE.CylinderGeometry(0.09,0.085,0.2,10), new THREE.MeshStandardMaterial({map:cupcakeTex,roughness:0.8}));
        cupcake.position.set(-2.0, 0.97, 1.65); officeGroup.add(cupcake);
        const frosting = new THREE.Mesh(new THREE.SphereGeometry(0.09,8,6,0,Math.PI*2,0,Math.PI/2), new THREE.MeshStandardMaterial({color:0xffaabb,roughness:0.9}));
        frosting.position.set(-2.0,1.07,1.65); officeGroup.add(frosting);
        const candle = new THREE.Mesh(new THREE.CylinderGeometry(0.01,0.01,0.08,6), new THREE.MeshStandardMaterial({color:0xffe080}));
        candle.position.set(-2.0,1.13,1.65); officeGroup.add(candle);
        const flame = new THREE.Mesh(new THREE.SphereGeometry(0.015,6,6), new THREE.MeshBasicMaterial({color:0xff8800}));
        flame.position.set(-2.0,1.19,1.65); officeGroup.add(flame);
        const flameGlow = new THREE.PointLight(0xff6600,0.4,1.5);
        flameGlow.position.set(-2.0,1.19,1.65); scene.add(flameGlow);
    })();
    // Crumpled papers
    (function(){
        const pc=document.createElement('canvas'); pc.width=64; pc.height=64;
        const pctx=pc.getContext('2d');
        pctx.fillStyle='#ddd8c0'; pctx.fillRect(0,0,64,64);
        pctx.strokeStyle='rgba(100,90,70,0.25)'; pctx.lineWidth=1;
        for(let i=0;i<6;i++){pctx.beginPath();pctx.moveTo(Math.random()*64,Math.random()*64);pctx.lineTo(Math.random()*64,Math.random()*64);pctx.stroke();}
        pctx.strokeStyle='rgba(100,100,80,0.2)'; pctx.lineWidth=0.5;
        for(let y=8;y<64;y+=8){pctx.beginPath();pctx.moveTo(4,y);pctx.lineTo(60,y);pctx.stroke();}
        const paperTex=new THREE.CanvasTexture(pc);
        const paperMat=new THREE.MeshStandardMaterial({map:paperTex,roughness:1});
        [[-1.4,1.66],[-1.72,1.74],[-1.56,1.5]].forEach(([px,pz],i)=>{
            const paper=new THREE.Mesh(new THREE.BoxGeometry(0.32,0.01,0.24),paperMat.clone());
            paper.position.set(px,0.96,pz); paper.rotation.y=i*0.55; officeGroup.add(paper);
        });
    })();
    addDeskFan(1.8, 0.96, 1.65);

    // === FNAF1-STYLE FRONT DESK (visible at bottom of player view) ===
    // Camera is at z=-0.4 looking toward NEGATIVE z. Desk must be at z < -0.5 to be in front.
    // We place it at z=-1.0 to z=-2.2 so it fills the bottom of the FOV nicely.
    const fdMat  = new THREE.MeshStandardMaterial({ color: 0x111008, roughness: 0.75, metalness: 0.2 });
    const fdTrim = new THREE.MeshStandardMaterial({ color: 0x1e1a10, roughness: 0.4,  metalness: 0.6 });

    // Wide top surface
    const fdTop = new THREE.Mesh(new THREE.BoxGeometry(7.0, 0.14, 1.8), fdMat);
    fdTop.position.set(0, 0.88, -1.7);
    fdTop.castShadow = true; officeGroup.add(fdTop);

    // Front face panel (vertical face closest to camera)
    const fdFront = new THREE.Mesh(new THREE.BoxGeometry(7.0, 0.88, 0.1), fdMat);
    fdFront.position.set(0, 0.44, -0.82); officeGroup.add(fdFront);

    // Angled lower skirt
    const fdSkirt = new THREE.Mesh(new THREE.BoxGeometry(7.0, 0.22, 0.5), fdMat);
    fdSkirt.position.set(0, 0.11, -1.0);
    fdSkirt.rotation.x = 0.18; officeGroup.add(fdSkirt);

    // Shiny metal top trim
    const fdTopTrim = new THREE.Mesh(new THREE.BoxGeometry(7.1, 0.06, 0.06), fdTrim);
    fdTopTrim.position.set(0, 0.96, -0.82); officeGroup.add(fdTopTrim);

    // Side end-caps
    [-3.48, 3.48].forEach(sx => {
        const cap = new THREE.Mesh(new THREE.BoxGeometry(0.1, 0.9, 1.8), fdMat);
        cap.position.set(sx, 0.45, -1.7); officeGroup.add(cap);
    });

    // Row of small indicator lights on front face
    const indicatorColors = [0xff1100, 0x00ff44, 0xffcc00, 0x00ff44, 0xff1100, 0x00ff44, 0xffcc00];
    indicatorColors.forEach((col, i) => {
        const iMat = new THREE.MeshBasicMaterial({ color: col });
        const dot = new THREE.Mesh(new THREE.CylinderGeometry(0.022, 0.022, 0.025, 8), iMat);
        dot.rotation.x = Math.PI / 2;
        dot.position.set(-1.5 + i * 0.5, 0.64, -0.77); officeGroup.add(dot);
        const ig = new THREE.PointLight(col, 0.08, 0.5);
        ig.position.set(-1.5 + i * 0.5, 0.64, -0.76); scene.add(ig);
    });

    // Keyboard on desk surface
    const kbMat2 = new THREE.MeshStandardMaterial({ color: 0x0c0c0c, roughness: 0.65 });
    const fdKb = new THREE.Mesh(new THREE.BoxGeometry(0.85, 0.03, 0.32), kbMat2);
    fdKb.position.set(0.5, 0.91, -1.5); officeGroup.add(fdKb);
    const kMat2 = new THREE.MeshStandardMaterial({ color: 0x1c1c1c, roughness: 0.5 });
    for (let row = 0; row < 3; row++) for (let col2 = 0; col2 < 11; col2++) {
        const k = new THREE.Mesh(new THREE.BoxGeometry(0.058, 0.018, 0.052), kMat2);
        k.position.set(0.14 + col2 * 0.064, 0.929, -1.62 + row * 0.072); officeGroup.add(k);
    }

    // Notepad / schedule sheet
    const npMat = new THREE.MeshStandardMaterial({ color: 0xf0ead8, roughness: 1.0 });
    const notepad2 = new THREE.Mesh(new THREE.BoxGeometry(0.55, 0.015, 0.44), npMat);
    notepad2.position.set(-1.5, 0.896, -1.6); notepad2.rotation.y = 0.12; officeGroup.add(notepad2);
    const lnMat = new THREE.MeshBasicMaterial({ color: 0xbbbbaa });
    for (let li = 0; li < 6; li++) {
        const ln = new THREE.Mesh(new THREE.BoxGeometry(0.42, 0.002, 0.007), lnMat);
        ln.position.set(-1.5, 0.905, -1.75 + li * 0.058); ln.rotation.y = 0.12; officeGroup.add(ln);
    }

    // Small desk lamp on front desk
    const deskLampMat = new THREE.MeshStandardMaterial({ color: 0x443322, roughness: 0.6 });
    const dlBase = new THREE.Mesh(new THREE.CylinderGeometry(0.1, 0.13, 0.055, 10), deskLampMat);
    dlBase.position.set(2.8, 0.91, -1.5); officeGroup.add(dlBase);
    const dlNeck = new THREE.Mesh(new THREE.CylinderGeometry(0.022, 0.022, 0.28, 7), deskLampMat);
    dlNeck.position.set(2.8, 1.05, -1.5); officeGroup.add(dlNeck);
    const dlShade = new THREE.Mesh(new THREE.CylinderGeometry(0.16, 0.26, 0.22, 10, 1, true),
        new THREE.MeshStandardMaterial({ color: 0x554422, roughness: 0.7, side: THREE.DoubleSide }));
    dlShade.position.set(2.8, 1.22, -1.5); officeGroup.add(dlShade);
    const dlBulb = new THREE.Mesh(new THREE.SphereGeometry(0.055, 7, 7),
        new THREE.MeshBasicMaterial({ color: 0xffeeaa }));
    dlBulb.position.set(2.8, 1.28, -1.5); officeGroup.add(dlBulb);
    const dlGlow = new THREE.PointLight(0xffcc66, 1.2, 3.5);
    dlGlow.position.set(2.8, 1.1, -1.5); scene.add(dlGlow);

    // === DOOR FRAMES & DOORS ===
    buildDoorFrame(-5.5, true);
    buildDoorFrame(5.5, false);

    leftDoorObj = makeDoor(-5.4, doorTex);
    rightDoorObj = makeDoor(5.4, doorTex);
    leftDoorObj.visible = false; rightDoorObj.visible = false;
    officeGroup.add(leftDoorObj); officeGroup.add(rightDoorObj);

    // Left hallway depth
    addHallDepth(-5.5, true);
    addHallDepth(5.5, false);

    // Hallway wall texture continuation
    addHallwayWalls(-5.5, true);
    addHallwayWalls(5.5, false);
}

function addWallBalloons(x, y, z) {
    const colors = [0xff4444, 0x4444ff, 0xffff00, 0x44ff44, 0xff44ff];
    colors.forEach((col, i) => {
        const ballMat = new THREE.MeshStandardMaterial({ color: col, roughness: 0.3, emissive: new THREE.Color(col).multiplyScalar(0.1) });
        const bx = x + (i-2)*0.3 + (Math.random()-0.5)*0.2;
        const by = y + Math.random()*0.6;
        const balloon = new THREE.Mesh(new THREE.SphereGeometry(0.18, 8, 8), ballMat);
        balloon.position.set(bx, by, z+0.02); officeGroup.add(balloon);
        // String
        const strMat = new THREE.LineBasicMaterial({ color: 0xaaaaaa });
        const pts = [new THREE.Vector3(bx, by-0.18, z+0.02), new THREE.Vector3(bx+0.05, by-0.5, z+0.02)];
        const strGeo = new THREE.BufferGeometry().setFromPoints(pts);
        officeGroup.add(new THREE.Line(strGeo, strMat));
    });
}

function addColorPoster(x, y, z, bg, accent, label) {
    const c = document.createElement('canvas'); c.width=256; c.height=320;
    const ctx = c.getContext('2d');
    const grad = ctx.createLinearGradient(0,0,0,320);
    grad.addColorStop(0, bg); grad.addColorStop(1, '#000a06');
    ctx.fillStyle=grad; ctx.fillRect(0,0,256,320);
    // Border
    ctx.strokeStyle=accent; ctx.lineWidth=6; ctx.strokeRect(8,8,240,304);
    ctx.strokeStyle=accent+'88'; ctx.lineWidth=2; ctx.strokeRect(14,14,228,292);
    // Stars
    ctx.fillStyle=accent;
    for(let i=0;i<12;i++){
        ctx.beginPath(); ctx.arc(20+Math.random()*216, 20+Math.random()*280, 2+Math.random()*3, 0, Math.PI*2); ctx.fill();
    }
    // Text
    ctx.fillStyle=accent; ctx.font='bold 32px monospace'; ctx.textAlign='center';
    label.split('\n').forEach((l,i) => ctx.fillText(l, 128, 130+i*40));
    ctx.font='18px monospace'; ctx.fillStyle=accent+'aa'; ctx.fillText('EST. 1983', 128, 260);
    const tex = new THREE.CanvasTexture(c);
    const p = new THREE.Mesh(new THREE.PlaneGeometry(1.4, 1.8), new THREE.MeshStandardMaterial({map:tex,roughness:0.8}));
    p.position.set(x,y,z); officeGroup.add(p);
    const fr = new THREE.Mesh(new THREE.BoxGeometry(1.5, 1.95, 0.05), new THREE.MeshStandardMaterial({color:0x3a2810}));
    fr.position.set(x,y,z-0.07); officeGroup.add(fr);
}

function addDeskFan(x, y, z) {
    // Fan base
    const mat = new THREE.MeshStandardMaterial({ color: 0x888888, roughness: 0.5, metalness: 0.4 });
    const base = new THREE.Mesh(new THREE.CylinderGeometry(0.12, 0.14, 0.06, 8), mat);
    base.position.set(x, y+0.03, z); officeGroup.add(base);
    // Neck
    const neck = new THREE.Mesh(new THREE.CylinderGeometry(0.03, 0.03, 0.3, 6), mat);
    neck.position.set(x, y+0.18, z); officeGroup.add(neck);
    // Fan head (cage)
    const cage = new THREE.Mesh(new THREE.TorusGeometry(0.14, 0.02, 6, 16), mat);
    cage.position.set(x, y+0.35, z); officeGroup.add(cage);
    // Fan blades
    const bladeMat = new THREE.MeshStandardMaterial({ color: 0xaaaaaa, roughness: 0.3, metalness: 0.6, side: THREE.DoubleSide });
    [0,1,2].forEach(i => {
        const blade = new THREE.Mesh(new THREE.PlaneGeometry(0.1, 0.12), bladeMat);
        blade.position.set(x + Math.cos(i*Math.PI*2/3)*0.08, y+0.35, z + Math.sin(i*Math.PI*2/3)*0.08);
        blade.rotation.y = i*Math.PI*2/3; blade.userData.isBlade = true;
        officeGroup.add(blade);
    });
}

function addHallwayWalls(x, isLeft) {
    const hwTex = makeWallTexture(); hwTex.wrapS=hwTex.wrapT=THREE.RepeatWrapping; hwTex.repeat.set(1,1);
    const hwMat = new THREE.MeshStandardMaterial({ map: hwTex, roughness: 0.9 });
    // Back wall of hallway
    const hw = new THREE.Mesh(new THREE.PlaneGeometry(2.5, 3.8), hwMat);
    hw.position.set(x+(isLeft?-1.2:1.2), 1.9, -5.5);
    hw.rotation.y = isLeft ? Math.PI/2 : -Math.PI/2;
    officeGroup.add(hw);
}

function buildDoorFrame(x, isLeft) {
    const frameMat = new THREE.MeshStandardMaterial({ color: 0x333344, roughness: 0.7, metalness: 0.3 });
    // Door opening is 2.0 wide (z from -1.6 to 0.4), 3.2 tall
    // Top horizontal beam - sits above door opening only
    const top = new THREE.Mesh(new THREE.BoxGeometry(0.22, 0.28, 2.2), frameMat);
    top.position.set(x, 3.34, -0.6); officeGroup.add(top);
    // Left side post (front side z=0.3)
    const sideF = new THREE.Mesh(new THREE.BoxGeometry(0.22, 3.4, 0.22), frameMat);
    sideF.position.set(x, 1.7, 0.3); officeGroup.add(sideF);
    // Right side post (back side z=-1.5)
    const sideB = new THREE.Mesh(new THREE.BoxGeometry(0.22, 3.4, 0.22), frameMat);
    sideB.position.set(x, 1.7, -1.5); officeGroup.add(sideB);
    // Warning stripes on floor
    const stripeMat = new THREE.MeshStandardMaterial({
        color: 0xff4400, emissive: 0x551100, emissiveIntensity: 0.5
    });
    const floorStripe = new THREE.Mesh(new THREE.BoxGeometry(0.3, 0.02, 2.2), stripeMat);
    floorStripe.position.set(x, 0.01, -0.6); officeGroup.add(floorStripe);
    // Door button panel
    addButtonPanel(x + (isLeft ? 0.55 : -0.55), 1.4, -1.2);
}

function makeDoor(x, doorTex) {
    const mat = new THREE.MeshStandardMaterial({ map: doorTex, roughness: 0.5, metalness: 0.4 });
    // Flat rectangle door - thin slab that fills the door opening cleanly
    const door = new THREE.Mesh(new THREE.BoxGeometry(0.1, 3.3, 1.95), mat);
    door.position.set(x, 1.65, -0.62);
    return door;
}

function addButtonPanel(x, y, z) {
    const panelMat = new THREE.MeshStandardMaterial({ color: 0x222233, roughness: 0.5 });
    const panel = new THREE.Mesh(new THREE.BoxGeometry(0.1, 0.5, 0.35), panelMat);
    panel.position.set(x, y, z); officeGroup.add(panel);
    // Buttons
    const btnMat = new THREE.MeshStandardMaterial({ color: 0xff2200, emissive: 0x880000, emissiveIntensity: 0.8 });
    const btn = new THREE.Mesh(new THREE.CylinderGeometry(0.07, 0.07, 0.05, 8), btnMat);
    btn.position.set(x, y+0.08, z); btn.rotation.z = Math.PI/2; officeGroup.add(btn);
    const btnMat2 = new THREE.MeshStandardMaterial({ color: 0x22ff44, emissive: 0x008822, emissiveIntensity: 0.8 });
    const btn2 = new THREE.Mesh(new THREE.CylinderGeometry(0.07, 0.07, 0.05, 8), btnMat2);
    btn2.position.set(x, y-0.08, z); btn2.rotation.z = Math.PI/2; officeGroup.add(btn2);
}

function addPoster(x, y, z, bg, accent, label) {
    const posterMat = new THREE.MeshStandardMaterial({
        color: new THREE.Color(bg), emissive: new THREE.Color(accent),
        emissiveIntensity: 0.3, roughness: 0.9
    });
    const poster = new THREE.Mesh(new THREE.PlaneGeometry(1.1, 1.4), posterMat);
    poster.position.set(x, y, z+0.01); officeGroup.add(poster);
    // Frame
    const frameMat = new THREE.MeshStandardMaterial({ color: 0x4a3820 });
    const frame = new THREE.Mesh(new THREE.PlaneGeometry(1.2, 1.5), frameMat);
    frame.position.set(x, y, z); officeGroup.add(frame);
}

function addDeskCup(x, y, z) {
    const mat = new THREE.MeshStandardMaterial({ color: 0x663300, roughness: 0.6 });
    const cup = new THREE.Mesh(new THREE.CylinderGeometry(0.08, 0.07, 0.22, 8), mat);
    cup.position.set(x, y+0.11, z); officeGroup.add(cup);
}

function addDeskPapers(x, y, z) {
    const mat = new THREE.MeshStandardMaterial({ color: 0xeeeecc, roughness: 1 });
    const paper = new THREE.Mesh(new THREE.BoxGeometry(0.4, 0.01, 0.3), mat);
    paper.position.set(x, y+0.01, z); paper.rotation.y = 0.2; officeGroup.add(paper);
}

function addHallDepth(x, isLeft) {
    // Dark hall opening suggestion
    const dMat = new THREE.MeshStandardMaterial({ color: 0x0a0810, roughness: 1 });
    const depth = new THREE.Mesh(new THREE.BoxGeometry(1.8, 3.5, 4), dMat);
    depth.position.set(x + (isLeft ? -1 : 1), 1.75, -3.5);
    officeGroup.add(depth);
}

// ---- ANIMATRONIC 3D MODELS (visible in office when at doors) ----
function buildAnimatronicModels() {
    const configs = {
        freddy: { body: 0x7a3a10, hat: 0x2a1200, eyeCol: 0xffffff, glow: 0xff8800, bellyCol: 0xc8956e, bowtieCol: 0x1a0800 },
        bonnie: { body: 0x5a0d8a, hat: 0x2a0050, eyeCol: 0xff88ff, glow: 0xaa44ff, bellyCol: 0xddaaff, bowtieCol: 0x220044 },
        chica:  { body: 0xcc9900, hat: 0x886600, eyeCol: 0xffffff, glow: 0xffdd00, bellyCol: 0xffffff, bowtieCol: 0xff4400 },
        foxy:   { body: 0xcc2200, hat: 0x881100, eyeCol: 0xff8800, glow: 0xff4400, bellyCol: 0xddaa88, bowtieCol: 0x440000 },
    };

    for (const [name, cfg] of Object.entries(configs)) {
        const group = new THREE.Group();

        // Legs (lower body)
        [-0.18, 0.18].forEach(lx => {
            // Upper leg
            const upperLeg = new THREE.Mesh(new THREE.BoxGeometry(0.22, 0.55, 0.25),
                new THREE.MeshStandardMaterial({ color: cfg.body, roughness: 0.7 }));
            upperLeg.position.set(lx, -0.15, 0); group.add(upperLeg);
            // Lower leg / foot
            const lowerLeg = new THREE.Mesh(new THREE.BoxGeometry(0.2, 0.4, 0.28),
                new THREE.MeshStandardMaterial({ color: 0x111111, roughness: 0.5 }));
            lowerLeg.position.set(lx, -0.58, 0.02); group.add(lowerLeg);
            // Foot
            const foot = new THREE.Mesh(new THREE.BoxGeometry(0.22, 0.1, 0.38),
                new THREE.MeshStandardMaterial({ color: 0x0a0a0a, roughness: 0.4 }));
            foot.position.set(lx, -0.82, 0.07); group.add(foot);
        });

        // Torso / Body
        const body = new THREE.Mesh(new THREE.BoxGeometry(0.75, 1.05, 0.52),
            new THREE.MeshStandardMaterial({ color: cfg.body, roughness: 0.65 }));
        body.position.y = 0.58; group.add(body);

        // Belly plate
        const belly = new THREE.Mesh(new THREE.BoxGeometry(0.42, 0.52, 0.08),
            new THREE.MeshStandardMaterial({ color: cfg.bellyCol, roughness: 0.9 }));
        belly.position.set(0, 0.58, 0.27); group.add(belly);

        // Chest detail - slight protrusion / chest plate
        const chest = new THREE.Mesh(new THREE.BoxGeometry(0.55, 0.28, 0.06),
            new THREE.MeshStandardMaterial({ color: new THREE.Color(cfg.body).multiplyScalar(1.15), roughness: 0.6 }));
        chest.position.set(0, 0.78, 0.28); group.add(chest);

        // Bowtie
        const btieMat = new THREE.MeshStandardMaterial({ color: cfg.bowtieCol, roughness: 0.6 });
        [-0.11,0.11].forEach((bx,bi) => {
            const btieSide = new THREE.Mesh(new THREE.BoxGeometry(0.11, 0.1, 0.05), btieMat);
            btieSide.position.set(bx, 1.04, 0.28); btieSide.rotation.z = bi===0?0.25:-0.25; group.add(btieSide);
        });

        // Neck
        const neck = new THREE.Mesh(new THREE.BoxGeometry(0.28, 0.18, 0.24),
            new THREE.MeshStandardMaterial({ color: cfg.body, roughness: 0.7 }));
        neck.position.set(0, 1.14, 0); group.add(neck);

        // Head
        const head = new THREE.Mesh(new THREE.BoxGeometry(0.68, 0.68, 0.58),
            new THREE.MeshStandardMaterial({ color: cfg.body, roughness: 0.6 }));
        head.position.y = 1.42; group.add(head);

        // Cheeks (rounded cheek pads)
        [-0.32, 0.32].forEach(cx => {
            const cheek = new THREE.Mesh(new THREE.SphereGeometry(0.12, 8, 6),
                new THREE.MeshStandardMaterial({ color: new THREE.Color(cfg.body).multiplyScalar(0.85), roughness: 0.8 }));
            cheek.position.set(cx, 1.38, 0.22); group.add(cheek);
        });

        // Snout (muzzle)
        const snoutW = name === 'foxy' ? 0.22 : 0.28;
        const snout = new THREE.Mesh(new THREE.BoxGeometry(snoutW, 0.2, 0.22),
            new THREE.MeshStandardMaterial({ color: new THREE.Color(cfg.body).multiplyScalar(0.78), roughness: 0.8 }));
        snout.position.set(0, 1.36, 0.35); group.add(snout);

        // Mouth line
        const mouthMat = new THREE.MeshBasicMaterial({ color: 0x1a0800 });
        const mouth = new THREE.Mesh(new THREE.BoxGeometry(0.22, 0.025, 0.03), mouthMat);
        mouth.position.set(0, 1.27, 0.46); group.add(mouth);
        // Teeth
        const teethMat = new THREE.MeshBasicMaterial({ color: 0xfff5e0 });
        [-0.06, 0, 0.06].forEach(tx => {
            const tooth = new THREE.Mesh(new THREE.BoxGeometry(0.04, 0.06, 0.025), teethMat);
            tooth.position.set(tx, 1.31, 0.46); group.add(tooth);
        });

        // Nose
        const noseMat = new THREE.MeshBasicMaterial({ color: 0x111111 });
        const nose = new THREE.Mesh(new THREE.SphereGeometry(0.035, 6, 6), noseMat);
        nose.position.set(0, 1.42, 0.47); group.add(nose);

        // Eyes (larger, more detailed)
        [-0.18, 0.18].forEach((ex, i) => {
            // Eye white / sclera
            const eyeWhite = new THREE.Mesh(new THREE.SphereGeometry(0.1, 10, 8),
                new THREE.MeshBasicMaterial({ color: cfg.eyeCol }));
            eyeWhite.position.set(ex, 1.48, 0.3); group.add(eyeWhite);
            // Iris
            const irisMat = new THREE.MeshBasicMaterial({ color: name==='chica'?0x3399ff : name==='foxy'?0xff6600 : 0x2244aa });
            const iris = new THREE.Mesh(new THREE.SphereGeometry(0.062, 8, 8), irisMat);
            iris.position.set(ex, 1.48, 0.37); group.add(iris);
            // Pupil
            const pupil = new THREE.Mesh(new THREE.SphereGeometry(0.038, 6, 6),
                new THREE.MeshBasicMaterial({ color: 0x000000 }));
            pupil.position.set(ex, 1.48, 0.41); group.add(pupil);
            // Eye shine
            const shine = new THREE.Mesh(new THREE.SphereGeometry(0.018, 5, 5),
                new THREE.MeshBasicMaterial({ color: 0xffffff }));
            shine.position.set(ex+0.025, 1.5, 0.43); group.add(shine);
        });

        // Eyebrows
        const browMat = new THREE.MeshBasicMaterial({ color: 0x111111 });
        [-0.18, 0.18].forEach((ex, i) => {
            const brow = new THREE.Mesh(new THREE.BoxGeometry(0.18, 0.03, 0.03), browMat);
            brow.position.set(ex, 1.61, 0.3); brow.rotation.z = i===0?0.2:-0.2; group.add(brow);
        });

        // Hat (Freddy & Bonnie) - better proportioned
        if (name === 'freddy' || name === 'bonnie') {
            const hatMat = new THREE.MeshStandardMaterial({ color: cfg.hat, roughness: 0.8 });
            const brim = new THREE.Mesh(new THREE.CylinderGeometry(0.38, 0.38, 0.055, 12), hatMat);
            brim.position.y = 1.79; group.add(brim);
            const hatTop = new THREE.Mesh(new THREE.CylinderGeometry(0.24, 0.3, 0.42, 12), hatMat);
            hatTop.position.y = 2.02; group.add(hatTop);
            // Hat band
            const bandMat = new THREE.MeshStandardMaterial({ color: name==='freddy'?0xff6600:0x660088, roughness: 0.6 });
            const band = new THREE.Mesh(new THREE.CylinderGeometry(0.242, 0.242, 0.08, 12), bandMat);
            band.position.y = 1.84; group.add(band);
        }

        // Chica bib (white with text)
        if (name === 'chica') {
            const bibMat = new THREE.MeshStandardMaterial({ color: 0xffffff, roughness: 0.9 });
            const bib = new THREE.Mesh(new THREE.BoxGeometry(0.38, 0.32, 0.04), bibMat);
            bib.position.set(0, 0.55, 0.29); group.add(bib);
            // "LET'S EAT!" on bib as colored detail
            const textMat = new THREE.MeshBasicMaterial({ color: 0xff3300 });
            const textBar = new THREE.Mesh(new THREE.BoxGeometry(0.28, 0.04, 0.02), textMat);
            textBar.position.set(0, 0.56, 0.32); group.add(textBar);
        }

        // Arms - better shaped
        [-0.52, 0.52].forEach((ax, i) => {
            // Upper arm
            const upperArm = new THREE.Mesh(new THREE.BoxGeometry(0.2, 0.52, 0.22),
                new THREE.MeshStandardMaterial({ color: cfg.body, roughness: 0.7 }));
            upperArm.position.set(ax, 0.68, 0);
            upperArm.rotation.z = (i===0 ? 1 : -1) * 0.22;
            group.add(upperArm);
            // Lower arm / hand
            const lowerArm = new THREE.Mesh(new THREE.BoxGeometry(0.17, 0.44, 0.19),
                new THREE.MeshStandardMaterial({ color: new THREE.Color(cfg.body).multiplyScalar(0.9), roughness: 0.7 }));
            lowerArm.position.set(ax * 1.08, 0.28, 0.04);
            lowerArm.rotation.z = (i===0 ? 1 : -1) * 0.12;
            group.add(lowerArm);
            // Hand/claw
            const hand = new THREE.Mesh(new THREE.BoxGeometry(0.2, 0.18, 0.2),
                new THREE.MeshStandardMaterial({ color: 0x111111, roughness: 0.4 }));
            hand.position.set(ax * 1.12, 0.04, 0.04); group.add(hand);
            // Fingers
            [-0.07, 0, 0.07].forEach(fx => {
                const finger = new THREE.Mesh(new THREE.BoxGeometry(0.045, 0.12, 0.045),
                    new THREE.MeshStandardMaterial({ color: 0x0d0d0d, roughness: 0.5 }));
                finger.position.set(ax * 1.12 + fx, -0.07, 0.04); group.add(finger);
            });
        });

        // Foxy hook
        if (name === 'foxy') {
            const hook = new THREE.Mesh(
                new THREE.TorusGeometry(0.14, 0.035, 8, 14, Math.PI * 1.3),
                new THREE.MeshStandardMaterial({ color: 0xaaaaaa, metalness: 0.9, roughness: 0.15 })
            );
            hook.position.set(0.5, 0.24, 0.1); hook.rotation.z = Math.PI/2; group.add(hook);
            // Hook shine
            const hookShine = new THREE.Mesh(new THREE.TorusGeometry(0.14, 0.01, 4, 10, Math.PI * 0.4),
                new THREE.MeshBasicMaterial({ color: 0xffffff }));
            hookShine.position.set(0.5, 0.24, 0.11); hookShine.rotation.z = Math.PI/2; group.add(hookShine);
            // Foxy also has a torn/patchy look
            const patchMat = new THREE.MeshStandardMaterial({ color: 0x991a00, roughness: 0.9 });
            [[0.1, 0.5, 0.27], [-0.15, 0.3, 0.27], [0.2, 0.8, 0.27]].forEach(([px,py,pz]) => {
                const patch = new THREE.Mesh(new THREE.BoxGeometry(0.14, 0.1, 0.04), patchMat);
                patch.position.set(px, py, pz); patch.rotation.z = Math.random()*0.5; group.add(patch);
            });
        }

        // Eye glow light
        const glow = new THREE.PointLight(cfg.glow, 0, 3);
        glow.position.y = 1.48; group.add(glow);
        group.userData.glow = glow;

        group.visible = false;
        group.position.set(0, 0, -20);
        scene.add(group);
        animModels[name] = group;
    }
}

// ---- CAMERA MONITOR DRAWING ----
function drawCameraMonitor() {
    const W = camCanvas.width, H = camCanvas.height;
    const loc = CAM_LOCATIONS[activeCamIndex];
    const theme = CAM_BG_COLORS[loc] || { bg: '#111', floor: '#1a1a1a', accent: '#333' };
    const ctx = camCtx;

    // Scanline flicker
    const flicker = 0.88 + Math.random() * 0.12;
    const t = Date.now() * 0.001;

    // === ROOM BACKGROUND ===
    // Sky gradient for room depth
    const bg = ctx.createLinearGradient(0, 0, 0, H);
    bg.addColorStop(0, theme.bg);
    bg.addColorStop(0.65, theme.floor);
    bg.addColorStop(1, darken(theme.floor, 0.7));
    ctx.fillStyle = bg;
    ctx.fillRect(0, 0, W, H);

    // === DRAW ROOM-SPECIFIC DETAILS ===
    if (loc === LOCATIONS.STAGE) {
        drawShowStage(ctx, W, H, t);
    } else if (loc === LOCATIONS.DINING) {
        drawDiningArea(ctx, W, H, t);
    } else if (loc === LOCATIONS.PIRATE_COVE) {
        drawPirateCove(ctx, W, H, t);
    } else if (loc === LOCATIONS.BACKSTAGE) {
        drawBackstage(ctx, W, H, t);
    } else if (loc === LOCATIONS.SUPPLY) {
        drawSupplyCloset(ctx, W, H, t);
    } else {
        drawGenericHallway(ctx, W, H, theme, t);
    }

    // Foxy running down west hall
    if (loc === LOCATIONS.WEST_HALL && animatronics.foxy && animatronics.foxy.location === 'running') {
        const prog = animatronics.foxy.runProgress || 0;
        // Foxy sprints from far end toward camera
        const foxyX = W * (0.15 + prog * 0.5);
        const foxyScale = 0.4 + prog * 0.7;
        // Motion blur
        for(let mb=3;mb>=1;mb--) {
            camCtx.globalAlpha = 0.12/mb;
            drawAnimatronicSprite(camCtx, 'foxy', foxyX - mb*22, H*0.62, foxyScale*0.9, false);
        }
        camCtx.globalAlpha = 1;
        drawAnimatronicSprite(camCtx, 'foxy', foxyX, H*0.62, foxyScale, false);
    }
    // Check animatronics
    const presentAnimatronics = [];
    for (const [name, a] of Object.entries(animatronics)) {
        if (a.location === loc) presentAnimatronics.push(name);
    }
    if (loc === LOCATIONS.PIRATE_COVE) {
        const foxy = animatronics.foxy;
        if (['peek1','peek2','peek3'].includes(foxy.location)) {
            presentAnimatronics.push('foxy_peek');
        }
    }

    // Draw animatronics
    if (presentAnimatronics.length > 0) {
        presentAnimatronics.forEach((name, i) => {
            const xOffset = W * 0.5 + (i - presentAnimatronics.length/2 + 0.5) * 130;
            const actualName = name.replace('_peek', '');
            const isPeek = name.includes('_peek');
            drawAnimatronicSprite(ctx, actualName, xOffset, H * 0.62, isPeek ? 0.55 : 1.0, isPeek);
        });
    } else {
        ctx.fillStyle = theme.accent + '44';
        ctx.font = '12px monospace';
        ctx.textAlign = 'center';
        ctx.fillText('[ EMPTY ]', W/2, H*0.55);
    }

    // Camera label bar
    ctx.fillStyle = 'rgba(0,0,0,0.65)';
    ctx.fillRect(0, 0, W, 26);
    // REC dot blinking
    const recAlpha = (Math.sin(t * 3) > 0) ? 1 : 0.3;
    ctx.fillStyle = `rgba(255,0,0,${recAlpha})`;
    ctx.beginPath(); ctx.arc(10, 13, 5, 0, Math.PI*2); ctx.fill();
    ctx.fillStyle = '#00ff88';
    ctx.font = 'bold 13px monospace';
    ctx.textAlign = 'left';
    ctx.fillText(' REC  ' + CAM_NAMES[activeCamIndex], 18, 17);

    // Timestamp top right
    const hrs = [12,1,2,3,4,5,6];
    ctx.fillStyle = '#88ffaa';
    ctx.font = '12px monospace';
    ctx.textAlign = 'right';
    ctx.fillText(hrs[Math.min(Math.floor(nightHour),6)] + ':' + String(Math.floor((nightHour%1)*60)).padStart(2,'0') + ' AM', W-8, 17);

    // CRT scanlines effect
    for (let y = 0; y < H; y += 2) {
        ctx.fillStyle = 'rgba(0,0,0,0.12)';
        ctx.fillRect(0, y, W, 1);
    }

    // Vignette
    const vign = ctx.createRadialGradient(W/2, H/2, H*0.2, W/2, H/2, H*0.75);
    vign.addColorStop(0, 'rgba(0,0,0,0)');
    vign.addColorStop(1, 'rgba(0,0,0,0.4)');
    ctx.fillStyle = vign;
    ctx.fillRect(0, 0, W, H);

    // Random static noise
    if (Math.random() < 0.06) {
        ctx.fillStyle = 'rgba(255,255,255,0.035)';
        for (let n = 0; n < 300; n++) {
            ctx.fillRect(Math.random()*W, Math.random()*H, Math.random()*4+1, 1);
        }
    }
    // Glitch line
    if (Math.random() < 0.03) {
        const gy = Math.random() * H;
        ctx.fillStyle = 'rgba(0,255,100,0.12)';
        ctx.fillRect(0, gy, W, 2+Math.random()*3);
    }

    // Overall darkness flicker
    ctx.fillStyle = `rgba(0,0,0,${(1-flicker)*0.4})`;
    ctx.fillRect(0, 0, W, H);

    if (officeGroup && officeGroup.userData.camTexture) {
        officeGroup.userData.camTexture.needsUpdate = true;
    }
}

function drawShowStage(ctx, W, H, t) {
    // Colorful stage background
    const bgGrad = ctx.createLinearGradient(0,0,0,H);
    bgGrad.addColorStop(0,'#1a0a2a'); bgGrad.addColorStop(0.7,'#2a1a3a'); bgGrad.addColorStop(1,'#0d0814');
    ctx.fillStyle=bgGrad; ctx.fillRect(0,0,W,H);
    // Stage platform
    ctx.fillStyle='#3a2a10';
    ctx.fillRect(0, H*0.6, W, H*0.4);
    ctx.fillStyle='#2a1a08';
    ctx.fillRect(0, H*0.6, W, 6);
    // Colorful balloons on wall
    const ballColors = ['#ff4444','#4444ff','#ffff44','#44ff44','#ff44ff','#44ffff'];
    for(let i=0;i<18;i++){
        const bx = (i/17)*W*0.9 + W*0.05;
        const by = 30 + Math.sin(t+i*0.7)*8 + (i%3)*15;
        ctx.fillStyle = ballColors[i%ballColors.length];
        ctx.beginPath(); ctx.arc(bx, by, 14, 0, Math.PI*2); ctx.fill();
        // String
        ctx.strokeStyle='rgba(200,200,200,0.4)'; ctx.lineWidth=1;
        ctx.beginPath(); ctx.moveTo(bx, by+14); ctx.lineTo(bx+5, by+35); ctx.stroke();
    }
    // Curtains
    ctx.fillStyle='#6a0000';
    ctx.fillRect(0, 0, W*0.15, H); ctx.fillRect(W*0.85, 0, W*0.15, H);
    // Curtain folds
    ctx.strokeStyle='#880000'; ctx.lineWidth=2;
    for(let i=1;i<4;i++){
        ctx.beginPath(); ctx.moveTo(W*0.15*i/4, 0); ctx.lineTo(W*0.15*i/4, H); ctx.stroke();
        ctx.beginPath(); ctx.moveTo(W - W*0.15*i/4, 0); ctx.lineTo(W - W*0.15*i/4, H); ctx.stroke();
    }
    // CELEBRATE banner
    ctx.fillStyle='#2a6a22'; ctx.fillRect(W*0.2, 12, W*0.6, 28);
    ctx.fillStyle='#ffff00'; ctx.font='bold 16px Impact,monospace'; ctx.textAlign='center';
    ctx.fillText('CELEBRATE!', W/2, 31);
    // Floor checkerboard
    const tS=32;
    for(let r=0;r<4;r++) for(let c=0;c<Math.ceil(W/tS);c++){
        ctx.fillStyle = (r+c)%2===0 ? '#3a3020' : '#2a2015';
        ctx.fillRect(c*tS, H*0.6+r*tS, tS, tS);
    }
}

function drawDiningArea(ctx, W, H, t) {
    // Tables
    ctx.fillStyle='#181810'; ctx.fillRect(0,H*0.62,W,H*0.38);
    // Tables
    [[W*0.2, H*0.55],[W*0.5, H*0.55],[W*0.8, H*0.55]].forEach(([tx,ty]) => {
        ctx.fillStyle='#8B6914';
        ctx.fillRect(tx-40, ty, 80, 10);
        ctx.fillStyle='#5a4010';
        ctx.fillRect(tx-3, ty+10, 6, 30);
        // Plates/cups on table
        ctx.fillStyle='#eeeecc';
        ctx.beginPath(); ctx.ellipse(tx-15, ty+5, 10, 4, 0, 0, Math.PI*2); ctx.fill();
        ctx.fillStyle='#cc7700';
        ctx.beginPath(); ctx.ellipse(tx+15, ty+5, 6, 6, 0, 0, Math.PI*2); ctx.fill();
    });
    // Wall checkers
    for(let i=0;i<Math.ceil(W/48);i++){
        ctx.fillStyle=i%2===0?'#1a1a0a':'#111108';
        ctx.fillRect(i*48, 0, 48, H*0.62);
    }
}

function drawPirateCove(ctx, W, H, t) {
    ctx.fillStyle='#0d0400'; ctx.fillRect(0,0,W,H);
    // Sign above curtain
    ctx.fillStyle='#2a1000'; ctx.fillRect(W*0.12,H*0.02,W*0.76,H*0.11);
    ctx.strokeStyle='#883300'; ctx.lineWidth=3; ctx.strokeRect(W*0.12,H*0.02,W*0.76,H*0.11);
    ctx.fillStyle='#ff8800'; ctx.font=`bold ${Math.round(W*0.042)}px Impact,monospace`; ctx.textAlign='center';
    ctx.fillText("★ PIRATE'S COVE ★",W/2,H*0.085);
    // Backdrop stars/ambiance
    ctx.fillStyle='rgba(80,30,0,0.25)';
    const coveGlow=ctx.createRadialGradient(W/2,H*0.5,0,W/2,H*0.5,W*0.4);
    coveGlow.addColorStop(0,'rgba(100,40,0,0.15)'); coveGlow.addColorStop(1,'rgba(0,0,0,0)');
    ctx.fillStyle=coveGlow; ctx.fillRect(0,0,W,H);
    // Big curtain folds - rich red
    const curtGrad=ctx.createLinearGradient(0,0,W,0);
    curtGrad.addColorStop(0,'#180200'); curtGrad.addColorStop(0.15,'#2a0500'); curtGrad.addColorStop(0.5,'#220400'); curtGrad.addColorStop(0.85,'#2a0500'); curtGrad.addColorStop(1,'#180200');
    ctx.fillStyle=curtGrad; ctx.fillRect(0,H*0.13,W,H*0.73);
    // Curtain fold shading
    for(let i=0;i<10;i++) {
        const cx2=i*W/9;
        const shadGrad=ctx.createLinearGradient(cx2,0,cx2+W/18,0);
        shadGrad.addColorStop(0,'rgba(0,0,0,0.4)'); shadGrad.addColorStop(0.5,'rgba(80,10,0,0.1)'); shadGrad.addColorStop(1,'rgba(0,0,0,0.3)');
        ctx.fillStyle=shadGrad; ctx.fillRect(cx2,H*0.13,W/9,H*0.73);
    }
    // Fold lines with bezier curves
    ctx.strokeStyle='rgba(60,10,0,0.75)'; ctx.lineWidth=3;
    for(let i=0;i<10;i++) {
        const cx2=i*W/9;
        ctx.beginPath(); ctx.moveTo(cx2,H*0.13); ctx.bezierCurveTo(cx2+10,H*0.35,cx2-10,H*0.6,cx2+5,H*0.86); ctx.stroke();
    }
    // Rope at top of curtain
    ctx.strokeStyle='#774400'; ctx.lineWidth=6;
    ctx.beginPath(); ctx.moveTo(0,H*0.13); ctx.lineTo(W,H*0.13); ctx.stroke();
    ctx.strokeStyle='#886600'; ctx.lineWidth=3;
    ctx.beginPath(); ctx.moveTo(0,H*0.13); ctx.lineTo(W,H*0.13); ctx.stroke();
    for(let i=0;i<12;i++) { ctx.strokeStyle='#665500'; ctx.lineWidth=2; ctx.beginPath(); ctx.arc(i*W/11,H*0.13+9,9,0,Math.PI); ctx.stroke(); }
    // OUT OF ORDER sign
    ctx.fillStyle='rgba(0,0,0,0.65)'; ctx.fillRect(W*0.28,H*0.36,W*0.44,58);
    ctx.strokeStyle='#ff4400'; ctx.lineWidth=2; ctx.strokeRect(W*0.28,H*0.36,W*0.44,58);
    ctx.fillStyle='#ff8800'; ctx.font=`bold ${Math.round(W*0.03)}px monospace`; ctx.textAlign='center';
    ctx.fillText('★  SORRY!  ★',W/2,H*0.36+24);
    ctx.font=`${Math.round(W*0.025)}px monospace`; ctx.fillStyle='#ff4400';
    ctx.fillText('OUT OF ORDER',W/2,H*0.36+46);
    // Creepy gap glow
    const gapG=ctx.createRadialGradient(W/2,H*0.52,0,W/2,H*0.52,W*0.12);
    gapG.addColorStop(0,'rgba(255,80,0,0.1)'); gapG.addColorStop(1,'rgba(0,0,0,0)');
    ctx.fillStyle=gapG; ctx.fillRect(0,0,W,H);
    // Floor (dock planks)
    ctx.fillStyle='#0a0300'; ctx.fillRect(0,H*0.86,W,H*0.14);
    ctx.strokeStyle='#150800'; ctx.lineWidth=2;
    for(let i=0;i<9;i++) { ctx.beginPath(); ctx.moveTo(i*W/8,H*0.86); ctx.lineTo(i*W/8,H); ctx.stroke(); }
    // Foxy peek states
    const foxy=animatronics.foxy;
    if(foxy && foxy.location==='peek1') {
        // Single eye glow through curtain
        const eyeG=ctx.createRadialGradient(W*0.44,H*0.48,0,W*0.44,H*0.48,30);
        eyeG.addColorStop(0,'rgba(255,130,0,0.9)'); eyeG.addColorStop(0.4,'rgba(200,80,0,0.6)'); eyeG.addColorStop(1,'rgba(0,0,0,0)');
        ctx.fillStyle=eyeG; ctx.fillRect(0,0,W,H);
        ctx.fillStyle='rgba(200,50,0,0.95)'; ctx.beginPath(); ctx.arc(W*0.44,H*0.48,22,0,Math.PI*2); ctx.fill();
        ctx.fillStyle='#ff8800'; ctx.beginPath(); ctx.arc(W*0.44,H*0.48,11,0,Math.PI*2); ctx.fill();
        ctx.fillStyle='#000'; ctx.beginPath(); ctx.arc(W*0.44,H*0.48,5,0,Math.PI*2); ctx.fill();
        ctx.strokeStyle='rgba(180,180,180,0.55)'; ctx.lineWidth=3.5;
        ctx.beginPath(); ctx.arc(W*0.5,H*0.56,13,0,Math.PI*1.4); ctx.stroke();
    } else if(foxy && foxy.location==='peek2') {
        // Head peeking from left
        const peekX=W*0.32;
        ctx.fillStyle='#1a0300'; ctx.fillRect(0,H*0.13,peekX+5,H*0.73);
        ctx.fillStyle='#cc2200'; ctx.beginPath(); ctx.roundRect(peekX-8,H*0.28,72,68,6); ctx.fill();
        ctx.fillStyle='#fff'; ctx.beginPath(); ctx.arc(peekX+20,H*0.38,13,0,Math.PI*2); ctx.fill();
        ctx.fillStyle='#ff8800'; ctx.beginPath(); ctx.arc(peekX+20,H*0.38,7,0,Math.PI*2); ctx.fill();
        ctx.fillStyle='#111'; ctx.beginPath(); ctx.arc(peekX+20,H*0.38,3.5,0,Math.PI*2); ctx.fill();
        ctx.fillStyle='rgba(0,0,0,0.88)'; ctx.beginPath(); ctx.arc(peekX+52,H*0.38,14,0,Math.PI*2); ctx.fill();
        ctx.fillStyle='#fff'; [[peekX+18,H*0.56],[peekX+30,H*0.56],[peekX+42,H*0.56]].forEach(([tx,ty])=>{ ctx.fillRect(tx,ty,9,13); });
        ctx.strokeStyle='rgba(200,180,180,0.5)'; ctx.lineWidth=3; ctx.beginPath(); ctx.arc(peekX+62,H*0.62,13,0,Math.PI*1.4); ctx.stroke();
    } else if(foxy && foxy.location==='peek3') {
        // Foxy fully in the opening
        drawAnimatronicSprite(ctx,'foxy',W*0.5,H*0.65,0.85,true);
    }
}

function drawBackstage(ctx, W, H, t) {
    ctx.fillStyle='#0a0a0a'; ctx.fillRect(0,0,W,H);
    // Brick wall pattern
    for(let r=0;r<10;r++) for(let c=0;c<12;c++) {
        const xOff=(r%2)*22; ctx.fillStyle=r%3===0?'#141414':'#0f0f0f';
        ctx.fillRect(c*44-xOff+1,r*22+1,42,20);
        ctx.strokeStyle='#050505'; ctx.lineWidth=1; ctx.strokeRect(c*44-xOff,r*22,44,22);
    }
    // Shelves
    ctx.fillStyle='#1c1c1c'; ctx.fillRect(W*0.04,H*0.18,W*0.92,9); ctx.fillRect(W*0.04,H*0.48,W*0.92,9); ctx.fillRect(W*0.04,H*0.72,W*0.92,9);
    // Animatronic heads on top shelf
    // Freddy head
    ctx.fillStyle='#7a3810'; ctx.beginPath(); ctx.arc(W*0.18,H*0.31,22,0,Math.PI*2); ctx.fill();
    ctx.fillStyle='#fff'; ctx.beginPath(); ctx.arc(W*0.14,H*0.28,6,0,Math.PI*2); ctx.fill(); ctx.beginPath(); ctx.arc(W*0.22,H*0.28,6,0,Math.PI*2); ctx.fill();
    ctx.fillStyle='#111'; ctx.beginPath(); ctx.arc(W*0.14,H*0.28,3,0,Math.PI*2); ctx.fill(); ctx.beginPath(); ctx.arc(W*0.22,H*0.28,3,0,Math.PI*2); ctx.fill();
    // Bonnie head
    ctx.fillStyle='#4a0870'; ctx.beginPath(); ctx.arc(W*0.48,H*0.31,20,0,Math.PI*2); ctx.fill();
    ctx.fillStyle='rgba(255,100,255,0.8)'; ctx.beginPath(); ctx.arc(W*0.44,H*0.28,5,0,Math.PI*2); ctx.fill(); ctx.beginPath(); ctx.arc(W*0.52,H*0.28,5,0,Math.PI*2); ctx.fill();
    // Chica head
    ctx.fillStyle='#aa8800'; ctx.beginPath(); ctx.arc(W*0.78,H*0.31,20,0,Math.PI*2); ctx.fill();
    ctx.fillStyle='#fff'; ctx.beginPath(); ctx.arc(W*0.74,H*0.28,5,0,Math.PI*2); ctx.fill(); ctx.beginPath(); ctx.arc(W*0.82,H*0.28,5,0,Math.PI*2); ctx.fill();
    // Endoskeleton parts on lower shelf
    ctx.fillStyle='rgba(160,160,160,0.6)'; ctx.fillRect(W*0.1,H*0.53,W*0.2,H*0.16); // torso
    ctx.fillStyle='rgba(100,100,100,0.7)'; [[W*0.38,H*0.56],[W*0.5,H*0.54],[W*0.62,H*0.57]].forEach(([bx,by])=>{ ctx.beginPath(); ctx.arc(bx,by,12,0,Math.PI*2); ctx.fill(); });
    // Glowing endoskeleton eyes on floor
    const eyeFlicker = (Math.sin(Date.now()*0.003)>0) ? 1 : 0.4;
    ctx.fillStyle=`rgba(255,255,255,${eyeFlicker})`;
    ctx.beginPath(); ctx.arc(W*0.55,H*0.83,5,0,Math.PI*2); ctx.fill();
    ctx.beginPath(); ctx.arc(W*0.63,H*0.83,5,0,Math.PI*2); ctx.fill();
    // Floor
    ctx.fillStyle='#111'; ctx.fillRect(0,H*0.76,W,H*0.24);
    // EMPLOYEES ONLY sign
    ctx.fillStyle='#ffcc00'; ctx.font=`bold ${Math.round(W*0.025)}px monospace`; ctx.textAlign='center';
    ctx.fillText('⚠ EMPLOYEES ONLY ⚠',W/2,H*0.93);
}

function drawSupplyCloset(ctx, W, H, t) {
    ctx.fillStyle='#111'; ctx.fillRect(0,0,W,H);
    ctx.fillStyle='#1a1a1a'; ctx.fillRect(W*0.04,H*0.14,W*0.92,8); ctx.fillRect(W*0.04,H*0.5,W*0.92,8); ctx.fillRect(W*0.04,H*0.72,W*0.92,8);
    const boxColors=['#3a1800','#183a00','#001838','#3a3000','#2a001a'];
    for(let r=0;r<2;r++) for(let i=0;i<5;i++) {
        const bx=W*0.06+i*W*0.185, by=r===0?H*0.2:H*0.55, bw=W*0.17, bh=H*0.27;
        ctx.fillStyle=boxColors[(r*5+i)%5]; ctx.fillRect(bx,by,bw,bh);
        ctx.strokeStyle='rgba(0,0,0,0.5)'; ctx.lineWidth=1; ctx.strokeRect(bx,by,bw,bh);
        // Box label lines
        ctx.strokeStyle='rgba(255,255,255,0.12)'; ctx.lineWidth=1;
        ctx.beginPath(); ctx.moveTo(bx+4,by+8); ctx.lineTo(bx+bw-4,by+8); ctx.stroke();
    }
    ctx.strokeStyle='#4a2800'; ctx.lineWidth=5; ctx.beginPath(); ctx.moveTo(W*0.88,H*0.76); ctx.lineTo(W*0.85,H*0.2); ctx.stroke();
    ctx.fillStyle='#888'; for(let i=0;i<5;i++){ const fy=H*0.74-i*12; ctx.fillRect(W*0.82,fy,W*0.08,4); }
    ctx.fillStyle='#141414'; ctx.fillRect(0,H*0.76,W,H*0.24);
    // Tile floor  
    for(let i=0;i<8;i++){ ctx.fillStyle=i%2===0?'#161616':'#111111'; ctx.fillRect(i*W/7,H*0.76,W/7,H*0.24); }
}

function drawGenericHallway(ctx, W, H, theme, t) {
    // Brick wall pattern
    const bH=20, bW=40;
    for(let row=0;row<Math.ceil(H*0.65/bH);row++){
        for(let col=0;col<Math.ceil(W/bW)+1;col++){
            const xOff=(row%2)*(bW/2);
            const x=col*bW - xOff, y=row*bH;
            ctx.fillStyle=row%3===0?darken(theme.bg,0.85):theme.bg;
            ctx.fillRect(x+1,y+1,bW-2,bH-2);
            ctx.fillStyle=darken(theme.bg,0.6);
            ctx.fillRect(x,y,bW,1); ctx.fillRect(x,y,1,bH);
        }
    }
    // Floor
    ctx.fillStyle=theme.floor; ctx.fillRect(0, H*0.65, W, H*0.35);
    // Floor tiles
    for(let i=0;i<Math.ceil(W/48);i++){
        ctx.fillStyle=i%2===0?theme.floor:darken(theme.floor,0.8);
        ctx.fillRect(i*48, H*0.65, 48, H*0.35);
    }
    // Perspective lines (hallway depth)
    ctx.strokeStyle=theme.accent+'55'; ctx.lineWidth=1;
    [0.1,0.3,0.7,0.9].forEach(frac=>{
        ctx.beginPath(); ctx.moveTo(W/2, H*0.35); ctx.lineTo(W*frac, H); ctx.stroke();
    });
    // Dim light source on ceiling
    const lightGrad = ctx.createRadialGradient(W/2, 5, 0, W/2, 5, W*0.4);
    lightGrad.addColorStop(0, theme.accent+'66'); lightGrad.addColorStop(1, 'rgba(0,0,0,0)');
    ctx.fillStyle=lightGrad; ctx.fillRect(0,0,W,H*0.4);
}

function drawAnimatronicSprite(ctx, name, cx, cy, scale=1.0, isPeeking=false) {
    const cfg = ANIM_DRAW[name];
    if (!cfg) return;

    const t = Date.now() * 0.002;
    const breathe = Math.sin(t * 1.5) * 2 * scale;
    const s = scale * (isPeeking ? 0.75 : 1.0);
    const bodyW = 68 * s, bodyH = 88 * s;
    const headW = 62 * s, headH = 62 * s;
    const legH = 55 * s;
    const eyeR = 11 * s;

    // Cast shadow on floor
    ctx.save();
    ctx.globalAlpha = 0.35;
    ctx.fillStyle = '#000';
    ctx.beginPath();
    ctx.ellipse(cx, cy + legH * 0.55 + 6, bodyW * 0.55, 10 * s, 0, 0, Math.PI * 2);
    ctx.fill();
    ctx.restore();

    if (isPeeking) {
        // Pirate Cove curtains
        const curtainGrad1 = ctx.createLinearGradient(cx-120*s, 0, cx-40*s, 0);
        curtainGrad1.addColorStop(0, '#200800'); curtainGrad1.addColorStop(1, '#3a1500');
        ctx.fillStyle = curtainGrad1;
        ctx.fillRect(cx - 140*s, cy - headH * 2, 100*s, headH * 3);

        const curtainGrad2 = ctx.createLinearGradient(cx+40*s, 0, cx+120*s, 0);
        curtainGrad2.addColorStop(0, '#3a1500'); curtainGrad2.addColorStop(1, '#200800');
        ctx.fillStyle = curtainGrad2;
        ctx.fillRect(cx + 40*s, cy - headH * 2, 100*s, headH * 3);
    }

    if (!isPeeking) {
        // === LEGS ===
        ctx.fillStyle = '#181818';
        // Left leg with slight perspective
        ctx.beginPath();
        ctx.moveTo(cx - bodyW*0.35, cy + breathe);
        ctx.lineTo(cx - bodyW*0.08, cy + breathe);
        ctx.lineTo(cx - bodyW*0.12, cy + legH + breathe);
        ctx.lineTo(cx - bodyW*0.38, cy + legH + breathe);
        ctx.closePath(); ctx.fill();
        // Right leg
        ctx.beginPath();
        ctx.moveTo(cx + bodyW*0.08, cy + breathe);
        ctx.lineTo(cx + bodyW*0.35, cy + breathe);
        ctx.lineTo(cx + bodyW*0.38, cy + legH + breathe);
        ctx.lineTo(cx + bodyW*0.12, cy + legH + breathe);
        ctx.closePath(); ctx.fill();
        // Feet
        ctx.fillStyle = '#111';
        ctx.fillRect(cx - bodyW*0.38, cy + legH + breathe, bodyW*0.28, 10*s);
        ctx.fillRect(cx + bodyW*0.10, cy + legH + breathe, bodyW*0.28, 10*s);
    }

    // === BODY ===
    const bodyGrad = ctx.createLinearGradient(cx - bodyW/2, 0, cx + bodyW/2, 0);
    bodyGrad.addColorStop(0, darken(cfg.bodyColor, 0.6));
    bodyGrad.addColorStop(0.3, cfg.bodyColor);
    bodyGrad.addColorStop(0.7, lighten(cfg.bodyColor, 1.15));
    bodyGrad.addColorStop(1, darken(cfg.bodyColor, 0.55));
    ctx.fillStyle = bodyGrad;
    const bodyTop = cy - bodyH + breathe;
    ctx.beginPath();
    ctx.roundRect(cx - bodyW/2, bodyTop, bodyW, bodyH, 4*s);
    ctx.fill();

    // Body shading - bottom dark
    const bodyShadow = ctx.createLinearGradient(0, bodyTop, 0, bodyTop + bodyH);
    bodyShadow.addColorStop(0, 'rgba(255,255,255,0.1)');
    bodyShadow.addColorStop(0.5, 'rgba(0,0,0,0)');
    bodyShadow.addColorStop(1, 'rgba(0,0,0,0.3)');
    ctx.fillStyle = bodyShadow;
    ctx.beginPath();
    ctx.roundRect(cx - bodyW/2, bodyTop, bodyW, bodyH, 4*s);
    ctx.fill();

    // Belly / inner color
    ctx.fillStyle = 'rgba(230,210,165,0.6)';
    ctx.beginPath();
    ctx.ellipse(cx, cy - bodyH * 0.4 + breathe, bodyW * 0.28, bodyH * 0.33, 0, 0, Math.PI*2);
    ctx.fill();

    // Chica bib "LET'S EAT"
    if (name === 'chica') {
        ctx.fillStyle = '#fffff0';
        ctx.beginPath(); ctx.roundRect(cx - bodyW*0.23, cy - bodyH*0.6 + breathe, bodyW*0.46, bodyH*0.35, 3*s); ctx.fill();
        ctx.fillStyle = '#cc0000'; ctx.font = `bold ${Math.round(9*s)}px monospace`; ctx.textAlign='center';
        ctx.fillText("LET'S EAT!", cx, cy - bodyH*0.45 + breathe);
    }

    // Bow tie (Freddy)
    if (name === 'freddy') {
        ctx.fillStyle = '#cc0000';
        ctx.beginPath();
        ctx.moveTo(cx - 12*s, cy - bodyH*0.82 + breathe);
        ctx.lineTo(cx, cy - bodyH*0.75 + breathe);
        ctx.lineTo(cx + 12*s, cy - bodyH*0.82 + breathe);
        ctx.lineTo(cx, cy - bodyH*0.89 + breathe);
        ctx.closePath(); ctx.fill();
    }

    // === ARMS ===
    const armMat = ctx.createLinearGradient(0,0,bodyW*0.3,0);
    armMat.addColorStop(0, darken(cfg.bodyColor,0.65)); armMat.addColorStop(1, cfg.bodyColor);
    ctx.fillStyle = cfg.bodyColor;
    if (!isPeeking) {
        // Left arm
        ctx.beginPath();
        ctx.moveTo(cx - bodyW/2, cy - bodyH*0.82 + breathe);
        ctx.lineTo(cx - bodyW/2 - 22*s, cy - bodyH*0.72 + breathe);
        ctx.lineTo(cx - bodyW/2 - 20*s, cy - bodyH*0.25 + breathe);
        ctx.lineTo(cx - bodyW/2, cy - bodyH*0.3 + breathe);
        ctx.closePath(); ctx.fill();
        // Right arm
        ctx.beginPath();
        ctx.moveTo(cx + bodyW/2, cy - bodyH*0.82 + breathe);
        ctx.lineTo(cx + bodyW/2 + 22*s, cy - bodyH*0.72 + breathe);
        ctx.lineTo(cx + bodyW/2 + 20*s, cy - bodyH*0.25 + breathe);
        ctx.lineTo(cx + bodyW/2, cy - bodyH*0.3 + breathe);
        ctx.closePath(); ctx.fill();
        // Foxy hook
        if (name === 'foxy') {
            ctx.strokeStyle = '#aaaaaa'; ctx.lineWidth = 3*s;
            ctx.beginPath();
            ctx.arc(cx + bodyW/2 + 18*s, cy - bodyH*0.22 + breathe, 10*s, 0, Math.PI*1.4);
            ctx.stroke();
        }
    }

    // === HEAD ===
    const headTop = cy - bodyH - headH + breathe;
    const headGrad = ctx.createLinearGradient(cx - headW/2, 0, cx + headW/2, 0);
    headGrad.addColorStop(0, darken(cfg.bodyColor, 0.65));
    headGrad.addColorStop(0.45, lighten(cfg.bodyColor, 1.1));
    headGrad.addColorStop(1, darken(cfg.bodyColor, 0.65));
    ctx.fillStyle = headGrad;
    ctx.beginPath();
    ctx.roundRect(cx - headW/2, headTop, headW, headH, 5*s);
    ctx.fill();

    // Head shading
    const headShadow = ctx.createLinearGradient(0, headTop, 0, headTop + headH);
    headShadow.addColorStop(0,'rgba(255,255,255,0.12)');
    headShadow.addColorStop(1,'rgba(0,0,0,0.25)');
    ctx.fillStyle = headShadow;
    ctx.beginPath(); ctx.roundRect(cx - headW/2, headTop, headW, headH, 5*s); ctx.fill();

    // Ear shapes
    ctx.fillStyle = darken(cfg.bodyColor, 0.8);
    if (name === 'freddy' || name === 'bonnie') {
        // Round ears
        [[cx - headW*0.42, headTop - 8*s],[cx + headW*0.42, headTop - 8*s]].forEach(([ex,ey]) => {
            ctx.beginPath(); ctx.arc(ex, ey, 10*s, 0, Math.PI*2); ctx.fill();
            ctx.fillStyle = darken(cfg.bodyColor, 0.5);
            ctx.beginPath(); ctx.arc(ex, ey, 6*s, 0, Math.PI*2); ctx.fill();
            ctx.fillStyle = darken(cfg.bodyColor, 0.8);
        });
    } else if (name === 'chica') {
        // Chica beak - yellow
        ctx.fillStyle = '#ffcc00';
        ctx.beginPath();
        ctx.moveTo(cx - headW*0.15, headTop + headH*0.48);
        ctx.lineTo(cx + headW*0.15, headTop + headH*0.48);
        ctx.lineTo(cx, headTop + headH*0.72);
        ctx.closePath(); ctx.fill();
        ctx.fillStyle = '#e6aa00';
        ctx.beginPath();
        ctx.moveTo(cx - headW*0.15, headTop + headH*0.6);
        ctx.lineTo(cx + headW*0.15, headTop + headH*0.6);
        ctx.lineTo(cx, headTop + headH*0.72);
        ctx.closePath(); ctx.fill();
    } else if (name === 'foxy') {
        // Foxy pointed ears
        [[-1,1],[1,1]].forEach(([dx,]) => {
            ctx.fillStyle = cfg.bodyColor;
            ctx.beginPath();
            ctx.moveTo(cx + dx*headW*0.35, headTop + 5*s);
            ctx.lineTo(cx + dx*headW*0.5, headTop - 18*s);
            ctx.lineTo(cx + dx*headW*0.18, headTop + 2*s);
            ctx.closePath(); ctx.fill();
            ctx.fillStyle = '#ff9999';
            ctx.beginPath();
            ctx.moveTo(cx + dx*headW*0.35, headTop + 5*s);
            ctx.lineTo(cx + dx*headW*0.46, headTop - 13*s);
            ctx.lineTo(cx + dx*headW*0.22, headTop + 3*s);
            ctx.closePath(); ctx.fill();
        });
    }

    // Snout
    if (name !== 'chica') {
        const snoutCol = darken(cfg.bodyColor, 0.78);
        ctx.fillStyle = snoutCol;
        ctx.beginPath();
        ctx.ellipse(cx, headTop + headH*0.62, headW*0.25, headH*0.2, 0, 0, Math.PI*2);
        ctx.fill();
        // Nose
        ctx.fillStyle = darken(cfg.bodyColor, 0.4);
        ctx.beginPath(); ctx.ellipse(cx, headTop + headH*0.52, 5*s, 4*s, 0, 0, Math.PI*2); ctx.fill();
        // Mouth
        ctx.strokeStyle = darken(cfg.bodyColor, 0.4); ctx.lineWidth = 2*s;
        ctx.beginPath();
        ctx.moveTo(cx - headW*0.15, headTop + headH*0.7);
        ctx.quadraticCurveTo(cx, headTop + headH*0.82, cx + headW*0.15, headTop + headH*0.7);
        ctx.stroke();
        // Teeth
        ctx.fillStyle = '#ffffee';
        [-headW*0.12, -headW*0.02, headW*0.08].forEach(tx => {
            ctx.fillRect(cx+tx, headTop+headH*0.71, headW*0.08*0.7, headH*0.08);
        });
    }

    // === EYES ===
    [-headW*0.24, headW*0.24].forEach((ex, i) => {
        const eyeX = cx + ex;
        const eyeY = headTop + headH * 0.38;

        // Foxy eye patch on left eye
        if (name === 'foxy' && i === 0) {
            ctx.fillStyle = 'rgba(0,0,0,0.85)';
            ctx.beginPath(); ctx.arc(eyeX, eyeY, eyeR * 1.3, 0, Math.PI*2); ctx.fill();
            ctx.strokeStyle = '#553300'; ctx.lineWidth = 2;
            ctx.beginPath(); ctx.arc(eyeX, eyeY, eyeR * 1.5, 0, Math.PI*2); ctx.stroke();
            return;
        }

        // Eye white glow
        ctx.fillStyle = cfg.accent + '33';
        ctx.beginPath(); ctx.arc(eyeX, eyeY, eyeR*1.5, 0, Math.PI*2); ctx.fill();
        // Sclera
        ctx.fillStyle = '#fff';
        ctx.beginPath(); ctx.arc(eyeX, eyeY, eyeR, 0, Math.PI*2); ctx.fill();
        // Iris
        ctx.fillStyle = cfg.eyeColor;
        ctx.beginPath(); ctx.arc(eyeX, eyeY, eyeR*0.65, 0, Math.PI*2); ctx.fill();
        // Pupil
        ctx.fillStyle = '#000';
        ctx.beginPath(); ctx.arc(eyeX, eyeY, eyeR*0.35, 0, Math.PI*2); ctx.fill();
        // Eye shine
        ctx.fillStyle = 'rgba(255,255,255,0.7)';
        ctx.beginPath(); ctx.arc(eyeX - eyeR*0.3, eyeY - eyeR*0.3, eyeR*0.2, 0, Math.PI*2); ctx.fill();
    });

    // === HAT ===
    if (name === 'freddy' || name === 'bonnie') {
        ctx.fillStyle = cfg.hatColor;
        // Brim
        ctx.fillRect(cx - headW*0.56, headTop - 10*s, headW*1.12, 9*s);
        // Top
        const hatGrad = ctx.createLinearGradient(cx-headW*0.28, 0, cx+headW*0.28, 0);
        hatGrad.addColorStop(0, darken(cfg.hatColor, 0.7));
        hatGrad.addColorStop(0.5, lighten(cfg.hatColor, 1.1));
        hatGrad.addColorStop(1, darken(cfg.hatColor, 0.7));
        ctx.fillStyle = hatGrad;
        ctx.fillRect(cx - headW*0.28, headTop - 46*s, headW*0.56, 37*s);
        // Hat band
        ctx.fillStyle = '#222'; ctx.fillRect(cx - headW*0.28, headTop - 12*s, headW*0.56, 5*s);
        if (name === 'freddy') {
            ctx.fillStyle = '#ff4400'; ctx.fillRect(cx - headW*0.28, headTop - 13*s, headW*0.56, 2*s);
        }
    }

    // Name tag at top
    ctx.fillStyle = cfg.accent + 'ee';
    ctx.font = `bold ${Math.round(12*s)}px monospace`;
    ctx.textAlign = 'center';
    ctx.shadowColor = cfg.accent; ctx.shadowBlur = 8*s;
    ctx.fillText(cfg.name, cx, headTop - 20*s);
    ctx.shadowBlur = 0;
}

function lighten(hexColor, factor) {
    const r = Math.min(255, parseInt(hexColor.slice(1,3),16) * factor);
    const g = Math.min(255, parseInt(hexColor.slice(3,5),16) * factor);
    const b = Math.min(255, parseInt(hexColor.slice(5,7),16) * factor);
    return `rgb(${Math.round(r)},${Math.round(g)},${Math.round(b)})`;
}

function darken(hexColor, factor) {
    const r = parseInt(hexColor.slice(1,3),16);
    const g = parseInt(hexColor.slice(3,5),16);
    const b = parseInt(hexColor.slice(5,7),16);
    return `rgb(${Math.round(r*factor)},${Math.round(g*factor)},${Math.round(b*factor)})`;
}

// ---- GAME STATE ----
function startGame() {
    currentNight = selectedNight;
    stopMenuAnimation();
    stopDeathAnimation();
    document.getElementById('start-screen').style.display = 'none';
    document.getElementById('death-screen').classList.remove('visible');
    document.getElementById('win-screen').classList.remove('visible');
    document.getElementById('hud').style.display = 'block';

    power = 100; nightTimer = 0; nightHour = 0; gameRunning = true; gameOver = false;
    doors = { left: false, right: false }; lights = { left: false, right: false };
    lookAngle = 0; lookTarget = 0; activeCamIndex = 0;

    ['left','right'].forEach(side => {
        document.getElementById(`${side}-door-btn`).classList.remove('active');
        document.getElementById(`${side}-light-btn`).classList.remove('active');
    });
    leftDoorObj.visible = false; rightDoorObj.visible = false;
    leftLightObj.intensity = 0; rightLightObj.intensity = 0;

    initAnimatronics();
    updateCameraStatuses();
    updatePowerDisplay();
    document.getElementById('night-display').textContent = `Night ${currentNight}`;
    camera.position.set(0, 1.72, 0.5);
    clock.start(); getAudioCtx();
}

function retryGame() { stopDeathAnimation(); document.getElementById('death-screen').classList.remove('visible'); startGame(); }
function goToMenu() {
    document.getElementById('death-screen').classList.remove('visible');
    document.getElementById('win-screen').classList.remove('visible');
    document.getElementById('start-screen').style.display = 'flex';
    stopDeathAnimation();
    startMenuAnimation();
    gameRunning = false; gameOver = false;
    for (const m of Object.values(animModels)) m.visible = false;
}
function nextNight() {
    document.getElementById('win-screen').classList.remove('visible');
    if (selectedNight < 5) { selectedNight++; selectNight(selectedNight); }
    startGame();
}
function selectNight(n) {
    selectedNight = n;
    document.querySelectorAll('.night-btn').forEach(b => b.classList.remove('selected'));
    document.getElementById(`night-${n}-btn`).classList.add('selected');
}

// ---- DOORS & LIGHTS ----
function toggleDoor(side) {
    if (!gameRunning || gameOver) return;
    doors[side] = !doors[side];
    document.getElementById(`${side}-door-btn`).classList.toggle('active', doors[side]);
    if (side === 'left') leftDoorObj.visible = doors[side];
    else rightDoorObj.visible = doors[side];
    playDoorSound();
}

function toggleLight(side) {
    if (!gameRunning || gameOver) return;
    lights[side] = !lights[side];
    document.getElementById(`${side}-light-btn`).classList.toggle('active', lights[side]);
    if (side === 'left') leftLightObj.intensity = lights[side] ? 3 : 0;
    else rightLightObj.intensity = lights[side] ? 3 : 0;
    playLightSound();
    checkLightWarning(side);
}

function checkLightWarning(side) {
    if (!lights[side]) return;
    const doorSide = side === 'left' ? LOCATIONS.LEFT_DOOR : LOCATIONS.RIGHT_DOOR;
    for (const [name, a] of Object.entries(animatronics)) {
        if (a.location === doorSide) {
            showAlert(`⚠ ${a.name.toUpperCase()} IS AT THE ${side.toUpperCase()} DOOR!`);
            playAlertSound();
        }
    }
}

// ---- CAMERAS ----
function openCameras() {
    if (!gameRunning || gameOver) return;
    cameraOpen = true;
    document.getElementById('camera-overlay').classList.add('visible');
    playCameraSound(); updateCameraStatuses();
    animatronics.foxy.cameraWatchCount = (animatronics.foxy.cameraWatchCount || 0) + 1;
    selectCamera(activeCamIndex);
}
function closeCameras() {
    cameraOpen = false;
    document.getElementById('camera-overlay').classList.remove('visible');
    playCameraSound();
}
function selectCamera(index) {
    activeCamIndex = index;
    document.querySelectorAll('.cam-button').forEach(b => b.classList.remove('active'));
    document.getElementById(`cam-${index}`).classList.add('active');
    // Highlight map room
    document.querySelectorAll('.map-room').forEach(b => b.classList.remove('map-active'));
    const mapEl = document.getElementById(`map-${index}`);
    if(mapEl) mapEl.classList.add('map-active');
    document.getElementById('cam-preview-label').textContent = CAM_NAMES[index];
    drawCameraMonitor();
    updateCamPreview();
}

function updateCamPreview() {
    const preview = document.getElementById('cam-preview-canvas');
    if (!preview) return;
    if(preview.width !== camCanvas.width) { preview.width = camCanvas.width; preview.height = camCanvas.height; }
    const pCtx = preview.getContext('2d');
    pCtx.drawImage(camCanvas, 0, 0);
}

function updateCameraStatuses() {
    CAM_LOCATIONS.forEach((loc, i) => {
        const el = document.getElementById(`cam-status-${i}`);
        if (!el) return;
        let found = false;
        for (const a of Object.values(animatronics)) {
            if (a.location === loc) {
                el.textContent = a.name.toUpperCase();
                el.className = 'cam-status alert';
                found = true; break;
            }
        }
        if (!found) { el.textContent = 'CLEAR'; el.className = 'cam-status clear'; }
    });
}

// ---- POWER ----
function updatePowerDisplay() {
    const p = Math.max(0, Math.round(power));
    document.getElementById('power-display').textContent = `Power: ${p}%`;
    document.getElementById('power-bar').style.width = p + '%';
    document.getElementById('power-bar').style.background =
        p > 60 ? '#00ff44' : p > 30 ? '#ffcc00' : '#ff4400';
}
function getPowerDrain() {
    let d = 0.025;
    if (doors.left) d += 0.035;
    if (doors.right) d += 0.035;
    if (lights.left) d += 0.025;
    if (lights.right) d += 0.025;
    if (cameraOpen) d += 0.015;
    return d;
}

// ---- ANIMATRONIC MOVEMENT ----
let foxyNight1Timer = 0;
function updateAnimatronics(dt) {
    for (const [name, a] of Object.entries(animatronics)) {
        // Night 1: foxy has 1/1000 chance per second to activate
        if (name === 'foxy' && currentNight === 1 && !a.night1Activated) {
            foxyNight1Timer += dt;
            if (foxyNight1Timer >= 1.0) {
                foxyNight1Timer = 0;
                if (Math.random() < 1/1000) {
                    a.level = 2;
                    a.night1Activated = true;
                    showAlert('★ FOXY HAS ACTIVATED!');
                }
            }
        }
        if (a.level === 0) continue;
        a.moveTimer += dt;
        const interval = a.moveInterval * (1 / (a.level * 0.5 + 0.5));
        if (a.moveTimer >= interval) {
            a.moveTimer = 0;
            if (Math.random() < a.level / 20) moveAnimatronic(name, a);
        }
        updateAnimatronicModel(name, a);
    }
}

function moveAnimatronic(name, a) {
    if (name === 'foxy') { moveFoxy(a); return; }
    const nextIdx = Math.min(a.pathIndex + 1, a.path.length - 1);
    const nextLoc = a.path[nextIdx];
    if (nextLoc === LOCATIONS.LEFT_DOOR && doors.left) return;
    if (nextLoc === LOCATIONS.RIGHT_DOOR && doors.right) return;
    if (nextLoc === LOCATIONS.OFFICE && isBlockedByDoor(name)) return;
    a.pathIndex = nextIdx; a.location = nextLoc;
    if (nextLoc === LOCATIONS.OFFICE) triggerJumpscare(name, a);
    updateCameraStatuses();
}

function isBlockedByDoor(name) {
    if (name === 'bonnie' && doors.left) return true;
    if (name === 'chica' && doors.right) return true;
    if (name === 'freddy' && (doors.left || doors.right)) return true;
    return false;
}

function moveFoxy(a) {
    a.foxyStage = Math.min(a.foxyStage + 1, FOXY_STAGES.length - 1);
    a.location = FOXY_STAGES[a.foxyStage];
    if (cameraOpen && a.foxyStage > 0 && a.foxyStage < 4) {
        a.foxyStage = Math.max(0, a.foxyStage - 1);
        a.location = FOXY_STAGES[a.foxyStage];
    }
    // Foxy runs down the left hallway
    if (a.location === 'running') {
        a.runProgress = 0;
        a.runTimer = 0;
        showAlert('⚠ FOXY IS RUNNING DOWN THE LEFT HALL!');
        playAlertSound();
    }
    if (a.location === LOCATIONS.LEFT_DOOR) {
        if (!doors.left) {
            setTimeout(() => {
                if (animatronics.foxy && animatronics.foxy.location === LOCATIONS.LEFT_DOOR && !doors.left) {
                    triggerJumpscare('foxy', a);
                }
            }, 1500);
        } else {
            power -= 5;
            setTimeout(() => { a.foxyStage = 0; a.location = FOXY_STAGES[0]; updateCameraStatuses(); }, 2000);
        }
    }
    updateCameraStatuses();
}

function updateAnimatronicModel(name, a) {
    const model = animModels[name];
    if (!model) return;
    const atDoor = a.location === LOCATIONS.LEFT_DOOR || a.location === LOCATIONS.RIGHT_DOOR ||
                   a.location === LOCATIONS.WEST_CORNER || a.location === LOCATIONS.EAST_CORNER;
    if (atDoor) {
        model.visible = true;
        model.userData.glow.intensity = 2.5;
        if (a.location === LOCATIONS.LEFT_DOOR || a.location === LOCATIONS.WEST_CORNER) {
            model.position.set(-5.0, 0, -1.2); model.rotation.y = Math.PI/3;
        } else {
            model.position.set(5.0, 0, -1.2); model.rotation.y = -Math.PI/3;
        }
        // Animate the model (bob)
        model.position.y = Math.sin(Date.now() * 0.003) * 0.05;
    } else {
        model.visible = false;
        model.userData.glow.intensity = 0;
    }
}

// ---- JUMPSCARE ----
function triggerJumpscare(name, a) {
    if (gameOver) return;
    gameOver = true; gameRunning = false;
    const jsEl = document.getElementById('jumpscare');
    jsEl.classList.add('visible');
    startJumpscareCanvas(name);
    playJumpscareSound();
    let shake = 0;
    const si = setInterval(() => {
        shake++;
        document.getElementById('canvas').style.transform = `translate(${(Math.random()-0.5)*18}px,${(Math.random()-0.5)*18}px) rotate(${(Math.random()-0.5)*3}deg)`;
        if (shake > 25) { clearInterval(si); document.getElementById('canvas').style.transform = 'none'; }
    }, 35);
    setTimeout(() => {
        stopJumpscareCanvas();
        jsEl.classList.remove('visible');
        document.getElementById('killer-name').textContent = a.name;
        document.getElementById('death-screen').classList.add('visible');
        startDeathAnimation(a.name);
    }, 1800);
}

// ---- POWER OUT ----
function triggerPowerOut() {
    if (gameOver) return;
    gameOver = true; gameRunning = false;
    showAlert('⚡ POWER OUTAGE — FREDDY IS COMING!');
    setTimeout(() => {
        const jsEl = document.getElementById('jumpscare');
        jsEl.classList.add('visible');
        startJumpscareCanvas('freddy');
        playJumpscareSound();
        setTimeout(() => {
            stopJumpscareCanvas();
            jsEl.classList.remove('visible');
            document.getElementById('killer-name').textContent = 'Freddy Fazbear (Power Outage)';
            document.getElementById('death-screen').classList.add('visible');
            startDeathAnimation('Freddy Fazbear (Power Outage)');
        }, 1800);
    }, 4000);
}

// ---- TIME ----
function updateTimeDisplay() {
    const hours = [12,1,2,3,4,5,6];
    document.getElementById('time-display').textContent = hours[Math.min(Math.floor(nightHour),6)] + ' AM';
}

// ---- ALERT ----
let alertTimeout = null;
function showAlert(msg) {
    const el = document.getElementById('alert-box');
    el.textContent = msg; el.classList.add('visible');
    if (alertTimeout) clearTimeout(alertTimeout);
    alertTimeout = setTimeout(() => el.classList.remove('visible'), 3000);
}

// ---- WIN ----
function triggerWin() {
    gameRunning = false; gameOver = true; play6amSound();
    const banner = document.getElementById('night-complete');
    banner.textContent = `🌅 6 AM — NIGHT ${currentNight} COMPLETE!`;
    banner.classList.add('visible');
    setTimeout(() => {
        banner.classList.remove('visible');
        document.getElementById('win-screen').classList.add('visible');
        document.getElementById('win-sub').textContent = currentNight < 5
            ? `Night ${currentNight} done! ${5 - currentNight} night${5-currentNight===1?'':'s'} remaining.`
            : '🏆 You survived all 5 nights! Legend.';
        const nextBtn = document.querySelector('#win-screen button:first-of-type');
        if (currentNight >= 5 && nextBtn) nextBtn.style.display = 'none';
    }, 4000);
}

// ---- MENU BACKGROUND ANIMATION ----
let menuAnimFrame = null;
function startMenuAnimation() {
    const canvas = document.getElementById('menu-bg-canvas');
    if (!canvas) return;
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
    const ctx = canvas.getContext('2d');
    let t = 0;
    function drawMenu() {
        menuAnimFrame = requestAnimationFrame(drawMenu);
        const W = canvas.width, H = canvas.height;
        t += 0.005;
        // Dark background
        ctx.fillStyle = '#000'; ctx.fillRect(0,0,W,H);
        // Draw the restaurant back wall
        const bgGrad = ctx.createLinearGradient(0,0,0,H);
        bgGrad.addColorStop(0,'#100a18'); bgGrad.addColorStop(0.6,'#180e20'); bgGrad.addColorStop(1,'#060408');
        ctx.fillStyle=bgGrad; ctx.fillRect(0,0,W,H);
        // Brick texture hint
        const bW=Math.floor(W/16), bH=Math.floor(H/20);
        for(let row=0;row<20;row++) for(let col=0;col<17;col++){
            const xOff=(row%2)*(bW/2);
            const bx=col*bW-xOff, by=row*bH;
            ctx.fillStyle=`rgba(20,15,28,${0.4+Math.random()*0.1})`;
            ctx.fillRect(bx+1,by+1,bW-2,bH-2);
            ctx.fillStyle='rgba(0,0,0,0.6)';
            ctx.fillRect(bx,by,bW,1); ctx.fillRect(bx,by,1,bH);
        }
        // Spotlight effect from above
        const spotlight = ctx.createRadialGradient(W/2, -H*0.2, 0, W/2, H*0.3, W*0.6);
        spotlight.addColorStop(0,'rgba(80,40,0,0.3)'); spotlight.addColorStop(1,'rgba(0,0,0,0)');
        ctx.fillStyle=spotlight; ctx.fillRect(0,0,W,H);
        // Balloons floating
        const ballColors = ['#ff4444','#4499ff','#ffff44','#44ff88','#ff44ff'];
        for(let i=0;i<12;i++){
            const bx = (i/11)*W*0.9 + W*0.05;
            const by = (H*0.15) + Math.sin(t+i*0.8)*25;
            ctx.fillStyle=ballColors[i%5];
            ctx.globalAlpha=0.5;
            ctx.beginPath(); ctx.arc(bx, by, 18+i%3*5, 0, Math.PI*2); ctx.fill();
            ctx.globalAlpha=1;
            ctx.strokeStyle='rgba(150,150,150,0.3)'; ctx.lineWidth=1;
            ctx.beginPath(); ctx.moveTo(bx,by+18); ctx.lineTo(bx+8,by+50); ctx.stroke();
        }
        // Animatronics silhouettes on the stage (subtle)
        ctx.globalAlpha=0.12;
        [W*0.25, W*0.5, W*0.75].forEach((sx,i) => {
            ctx.fillStyle=['#5a0d8a','#8B4513','#ccaa00'][i];
            const sh = H*0.4;
            const sy = H*0.85;
            // Body silhouette
            ctx.fillRect(sx-25, sy-sh, 50, sh);
            // Head
            ctx.beginPath(); ctx.arc(sx, sy-sh-25, 30, 0, Math.PI*2); ctx.fill();
        });
        ctx.globalAlpha=1;
        // Vignette
        const vign = ctx.createRadialGradient(W/2, H/2, H*0.1, W/2, H/2, H*0.9);
        vign.addColorStop(0,'rgba(0,0,0,0)'); vign.addColorStop(1,'rgba(0,0,0,0.85)');
        ctx.fillStyle=vign; ctx.fillRect(0,0,W,H);
    }
    drawMenu();
}

function stopMenuAnimation() {
    if (menuAnimFrame) { cancelAnimationFrame(menuAnimFrame); menuAnimFrame=null; }
}

// ---- DEATH SCREEN ANIMATION ----
let deathAnimFrame = null;
function startDeathAnimation(killerName) {
    const canvas = document.getElementById('death-bg-canvas');
    if (!canvas) return;
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
    const ctx = canvas.getContext('2d');
    let t = 0;
    const anim_colors = {
        'Freddy Fazbear': ['#3a1500','#8B4513'],
        'Freddy Fazbear (Power Outage)': ['#3a1500','#8B4513'],
        'Bonnie': ['#2a0045','#5a0d8a'],
        'Chica': ['#3a2a00','#ccaa00'],
        'Foxy': ['#3a0800','#cc3300'],
    };
    const colors = anim_colors[killerName] || ['#200000','#440000'];
    function drawDeath() {
        deathAnimFrame = requestAnimationFrame(drawDeath);
        t += 0.02;
        const W=canvas.width, H=canvas.height;
        ctx.fillStyle='#000'; ctx.fillRect(0,0,W,H);
        // Pulsing dark background
        const pulse = 0.5 + Math.sin(t*1.5)*0.3;
        const bgGrad = ctx.createRadialGradient(W/2,H/2,0,W/2,H/2,W*0.8);
        bgGrad.addColorStop(0, colors[1]+'aa');
        bgGrad.addColorStop(0.4+pulse*0.1, colors[0]+'88');
        bgGrad.addColorStop(1, '#000');
        ctx.fillStyle=bgGrad; ctx.fillRect(0,0,W,H);
        // Static/noise
        ctx.globalAlpha=0.04;
        for(let i=0;i<200;i++){
            ctx.fillStyle=`rgb(${Math.random()*255|0},${Math.random()*255|0},${Math.random()*255|0})`;
            ctx.fillRect(Math.random()*W, Math.random()*H, 2, 2);
        }
        ctx.globalAlpha=1;
        // Blood drip effect at top
        ctx.fillStyle='rgba(150,0,0,0.6)';
        for(let i=0;i<8;i++){
            const dx = W*0.1 + i*W*0.115;
            const dh = 60 + Math.sin(t*0.7+i)*30;
            ctx.fillRect(dx, 0, 12+i%3*4, dh);
            ctx.beginPath(); ctx.arc(dx+6, dh, 10+i%3*4, 0, Math.PI*2); ctx.fill();
        }
        // Vignette
        const vign=ctx.createRadialGradient(W/2,H/2,0,W/2,H/2,W*0.7);
        vign.addColorStop(0,'rgba(0,0,0,0)'); vign.addColorStop(1,'rgba(0,0,0,0.7)');
        ctx.fillStyle=vign; ctx.fillRect(0,0,W,H);
    }
    drawDeath();
}
function stopDeathAnimation() {
    if (deathAnimFrame) { cancelAnimationFrame(deathAnimFrame); deathAnimFrame=null; }
}

// ---- JUMPSCARE CANVAS ----
let jsFrame=null, jsName='freddy';
function startJumpscareCanvas(name) {
    jsName=name;
    const canvas=document.getElementById('jumpscare-canvas');
    if(!canvas) return;
    canvas.width=window.innerWidth; canvas.height=window.innerHeight;
    const ctx=canvas.getContext('2d');
    let t=0;
    const cfg=ANIM_DRAW[name]||ANIM_DRAW.freddy;
    function draw(){
        jsFrame=requestAnimationFrame(draw);
        t+=0.18;
        const W=canvas.width,H=canvas.height;
        ctx.fillStyle='#000'; ctx.fillRect(0,0,W,H);
        // Flash background in character color
        const flashAlpha=0.3+Math.sin(t*20)*0.3;
        ctx.fillStyle=cfg.accent+Math.round(flashAlpha*255).toString(16).padStart(2,'0');
        ctx.fillRect(0,0,W,H);
        // Draw giant face zooming in
        const scale=0.8+Math.sin(t*8)*0.25;
        const cx=W/2 + Math.sin(t*15)*(15+t*3);
        const cy=H/2 + Math.cos(t*13)*(10+t*2);
        ctx.save();
        ctx.translate(cx,cy);
        ctx.scale(scale*3.5,scale*3.5);
        drawAnimatronicSprite(ctx, name, 0, 120, 1.0, false);
        ctx.restore();
        // Overlay color flash
        if(Math.sin(t*18)>0.5){
            ctx.fillStyle=`rgba(255,0,0,0.15)`;
            ctx.fillRect(0,0,W,H);
        }
    }
    draw();
}
function stopJumpscareCanvas(){
    if(jsFrame){cancelAnimationFrame(jsFrame);jsFrame=null;}
}
let camUpdateTimer = 0;
function gameLoop() {
    requestAnimationFrame(gameLoop);
    if (!gameRunning) { renderer.render(scene, camera); return; }

    const dt = Math.min(clock.getDelta(), 0.05);

    // Smooth look
    lookAngle += (lookTarget - lookAngle) * 6 * dt;
    camera.rotation.y = -lookAngle;
    camera.rotation.x = -0.14 + Math.sin(Date.now() * 0.0006) * 0.003;
    camera.position.y = 1.72 + Math.sin(Date.now() * 0.0006) * 0.004;

    // Power
    power = Math.max(0, power - getPowerDrain() * dt);
    updatePowerDisplay();
    if (power <= 0) { triggerPowerOut(); return; }

    // Time
    nightTimer += dt;
    nightHour = (nightTimer / nightDuration) * 6;
    updateTimeDisplay();
    if (nightHour >= 6) { triggerWin(); return; }

    // Animatronics
    updateAnimatronics(dt);
    // Foxy run animation progress
    if (animatronics.foxy && animatronics.foxy.location === 'running') {
        animatronics.foxy.runTimer = (animatronics.foxy.runTimer||0) + dt;
        animatronics.foxy.runProgress = Math.min((animatronics.foxy.runTimer||0)/2.5, 1);
        if (animatronics.foxy.runProgress >= 1) {
            animatronics.foxy.foxyStage = Math.min(animatronics.foxy.foxyStage+1, FOXY_STAGES.length-1);
            animatronics.foxy.location = FOXY_STAGES[animatronics.foxy.foxyStage];
            updateCameraStatuses();
        }
    }
    if (cameraOpen) updateCameraStatuses();

    // Camera monitor texture update (30fps enough)
    camUpdateTimer += dt;
    if (camUpdateTimer > 0.033) {
        camUpdateTimer = 0;
        drawCameraMonitor();
        if (cameraOpen) updateCamPreview();
    }

    // Screen noise flicker
    const noiseEl = document.getElementById('noise-overlay');
    noiseEl.style.opacity = Math.random() < 0.03 ? (Math.random() * 0.12).toString() : '0';

    renderer.render(scene, camera);
}

// ---- INIT ----
window.addEventListener('load', () => {
    startMenuAnimation();
    initThree();
    gameLoop();
});

// ---- KEYBOARD ----
document.addEventListener('keydown', e => {
    if (!gameRunning || gameOver) return;
    switch(e.key.toLowerCase()) {
        case 'q': toggleDoor('left'); break;
        case 'e': toggleDoor('right'); break;
        case 'a': toggleLight('left'); break;
        case 'd': toggleLight('right'); break;
        case 'c': cameraOpen ? closeCameras() : openCameras(); break;
    }
});

</script>
</body>
</html>
