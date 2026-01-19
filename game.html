<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JETBLADE DOMINION</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            overflow: hidden;
            background: #000;
            font-family: 'Orbitron', sans-serif;
        }

        body.no-cursor {
            cursor: none;
        }

        #gameCanvas {
            display: block;
        }

        /* Overlays */
        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            display: none;
            z-index: 5;
        }

        #motionBlur {
            background: radial-gradient(ellipse at center, transparent 40%, rgba(180, 0, 0, 0.15) 100%);
        }

        #motionBlur.active {
            display: block;
        }

        #hellbatTint {
            background: linear-gradient(135deg, rgba(80, 0, 0, 0.08), rgba(40, 0, 0, 0.04));
            z-index: 4;
        }

        #forcefieldOverlay {
            background: radial-gradient(ellipse at center, rgba(0, 200, 255, 0.05), rgba(100, 0, 255, 0.1) 50%, transparent 70%);
            animation: shimmer 2s infinite;
        }

        #stealthTint {
            background: linear-gradient(135deg, rgba(0, 100, 200, 0.08), rgba(0, 150, 255, 0.1));
            z-index: 4;
        }

        #invincibilityFlash {
            background: rgba(255, 150, 0, 0.25);
            z-index: 4;
            transition: background 0.2s;
        }

        #invincibilityFlash.stealth-rebound {
            background: rgba(0, 200, 255, 0.3);
        }

        #domainEdgeGlow {
            box-shadow: inset 0 0 150px rgba(255, 50, 0, 0.5);
            animation: pulse 1s infinite;
            z-index: 3;
        }

        #atmosphericGlow {
            background: radial-gradient(ellipse at center, rgba(255, 255, 255, 0.03) 0%, transparent 60%);
            display: block;
            z-index: 1;
        }

        @keyframes pulse {

            0%,
            100% {
                opacity: 0.8;
            }

            50% {
                opacity: 1;
            }
        }

        @keyframes shimmer {

            0%,
            100% {
                opacity: 0.4;
            }

            50% {
                opacity: 0.7;
            }
        }

        /* HUD */
        #hud {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 10;
        }

        /* Radar with compass */
        #leftPanel {
            position: fixed;
            left: 30px;
            top: 50%;
            transform: translateY(-50%);
        }

        #radarContainer {
            width: 180px;
            height: 180px;
            background: rgba(0, 20, 10, 0.9);
            border: 2px solid #00ffaa;
            border-radius: 50%;
            position: relative;
            box-shadow: 0 0 25px rgba(0, 255, 170, 0.4), inset 0 0 40px rgba(0, 50, 30, 0.5);
            backdrop-filter: blur(10px);
        }

        #radarSweep {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 50%;
            height: 2px;
            background: linear-gradient(to right, #00ffaa, transparent);
            transform-origin: left center;
            animation: sweep 3s linear infinite;
        }

        @keyframes sweep {
            from {
                transform: rotate(0deg);
            }

            to {
                transform: rotate(360deg);
            }
        }

        .radar-ring {
            position: absolute;
            border: 1px solid rgba(0, 255, 170, 0.2);
            border-radius: 50%;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }

        /* ========== EPIC PLAYER RADAR INDICATOR ========== */
        #radarPlayerSystem {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 40px;
            height: 40px;
            transform: translate(-50%, -50%);
            pointer-events: none;
        }

        /* Outer rotating tech ring */
        #radarOuterRing {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 32px;
            height: 32px;
            border: 2px solid rgba(0, 170, 255, 0.4);
            border-top: 2px solid #00aaff;
            border-radius: 50%;
            transform: translate(-50%, -50%);
            animation: radarRingSpin 4s linear infinite;
            box-shadow: 0 0 8px rgba(0, 170, 255, 0.3);
        }

        @keyframes radarRingSpin {
            from {
                transform: translate(-50%, -50%) rotate(0deg);
            }

            to {
                transform: translate(-50%, -50%) rotate(360deg);
            }
        }

        /* Inner rotating ring (counter-direction) */
        #radarInnerRing {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 24px;
            height: 24px;
            border: 1px dashed rgba(0, 170, 255, 0.3);
            border-radius: 50%;
            transform: translate(-50%, -50%);
            animation: radarRingSpinReverse 3s linear infinite;
        }

        @keyframes radarRingSpinReverse {
            from {
                transform: translate(-50%, -50%) rotate(360deg);
            }

            to {
                transform: translate(-50%, -50%) rotate(0deg);
            }
        }

        /* Core player triangle */
        #radarCenter {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-left: 7px solid transparent;
            border-right: 7px solid transparent;
            border-bottom: 14px solid #00aaff;
            transform: translate(-50%, -50%);
            filter: drop-shadow(0 0 8px #00aaff) drop-shadow(0 0 4px #ffffff);
            transition: transform 0.08s ease-out, border-bottom-color 0.3s, filter 0.3s;
            z-index: 5;
        }

        /* Triangle inner glow core */
        #radarCenterCore {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-left: 4px solid transparent;
            border-right: 4px solid transparent;
            border-bottom: 8px solid #ffffff;
            transform: translate(-50%, -50%);
            opacity: 0.8;
            z-index: 6;
            animation: coreGlowPulse 1.5s ease-in-out infinite;
        }

        @keyframes coreGlowPulse {

            0%,
            100% {
                opacity: 0.6;
            }

            50% {
                opacity: 1;
            }
        }

        /* Speed indicator arcs (left & right) */
        #radarSpeedArcLeft,
        #radarSpeedArcRight {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 36px;
            height: 36px;
            border: 2px solid transparent;
            border-radius: 50%;
            transform: translate(-50%, -50%);
            opacity: 0;
            transition: opacity 0.2s, border-color 0.2s;
        }

        #radarSpeedArcLeft {
            border-left-color: #00aaff;
            clip-path: polygon(0 0, 50% 0, 50% 100%, 0 100%);
        }

        #radarSpeedArcRight {
            border-right-color: #00aaff;
            clip-path: polygon(50% 0, 100% 0, 100% 100%, 50% 100%);
        }

        #radarSpeedArcLeft.active,
        #radarSpeedArcRight.active {
            opacity: 1;
            animation: speedArcPulse 0.4s ease-out infinite;
        }

        @keyframes speedArcPulse {

            0%,
            100% {
                transform: translate(-50%, -50%) scale(1);
                opacity: 1;
            }

            50% {
                transform: translate(-50%, -50%) scale(1.15);
                opacity: 0.7;
            }
        }

        /* Boost thrust trails */
        #radarBoostTrailLeft,
        #radarBoostTrailRight {
            position: absolute;
            top: 50%;
            width: 3px;
            height: 0;
            background: linear-gradient(to bottom, #00aaff, transparent);
            transform: translateX(-50%);
            opacity: 0;
            transition: height 0.15s, opacity 0.15s;
            z-index: 3;
        }

        #radarBoostTrailLeft {
            left: calc(50% - 5px);
        }

        #radarBoostTrailRight {
            left: calc(50% + 5px);
        }

        #radarBoostTrailLeft.active,
        #radarBoostTrailRight.active {
            height: 20px;
            opacity: 0.9;
            animation: boostTrailFlicker 0.1s ease-in-out infinite;
        }

        @keyframes boostTrailFlicker {

            0%,
            100% {
                opacity: 0.9;
                height: 20px;
            }

            50% {
                opacity: 0.7;
                height: 18px;
            }
        }

        /* Pulsing detection ping */
        #radarPing {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 10px;
            height: 10px;
            border: 2px solid #00aaff;
            border-radius: 50%;
            transform: translate(-50%, -50%);
            opacity: 0;
            pointer-events: none;
        }

        #radarPing.active {
            animation: radarPingExpand 2s ease-out infinite;
        }

        @keyframes radarPingExpand {
            0% {
                width: 10px;
                height: 10px;
                opacity: 0.8;
                border-width: 2px;
            }

            100% {
                width: 80px;
                height: 80px;
                opacity: 0;
                border-width: 1px;
            }
        }

        /* ========== MODE-SPECIFIC STYLES ========== */
        /* HELLBAT MODE */
        .radar-hellbat #radarCenter {
            border-bottom-color: #ff3300;
            filter: drop-shadow(0 0 10px #ff3300) drop-shadow(0 0 5px #ff6600);
        }

        .radar-hellbat #radarCenterCore {
            border-bottom-color: #ffaa00;
        }

        .radar-hellbat #radarOuterRing {
            border-color: rgba(255, 51, 0, 0.4);
            border-top-color: #ff3300;
            box-shadow: 0 0 12px rgba(255, 51, 0, 0.5);
            animation-duration: 2s;
        }

        .radar-hellbat #radarInnerRing {
            border-color: rgba(255, 100, 0, 0.4);
            animation-duration: 1.5s;
        }

        .radar-hellbat #radarSpeedArcLeft,
        .radar-hellbat #radarSpeedArcRight {
            border-color: transparent;
        }

        .radar-hellbat #radarSpeedArcLeft {
            border-left-color: #ff6600;
        }

        .radar-hellbat #radarSpeedArcRight {
            border-right-color: #ff6600;
        }

        .radar-hellbat #radarBoostTrailLeft,
        .radar-hellbat #radarBoostTrailRight {
            background: linear-gradient(to bottom, #ff3300, #ff6600, transparent);
        }

        .radar-hellbat #radarPing {
            border-color: #ff3300;
        }

        .radar-hellbat #radarOuterRing {
            animation-name: radarRingSpinHellbat;
        }

        @keyframes radarRingSpinHellbat {
            from {
                transform: translate(-50%, -50%) rotate(0deg);
            }

            to {
                transform: translate(-50%, -50%) rotate(-360deg);
            }
        }

        /* STEALTH MODE */
        .radar-stealth #radarCenter {
            border-bottom-color: #00ffff;
            filter: drop-shadow(0 0 12px #00ffff) drop-shadow(0 0 6px #88ffff);
        }

        .radar-stealth #radarCenterCore {
            border-bottom-color: #aaffff;
            animation: coreGlowPulseStealth 0.8s ease-in-out infinite;
        }

        @keyframes coreGlowPulseStealth {

            0%,
            100% {
                opacity: 0.4;
            }

            50% {
                opacity: 0.9;
            }
        }

        .radar-stealth #radarOuterRing {
            border-color: rgba(0, 255, 255, 0.2);
            border-top-color: rgba(0, 255, 255, 0.6);
            box-shadow: 0 0 15px rgba(0, 255, 255, 0.3);
            animation-duration: 6s;
        }

        .radar-stealth #radarInnerRing {
            border-color: rgba(0, 255, 255, 0.15);
            animation-duration: 5s;
        }

        .radar-stealth #radarSpeedArcLeft,
        .radar-stealth #radarSpeedArcRight {
            border-color: transparent;
        }

        .radar-stealth #radarSpeedArcLeft {
            border-left-color: #00ffff;
        }

        .radar-stealth #radarSpeedArcRight {
            border-right-color: #00ffff;
        }

        .radar-stealth #radarBoostTrailLeft,
        .radar-stealth #radarBoostTrailRight {
            background: linear-gradient(to bottom, #00ffff, #00aaff, transparent);
        }

        .radar-stealth #radarPing {
            border-color: #00ffff;
            animation-duration: 3s;
        }

        .radar-stealth #radarPlayerSystem {
            animation: stealthFlicker 0.15s ease-in-out infinite;
        }

        @keyframes stealthFlicker {

            0%,
            90%,
            100% {
                opacity: 1;
            }

            95% {
                opacity: 0.6;
            }
        }

        /* Lock-on indicator */
        #radarLockIndicator {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 44px;
            height: 44px;
            border: 2px solid #ffaa00;
            border-radius: 4px;
            transform: translate(-50%, -50%) rotate(45deg);
            opacity: 0;
            transition: opacity 0.2s;
        }

        #radarLockIndicator.active {
            opacity: 1;
            animation: lockIndicatorPulse 0.5s ease-in-out infinite;
        }

        @keyframes lockIndicatorPulse {

            0%,
            100% {
                transform: translate(-50%, -50%) rotate(45deg) scale(1);
                opacity: 1;
            }

            50% {
                transform: translate(-50%, -50%) rotate(45deg) scale(1.1);
                opacity: 0.8;
            }
        }

        /* Damage warning flash */
        .radar-damage #radarPlayerSystem {
            animation: radarDamageFlash 0.15s ease-out 3;
        }

        @keyframes radarDamageFlash {

            0%,
            100% {
                filter: none;
            }

            50% {
                filter: brightness(2) hue-rotate(-30deg);
            }
        }

        /* ========== KILL FEED ========== */
        #killFeed {
            position: fixed;
            bottom: 120px;
            right: 30px;
            display: flex;
            flex-direction: column;
            gap: 8px;
            pointer-events: none;
            z-index: 100;
        }

        .kill-feed-item {
            background: rgba(0, 20, 10, 0.85);
            border: 1px solid #00ffaa;
            border-radius: 4px;
            padding: 8px 15px;
            color: #00ffaa;
            font-size: 11px;
            letter-spacing: 1px;
            text-shadow: 0 0 8px #00ffaa;
            animation: killFeedSlide 0.3s ease-out, killFeedFade 3s ease-out forwards;
            box-shadow: 0 0 15px rgba(0, 255, 170, 0.3);
        }

        .kill-feed-item .enemy-type {
            color: #ff6600;
            font-weight: bold;
            text-shadow: 0 0 8px #ff6600;
        }

        .kill-feed-item .score {
            color: #ffaa00;
            font-weight: bold;
        }

        @keyframes killFeedSlide {
            from {
                transform: translateX(100px);
                opacity: 0;
            }

            to {
                transform: translateX(0);
                opacity: 1;
            }
        }

        @keyframes killFeedFade {

            0%,
            70% {
                opacity: 1;
            }

            100% {
                opacity: 0;
            }
        }

        /* Mode-specific kill feed */
        .hellbat-mode .kill-feed-item {
            border-color: #ff3300;
            color: #ff6600;
            text-shadow: 0 0 8px #ff3300;
            box-shadow: 0 0 15px rgba(255, 51, 0, 0.4);
        }

        .stealth-mode .kill-feed-item {
            border-color: #00ffff;
            color: #00ffff;
            text-shadow: 0 0 8px #00ffff;
            box-shadow: 0 0 15px rgba(0, 255, 255, 0.3);
        }

        /* ========== COMBO COUNTER ========== */
        #comboContainer {
            position: fixed;
            top: 35%;
            right: 80px;
            text-align: right;
            pointer-events: none;
            z-index: 100;
            opacity: 0;
            transform: scale(0.8);
            transition: opacity 0.2s, transform 0.2s;
        }

        #comboContainer.active {
            opacity: 1;
            transform: scale(1);
        }

        #comboCount {
            font-size: 72px;
            font-weight: 900;
            color: #ffaa00;
            text-shadow: 0 0 30px #ffaa00, 0 0 60px #ff6600;
            line-height: 1;
            animation: comboPulse 0.3s ease-out;
        }

        #comboLabel {
            font-size: 18px;
            color: #ffaa00;
            letter-spacing: 4px;
            margin-top: -5px;
            text-shadow: 0 0 15px #ffaa00;
        }

        #comboMultiplier {
            font-size: 28px;
            font-weight: bold;
            color: #00ffaa;
            text-shadow: 0 0 20px #00ffaa;
            margin-top: 5px;
        }

        @keyframes comboPulse {
            0% {
                transform: scale(1.3);
            }

            100% {
                transform: scale(1);
            }
        }

        /* Combo escalation colors */
        #comboContainer.combo-3 #comboCount {
            color: #00ff66;
            text-shadow: 0 0 30px #00ff66;
        }

        #comboContainer.combo-4 #comboCount {
            color: #00ffff;
            text-shadow: 0 0 30px #00ffff;
        }

        #comboContainer.combo-5 #comboCount {
            color: #ff00ff;
            text-shadow: 0 0 40px #ff00ff, 0 0 80px #ff00ff;
        }

        /* ========== KILL STREAK BANNERS ========== */
        #streakBanner {
            position: fixed;
            top: 20%;
            left: 50%;
            transform: translateX(-50%) scale(0);
            text-align: center;
            pointer-events: none;
            z-index: 150;
            opacity: 0;
        }

        #streakBanner.active {
            animation: streakBannerIn 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
        }

        @keyframes streakBannerIn {
            0% {
                transform: translateX(-50%) scale(0);
                opacity: 0;
            }

            60% {
                transform: translateX(-50%) scale(1.1);
                opacity: 1;
            }

            100% {
                transform: translateX(-50%) scale(1);
                opacity: 1;
            }
        }

        #streakBanner.fadeOut {
            animation: streakBannerOut 0.5s ease-in forwards;
        }

        @keyframes streakBannerOut {
            0% {
                transform: translateX(-50%) scale(1);
                opacity: 1;
            }

            100% {
                transform: translateX(-50%) scale(0.8);
                opacity: 0;
            }
        }

        #streakText {
            font-size: 48px;
            font-weight: 900;
            letter-spacing: 8px;
            color: #ff6600;
            text-shadow: 0 0 30px #ff6600, 0 0 60px #ff3300, 0 0 90px #ff0000;
        }

        #streakSubtext {
            font-size: 16px;
            color: #ffaa00;
            letter-spacing: 6px;
            margin-top: 5px;
        }

        /* Streak level colors */
        .streak-3 #streakText {
            color: #00ff66;
            text-shadow: 0 0 30px #00ff66;
        }

        .streak-5 #streakText {
            color: #ffaa00;
            text-shadow: 0 0 40px #ffaa00, 0 0 80px #ff6600;
        }

        .streak-10 #streakText {
            color: #ff00ff;
            text-shadow: 0 0 50px #ff00ff, 0 0 100px #ff00ff;
            animation: godlikePulse 0.5s infinite;
        }

        @keyframes godlikePulse {

            0%,
            100% {
                transform: scale(1);
            }

            50% {
                transform: scale(1.05);
            }
        }

        /* ========== DAMAGE DIRECTION INDICATOR ========== */
        #damageIndicator {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 50;
        }

        .damage-arc {
            position: absolute;
            width: 100%;
            height: 100%;
            opacity: 0;
            transition: opacity 0.1s;
        }

        .damage-arc.active {
            opacity: 1;
            animation: damageFlash 0.4s ease-out;
        }

        .damage-arc-top {
            background: linear-gradient(to bottom, rgba(255, 0, 0, 0.6) 0%, transparent 30%);
        }

        .damage-arc-bottom {
            background: linear-gradient(to top, rgba(255, 0, 0, 0.6) 0%, transparent 30%);
        }

        .damage-arc-left {
            background: linear-gradient(to right, rgba(255, 0, 0, 0.6) 0%, transparent 30%);
        }

        .damage-arc-right {
            background: linear-gradient(to left, rgba(255, 0, 0, 0.6) 0%, transparent 30%);
        }

        .damage-arc-rear {
            background: radial-gradient(ellipse at 50% 100%, rgba(255, 0, 0, 0.7) 0%, transparent 50%);
        }

        @keyframes damageFlash {
            0% {
                opacity: 1;
            }

            100% {
                opacity: 0;
            }
        }

        /* ========== SPEED LINES ========== */
        #speedLines {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 3;
            opacity: 0;
            transition: opacity 0.3s;
        }

        #speedLines.active {
            opacity: 1;
        }

        .speed-line {
            position: absolute;
            background: linear-gradient(to bottom, transparent, rgba(255, 255, 255, 0.4), transparent);
            transform-origin: center bottom;
        }

        /* Radial speed lines container */
        #speedLinesInner {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 200%;
            height: 200%;
            transform: translate(-50%, -50%);
        }

        /* Mode-specific speed lines */
        .hellbat-mode #speedLines .speed-line {
            background: linear-gradient(to bottom, transparent, rgba(255, 100, 0, 0.5), transparent);
        }

        .stealth-mode #speedLines .speed-line {
            background: linear-gradient(to bottom, transparent, rgba(0, 255, 255, 0.3), transparent);
        }

        /* ========== POWER-UPS ========== */
        .powerup-indicator {
            position: fixed;
            padding: 10px 20px;
            border-radius: 8px;
            font-size: 14px;
            font-weight: bold;
            letter-spacing: 2px;
            z-index: 100;
            pointer-events: none;
            animation: powerupSlide 0.3s ease-out;
        }

        #healthBoostIndicator {
            bottom: 200px;
            left: 50%;
            transform: translateX(-50%);
            background: rgba(0, 100, 0, 0.8);
            border: 2px solid #00ff00;
            color: #00ff00;
            box-shadow: 0 0 20px rgba(0, 255, 0, 0.5);
            display: none;
        }

        #rapidFireIndicator {
            bottom: 240px;
            left: 50%;
            transform: translateX(-50%);
            background: rgba(100, 30, 0, 0.8);
            border: 2px solid #ff4400;
            color: #ff4400;
            box-shadow: 0 0 20px rgba(255, 68, 0, 0.5);
            display: none;
        }

        @keyframes powerupSlide {
            from {
                transform: translateX(-50%) translateY(20px);
                opacity: 0;
            }

            to {
                transform: translateX(-50%) translateY(0);
                opacity: 1;
            }
        }

        /* ========== BOSS HEALTH BAR ========== */
        #bossHealthContainer {
            position: fixed;
            top: 60px;
            left: 50%;
            transform: translateX(-50%);
            width: 400px;
            text-align: center;
            z-index: 100;
            display: none;
        }

        #bossName {
            font-size: 18px;
            color: #ff3300;
            letter-spacing: 4px;
            text-shadow: 0 0 15px #ff3300;
            margin-bottom: 8px;
        }

        #bossHealthBar {
            width: 100%;
            height: 16px;
            background: rgba(0, 0, 0, 0.8);
            border: 2px solid #ff3300;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 0 20px rgba(255, 51, 0, 0.4);
        }

        #bossHealthFill {
            height: 100%;
            background: linear-gradient(90deg, #ff0000, #ff3300, #ff6600);
            width: 100%;
            transition: width 0.2s;
            box-shadow: 0 0 10px #ff3300;
        }

        #bossHealthText {
            font-size: 12px;
            color: #ff6600;
            margin-top: 4px;
            letter-spacing: 2px;
        }

        /* ========== OVERDRIVE MODE ========== */
        #overdriveOverlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 4;
            display: none;
            background: radial-gradient(ellipse at center, transparent 40%, rgba(255, 200, 0, 0.1) 100%);
            animation: overdrivePulse 0.5s ease-in-out infinite;
        }

        @keyframes overdrivePulse {

            0%,
            100% {
                opacity: 0.5;
            }

            50% {
                opacity: 1;
            }
        }

        #radarBlips {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }

        .compass-dir {
            position: absolute;
            color: #00ffaa;
            font-size: 11px;
            font-weight: bold;
            text-shadow: 0 0 8px #00ffaa;
        }

        .compass-n {
            top: 6px;
            left: 50%;
            transform: translateX(-50%);
        }

        .compass-s {
            bottom: 6px;
            left: 50%;
            transform: translateX(-50%);
        }

        .compass-e {
            right: 6px;
            top: 50%;
            transform: translateY(-50%);
        }

        .compass-w {
            left: 6px;
            top: 50%;
            transform: translateY(-50%);
        }

        #radarLabel {
            text-align: center;
            color: #00ffaa;
            font-size: 10px;
            margin-top: 10px;
            letter-spacing: 3px;
            text-shadow: 0 0 10px #00ffaa;
        }

        /* Right panel meters */
        #rightPanel {
            position: fixed;
            right: 30px;
            top: 50%;
            transform: translateY(-50%);
            display: flex;
            flex-direction: column;
            gap: 30px;
            align-items: flex-end;
        }

        .meter-container {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .meter-label {
            color: #00ffaa;
            font-size: 10px;
            letter-spacing: 2px;
            writing-mode: vertical-rl;
            transform: rotate(180deg);
            text-shadow: 0 0 10px #00ffaa;
        }

        .meter-bar {
            width: 14px;
            height: 150px;
            background: rgba(0, 20, 10, 0.9);
            border: 2px solid #00ffaa;
            border-radius: 7px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 0 15px rgba(0, 255, 170, 0.3), inset 0 0 20px rgba(0, 50, 30, 0.5);
        }

        .meter-fill {
            position: absolute;
            bottom: 0;
            width: 100%;
            background: linear-gradient(to top, #00ff66, #00ffaa, #88ffcc);
            transition: height 0.2s;
            box-shadow: 0 0 15px #00ffaa;
        }

        .meter-value {
            color: #00ffaa;
            font-size: 14px;
            font-weight: bold;
            min-width: 50px;
            text-align: right;
            text-shadow: 0 0 15px #00ffaa;
        }

        /* Top HUD */
        #topHud {
            position: fixed;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 40px;
        }

        .hud-stat {
            text-align: center;
            color: #00ffaa;
            background: rgba(0, 20, 10, 0.7);
            padding: 10px 20px;
            border-radius: 8px;
            border: 1px solid rgba(0, 255, 170, 0.3);
        }

        .hud-stat-label {
            font-size: 10px;
            opacity: 0.7;
            letter-spacing: 2px;
        }

        .hud-stat-value {
            font-size: 24px;
            font-weight: bold;
            text-shadow: 0 0 15px #00ffaa;
        }

        /* Mode indicator */
        #modeIndicator {
            position: fixed;
            top: 20px;
            right: 30px;
            padding: 15px 25px;
            border-radius: 8px;
            font-size: 14px;
            font-weight: bold;
            letter-spacing: 3px;
            backdrop-filter: blur(10px);
        }

        #modeIndicator.normal {
            background: rgba(255, 255, 255, 0.1);
            border: 2px solid rgba(255, 255, 255, 0.8);
            color: #fff;
            box-shadow: 0 0 20px rgba(255, 255, 255, 0.2);
        }

        #modeIndicator.hellbat {
            background: rgba(100, 0, 0, 0.4);
            border: 2px solid #ff0000;
            color: #ff0000;
            animation: hellbatPulse 1.5s infinite;
        }

        #modeIndicator.stealth {
            background: rgba(0, 100, 255, 0.2);
            border: 2px solid #00ccff;
            color: #00ccff;
            animation: pulse 2s infinite;
        }

        @keyframes hellbatPulse {

            0%,
            100% {
                box-shadow: 0 0 20px rgba(255, 0, 0, 0.5);
            }

            50% {
                box-shadow: 0 0 40px rgba(255, 0, 0, 0.8);
            }
        }

        /* Crosshair - HIDDEN by default */
        #crosshair {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 40px;
            height: 40px;
            z-index: 20;
            pointer-events: none;
            display: none;
            /* Hidden by default */
        }

        #crosshair::before,
        #crosshair::after {
            content: '';
            position: absolute;
            background: rgba(255, 255, 255, 0.9);
            box-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
        }

        #crosshair::before {
            width: 20px;
            height: 2px;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }

        #crosshair::after {
            width: 2px;
            height: 20px;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }

        #crosshair.hellbat::before,
        #crosshair.hellbat::after {
            background: #ff0000;
            box-shadow: 0 0 15px #ff0000;
        }

        #crosshair.stealth::before,
        #crosshair.stealth::after {
            background: #00ccff;
            box-shadow: 0 0 15px #00ccff;
        }

        .crosshair-circle {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 30px;
            height: 30px;
            border: 1px solid rgba(255, 255, 255, 0.6);
            border-radius: 50%;
            box-shadow: 0 0 10px rgba(255, 255, 255, 0.2);
        }

        #crosshair.hellbat .crosshair-circle {
            border-color: rgba(255, 0, 0, 0.8);
            box-shadow: 0 0 15px rgba(255, 0, 0, 0.4);
        }

        #crosshair.stealth .crosshair-circle {
            border-color: rgba(0, 200, 255, 0.8);
            box-shadow: 0 0 15px rgba(0, 200, 255, 0.4);
        }

        /* Holographic Aim Lens - appears on right-click */
        #aimLens {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 120px;
            height: 120px;
            z-index: 25;
            pointer-events: none;
            display: none;
        }

        /* Deploy Animation */
        @keyframes lensDeploy {
            0% {
                transform: translate(-50%, -50%) scale(0.4) rotate(-45deg);
                opacity: 0;
            }

            100% {
                transform: translate(-50%, -50%) scale(1) rotate(0deg);
                opacity: 1;
            }
        }

        /* Continuous Rotation */
        @keyframes spinSlow {
            from {
                transform: translate(-50%, -50%) rotate(0deg);
            }

            to {
                transform: translate(-50%, -50%) rotate(360deg);
            }
        }

        @keyframes spinReverse {
            from {
                transform: translate(-50%, -50%) rotate(360deg);
            }

            to {
                transform: translate(-50%, -50%) rotate(0deg);
            }
        }

        #aimLens.active {
            display: block;
            animation: lensDeploy 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .aim-lens-outer {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 100px;
            height: 100px;
            border: 2px solid rgba(0, 255, 200, 0.8);
            border-radius: 50%;
            box-shadow: 0 0 20px rgba(0, 255, 200, 0.5), inset 0 0 30px rgba(0, 255, 200, 0.1);
        }

        #aimLens.active .aim-lens-outer {
            animation: spinSlow 10s linear infinite;
        }

        .aim-lens-inner {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 60px;
            height: 60px;
            border: 1px solid rgba(0, 255, 200, 0.5);
            border-radius: 50%;
        }

        #aimLens.active .aim-lens-inner {
            animation: spinReverse 6s linear infinite;
        }

        .aim-lens-center {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 8px;
            height: 8px;
            background: rgba(0, 255, 200, 0.9);
            border-radius: 50%;
            box-shadow: 0 0 15px rgba(0, 255, 200, 0.8);
        }

        .aim-lens-crosshair {
            position: absolute;
            background: rgba(0, 255, 200, 0.6);
        }

        .aim-lens-crosshair.h {
            width: 30px;
            height: 1px;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }

        .aim-lens-crosshair.v {
            width: 1px;
            height: 30px;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }

        /* Rotating segments */
        .aim-segment {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 55px;
            height: 3px;
            transform-origin: left center;
        }

        .aim-segment::after {
            content: '';
            position: absolute;
            right: 0;
            width: 15px;
            height: 3px;
            background: rgba(0, 255, 200, 0.8);
            border-radius: 2px;
            box-shadow: 0 0 10px rgba(0, 255, 200, 0.6);
        }

        .aim-segment:nth-child(1) {
            transform: rotate(0deg);
        }

        .aim-segment:nth-child(2) {
            transform: rotate(90deg);
        }

        .aim-segment:nth-child(3) {
            transform: rotate(180deg);
        }

        .aim-segment:nth-child(4) {
            transform: rotate(270deg);
        }

        #aimLens.active .aim-segment {
            animation: rotateSegments 3s linear infinite;
        }

        @keyframes rotateSegments {
            from {
                transform: rotate(var(--start-angle));
            }

            to {
                transform: rotate(calc(var(--start-angle) + 360deg));
            }
        }

        /* Lock progress ring */
        .lock-progress {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 80px;
            height: 80px;
        }

        .lock-progress circle {
            fill: none;
            stroke-width: 3;
            stroke-linecap: round;
            transform: rotate(-90deg);
            transform-origin: center;
        }

        .lock-progress-bg {
            stroke: rgba(0, 255, 200, 0.2);
        }

        .lock-progress-fill {
            stroke: rgba(0, 255, 200, 0.9);
            stroke-dasharray: 251;
            stroke-dashoffset: 251;
            transition: stroke-dashoffset 0.1s;
        }

        /* Locked state */
        #aimLens.locked .aim-lens-outer {
            animation: none;
            border-color: rgba(255, 50, 50, 0.9);
            box-shadow: 0 0 30px rgba(255, 50, 50, 0.7), inset 0 0 40px rgba(255, 50, 50, 0.2);
            transform: translate(-50%, -50%) scale(1.05);
            /* Slight pulse size */
            transition: all 0.2s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        #aimLens.locked .aim-lens-inner {
            border-color: rgba(255, 50, 50, 0.7);
        }

        #aimLens.locked .aim-lens-center {
            background: rgba(255, 50, 50, 1);
            box-shadow: 0 0 20px rgba(255, 50, 50, 1);
        }

        #aimLens.locked .aim-lens-crosshair {
            background: rgba(255, 50, 50, 0.8);
        }

        #aimLens.locked .aim-segment::after {
            background: rgba(255, 50, 50, 0.9);
            box-shadow: 0 0 15px rgba(255, 50, 50, 0.8);
        }

        #aimLens.locked .lock-progress-fill {
            stroke: rgba(255, 50, 50, 1);
        }

        /* LOCKED text */
        #lockedIndicator {
            position: fixed;
            top: calc(50% - 80px);
            left: 50%;
            transform: translateX(-50%);
            color: #ff3333;
            font-size: 18px;
            font-weight: bold;
            letter-spacing: 5px;
            text-shadow: 0 0 20px #ff0000, 0 0 40px #ff0000;
            display: none;
            z-index: 30;
            animation: lockedPulse 0.3s infinite;
        }

        @keyframes lockedPulse {

            0%,
            100% {
                opacity: 1;
            }

            50% {
                opacity: 0.7;
            }
        }

        /* Slow-mo overlay */
        #slowMoOverlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(ellipse at center, transparent 50%, rgba(0, 50, 80, 0.15) 100%);
            pointer-events: none;
            display: none;
            z-index: 3;
        }

        #slowMoOverlay.active {
            display: block;
        }

        /* Target box on enemy */
        #targetBox {
            position: fixed;
            width: 60px;
            height: 60px;
            border: 2px solid rgba(255, 50, 50, 0.8);
            pointer-events: none;
            display: none;
            z-index: 25;
            box-shadow: 0 0 15px rgba(255, 50, 50, 0.5);
        }

        #targetBox::before,
        #targetBox::after {
            content: '';
            position: absolute;
            background: rgba(255, 50, 50, 0.8);
        }

        #targetBox::before {
            width: 10px;
            height: 2px;
            top: -8px;
            left: 50%;
            transform: translateX(-50%);
        }

        #targetBox::after {
            width: 10px;
            height: 2px;
            bottom: -8px;
            left: 50%;
            transform: translateX(-50%);
        }

        /* ========== NEW HUD SYSTEM ========== */

        /* HP Bar Container - SLEEK TECH DESIGN */
        .hud-hp-container {
            position: fixed;
            bottom: 40px;
            left: 50%;
            transform: translateX(-50%) skewX(-20deg);
            width: 320px;
            height: 12px;
            background: rgba(0, 5, 10, 0.6);
            border: 1px solid rgba(0, 255, 170, 0.3);
            /* Sharp edges - no radius */
            overflow: hidden;
            box-shadow: 0 0 15px rgba(0, 62, 31, 0.5), inset 0 0 10px rgba(0, 0, 0, 0.8);
            z-index: 100;
            backdrop-filter: blur(4px);
        }

        /* Decorative brackets for tech feel */
        .hud-hp-container::before,
        .hud-hp-container::after {
            content: '';
            position: absolute;
            top: 0;
            bottom: 0;
            width: 4px;
            background: rgba(0, 255, 170, 0.5);
            z-index: 2;
        }

        .hud-hp-container::before {
            left: 0;
            border-right: 1px solid rgba(0, 0, 0, 0.5);
        }

        .hud-hp-container::after {
            right: 0;
            border-left: 1px solid rgba(0, 0, 0, 0.5);
        }

        .hud-hp-fill {
            height: 100%;
            width: 100%;
            /* Default to healthy green */
            background: linear-gradient(90deg, #008855, #00ffaa);
            /* Segmented Overlay */
            background-image: linear-gradient(90deg, #008855, #00ffaa),
                repeating-linear-gradient(45deg,
                    transparent,
                    transparent 8px,
                    rgba(0, 0, 0, 0.6) 8px,
                    rgba(0, 0, 0, 0.6) 10px);
            background-blend-mode: overlay;

            box-shadow: 0 0 20px rgba(0, 255, 170, 0.6);
            transition: width 0.4s cubic-bezier(0.2, 0.8, 0.2, 1), filter 0.3s;
        }

        /* COLOR STATES managed via classes now */
        .hud-hp-fill.state-healthy {
            /* Green */
            background-image: linear-gradient(90deg, #008855, #00ffaa),
                repeating-linear-gradient(45deg, transparent, transparent 8px, rgba(0, 0, 0, 0.6) 8px, rgba(0, 0, 0, 0.6) 10px);
            box-shadow: 0 0 20px rgba(0, 255, 170, 0.6);
        }

        .hud-hp-fill.state-warning {
            /* Yellow */
            background-image: linear-gradient(90deg, #886600, #ffcc00),
                repeating-linear-gradient(45deg, transparent, transparent 8px, rgba(0, 0, 0, 0.6) 8px, rgba(0, 0, 0, 0.6) 10px);
            box-shadow: 0 0 20px rgba(255, 200, 0, 0.6);
        }

        .hud-hp-fill.state-critical {
            /* Red */
            background-image: linear-gradient(90deg, #880000, #ff0000),
                repeating-linear-gradient(45deg, transparent, transparent 8px, rgba(0, 0, 0, 0.6) 8px, rgba(0, 0, 0, 0.6) 10px);
            box-shadow: 0 0 25px rgba(255, 0, 0, 0.8);
            animation: hpPulseCritical 0.6s ease-in-out infinite alternate;
        }

        @keyframes hpPulseCritical {
            0% {
                filter: brightness(1);
                opacity: 1;
            }

            100% {
                filter: brightness(1.5);
                opacity: 0.6;
            }
        }

        /* Ability Dials Container */
        .hud-abilities-container {
            position: fixed;
            bottom: 50px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 40px;
            align-items: flex-end;
            z-index: 100;
        }

        .hud-dial {
            position: relative;
            width: 44px;
            height: 44px;
            opacity: 0.7;
            transition: all 0.3s;
        }

        .hud-dial.glow {
            opacity: 1;
            filter: drop-shadow(0 0 8px currentColor);
            transform: scale(1.1);
        }

        .dial-svg {
            transform: rotate(-90deg);
            /* Start from top */
            width: 100%;
            height: 100%;
        }

        .dial-bg {
            fill: none;
            stroke: rgba(0, 20, 10, 0.8);
            stroke-width: 4;
        }

        .dial-fg {
            fill: none;
            stroke: currentColor;
            stroke-width: 4;
            stroke-linecap: round;
            stroke-dasharray: 100;
            /* Approx circumference for r=16 (2*pi*16 ~= 100) */
            stroke-dashoffset: 100;
            /* Full empty */
            transition: stroke-dashoffset 0.1s linear;
        }

        /* Ability Specific Colors */
        #dial-hellbat {
            color: #ff0000;
        }

        #dial-forcefield {
            color: #00ccff;
        }

        #dial-shockwave {
            color: #ff00ff;
        }

        .dial-icon {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 6px;
            height: 6px;
            border-radius: 50%;
            background: currentColor;
            opacity: 0.3;
            box-shadow: 0 0 5px currentColor;
        }

        .hud-dial.glow .dial-icon {
            opacity: 1;
            box-shadow: 0 0 10px currentColor;
        }

        /* Info displays */
        #missileInfo {
            position: fixed;
            bottom: 30px;
            right: 30px;
            text-align: right;
            background: rgba(0, 20, 10, 0.7);
            padding: 10px 15px;
            border-radius: 8px;
            border: 1px solid rgba(0, 255, 170, 0.3);
        }

        #missileInfo .label {
            font-size: 10px;
            color: #00ffaa;
            opacity: 0.7;
            letter-spacing: 2px;
        }

        #missileInfo .value {
            font-size: 28px;
            color: #ff6600;
            font-weight: bold;
            text-shadow: 0 0 20px #ff6600;
        }

        #controls {
            position: fixed;
            bottom: 20px;
            left: 20px;
            font-size: 9px;
            color: #00ffaa;
            opacity: 0.6;
            line-height: 1.6;
            text-shadow: 0 0 5px #00ffaa;
        }

        #warning {
            position: fixed;
            top: 120px;
            left: 50%;
            transform: translateX(-50%);
            color: #ff3300;
            font-size: 16px;
            letter-spacing: 3px;
            display: none;
            animation: blink 0.5s infinite;
            text-shadow: 0 0 20px #ff3300;
        }

        @keyframes blink {

            0%,
            100% {
                opacity: 1;
            }

            50% {
                opacity: 0.5;
            }
        }

        /* Domain warning - positioned below topHud to avoid overlap */
        #domainIndicator {
            position: fixed;
            top: 115px;
            left: 50%;
            transform: translateX(-50%);
            color: #00ffaa;
            font-size: 12px;
            letter-spacing: 2px;
            opacity: 0.85;
            text-shadow: 0 0 10px #00ffaa, 0 1px 3px rgba(0, 0, 0, 0.8);
            background: rgba(0, 20, 10, 0.5);
            padding: 4px 12px;
            border-radius: 4px;
            border: 1px solid rgba(0, 255, 170, 0.2);
        }

        #domainIndicator.warning {
            color: #ff3300;
            opacity: 1;
            animation: blink 0.5s infinite;
        }

        #domainWarning {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            text-align: center;
            display: none;
            z-index: 50;
            pointer-events: none;
        }

        #domainWarning.active {
            display: block;
        }

        #domainWarningText {
            color: #ff3300;
            font-size: 28px;
            letter-spacing: 5px;
            text-shadow: 0 0 30px #ff3300;
            margin-bottom: 20px;
        }

        #domainCountdown {
            color: #fff;
            font-size: 100px;
            font-weight: 900;
            text-shadow: 0 0 50px #ff0000;
        }

        #returnHint {
            display: none;
            top: 60px;
            right: 30px;
            color: #00ffaa;
            font-size: 11px;
            letter-spacing: 2px;
            opacity: 0.9;
            text-shadow: 0 0 10px #00ffaa, 0 1px 4px rgba(0, 0, 0, 0.9);
            background: rgba(0, 20, 10, 0.6);
            padding: 6px 12px;
            border-radius: 4px;
            border: 1px solid rgba(0, 255, 170, 0.3);
        }

        /* Bank Indicator - shows roll angle */
        #bankIndicator {
            position: fixed;
            bottom: 100px;
            left: 50%;
            transform: translateX(-50%);
            width: 120px;
            height: 30px;
            pointer-events: none;
        }

        #bankArc {
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 50px;
            border: 2px solid rgba(0, 255, 170, 0.3);
            border-bottom: none;
            border-radius: 50px 50px 0 0;
        }

        #bankNeedle {
            position: absolute;
            bottom: 0;
            left: 50%;
            width: 2px;
            height: 25px;
            background: linear-gradient(to top, #00ffaa, transparent);
            transform-origin: bottom center;
            transition: transform 0.1s ease-out;
            box-shadow: 0 0 8px #00ffaa;
        }

        #bankCenter {
            position: absolute;
            bottom: -3px;
            left: 50%;
            transform: translateX(-50%);
            width: 6px;
            height: 6px;
            background: #00ffaa;
            border-radius: 50%;
            box-shadow: 0 0 10px #00ffaa;
        }

        .bank-mark {
            position: absolute;
            bottom: 0;
            width: 1px;
            height: 8px;
            background: rgba(0, 255, 170, 0.5);
            transform-origin: bottom center;
        }

        #gyroStatus {
            position: absolute;
            top: -20px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 8px;
            color: #00ffaa;
            letter-spacing: 2px;
            opacity: 0.6;
            white-space: nowrap;
        }

        #gyroStatus.active {
            color: #ffaa00;
            opacity: 1;
            text-shadow: 0 0 8px #ffaa00;
        }

        /* Title screen - realistic style */
        #startScreen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(180deg, #1fa2ff 0%, #12d8fa 50%, #a6ffcb 100%);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 100;
            overflow: hidden;
        }

        #menuClouds {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 60%;
            pointer-events: none;
            overflow: hidden;
        }

        .menu-cloud {
            position: absolute;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 50%;
            filter: blur(25px);
            box-shadow: 0 0 40px rgba(255, 255, 255, 0.8);
            animation: floatClouds 40s linear infinite alternate;
        }

        #menuMountains {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 55%;
            pointer-events: none;
            overflow: hidden;
        }

        .mountain-layer {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
        }

        /* Distant misty mountains with atmospheric haze */
        .mountain-far {
            height: 45%;
            background: linear-gradient(180deg,
                    rgba(120, 160, 140, 0.7) 0%,
                    rgba(95, 135, 115, 0.8) 30%,
                    rgba(75, 120, 95, 0.9) 60%,
                    rgba(60, 100, 80, 1) 100%);
            clip-path: polygon(0% 100%,
                    0% 75%,
                    3% 72%,
                    8% 68%,
                    12% 55%,
                    18% 48%,
                    22% 52%,
                    28% 45%,
                    32% 50%,
                    38% 42%,
                    42% 38%,
                    48% 45%,
                    52% 40%,
                    58% 48%,
                    62% 42%,
                    68% 50%,
                    72% 44%,
                    78% 52%,
                    82% 48%,
                    88% 55%,
                    92% 50%,
                    96% 58%,
                    100% 52%,
                    100% 100%);
            opacity: 0.75;
            filter: blur(2px);
        }

        /* Mid-distance forested hills with rich greens */
        .mountain-mid {
            height: 35%;
            background: linear-gradient(180deg,
                    #4a7a50 0%,
                    #3d6a42 25%,
                    #2d5a32 50%,
                    #1f4a24 75%,
                    #153a18 100%);
            clip-path: polygon(0% 100%,
                    0% 58%,
                    4% 52%,
                    8% 48%,
                    12% 42%,
                    16% 38%,
                    20% 45%,
                    24% 40%,
                    28% 35%,
                    34% 42%,
                    38% 38%,
                    44% 32%,
                    48% 40%,
                    52% 35%,
                    56% 42%,
                    60% 36%,
                    64% 32%,
                    70% 40%,
                    74% 35%,
                    78% 42%,
                    82% 38%,
                    88% 45%,
                    92% 40%,
                    96% 48%,
                    100% 42%,
                    100% 100%);
            opacity: 0.92;
            filter: blur(0.5px);
        }

        /* Closer forested hills - darker, more defined */
        .mountain-near {
            height: 25%;
            background: linear-gradient(180deg,
                    #2a5028 0%,
                    #224420 30%,
                    #1a3818 60%,
                    #122c10 100%);
            clip-path: polygon(0% 100%,
                    0% 55%,
                    3% 48%,
                    6% 42%,
                    10% 38%,
                    14% 32%,
                    18% 40%,
                    22% 35%,
                    26% 28%,
                    32% 38%,
                    36% 32%,
                    42% 25%,
                    46% 35%,
                    50% 28%,
                    54% 38%,
                    58% 32%,
                    64% 25%,
                    68% 35%,
                    72% 28%,
                    76% 38%,
                    80% 32%,
                    86% 42%,
                    90% 35%,
                    94% 45%,
                    98% 38%,
                    100% 50%,
                    100% 100%);
            opacity: 1;
        }

        /* Forest canopy texture overlay for nearest layer */
        .mountain-near::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background:
                radial-gradient(ellipse 8px 12px at 5% 60%, rgba(35, 70, 35, 0.8) 0%, transparent 100%),
                radial-gradient(ellipse 10px 15px at 12% 55%, rgba(28, 58, 28, 0.7) 0%, transparent 100%),
                radial-gradient(ellipse 7px 11px at 20% 50%, rgba(40, 75, 40, 0.8) 0%, transparent 100%),
                radial-gradient(ellipse 12px 18px at 28% 52%, rgba(32, 65, 32, 0.7) 0%, transparent 100%),
                radial-gradient(ellipse 9px 14px at 36% 48%, rgba(38, 72, 38, 0.8) 0%, transparent 100%),
                radial-gradient(ellipse 11px 16px at 45% 45%, rgba(30, 62, 30, 0.7) 0%, transparent 100%),
                radial-gradient(ellipse 8px 12px at 54% 50%, rgba(42, 78, 42, 0.8) 0%, transparent 100%),
                radial-gradient(ellipse 10px 14px at 62% 48%, rgba(35, 68, 35, 0.7) 0%, transparent 100%),
                radial-gradient(ellipse 9px 13px at 70% 52%, rgba(38, 74, 38, 0.8) 0%, transparent 100%),
                radial-gradient(ellipse 11px 17px at 78% 46%, rgba(32, 66, 32, 0.7) 0%, transparent 100%),
                radial-gradient(ellipse 8px 12px at 86% 50%, rgba(40, 76, 40, 0.8) 0%, transparent 100%),
                radial-gradient(ellipse 10px 15px at 94% 55%, rgba(28, 60, 28, 0.7) 0%, transparent 100%);
            pointer-events: none;
        }

        /* Atmospheric light gradient to simulate sun/sky reflection on distant hills */
        .mountain-far::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(180deg,
                    rgba(200, 230, 255, 0.15) 0%,
                    rgba(150, 200, 220, 0.1) 30%,
                    transparent 60%);
            pointer-events: none;
        }

        /* Subtle shadow on middle hills for depth */
        .mountain-mid::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg,
                    rgba(0, 30, 15, 0.2) 0%,
                    transparent 15%,
                    transparent 85%,
                    rgba(0, 30, 15, 0.15) 100%);
            pointer-events: none;
        }

        #titleContainer {
            position: relative;
            z-index: 10;
            text-align: center;
            margin-bottom: 60px;
        }

        #mainTitle {
            font-size: 84px;
            font-weight: 900;
            letter-spacing: 10px;
            text-transform: uppercase;
            color: #d0e0e3;
            background: linear-gradient(to bottom, #ffffff 0%, #d0e0e3 50%, #768a96 51%, #aebcbf 100%);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            filter: drop-shadow(0 0 20px rgba(0, 200, 255, 0.6));
            font-family: 'Orbitron', sans-serif;
            animation: titleReveal 1.5s cubic-bezier(0.2, 0.8, 0.2, 1) forwards, glitchText 5s infinite;
        }

        #subtitleText {
            font-size: 48px;
            font-weight: 700;
            letter-spacing: 18px;
            color: #fff;
            margin-top: 5px;
            text-shadow: 0 0 15px rgba(0, 0, 0, 0.5);
            opacity: 0.9;
        }

        #versionText {
            font-size: 16px;
            letter-spacing: 8px;
            color: #00ffaa;
            margin-top: 15px;
            text-shadow: 0 0 10px #00ffaa;
            font-weight: bold;
        }

        #startBtn {
            padding: 20px 60px;
            font-size: 20px;
            background: rgba(0, 20, 10, 0.8);
            border: 2px solid #00ffaa;
            color: #00ffaa;
            cursor: pointer;
            border-radius: 4px;
            letter-spacing: 6px;
            font-family: 'Orbitron', sans-serif;
            font-weight: 700;
            z-index: 10;
            transition: all 0.3s;
            pointer-events: auto;
            box-shadow: 0 0 20px rgba(0, 255, 170, 0.3);
            text-transform: uppercase;
            animation: btnPulse 2s infinite;
        }

        #startBtn:hover {
            background: rgba(0, 255, 170, 0.2);
            box-shadow: 0 0 40px rgba(0, 255, 170, 0.5);
            transform: scale(1.05);
        }

        #pauseHint {
            position: fixed;
            bottom: 40px;
            left: 50%;
            transform: translateX(-50%);
            color: #88ccff;
            font-size: 14px;
            letter-spacing: 3px;
            text-shadow: 0 0 10px rgba(136, 204, 255, 0.8);
            z-index: 10;
            animation: blinkHint 2s infinite;
        }

        /* Game over - Dramatic Death Screen */
        #gameOver {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(180deg, rgba(20, 0, 0, 0.95) 0%, rgba(0, 0, 0, 0.98) 50%, rgba(10, 0, 0, 0.95) 100%);
            display: none;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 2000;
        }

        /* Skull Symbol */
        #skullSymbol {
            font-size: 150px;
            margin-bottom: 30px;
            animation: skullPulse 2s ease-in-out infinite;
            filter: drop-shadow(0 0 30px #ff0000) drop-shadow(0 0 60px #ff3300);
        }

        @keyframes skullPulse {

            0%,
            100% {
                transform: scale(1);
                opacity: 1;
            }

            50% {
                transform: scale(1.05);
                opacity: 0.8;
            }
        }

        #gameOver h1 {
            font-size: 56px;
            color: #ff2200;
            text-shadow: 0 0 40px #ff0000, 0 0 80px #ff3300;
            margin-bottom: 15px;
            letter-spacing: 12px;
            animation: deathTextGlow 1.5s ease-in-out infinite alternate;
        }

        @keyframes deathTextGlow {
            0% {
                text-shadow: 0 0 40px #ff0000, 0 0 80px #ff3300;
            }

            100% {
                text-shadow: 0 0 60px #ff0000, 0 0 100px #ff3300, 0 0 120px #ff6600;
            }
        }

        #crashCause {
            font-size: 16px;
            color: #ff6644;
            letter-spacing: 4px;
            margin-bottom: 25px;
            opacity: 0.8;
            text-transform: uppercase;
        }

        #finalScore {
            font-size: 24px;
            color: #00ffaa;
            margin-bottom: 15px;
            text-shadow: 0 0 20px #00ffaa;
        }

        #finalKills {
            font-size: 18px;
            color: #ffaa00;
            margin-bottom: 40px;
            opacity: 0.9;
        }

        #restartBtn {
            padding: 25px 80px;
            font-size: 24px;
            background: linear-gradient(180deg, rgba(255, 50, 0, 0.3), rgba(200, 0, 0, 0.4));
            border: 3px solid #ff3300;
            color: #ff4400;
            cursor: pointer;
            border-radius: 12px;
            letter-spacing: 8px;
            transition: all 0.3s;
            font-family: 'Orbitron', sans-serif;
            pointer-events: auto;
            cursor: pointer;
            text-transform: uppercase;
            box-shadow: 0 0 30px rgba(255, 50, 0, 0.3), inset 0 0 20px rgba(255, 100, 0, 0.1);
            animation: respawnPulse 2s ease-in-out infinite;
        }

        @keyframes respawnPulse {

            0%,
            100% {
                box-shadow: 0 0 30px rgba(255, 50, 0, 0.3), inset 0 0 20px rgba(255, 100, 0, 0.1);
            }

            50% {
                box-shadow: 0 0 50px rgba(255, 50, 0, 0.5), inset 0 0 30px rgba(255, 100, 0, 0.2);
            }
        }

        #restartBtn:hover {
            background: linear-gradient(180deg, #ff4400, #cc0000);
            color: #fff;
            box-shadow: 0 0 60px #ff3300, 0 0 100px #ff6600;
            transform: scale(1.05);
        }

        /* Crash overlay effects */
        #crashOverlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(ellipse at center, rgba(255, 100, 0, 0.4) 0%, rgba(255, 50, 0, 0.2) 30%, rgba(0, 0, 0, 0.8) 100%);
            pointer-events: none;
            display: none;
            z-index: 90;
            animation: crashFlash 0.5s ease-out;
        }

        @keyframes crashFlash {
            0% {
                background: rgba(255, 200, 100, 0.9);
            }

            100% {
                background: radial-gradient(ellipse at center, rgba(255, 100, 0, 0.4) 0%, rgba(255, 50, 0, 0.2) 30%, rgba(0, 0, 0, 0.8) 100%);
            }
        }

        /* Smoke/fire border effect */
        #crashOverlay::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            box-shadow: inset 0 0 150px rgba(255, 80, 0, 0.6), inset 0 0 300px rgba(0, 0, 0, 0.8);
            animation: fireFlicker 0.2s infinite;
        }

        @keyframes fireFlicker {

            0%,
            100% {
                opacity: 1;
            }

            50% {
                opacity: 0.7;
            }
        }

        .shake {
            animation: screenShake 0.08s infinite;
        }

        @keyframes screenShake {

            0%,
            100% {
                transform: translate(0, 0);
            }

            20% {
                transform: translate(-8px, 6px);
            }

            40% {
                transform: translate(6px, -8px);
            }

            60% {
                transform: translate(-6px, -4px);
            }

            80% {
                transform: translate(4px, 6px);
            }
        }

        .violent-shake {
            animation: violentShake 0.05s infinite;
        }

        @keyframes violentShake {

            0%,
            100% {
                transform: translate(0, 0) rotate(0deg);
            }

            25% {
                transform: translate(-12px, 10px) rotate(-1deg);
            }

            50% {
                transform: translate(10px, -12px) rotate(1deg);
            }

            75% {
                transform: translate(-8px, -6px) rotate(-0.5deg);
            }
        }

        #confirmFlash {
            background: #fff;
            opacity: 0;
            pointer-events: none;
            z-index: 2000;
            transition: opacity 0.1s;
        }

        #confirmFlash.active {
            opacity: 0.8;
        }

        /* ========== PAUSE BUTTON ========== */
        #pauseBtn {
            position: fixed;
            top: 20px;
            left: 20px;
            width: 48px;
            height: 48px;
            background: rgba(40, 0, 0, 0.8);
            border: 2px solid #ff3333;
            clip-path: polygon(10px 0, 100% 0, 100% calc(100% - 10px), calc(100% - 10px) 100%, 0 100%, 0 10px);
            cursor: pointer;
            z-index: 2000;
            /* Ensure strictly above everything */
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 0 15px rgba(255, 50, 50, 0.4);
            transition: all 0.2s ease;
        }

        #pauseBtn:hover {
            box-shadow: 0 0 25px rgba(255, 50, 50, 0.8);
            background: rgba(80, 0, 0, 0.9);
            transform: scale(1.05);
        }

        #pauseBtn::before,
        #pauseBtn::after {
            content: '';
            width: 6px;
            height: 18px;
            background: #ff4444;
            box-shadow: 0 0 10px #ff4444;
            transform: skewX(-15deg);
        }

        #pauseBtn::before {
            margin-right: 4px;
        }

        #pauseBtn::after {
            margin-left: 4px;
        }

        #pauseBtn.playing::before {
            width: 0;
            height: 0;
            background: transparent;
            border-style: solid;
            border-width: 9px 0 9px 16px;
            border-color: transparent transparent transparent #ff4444;
            box-shadow: none;
            margin: 0;
            transform: none;
            margin-left: 4px;
        }

        #pauseBtn.playing::after {
            display: none;
        }

        /* ========== PAUSE OVERLAY - COCKPIT STYLE ========== */
        #pauseOverlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 10, 15, 0.92);
            display: none;
            z-index: 1500;
            align-items: center;
            justify-content: center;
            backdrop-filter: blur(8px);
        }

        #pauseOverlay.active {
            display: flex;
        }

        .cockpit-frame {
            position: relative;
            width: 90%;
            max-width: 1000px;
            height: 85%;
            border: 2px solid rgba(0, 255, 170, 0.5);
            background: rgba(0, 20, 30, 0.8);
            border-radius: 20px;
            box-shadow: 0 0 50px rgba(0, 200, 255, 0.2), inset 0 0 100px rgba(0, 20, 30, 0.8);
            display: flex;
            flex-direction: column;
            overflow: hidden;
        }

        /* Decorative corners */
        .cockpit-frame::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            background:
                linear-gradient(135deg, #00ffaa 20px, transparent 0) top left,
                linear-gradient(-135deg, #00ffaa 20px, transparent 0) top right,
                linear-gradient(45deg, #00ffaa 20px, transparent 0) bottom left,
                linear-gradient(-45deg, #00ffaa 20px, transparent 0) bottom right;
            background-size: 50% 50%;
            background-repeat: no-repeat;
            opacity: 0.6;
        }

        .cockpit-header {
            padding: 30px;
            text-align: center;
            border-bottom: 1px solid rgba(0, 255, 170, 0.3);
            background: linear-gradient(90deg, transparent, rgba(0, 255, 170, 0.1), transparent);
        }

        .cockpit-header h1 {
            font-size: 32px;
            color: #00ffaa;
            text-transform: uppercase;
            letter-spacing: 10px;
            margin-bottom: 10px;
            text-shadow: 0 0 20px rgba(0, 255, 170, 0.8);
        }

        .cockpit-header h2 {
            font-size: 16px;
            color: #88ccff;
            letter-spacing: 4px;
            font-weight: normal;
        }

        .cockpit-body {
            flex: 1;
            padding: 30px;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        /* Scrollbar aesthetics */
        .cockpit-body::-webkit-scrollbar {
            width: 8px;
        }

        .cockpit-body::-webkit-scrollbar-track {
            background: rgba(0, 20, 30, 0.5);
        }

        .cockpit-body::-webkit-scrollbar-thumb {
            background: #005544;
            border-radius: 4px;
        }

        .manual-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }

        .manual-section {
            background: rgba(0, 30, 40, 0.6);
            border: 1px solid rgba(0, 255, 170, 0.2);
            border-left: 4px solid #00ffaa;
            padding: 20px;
            position: relative;
        }

        .manual-section::after {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 10px;
            height: 10px;
            border-top: 1px solid #00ffaa;
            border-right: 1px solid #00ffaa;
        }

        .manual-section h3 {
            color: #fff;
            font-size: 14px;
            letter-spacing: 4px;
            margin-bottom: 20px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            padding-bottom: 10px;
            display: flex;
            align-items: center;
        }

        .manual-section h3::before {
            content: '►';
            margin-right: 10px;
            color: #00ffaa;
            font-size: 10px;
        }

        .control-row {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 12px;
            border-bottom: 1px dotted rgba(0, 255, 170, 0.2);
            padding-bottom: 5px;
        }

        .control-row:last-child {
            border-bottom: none;
        }

        .key-bind {
            font-family: monospace;
            color: #00ffaa;
            background: rgba(0, 255, 170, 0.1);
            padding: 2px 8px;
            border: 1px solid rgba(0, 255, 170, 0.4);
            border-radius: 3px;
            font-size: 12px;
            min-width: 30px;
            text-align: center;
        }

        .control-action {
            color: #b0d0e0;
            font-size: 12px;
            letter-spacing: 1px;
            text-align: right;
        }

        .cockpit-footer {
            padding: 20px;
            text-align: center;
            border-top: 1px solid rgba(0, 255, 170, 0.3);
            background: rgba(0, 10, 15, 0.5);
        }

        .resume-btn {
            background: linear-gradient(90deg, rgba(0, 50, 40, 0.8), rgba(0, 100, 80, 0.8));
            border: 1px solid #00ffaa;
            color: #00ffaa;
            padding: 15px 50px;
            font-family: 'Orbitron', sans-serif;
            font-size: 16px;
            letter-spacing: 6px;
            cursor: pointer;
            transition: all 0.3s;
            text-transform: uppercase;
            box-shadow: 0 0 20px rgba(0, 255, 170, 0.2);
        }

        .resume-btn:hover {
            background: #00ffaa;
            color: #000;
            box-shadow: 0 0 40px rgba(0, 255, 170, 0.6);
        }

        /* ========== COCKPIT GAUGES ========== */
        .cockpit-gauges {
            display: flex;
            flex-direction: row;
            gap: 20px;
            margin-bottom: 20px;
        }

        .dial-container {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            background: radial-gradient(circle at center, rgba(0, 30, 20, 0.9), rgba(0, 10, 5, 0.8));
            border: 2px solid rgba(255, 255, 255, 0.1);
            position: relative;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.5), inset 0 0 30px rgba(0, 0, 0, 0.8);
            backdrop-filter: blur(4px);
            transition: border-color 0.3s, box-shadow 0.3s;
        }

        .dial-glass {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            border-radius: 50%;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.1) 0%, transparent 40%, rgba(255, 255, 255, 0.05) 100%);
            box-shadow: inset 0 0 10px rgba(255, 255, 255, 0.05);
            pointer-events: none;
            z-index: 5;
        }

        .dial-ticks {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border-radius: 50%;
        }

        .tick {
            position: absolute;
            left: 50%;
            top: 0;
            width: 2px;
            height: 100%;
            transform: translateX(-50%);
            pointer-events: none;
        }

        .tick::before {
            content: '';
            position: absolute;
            top: 5px;
            left: 0;
            width: 100%;
            height: 8px;
            background: rgba(255, 255, 255, 0.4);
        }

        /* Tick rotations */
        .t-0 {
            transform: translateX(-50%) rotate(0deg);
        }

        .t-45 {
            transform: translateX(-50%) rotate(45deg);
        }

        .t-90 {
            transform: translateX(-50%) rotate(90deg);
        }

        .t-135 {
            transform: translateX(-50%) rotate(135deg);
        }

        .t-180 {
            transform: translateX(-50%) rotate(180deg);
        }

        .t-225 {
            transform: translateX(-50%) rotate(225deg);
        }

        .t-270 {
            transform: translateX(-50%) rotate(270deg);
        }

        .t-315 {
            transform: translateX(-50%) rotate(315deg);
        }

        .dial-label {
            position: absolute;
            top: 25%;
            left: 0;
            width: 100%;
            text-align: center;
            font-size: 10px;
            color: rgba(255, 255, 255, 0.5);
            letter-spacing: 2px;
            font-weight: bold;
            z-index: 2;
        }

        .dial-readout {
            position: absolute;
            bottom: 20%;
            left: 0;
            width: 100%;
            text-align: center;
            font-size: 18px;
            color: #fff;
            font-family: 'Orbitron', monospace;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
            z-index: 2;
        }

        .dial-center {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 12px;
            height: 12px;
            background: #333;
            border: 2px solid #555;
            border-radius: 50%;
            transform: translate(-50%, -50%);
            z-index: 4;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.5);
        }

        .dial-needle {
            position: absolute;
            bottom: 50%;
            left: 50%;
            width: 4px;
            height: 42%;
            background: #fff;
            transform-origin: bottom center;
            transform: translateX(-50%) rotate(0deg);
            z-index: 3;
            /* Pointed tip */
            clip-path: polygon(50% 0%, 100% 100%, 0% 100%);
            box-shadow: 0 0 5px rgba(255, 255, 255, 0.5);
            transition: transform 0.05s linear;
        }

        .dial-needle.blur-active {
            filter: blur(1.5px);
            opacity: 0.9;
        }

        /* Altitude specific states */
        .alt-danger-high {
            border-color: #ff2200 !important;
            box-shadow: 0 0 30px #ff2200, inset 0 0 40px rgba(100, 0, 0, 0.5) !important;
            animation: altPulse 0.5s infinite;
        }

        .alt-danger-high .dial-readout {
            color: #ff2200;
            text-shadow: 0 0 15px #ff0000;
        }

        .alt-danger-high .dial-needle {
            background: #ff2200;
            box-shadow: 0 0 10px #ff0000;
        }

        .alt-danger-low {
            border-color: #ff0000 !important;
            box-shadow: 0 0 20px #ff0000 !important;
            background: radial-gradient(circle at center, rgba(50, 0, 0, 0.9), rgba(20, 0, 0, 0.8));
        }

        .alt-danger-low .dial-readout {
            color: #ff4444;
        }

        .alt-danger-low .dial-needle {
            background: #ff4444;
        }

        .alt-warning-text {
            position: absolute;
            top: 15%;
            right: 28%;
            color: #ff2200;
            font-size: 16px;
            display: none;
            text-shadow: 0 0 10px #ff0000;
            animation: blink 0.2s infinite;
        }

        @keyframes altPulse {
            0% {
                box-shadow: 0 0 20px #ff2200, inset 0 0 20px rgba(100, 0, 0, 0.5);
            }

            50% {
                box-shadow: 0 0 50px #ff2200, inset 0 0 50px rgba(255, 0, 0, 0.3);
            }

            100% {
                box-shadow: 0 0 20px #ff2200, inset 0 0 20px rgba(100, 0, 0, 0.5);
            }
        }

        /* ANIMATIONS */
        @keyframes gradientBG {
            0% {
                background-position: 0% 50%;
            }

            50% {
                background-position: 100% 50%;
            }

            100% {
                background-position: 0% 50%;
            }
        }

        @keyframes floatClouds {
            0% {
                transform: translateX(-30px);
            }

            100% {
                transform: translateX(30px);
            }
        }

        @keyframes titleReveal {
            0% {
                opacity: 0;
                transform: scale(0.8) translateY(20px);
                filter: blur(10px);
            }

            100% {
                opacity: 1;
                transform: scale(1) translateY(0);
                filter: blur(0);
            }
        }

        @keyframes glitchText {

            0%,
            100% {
                transform: translate(0);
            }

            92% {
                transform: translate(0);
            }

            94% {
                transform: translate(-2px, 2px);
            }

            96% {
                transform: translate(2px, -2px);
            }

            98% {
                transform: translate(0);
            }
        }

        @keyframes btnPulse {
            0% {
                box-shadow: 0 0 20px rgba(0, 255, 170, 0.3);
            }

            50% {
                box-shadow: 0 0 40px rgba(0, 255, 170, 0.6), inset 0 0 10px rgba(0, 255, 170, 0.2);
            }

            100% {
                box-shadow: 0 0 20px rgba(0, 255, 170, 0.3);
            }
        }

        @keyframes blinkHint {

            0%,
            100% {
                opacity: 1;
            }

            50% {
                opacity: 0.3;
            }
        }

        @keyframes bossPulse {

            0%,
            100% {
                transform: scale(1);
                opacity: 1;
            }

            50% {
                transform: scale(1.3);
                opacity: 0.7;
            }
        }

        /* Dynamic Speed Lines Colors */
        .speed-line {
            background: linear-gradient(to bottom, transparent, rgba(0, 255, 170, 0.8));
            position: absolute;
            /* Ensure it works if not defined elsewhere */
        }

        body.hellbat-mode .speed-line {
            background: linear-gradient(to bottom, transparent, rgba(255, 51, 0, 0.9)) !important;
            box-shadow: 0 0 10px rgba(255, 50, 0, 0.5);
        }

        body.stealth-mode .speed-line {
            background: linear-gradient(to bottom, transparent, rgba(85, 0, 255, 0.6)) !important;
            opacity: 0.4 !important;
            /* Stealthier lines */
        }
    </style>
</head>

<body>
    <!-- PAUSE BUTTON - Always visible -->
    <div id="pauseBtn" title="Pause (P)"></div>

    <!-- PAUSE OVERLAY - Flight Manual -->
    <!-- PAUSE OVERLAY - Flight Manual -->
    <div id="pauseOverlay">
        <div class="cockpit-frame">
            <div class="cockpit-header">
                <h1>Flight Systems Paused</h1>
                <h2>Pilot Manual & Controls</h2>
            </div>
            <div class="cockpit-body">
                <div class="manual-section">
                    <h3>Flight Control</h3>
                    <div class="control-row"><span class="key-bind">W</span><span class="control-action">Pitch
                            Down</span></div>
                    <div class="control-row"><span class="key-bind">S</span><span class="control-action">Pitch Up</span>
                    </div>
                    <div class="control-row"><span class="key-bind">A</span><span class="control-action">Bank
                            Left</span></div>
                    <div class="control-row"><span class="key-bind">D</span><span class="control-action">Bank
                            Right</span></div>
                    <div class="control-row"><span class="key-bind">Q / E</span><span class="control-action">Yaw
                            Control</span></div>
                </div>

                <div class="manual-grid">
                    <div class="manual-section">
                        <h3>Combat Systems</h3>
                        <div class="control-row"><span class="key-bind">SPACE</span><span class="control-action">Vulcan
                                Cannon</span></div>
                        <div class="control-row"><span class="key-bind">LMB</span><span class="control-action">Fire
                                Missile</span></div>
                        <div class="control-row"><span class="key-bind">RMB</span><span class="control-action">Target
                                Lock / Slow-Mo</span></div>
                    </div>

                    <div class="manual-section">
                        <h3>Special Abilities</h3>
                        <div class="control-row"><span class="key-bind">SHIFT</span><span
                                class="control-action">Afterburner</span></div>
                        <div class="control-row"><span class="key-bind">C</span><span class="control-action">Evasive
                                Dash</span></div>
                        <div class="control-row"><span class="key-bind">G</span><span class="control-action">EMP
                                Shockwave</span></div>
                    </div>
                </div>

                <div class="manual-section">
                    <h3>Tactical Modes [X]</h3>
                    <div class="control-row">
                        <span class="key-bind" style="color:#fff; border-color:#fff;">NORMAL</span>
                        <span class="control-action">Balanced handling and weapons. Standard operation.</span>
                    </div>
                    <div class="control-row">
                        <span class="key-bind" style="color:#ff4444; border-color:#ff4444;">HELLBAT</span>
                        <span class="control-action">Max firepower. Death Ray [Hold F]. High heat signature.</span>
                    </div>
                    <div class="control-row">
                        <span class="key-bind" style="color:#00ccff; border-color:#00ccff;">STEALTH</span>
                        <span class="control-action">Forcefield active. Low visibility. Rebound terrain.</span>
                    </div>
                </div>
            </div>
            <div class="cockpit-footer">
                <button class="resume-btn" id="resumeBtn">RESUME MISSION</button>
            </div>
        </div>
    </div>

    <div id="startScreen">
        <div id="menuClouds"></div>
        <div id="menuMountains">
            <div class="mountain-layer mountain-far"></div>
            <div class="mountain-layer mountain-mid"></div>
            <div class="mountain-layer mountain-near"></div>
        </div>
        <div id="titleContainer">
            <h1 id="mainTitle">JETBLADE</h1>
            <h2 id="subtitleText">DOMINION 2.0</h2>
            <div id="versionText">CINEMATIC EDITION</div>
        </div>
        <button id="startBtn">ENGAGE SYSTEMS</button>
        <div id="pauseHint">Press P for Controls</div>
    </div>

    <div id="crashOverlay"></div>
    <div id="confirmFlash" class="overlay"></div>

    <div id="gameOver">
        <div id="skullSymbol">💀</div>
        <h1>AIRCRAFT DESTROYED</h1>
        <p id="crashCause">TERRAIN COLLISION</p>
        <p id="finalScore">SCORE: 0</p>
        <p id="finalKills">KILLS: 0</p>
        <button id="restartBtn">⟳ RESPAWN</button>
    </div>

    <div id="gameContainer">
        <div id="atmosphericGlow" class="overlay"></div>
        <div id="hellbatTint" class="overlay"></div>
        <div id="stealthTint" class="overlay"></div>
        <div id="motionBlur" class="overlay"></div>
        <div id="forcefieldOverlay" class="overlay"></div>
        <div id="invincibilityFlash" class="overlay"></div>
        <div id="domainEdgeGlow" class="overlay"></div>

        <!-- ========== CREATIVE UPGRADES ========== -->
        <!-- Kill Feed -->
        <div id="killFeed"></div>

        <!-- Combo Counter -->
        <div id="comboContainer">
            <div id="comboCount">0</div>
            <div id="comboLabel">COMBO</div>
            <div id="comboMultiplier">×1</div>
        </div>

        <!-- Kill Streak Banner -->
        <div id="streakBanner">
            <div id="streakText">KILLING SPREE!</div>
            <div id="streakSubtext">+10 HP RESTORED</div>
        </div>

        <!-- Damage Direction Indicator -->
        <div id="damageIndicator">
            <div class="damage-arc damage-arc-top"></div>
            <div class="damage-arc damage-arc-bottom"></div>
            <div class="damage-arc damage-arc-left"></div>
            <div class="damage-arc damage-arc-right"></div>
            <div class="damage-arc damage-arc-rear"></div>
        </div>

        <!-- Speed Lines -->
        <div id="speedLines">
            <div id="speedLinesInner"></div>
        </div>

        <!-- Power-up Indicators -->
        <div id="healthBoostIndicator" class="powerup-indicator">🔋 +25 HP</div>
        <div id="rapidFireIndicator" class="powerup-indicator">🔥 RAPID FIRE</div>

        <!-- Boss Health Bar -->
        <div id="bossHealthContainer">
            <div id="bossName">★ ACE COMMANDER ★</div>
            <div id="bossHealthBar">
                <div id="bossHealthFill"></div>
            </div>
            <div id="bossHealthText">500 / 500</div>
        </div>

        <!-- Overdrive Overlay -->
        <div id="overdriveOverlay" class="overlay"></div>

        <div id="hud">
            <div id="leftPanel">
                <div id="radarContainer">
                    <div class="compass-dir compass-n">N</div>
                    <div class="compass-dir compass-s">S</div>
                    <div class="compass-dir compass-e">E</div>
                    <div class="compass-dir compass-w">W</div>
                    <div class="radar-ring" style="width: 50px; height: 50px;"></div>
                    <div class="radar-ring" style="width: 100px; height: 100px;"></div>
                    <div class="radar-ring" style="width: 140px; height: 140px;"></div>
                    <!-- EPIC PLAYER RADAR INDICATOR SYSTEM -->
                    <div id="radarPlayerSystem">
                        <!-- Outer rotating tech ring -->
                        <div id="radarOuterRing"></div>
                        <!-- Inner counter-rotating ring -->
                        <div id="radarInnerRing"></div>
                        <!-- Core player triangle -->
                        <div id="radarCenter"></div>
                        <!-- Triangle inner glow -->
                        <div id="radarCenterCore"></div>
                        <!-- Speed indicator arcs -->
                        <div id="radarSpeedArcLeft"></div>
                        <div id="radarSpeedArcRight"></div>
                        <!-- Boost thrust trails -->
                        <div id="radarBoostTrailLeft"></div>
                        <div id="radarBoostTrailRight"></div>
                        <!-- Lock-on indicator -->
                        <div id="radarLockIndicator"></div>
                    </div>
                    <!-- Detection ping (separate for proper layering) -->
                    <div id="radarPing"></div>
                    <div id="radarSweep"></div>
                    <div id="radarBlips"></div>
                </div>
                <div id="radarLabel">TACTICAL RADAR</div>
            </div>

            <div id="rightPanel">
                <!-- Dual Circular Cockpit Gauges -->
                <div class="cockpit-gauges">
                    <!-- Speed Dial -->
                    <div class="dial-container" id="speedDial">
                        <div class="dial-glass"></div>
                        <div class="dial-ticks">
                            <div class="tick major t-0"></div>
                            <div class="tick major t-45"></div>
                            <div class="tick major t-90"></div>
                            <div class="tick major t-135"></div>
                            <div class="tick major t-180"></div>
                            <div class="tick major t-225"></div>
                            <div class="tick major t-270"></div>
                            <div class="tick major t-315"></div>
                        </div>
                        <div class="dial-label">SPD</div>
                        <div class="dial-readout" id="dialSpeedReadout">0</div>
                        <div class="dial-center"></div>
                        <div class="dial-needle" id="dialSpeedNeedle"></div>
                    </div>

                    <!-- Altitude Dial -->
                    <div class="dial-container" id="altDial">
                        <div class="dial-glass"></div>
                        <div class="dial-ticks">
                            <!-- Major ticks -->
                            <div class="tick major t-0"></div>
                            <div class="tick major t-45"></div>
                            <div class="tick major t-90"></div>
                            <div class="tick major t-135"></div>
                            <div class="tick major t-180"></div>
                            <div class="tick major t-225"></div>
                            <div class="tick major t-270"></div>
                            <div class="tick major t-315"></div>
                        </div>
                        <div class="dial-label">ALT</div>
                        <div class="dial-readout" id="dialAltReadout">0</div>
                        <div class="dial-center"></div>
                        <div class="dial-needle" id="dialAltNeedle"></div>
                        <div class="alt-warning-text" id="altWarning">⚠</div>
                    </div>
                </div>

                <!-- Legacy Shim -->
                <div style="display:none">
                    <div id="speedValue"></div>
                    <div id="speedFill"></div>
                    <div id="altValue"></div>
                    <div id="altFill"></div>
                </div>
            </div>

            <div id="topHud">
                <div class="hud-stat">
                    <div class="hud-stat-label">SCORE</div>
                    <div class="hud-stat-value" id="score">0</div>
                </div>
                <div class="hud-stat">
                    <div class="hud-stat-label">KILLS</div>
                    <div class="hud-stat-value" id="kills">0</div>
                </div>
            </div>

            <div id="modeIndicator" class="normal">NORMAL</div>

            <div id="crosshair">
                <div class="crosshair-circle"></div>
            </div>

            <!-- Holographic Aim Lens -->
            <div id="aimLens">
                <div class="aim-lens-outer"></div>
                <div class="aim-lens-inner"></div>
                <div class="aim-segment" style="--start-angle: 0deg;"></div>
                <div class="aim-segment" style="--start-angle: 90deg;"></div>
                <div class="aim-segment" style="--start-angle: 180deg;"></div>
                <div class="aim-segment" style="--start-angle: 270deg;"></div>
                <svg class="lock-progress" viewBox="0 0 80 80">
                    <circle class="lock-progress-bg" cx="40" cy="40" r="38" />
                    <circle class="lock-progress-fill" cx="40" cy="40" r="38" />
                </svg>
                <div class="aim-lens-crosshair h"></div>
                <div class="aim-lens-crosshair v"></div>
                <div class="aim-lens-center"></div>
            </div>
            <div id="lockedIndicator">◆ LOCKED ◆</div>
            <div id="slowMoOverlay"></div>
            <div id="targetBox"></div>

            <!-- NEW HUD SYSTEM -->
            <!-- Ability Dials -->
            <div class="hud-abilities-container">
                <!-- Hellbat Death Ray [F] -->
                <div class="hud-dial" id="dial-hellbat">
                    <svg class="dial-svg" viewBox="0 0 40 40">
                        <circle class="dial-bg" cx="20" cy="20" r="16"></circle>
                        <circle class="dial-fg" id="dial-hellbat-fill" cx="20" cy="20" r="16"></circle>
                    </svg>
                    <div class="dial-icon"></div>
                </div>

                <!-- Forcefield -->
                <div class="hud-dial" id="dial-forcefield">
                    <svg class="dial-svg" viewBox="0 0 40 40">
                        <circle class="dial-bg" cx="20" cy="20" r="16"></circle>
                        <circle class="dial-fg" id="dial-forcefield-fill" cx="20" cy="20" r="16"></circle>
                    </svg>
                    <div class="dial-icon"></div>
                </div>

                <!-- Shockwave [G] -->
                <div class="hud-dial" id="dial-shockwave">
                    <svg class="dial-svg" viewBox="0 0 40 40">
                        <circle class="dial-bg" cx="20" cy="20" r="16"></circle>
                        <circle class="dial-fg" id="dial-shockwave-fill" cx="20" cy="20" r="16"></circle>
                    </svg>
                    <div class="dial-icon"></div>
                </div>
            </div>

            <!-- Horizontal HP Bar -->
            <div class="hud-hp-container">
                <div class="hud-hp-fill" id="hud-hp-fill"></div>
            </div>

            <!-- Bank/Roll Indicator with Gyro Status -->
            <div id="bankIndicator">
                <div id="bankArc"></div>
                <div class="bank-mark" style="left: 50%; transform: translateX(-50%) rotate(-45deg);"></div>
                <div class="bank-mark" style="left: 50%; transform: translateX(-50%) rotate(-30deg);"></div>
                <div class="bank-mark" style="left: 50%; transform: translateX(-50%) rotate(-15deg);"></div>
                <div class="bank-mark"
                    style="left: 50%; transform: translateX(-50%) rotate(0deg); height: 12px; background: #00ffaa;">
                </div>
                <div class="bank-mark" style="left: 50%; transform: translateX(-50%) rotate(15deg);"></div>
                <div class="bank-mark" style="left: 50%; transform: translateX(-50%) rotate(30deg);"></div>
                <div class="bank-mark" style="left: 50%; transform: translateX(-50%) rotate(45deg);"></div>
                <div id="bankNeedle"></div>
                <div id="bankCenter"></div>
                <div id="gyroStatus">GYRO STANDBY</div>
            </div>

            <div id="missileInfo">
                <div class="label">MISSILES</div>
                <div class="value" id="missileCount">∞</div>
            </div>

            <!-- Controls removed as per user request -->
            <div id="controls" style="display: none;"></div>

            <div id="warning">⚠ INCOMING THREAT ⚠</div>
            <div id="domainIndicator">FLIGHT DOMAIN: SAFE</div>
            <div id="returnHint">R - RETURN TO BASE</div>

            <div id="domainWarning">
                <div id="domainWarningText">⚠ LEAVING COMBAT ZONE ⚠</div>
                <div id="domainCountdown">3</div>
            </div>
        </div>
    </div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <script>
        // ==================== CINEMATIC AUDIO SYSTEM ====================
        const AudioContext = window.AudioContext || window.webkitAudioContext;
        let audioCtx = null;
        let engineOsc = null;
        let engineGain = null;
        let engineFilter = null;
        let isEngineRunning = false;

        // Wind system nodes
        let windSource = null, windGain = null, windFilter = null;
        let isWindRunning = false;

        // Boost audio nodes
        let boostWindSource = null, boostWindGain = null;
        let isBoostWindRunning = false;

        // Environmental audio
        let terrainRumbleSource = null, terrainRumbleGain = null;
        let cloudMuffleGain = null;

        // Tracking sound interval
        let trackingTickInterval = null;
        let lastTrackingTick = 0;

        // Audio volume multipliers per mode
        const modeAudioSettings = {
            0: { engineVol: 1.0, weaponVol: 1.0, windVol: 1.0, bassPunch: 1.0 },  // Normal
            1: { engineVol: 1.3, weaponVol: 1.2, windVol: 0.9, bassPunch: 1.5 },  // Hellbat - aggressive
            2: { engineVol: 0.4, weaponVol: 0.35, windVol: 0.5, bassPunch: 0.6 }  // Stealth - muted
        };

        function initAudio() {
            if (audioCtx) return;
            audioCtx = new AudioContext();
        }

        // Create stereo panner for spatial audio
        function createStereoPanner(pan = 0) {
            if (!audioCtx) initAudio();
            const panner = audioCtx.createStereoPanner();
            panner.pan.value = Math.max(-1, Math.min(1, pan));
            return panner;
        }

        // Basic sound with optional stereo pan
        function playSound(freq, type, duration, volume = 0.15, pan = 0) {
            if (!audioCtx) initAudio();
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();
            const panner = createStereoPanner(pan);

            osc.connect(gain);
            gain.connect(panner);
            panner.connect(audioCtx.destination);

            osc.frequency.value = freq;
            osc.type = type;
            gain.gain.setValueAtTime(volume, audioCtx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + duration);
            osc.start();
            osc.stop(audioCtx.currentTime + duration);
        }

        // ========== WIND SOUND SYSTEM ==========
        function startWindSound() {
            if (!audioCtx) initAudio();
            if (isWindRunning) return;
            isWindRunning = true;

            // Create stereo wind noise
            const bufferSize = audioCtx.sampleRate * 2;
            const noiseBuffer = audioCtx.createBuffer(2, bufferSize, audioCtx.sampleRate);

            for (let channel = 0; channel < 2; channel++) {
                const data = noiseBuffer.getChannelData(channel);
                for (let i = 0; i < bufferSize; i++) {
                    data[i] = (Math.random() * 2 - 1) * 0.5;
                }
            }

            windSource = audioCtx.createBufferSource();
            windSource.buffer = noiseBuffer;
            windSource.loop = true;

            windFilter = audioCtx.createBiquadFilter();
            windFilter.type = 'bandpass';
            windFilter.frequency.value = 400;
            windFilter.Q.value = 0.5;

            windGain = audioCtx.createGain();
            windGain.gain.value = 0;

            windSource.connect(windFilter);
            windFilter.connect(windGain);
            windGain.connect(audioCtx.destination);

            windSource.start();
        }

        function updateWindSound(speed, maxSpeed, altitude, isBoosting) {
            if (!isWindRunning || !windGain) return;

            const speedRatio = speed / maxSpeed;
            const modeSettings = modeAudioSettings[currentMode];

            // Base wind intensity from speed
            let windIntensity = speedRatio * speedRatio * 0.08 * modeSettings.windVol;

            // Altitude affects wind character (higher = more wind)
            const altitudeFactor = Math.min(1, altitude / 800);
            windFilter.frequency.value = 300 + speedRatio * 600 + altitudeFactor * 200;

            // Boost dramatically increases wind
            if (isBoosting) {
                windIntensity *= 2.5;
                windFilter.frequency.value += 400;
            }

            windGain.gain.value = Math.min(0.15, windIntensity);
        }

        function stopWindSound() {
            if (!isWindRunning) return;
            isWindRunning = false;
            if (windSource) {
                windSource.stop();
                windSource = null;
            }
        }

        // ========== HELLBAT REACTOR ENGINE SYSTEM ==========
        // Deep pulsing reactor with metallic resonance and power surges
        let hellbatReactorOsc = null;
        let hellbatPulseOsc = null;
        let hellbatResonanceOsc = null;
        let hellbatReactorGain = null;
        let isHellbatReactorRunning = false;
        let hellbatPulseInterval = null;

        function startHellbatReactor() {
            if (!audioCtx) initAudio();
            if (isHellbatReactorRunning) return;
            isHellbatReactorRunning = true;

            // === LAYER 1: ULTRA-DEEP SUB-BASS (15-22Hz gut-punching bass) ===
            const ultraSubOsc = audioCtx.createOscillator();
            const ultraSubGain = audioCtx.createGain();
            const ultraSubFilter = audioCtx.createBiquadFilter();

            ultraSubOsc.type = 'sine';
            ultraSubOsc.frequency.value = 18; // Earthquake-level bass
            ultraSubFilter.type = 'lowpass';
            ultraSubFilter.frequency.value = 40;
            ultraSubFilter.Q.value = 1;

            ultraSubOsc.connect(ultraSubFilter);
            ultraSubFilter.connect(ultraSubGain);
            ultraSubGain.connect(audioCtx.destination);
            ultraSubGain.gain.value = 0.12;

            ultraSubOsc.start();

            // === LAYER 2: MAIN REACTOR BASS (25-45Hz sawtooth drone) ===
            hellbatReactorOsc = audioCtx.createOscillator();
            const reactorGain = audioCtx.createGain();
            const reactorFilter = audioCtx.createBiquadFilter();

            hellbatReactorOsc.type = 'sawtooth';
            hellbatReactorOsc.frequency.value = 28;
            reactorFilter.type = 'lowpass';
            reactorFilter.frequency.value = 90;
            reactorFilter.Q.value = 3;

            hellbatReactorOsc.connect(reactorFilter);
            reactorFilter.connect(reactorGain);
            reactorGain.connect(audioCtx.destination);
            reactorGain.gain.value = 0.1;
            hellbatReactorGain = reactorGain;

            hellbatReactorOsc.start();

            // === LAYER 3: PULSING RHYTHM (aggressive power surges) ===
            hellbatPulseOsc = audioCtx.createOscillator();
            const pulseGain = audioCtx.createGain();

            hellbatPulseOsc.type = 'triangle';
            hellbatPulseOsc.frequency.value = 32;

            hellbatPulseOsc.connect(pulseGain);
            pulseGain.connect(audioCtx.destination);

            // Create aggressive pulsing effect with LFO
            const lfo = audioCtx.createOscillator();
            const lfoGain = audioCtx.createGain();
            lfo.type = 'sine';
            lfo.frequency.value = 3.0; // Faster pulse rate for aggression
            lfoGain.gain.value = 0.05;
            lfo.connect(lfoGain);
            lfoGain.connect(pulseGain.gain);
            pulseGain.gain.value = 0.06;
            lfo.start();
            hellbatPulseOsc.lfo = lfo;

            hellbatPulseOsc.start();

            // === LAYER 4: METALLIC RESONANCE (industrial machine hum) ===
            hellbatResonanceOsc = audioCtx.createOscillator();
            const resonanceGain = audioCtx.createGain();
            const resonanceFilter = audioCtx.createBiquadFilter();

            hellbatResonanceOsc.type = 'square';
            hellbatResonanceOsc.frequency.value = 55;
            resonanceFilter.type = 'bandpass';
            resonanceFilter.frequency.value = 110;
            resonanceFilter.Q.value = 12; // Sharper resonance

            hellbatResonanceOsc.connect(resonanceFilter);
            resonanceFilter.connect(resonanceGain);
            resonanceGain.connect(audioCtx.destination);
            resonanceGain.gain.value = 0.025;

            hellbatResonanceOsc.start();

            // === LAYER 5: TURBINE WHINE (REMOVED) ===
            // User requested removal of "mosquito buzzing" sound
            const turbineOsc = null;
            const turbineGain = null;
            const turbineLfo = null;

            // === LAYER 6: HEAT DISTORTION (futuristic reactor heat signature) ===
            const heatBufferSize = audioCtx.sampleRate * 2;
            const heatBuffer = audioCtx.createBuffer(1, heatBufferSize, audioCtx.sampleRate);
            const heatData = heatBuffer.getChannelData(0);
            for (let i = 0; i < heatBufferSize; i++) {
                // Crackling noise with gaps for organic heat shimmer
                heatData[i] = (Math.random() * 2 - 1) * (Math.random() > 0.7 ? 0.3 : 0.05);
            }
            const heatSource = audioCtx.createBufferSource();
            heatSource.buffer = heatBuffer;
            heatSource.loop = true;

            const heatFilter = audioCtx.createBiquadFilter();
            heatFilter.type = 'bandpass';
            heatFilter.frequency.value = 180;
            heatFilter.Q.value = 2;

            const heatGain = audioCtx.createGain();
            heatGain.gain.value = 0.02;

            heatSource.connect(heatFilter);
            heatFilter.connect(heatGain);
            heatGain.connect(audioCtx.destination);

            heatSource.start();

            // Store all references for cleanup and updates
            hellbatReactorOsc.ultraSubOsc = ultraSubOsc;
            hellbatReactorOsc.ultraSubGain = ultraSubGain;
            hellbatReactorOsc.pulseOsc = hellbatPulseOsc;
            hellbatReactorOsc.resonanceOsc = hellbatResonanceOsc;
            hellbatReactorOsc.pulseGain = pulseGain;
            hellbatReactorOsc.resonanceGain = resonanceGain;
            hellbatReactorOsc.turbineOsc = turbineOsc;
            hellbatReactorOsc.turbineGain = turbineGain;
            hellbatReactorOsc.turbineLfo = turbineLfo;
            hellbatReactorOsc.heatSource = heatSource;
            hellbatReactorOsc.heatGain = heatGain;

            // === PERIODIC POWER SURGE SOUNDS (more frequent) ===
            hellbatPulseInterval = setInterval(() => {
                if (!isHellbatReactorRunning || currentMode !== 1) return;
                playHellbatPowerSurge();
            }, 2000 + Math.random() * 1500); // More frequent surges
        }

        function updateHellbatReactor(speed, maxSpeed, isBoosting) {
            if (!isHellbatReactorRunning || !hellbatReactorOsc) return;

            const speedRatio = speed / maxSpeed;
            const intensity = 0.5 + speedRatio * 0.5;

            // === ULTRA-DEEP SUB-BASS: intensifies with speed ===
            if (hellbatReactorOsc.ultraSubOsc) {
                hellbatReactorOsc.ultraSubOsc.frequency.value = 16 + speedRatio * 6;
            }
            if (hellbatReactorOsc.ultraSubGain) {
                hellbatReactorOsc.ultraSubGain.gain.value = 0.08 + speedRatio * 0.08;
            }

            // === MAIN REACTOR BASS: deepens and intensifies with speed ===
            hellbatReactorOsc.frequency.value = 25 + speedRatio * 18;
            if (hellbatReactorGain) {
                hellbatReactorGain.gain.value = 0.08 + speedRatio * 0.1;
            }

            // === PULSE RHYTHM: faster with speed ===
            if (hellbatPulseOsc && hellbatPulseOsc.lfo) {
                hellbatPulseOsc.lfo.frequency.value = 2.5 + speedRatio * 4;
            }
            if (hellbatReactorOsc.pulseGain) {
                hellbatReactorOsc.pulseGain.gain.value = 0.05 + speedRatio * 0.04;
            }

            // === METALLIC RESONANCE: sharper with speed ===
            if (hellbatReactorOsc.resonanceGain) {
                hellbatReactorOsc.resonanceGain.gain.value = 0.02 + speedRatio * 0.03;
            }

            // === TURBINE WHINE: (REMOVED) ===

            // === HEAT DISTORTION: more intense with speed ===
            if (hellbatReactorOsc.heatGain) {
                hellbatReactorOsc.heatGain.gain.value = 0.015 + speedRatio * 0.025;
            }

            // === BOOST STATE: MASSIVE POWER SURGE ===
            if (isBoosting) {
                // Ultra sub-bass POUNDS
                if (hellbatReactorOsc.ultraSubOsc) {
                    hellbatReactorOsc.ultraSubOsc.frequency.value = 20 + speedRatio * 10;
                }
                if (hellbatReactorOsc.ultraSubGain) {
                    hellbatReactorOsc.ultraSubGain.gain.value = 0.18 + speedRatio * 0.12;
                }

                // Main reactor ROARS
                hellbatReactorOsc.frequency.value = 38 + speedRatio * 28;
                if (hellbatReactorGain) hellbatReactorGain.gain.value = 0.15 + speedRatio * 0.12;

                // Pulse goes AGGRESSIVE
                if (hellbatPulseOsc.lfo) hellbatPulseOsc.lfo.frequency.value = 6 + speedRatio * 5;

                // Turbine SCREAMS
                if (hellbatReactorOsc.turbineOsc) {
                    hellbatReactorOsc.turbineOsc.frequency.value = 500 + speedRatio * 350;
                }
                if (hellbatReactorOsc.turbineGain) {
                    hellbatReactorOsc.turbineGain.gain.value = 0.025 + speedRatio * 0.02;
                }

                // Heat distortion CRACKLING
                if (hellbatReactorOsc.heatGain) {
                    hellbatReactorOsc.heatGain.gain.value = 0.035 + speedRatio * 0.025;
                }
            }
        }

        function stopHellbatReactor() {
            if (!isHellbatReactorRunning) return;
            isHellbatReactorRunning = false;

            if (hellbatPulseInterval) {
                clearInterval(hellbatPulseInterval);
                hellbatPulseInterval = null;
            }

            if (hellbatReactorOsc) {
                try {
                    hellbatReactorOsc.stop();
                    if (hellbatReactorOsc.pulseOsc) hellbatReactorOsc.pulseOsc.stop();
                    if (hellbatReactorOsc.resonanceOsc) hellbatReactorOsc.resonanceOsc.stop();
                    if (hellbatPulseOsc && hellbatPulseOsc.lfo) hellbatPulseOsc.lfo.stop();
                    // Stop new layers
                    if (hellbatReactorOsc.ultraSubOsc) hellbatReactorOsc.ultraSubOsc.stop();
                    if (hellbatReactorOsc.turbineOsc) hellbatReactorOsc.turbineOsc.stop();
                    if (hellbatReactorOsc.turbineLfo) hellbatReactorOsc.turbineLfo.stop();
                    if (hellbatReactorOsc.heatSource) hellbatReactorOsc.heatSource.stop();
                } catch (e) { }
                hellbatReactorOsc = null;
                hellbatPulseOsc = null;
                hellbatResonanceOsc = null;
            }
        }

        function playHellbatPowerSurge() {
            if (!audioCtx) initAudio();

            // === DEEP POWER SURGE WHOMP (gut-punch bass) ===
            const surgeOsc = audioCtx.createOscillator();
            const surgeGain = audioCtx.createGain();
            const surgeFilter = audioCtx.createBiquadFilter();

            surgeOsc.type = 'sawtooth';
            surgeOsc.frequency.setValueAtTime(22, audioCtx.currentTime);
            surgeOsc.frequency.exponentialRampToValueAtTime(55, audioCtx.currentTime + 0.12);
            surgeOsc.frequency.exponentialRampToValueAtTime(18, audioCtx.currentTime + 0.5);

            surgeFilter.type = 'lowpass';
            surgeFilter.frequency.value = 80;
            surgeFilter.Q.value = 3;

            surgeOsc.connect(surgeFilter);
            surgeFilter.connect(surgeGain);
            surgeGain.connect(audioCtx.destination);

            surgeGain.gain.setValueAtTime(0.01, audioCtx.currentTime);
            surgeGain.gain.exponentialRampToValueAtTime(0.18, audioCtx.currentTime + 0.08);
            surgeGain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.6);

            surgeOsc.start();
            surgeOsc.stop(audioCtx.currentTime + 0.65);

            // === METAL STRESS GROAN (reactor straining under power) ===
            setTimeout(() => {
                const stressOsc = audioCtx.createOscillator();
                const stressGain = audioCtx.createGain();
                const stressFilter = audioCtx.createBiquadFilter();

                stressOsc.type = 'square';
                stressOsc.frequency.setValueAtTime(120 + Math.random() * 80, audioCtx.currentTime);
                stressOsc.frequency.exponentialRampToValueAtTime(50, audioCtx.currentTime + 0.15);

                stressFilter.type = 'bandpass';
                stressFilter.frequency.value = 100;
                stressFilter.Q.value = 5;

                stressOsc.connect(stressFilter);
                stressFilter.connect(stressGain);
                stressGain.connect(audioCtx.destination);

                stressGain.gain.setValueAtTime(0.04, audioCtx.currentTime);
                stressGain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.2);

                stressOsc.start();
                stressOsc.stop(audioCtx.currentTime + 0.22);
            }, 80);

            // === ELECTRICAL DISCHARGE CRACKLE ===
            setTimeout(() => {
                const crackleBuffer = audioCtx.createBuffer(1, audioCtx.sampleRate * 0.15, audioCtx.sampleRate);
                const crackleData = crackleBuffer.getChannelData(0);
                for (let i = 0; i < crackleData.length; i++) {
                    crackleData[i] = (Math.random() > 0.85 ? (Math.random() * 2 - 1) * 0.8 : 0) * Math.exp(-i / (audioCtx.sampleRate * 0.06));
                }
                const crackleSource = audioCtx.createBufferSource();
                crackleSource.buffer = crackleBuffer;

                const crackleGain = audioCtx.createGain();
                const crackleFilter = audioCtx.createBiquadFilter();
                crackleFilter.type = 'highpass';
                crackleFilter.frequency.value = 800;

                crackleSource.connect(crackleFilter);
                crackleFilter.connect(crackleGain);
                crackleGain.connect(audioCtx.destination);
                crackleGain.gain.value = 0.06;

                crackleSource.start();
            }, 50);

            // === METALLIC CREAK (armor plates adjusting) ===
            setTimeout(() => {
                const creakOsc = audioCtx.createOscillator();
                const creakGain = audioCtx.createGain();
                creakOsc.type = 'square';
                creakOsc.frequency.setValueAtTime(200 + Math.random() * 150, audioCtx.currentTime);
                creakOsc.frequency.exponentialRampToValueAtTime(70, audioCtx.currentTime + 0.12);
                creakOsc.connect(creakGain);
                creakGain.connect(audioCtx.destination);
                creakGain.gain.setValueAtTime(0.03, audioCtx.currentTime);
                creakGain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.15);
                creakOsc.start();
                creakOsc.stop(audioCtx.currentTime + 0.18);
            }, 150);
        }

        // ========== HELLBAT TRANSFORMATION SEQUENCE ==========
        // Epic mechanical transformation: energy charge → servos → armor plates → power up → bass drop VOOM
        function playHellbatTransformation() {
            if (!audioCtx) initAudio();

            const t = audioCtx.currentTime;

            // === PHASE 1: LOW ENERGY CHARGE RUMBLE (0-400ms) ===
            const chargeOsc = audioCtx.createOscillator();
            const chargeGain = audioCtx.createGain();
            const chargeFilter = audioCtx.createBiquadFilter();

            chargeOsc.type = 'sawtooth';
            chargeOsc.frequency.setValueAtTime(20, t);
            chargeOsc.frequency.exponentialRampToValueAtTime(45, t + 0.4);

            chargeFilter.type = 'lowpass';
            chargeFilter.frequency.setValueAtTime(50, t);
            chargeFilter.frequency.exponentialRampToValueAtTime(150, t + 0.4);

            chargeOsc.connect(chargeFilter);
            chargeFilter.connect(chargeGain);
            chargeGain.connect(audioCtx.destination);

            chargeGain.gain.setValueAtTime(0.01, t);
            chargeGain.gain.exponentialRampToValueAtTime(0.2, t + 0.3);
            chargeGain.gain.exponentialRampToValueAtTime(0.15, t + 0.4);

            chargeOsc.start(t);
            chargeOsc.stop(t + 0.45);

            // === PHASE 2: RAPID SERVO WHINES (200-600ms) ===
            for (let i = 0; i < 5; i++) {
                setTimeout(() => {
                    const servoOsc = audioCtx.createOscillator();
                    const servoGain = audioCtx.createGain();
                    const servoFilter = audioCtx.createBiquadFilter();

                    servoOsc.type = 'sawtooth';
                    const baseFreq = 400 + i * 200 + Math.random() * 300;
                    servoOsc.frequency.setValueAtTime(baseFreq * 0.5, audioCtx.currentTime);
                    servoOsc.frequency.exponentialRampToValueAtTime(baseFreq, audioCtx.currentTime + 0.05);
                    servoOsc.frequency.exponentialRampToValueAtTime(baseFreq * 0.7, audioCtx.currentTime + 0.08);

                    servoFilter.type = 'bandpass';
                    servoFilter.frequency.value = baseFreq;
                    servoFilter.Q.value = 5;

                    servoOsc.connect(servoFilter);
                    servoFilter.connect(servoGain);
                    servoGain.connect(audioCtx.destination);

                    servoGain.gain.setValueAtTime(0.08, audioCtx.currentTime);
                    servoGain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.1);

                    servoOsc.start();
                    servoOsc.stop(audioCtx.currentTime + 0.12);
                }, 200 + i * 80);
            }

            // === PHASE 3: HEAVY ARMOR PLATES SHIFTING & LOCKING (400-900ms) ===
            const plateTimes = [400, 500, 620, 750, 880];
            plateTimes.forEach((delay, i) => {
                setTimeout(() => {
                    // HEAVY METALLIC SLAM (more impactful)
                    const slamOsc = audioCtx.createOscillator();
                    const slamOsc2 = audioCtx.createOscillator();
                    const slamGain = audioCtx.createGain();

                    slamOsc.type = 'square';
                    slamOsc.frequency.setValueAtTime(70 + i * 12, audioCtx.currentTime);
                    slamOsc.frequency.exponentialRampToValueAtTime(30, audioCtx.currentTime + 0.08);

                    slamOsc2.type = 'sawtooth';
                    slamOsc2.frequency.setValueAtTime(50 + i * 8, audioCtx.currentTime);
                    slamOsc2.frequency.exponentialRampToValueAtTime(22, audioCtx.currentTime + 0.1);

                    slamOsc.connect(slamGain);
                    slamOsc2.connect(slamGain);
                    slamGain.connect(audioCtx.destination);

                    slamGain.gain.setValueAtTime(0.2, audioCtx.currentTime);
                    slamGain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.12);

                    slamOsc.start();
                    slamOsc2.start();
                    slamOsc.stop(audioCtx.currentTime + 0.14);
                    slamOsc2.stop(audioCtx.currentTime + 0.14);

                    // HYDRAULIC HISS (pneumatic plate movement)
                    const hissBuffer = audioCtx.createBuffer(1, audioCtx.sampleRate * 0.12, audioCtx.sampleRate);
                    const hissData = hissBuffer.getChannelData(0);
                    for (let j = 0; j < hissData.length; j++) {
                        hissData[j] = (Math.random() * 2 - 1) * 0.6 * Math.exp(-j / (audioCtx.sampleRate * 0.04));
                    }
                    const hissSource = audioCtx.createBufferSource();
                    hissSource.buffer = hissBuffer;

                    const hissFilter = audioCtx.createBiquadFilter();
                    hissFilter.type = 'bandpass';
                    hissFilter.frequency.value = 3000 + Math.random() * 2000;
                    hissFilter.Q.value = 2;

                    const hissGain = audioCtx.createGain();
                    hissGain.gain.value = 0.08;

                    hissSource.connect(hissFilter);
                    hissFilter.connect(hissGain);
                    hissGain.connect(audioCtx.destination);

                    hissSource.start();

                    // Metallic resonance ring
                    setTimeout(() => {
                        const ringOsc = audioCtx.createOscillator();
                        const ringGain = audioCtx.createGain();
                        const ringFilter = audioCtx.createBiquadFilter();

                        ringOsc.type = 'sine';
                        ringOsc.frequency.value = 200 + i * 50 + Math.random() * 100;

                        ringFilter.type = 'bandpass';
                        ringFilter.frequency.value = ringOsc.frequency.value;
                        ringFilter.Q.value = 15;

                        ringOsc.connect(ringFilter);
                        ringFilter.connect(ringGain);
                        ringGain.connect(audioCtx.destination);

                        ringGain.gain.setValueAtTime(0.04, audioCtx.currentTime);
                        ringGain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.2);

                        ringOsc.start();
                        ringOsc.stop(audioCtx.currentTime + 0.25);
                    }, 30);

                    // Lock click
                    playSound(1500 + Math.random() * 500, 'square', 0.02, 0.06);
                }, delay);
            });

            // === PHASE 4: INTERNAL SYSTEMS POWERING UP (700-1100ms) ===
            setTimeout(() => {
                // Rising energy whine
                const powerOsc = audioCtx.createOscillator();
                const powerGain = audioCtx.createGain();

                powerOsc.type = 'sawtooth';
                powerOsc.frequency.setValueAtTime(100, audioCtx.currentTime);
                powerOsc.frequency.exponentialRampToValueAtTime(800, audioCtx.currentTime + 0.4);

                powerOsc.connect(powerGain);
                powerGain.connect(audioCtx.destination);

                powerGain.gain.setValueAtTime(0.02, audioCtx.currentTime);
                powerGain.gain.exponentialRampToValueAtTime(0.12, audioCtx.currentTime + 0.3);
                powerGain.gain.exponentialRampToValueAtTime(0.08, audioCtx.currentTime + 0.4);

                powerOsc.start();
                powerOsc.stop(audioCtx.currentTime + 0.45);

                // Electronic crackle overlay
                const noiseBuffer = audioCtx.createBuffer(1, audioCtx.sampleRate * 0.3, audioCtx.sampleRate);
                const noiseData = noiseBuffer.getChannelData(0);
                for (let i = 0; i < noiseData.length; i++) {
                    noiseData[i] = (Math.random() * 2 - 1) * (Math.random() > 0.9 ? 0.5 : 0.1);
                }
                const noiseSource = audioCtx.createBufferSource();
                noiseSource.buffer = noiseBuffer;

                const noiseGain = audioCtx.createGain();
                const noiseFilter = audioCtx.createBiquadFilter();
                noiseFilter.type = 'highpass';
                noiseFilter.frequency.value = 2000;

                noiseSource.connect(noiseFilter);
                noiseFilter.connect(noiseGain);
                noiseGain.connect(audioCtx.destination);
                noiseGain.gain.value = 0.05;

                noiseSource.start();
            }, 700);

            // === PHASE 5: MASSIVE BASS DROP & ENGINE VOOM FINALE (1100-1600ms) ===
            setTimeout(() => {
                // ULTRA-DEEP SUB-BASS DROP (earthquake level)
                const ultraDropOsc = audioCtx.createOscillator();
                const ultraDropGain = audioCtx.createGain();

                ultraDropOsc.type = 'sine';
                ultraDropOsc.frequency.setValueAtTime(80, audioCtx.currentTime);
                ultraDropOsc.frequency.exponentialRampToValueAtTime(18, audioCtx.currentTime + 0.3);

                ultraDropOsc.connect(ultraDropGain);
                ultraDropGain.connect(audioCtx.destination);

                ultraDropGain.gain.setValueAtTime(0.4, audioCtx.currentTime);
                ultraDropGain.gain.exponentialRampToValueAtTime(0.25, audioCtx.currentTime + 0.35);
                ultraDropGain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.8);

                ultraDropOsc.start();
                ultraDropOsc.stop(audioCtx.currentTime + 0.85);

                // MAIN SUB-BASS DROP (standard bass punch)
                const dropOsc = audioCtx.createOscillator();
                const dropGain = audioCtx.createGain();
                const dropFilter = audioCtx.createBiquadFilter();

                dropOsc.type = 'sine';
                dropOsc.frequency.setValueAtTime(120, audioCtx.currentTime);
                dropOsc.frequency.exponentialRampToValueAtTime(28, audioCtx.currentTime + 0.25);

                dropFilter.type = 'lowpass';
                dropFilter.frequency.value = 100;

                dropOsc.connect(dropFilter);
                dropFilter.connect(dropGain);
                dropGain.connect(audioCtx.destination);

                dropGain.gain.setValueAtTime(0.35, audioCtx.currentTime);
                dropGain.gain.exponentialRampToValueAtTime(0.2, audioCtx.currentTime + 0.3);
                dropGain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.6);

                dropOsc.start();
                dropOsc.stop(audioCtx.currentTime + 0.65);

                // EXPLOSIVE VOOM - 4-LAYER BURST
                const voomOsc1 = audioCtx.createOscillator(); // Deep sawtooth
                const voomOsc2 = audioCtx.createOscillator(); // Heavy square
                const voomOsc3 = audioCtx.createOscillator(); // Ultra-low sine
                const voomOsc4 = audioCtx.createOscillator(); // Triangle mid
                const voomGain = audioCtx.createGain();
                const voomFilter = audioCtx.createBiquadFilter();

                voomOsc1.type = 'sawtooth';
                voomOsc1.frequency.setValueAtTime(50, audioCtx.currentTime);
                voomOsc1.frequency.exponentialRampToValueAtTime(180, audioCtx.currentTime + 0.12);
                voomOsc1.frequency.exponentialRampToValueAtTime(70, audioCtx.currentTime + 0.45);

                voomOsc2.type = 'square';
                voomOsc2.frequency.setValueAtTime(35, audioCtx.currentTime);
                voomOsc2.frequency.exponentialRampToValueAtTime(140, audioCtx.currentTime + 0.1);
                voomOsc2.frequency.exponentialRampToValueAtTime(45, audioCtx.currentTime + 0.4);

                voomOsc3.type = 'sine';
                voomOsc3.frequency.setValueAtTime(20, audioCtx.currentTime);
                voomOsc3.frequency.exponentialRampToValueAtTime(60, audioCtx.currentTime + 0.08);
                voomOsc3.frequency.exponentialRampToValueAtTime(25, audioCtx.currentTime + 0.5);

                voomOsc4.type = 'triangle';
                voomOsc4.frequency.setValueAtTime(80, audioCtx.currentTime);
                voomOsc4.frequency.exponentialRampToValueAtTime(200, audioCtx.currentTime + 0.15);
                voomOsc4.frequency.exponentialRampToValueAtTime(90, audioCtx.currentTime + 0.35);

                voomFilter.type = 'lowpass';
                voomFilter.frequency.setValueAtTime(180, audioCtx.currentTime);
                voomFilter.frequency.exponentialRampToValueAtTime(600, audioCtx.currentTime + 0.12);
                voomFilter.frequency.exponentialRampToValueAtTime(150, audioCtx.currentTime + 0.5);

                voomOsc1.connect(voomFilter);
                voomOsc2.connect(voomFilter);
                voomOsc3.connect(voomFilter);
                voomOsc4.connect(voomFilter);
                voomFilter.connect(voomGain);
                voomGain.connect(audioCtx.destination);

                voomGain.gain.setValueAtTime(0.3, audioCtx.currentTime);
                voomGain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.6);

                voomOsc1.start();
                voomOsc2.start();
                voomOsc3.start();
                voomOsc4.start();
                voomOsc1.stop(audioCtx.currentTime + 0.65);
                voomOsc2.stop(audioCtx.currentTime + 0.65);
                voomOsc3.stop(audioCtx.currentTime + 0.6);
                voomOsc4.stop(audioCtx.currentTime + 0.55);

                // MASSIVE ENGINE IGNITION BURST (longer, louder)
                const burstBuffer = audioCtx.createBuffer(1, audioCtx.sampleRate * 0.5, audioCtx.sampleRate);
                const burstData = burstBuffer.getChannelData(0);
                for (let i = 0; i < burstData.length; i++) {
                    burstData[i] = (Math.random() * 2 - 1) * Math.exp(-i / (audioCtx.sampleRate * 0.15));
                }
                const burstSource = audioCtx.createBufferSource();
                burstSource.buffer = burstBuffer;

                const burstGain = audioCtx.createGain();
                const burstFilter = audioCtx.createBiquadFilter();
                burstFilter.type = 'lowpass';
                burstFilter.frequency.value = 500;

                burstSource.connect(burstFilter);
                burstFilter.connect(burstGain);
                burstGain.connect(audioCtx.destination);
                burstGain.gain.value = 0.2;

                burstSource.start();

                // FIRE ROAR (engine exhaust)
                const fireBuffer = audioCtx.createBuffer(1, audioCtx.sampleRate * 0.4, audioCtx.sampleRate);
                const fireData = fireBuffer.getChannelData(0);
                for (let i = 0; i < fireData.length; i++) {
                    fireData[i] = (Math.random() * 2 - 1) * 0.5 * Math.exp(-i / (audioCtx.sampleRate * 0.2));
                }
                const fireSource = audioCtx.createBufferSource();
                fireSource.buffer = fireBuffer;

                const fireGain = audioCtx.createGain();
                const fireFilter = audioCtx.createBiquadFilter();
                fireFilter.type = 'bandpass';
                fireFilter.frequency.value = 250;
                fireFilter.Q.value = 1;

                fireSource.connect(fireFilter);
                fireFilter.connect(fireGain);
                fireGain.connect(audioCtx.destination);
                fireGain.gain.value = 0.12;

                fireSource.start();

                // Start the Hellbat reactor engine
                startHellbatReactor();
            }, 1100);
        }

        // ========== HELLBAT MODE REFINED BOOST SOUND SYSTEM ==========
        // Precision engineering: turbine spin-up, sustained wind shear, clean deceleration
        let hellbatBoostTurbineOsc = null;
        let hellbatBoostWhineOsc = null;
        let hellbatBoostWindSource = null;
        let hellbatBoostGain = null;
        let isHellbatBoostRunning = false;

        // Hellbat-specific boost sound - refined turbine spin-up (SMOOTHENED)
        function playHellbatBoostStart() {
            if (!audioCtx) initAudio();

            // === PHASE 1: SMOOTH TURBINE SPIN-UP (gentle start, gradual acceleration) ===
            const spinUpOsc = audioCtx.createOscillator();
            const spinUpOsc2 = audioCtx.createOscillator();
            const spinUpGain = audioCtx.createGain();
            const spinUpFilter = audioCtx.createBiquadFilter();

            // Primary spin-up: very gentle start, smooth acceleration
            spinUpOsc.type = 'sine'; // Sine is smoother than sawtooth
            spinUpOsc.frequency.setValueAtTime(40, audioCtx.currentTime);
            spinUpOsc.frequency.exponentialRampToValueAtTime(150, audioCtx.currentTime + 0.3);
            spinUpOsc.frequency.exponentialRampToValueAtTime(600, audioCtx.currentTime + 0.6);
            spinUpOsc.frequency.exponentialRampToValueAtTime(1400, audioCtx.currentTime + 0.9);

            // Secondary harmonic - softer triangle wave
            spinUpOsc2.type = 'triangle';
            spinUpOsc2.frequency.setValueAtTime(60, audioCtx.currentTime);
            spinUpOsc2.frequency.exponentialRampToValueAtTime(200, audioCtx.currentTime + 0.3);
            spinUpOsc2.frequency.exponentialRampToValueAtTime(800, audioCtx.currentTime + 0.6);
            spinUpOsc2.frequency.exponentialRampToValueAtTime(1800, audioCtx.currentTime + 0.9);

            // Lowpass filter for smoother sound
            spinUpFilter.type = 'lowpass';
            spinUpFilter.frequency.setValueAtTime(100, audioCtx.currentTime);
            spinUpFilter.frequency.exponentialRampToValueAtTime(600, audioCtx.currentTime + 0.4);
            spinUpFilter.frequency.exponentialRampToValueAtTime(2000, audioCtx.currentTime + 0.8);
            spinUpFilter.Q.value = 0.7; // Lower Q for less resonance

            spinUpOsc.connect(spinUpFilter);
            spinUpOsc2.connect(spinUpFilter);
            spinUpFilter.connect(spinUpGain);
            spinUpGain.connect(audioCtx.destination);

            // SMOOTH volume envelope: very gradual fade-in
            spinUpGain.gain.setValueAtTime(0.001, audioCtx.currentTime);
            spinUpGain.gain.exponentialRampToValueAtTime(0.03, audioCtx.currentTime + 0.15);
            spinUpGain.gain.linearRampToValueAtTime(0.07, audioCtx.currentTime + 0.4);
            spinUpGain.gain.linearRampToValueAtTime(0.05, audioCtx.currentTime + 0.7);
            spinUpGain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 1.0);

            spinUpOsc.start();
            spinUpOsc2.start();
            spinUpOsc.stop(audioCtx.currentTime + 1.05);
            spinUpOsc2.stop(audioCtx.currentTime + 1.05);

            // === PHASE 2: GENTLE HIGH-FREQUENCY LAYER (delayed, smooth entry) ===
            setTimeout(() => {
                const whineOsc = audioCtx.createOscillator();
                const whineGain = audioCtx.createGain();
                const whineFilter = audioCtx.createBiquadFilter();

                whineOsc.type = 'sine'; // Smoother waveform
                whineOsc.frequency.setValueAtTime(800, audioCtx.currentTime);
                whineOsc.frequency.exponentialRampToValueAtTime(2000, audioCtx.currentTime + 0.5);
                whineOsc.frequency.linearRampToValueAtTime(2400, audioCtx.currentTime + 0.8);

                whineFilter.type = 'bandpass';
                whineFilter.frequency.value = 1800;
                whineFilter.Q.value = 1; // Low resonance

                whineOsc.connect(whineFilter);
                whineFilter.connect(whineGain);
                whineGain.connect(audioCtx.destination);

                // Very gentle fade-in
                whineGain.gain.setValueAtTime(0.001, audioCtx.currentTime);
                whineGain.gain.exponentialRampToValueAtTime(0.025, audioCtx.currentTime + 0.3);
                whineGain.gain.linearRampToValueAtTime(0.02, audioCtx.currentTime + 0.6);
                whineGain.gain.exponentialRampToValueAtTime(0.005, audioCtx.currentTime + 0.9);

                whineOsc.start();
                whineOsc.stop(audioCtx.currentTime + 0.95);
            }, 350);

            // === PHASE 3: SOFT AIRFLOW (very gentle wind-up) ===
            setTimeout(() => {
                // Ultra-smooth air pressure build
                const airBuffer = audioCtx.createBuffer(2, audioCtx.sampleRate * 0.6, audioCtx.sampleRate);
                for (let channel = 0; channel < 2; channel++) {
                    const data = airBuffer.getChannelData(channel);
                    for (let i = 0; i < data.length; i++) {
                        // Very smooth sine-squared envelope
                        const t = i / data.length;
                        const envelope = Math.sin(Math.PI * t) * Math.sin(Math.PI * t);
                        data[i] = (Math.random() * 2 - 1) * 0.25 * envelope;
                    }
                }
                const airSource = audioCtx.createBufferSource();
                airSource.buffer = airBuffer;

                const airFilter = audioCtx.createBiquadFilter();
                airFilter.type = 'lowpass';
                airFilter.frequency.value = 400;
                airFilter.Q.value = 0.5;

                const airGain = audioCtx.createGain();
                airGain.gain.setValueAtTime(0.001, audioCtx.currentTime);
                airGain.gain.exponentialRampToValueAtTime(0.04, audioCtx.currentTime + 0.2);

                airSource.connect(airFilter);
                airFilter.connect(airGain);
                airGain.connect(audioCtx.destination);

                airSource.start();
            }, 200);

            // Start the sustained hellbat boost sound (delayed for smooth transition)
            setTimeout(() => startHellbatBoostSustain(), 500);
        }

        // Sustained Hellbat boost: smooth wind shear + gentle turbine whine
        function startHellbatBoostSustain() {
            if (!audioCtx) initAudio();
            if (isHellbatBoostRunning) return;
            isHellbatBoostRunning = true;

            // === LAYER 1: SMOOTH TURBINE HUM (lower frequency, gentler) ===
            hellbatBoostTurbineOsc = audioCtx.createOscillator();
            const turbineGain = audioCtx.createGain();
            const turbineFilter = audioCtx.createBiquadFilter();

            hellbatBoostTurbineOsc.type = 'sine'; // Smoother than sawtooth
            hellbatBoostTurbineOsc.frequency.value = 1200; // Lower, more pleasant frequency

            // Very subtle pitch modulation
            const turbineLfo = audioCtx.createOscillator();
            const turbineLfoGain = audioCtx.createGain();
            turbineLfo.type = 'sine';
            turbineLfo.frequency.value = 2; // Slower wobble
            turbineLfoGain.gain.value = 15; // Smaller pitch variation
            turbineLfo.connect(turbineLfoGain);
            turbineLfoGain.connect(hellbatBoostTurbineOsc.frequency);
            turbineLfo.start();

            turbineFilter.type = 'lowpass'; // Smoother filter
            turbineFilter.frequency.value = 1800;
            turbineFilter.Q.value = 0.5; // Very low resonance

            hellbatBoostTurbineOsc.connect(turbineFilter);
            turbineFilter.connect(turbineGain);
            turbineGain.connect(audioCtx.destination);

            // Very slow fade-in
            turbineGain.gain.setValueAtTime(0.001, audioCtx.currentTime);
            turbineGain.gain.exponentialRampToValueAtTime(0.015, audioCtx.currentTime + 0.3);
            turbineGain.gain.linearRampToValueAtTime(0.025, audioCtx.currentTime + 0.6);

            hellbatBoostTurbineOsc.start();
            hellbatBoostTurbineOsc.lfo = turbineLfo;
            hellbatBoostTurbineOsc.gain = turbineGain;

            // === LAYER 2: SOFT SECONDARY TONE ===
            hellbatBoostWhineOsc = audioCtx.createOscillator();
            const whineGain = audioCtx.createGain();
            const whineFilter = audioCtx.createBiquadFilter();

            hellbatBoostWhineOsc.type = 'sine'; // Smooth sine wave
            hellbatBoostWhineOsc.frequency.value = 1800; // Lower harmonic

            whineFilter.type = 'bandpass';
            whineFilter.frequency.value = 2000;
            whineFilter.Q.value = 1; // Low resonance for smoothness

            hellbatBoostWhineOsc.connect(whineFilter);
            whineFilter.connect(whineGain);
            whineGain.connect(audioCtx.destination);

            // Very gradual fade-in
            whineGain.gain.setValueAtTime(0.001, audioCtx.currentTime);
            whineGain.gain.exponentialRampToValueAtTime(0.008, audioCtx.currentTime + 0.5);

            hellbatBoostWhineOsc.start();
            hellbatBoostWhineOsc.gain = whineGain;

            // === LAYER 3: SMOOTH STEREO WIND ===
            const windBufferSize = audioCtx.sampleRate * 2;
            const windBuffer = audioCtx.createBuffer(2, windBufferSize, audioCtx.sampleRate);
            for (let channel = 0; channel < 2; channel++) {
                const data = windBuffer.getChannelData(channel);
                for (let i = 0; i < windBufferSize; i++) {
                    // Softer noise amplitude
                    data[i] = (Math.random() * 2 - 1) * (channel === 0 ? 0.35 : 0.4);
                }
            }

            hellbatBoostWindSource = audioCtx.createBufferSource();
            hellbatBoostWindSource.buffer = windBuffer;
            hellbatBoostWindSource.loop = true;

            const windFilter = audioCtx.createBiquadFilter();
            windFilter.type = 'lowpass'; // Lowpass for smoother sound
            windFilter.frequency.value = 600;
            windFilter.Q.value = 0.3;

            hellbatBoostGain = audioCtx.createGain();
            // Slow, smooth fade-in
            hellbatBoostGain.gain.setValueAtTime(0.001, audioCtx.currentTime);
            hellbatBoostGain.gain.exponentialRampToValueAtTime(0.05, audioCtx.currentTime + 0.3);
            hellbatBoostGain.gain.linearRampToValueAtTime(0.08, audioCtx.currentTime + 0.6);

            hellbatBoostWindSource.connect(windFilter);
            windFilter.connect(hellbatBoostGain);
            hellbatBoostGain.connect(audioCtx.destination);

            hellbatBoostWindSource.start();
        }

        // Clean rotational deceleration with pressure-release whoof
        function playHellbatBoostEnd() {
            if (!audioCtx) initAudio();

            // Stop sustained boost sounds with smooth fade
            stopHellbatBoostSustain();

            // === PHASE 1: ROTATIONAL DECELERATION (turbine spinning down) ===
            const spinDownOsc = audioCtx.createOscillator();
            const spinDownOsc2 = audioCtx.createOscillator();
            const spinDownGain = audioCtx.createGain();
            const spinDownFilter = audioCtx.createBiquadFilter();

            // Primary spin-down: high to low frequency
            spinDownOsc.type = 'sawtooth';
            spinDownOsc.frequency.setValueAtTime(2500, audioCtx.currentTime);
            spinDownOsc.frequency.exponentialRampToValueAtTime(800, audioCtx.currentTime + 0.3);
            spinDownOsc.frequency.exponentialRampToValueAtTime(200, audioCtx.currentTime + 0.6);
            spinDownOsc.frequency.exponentialRampToValueAtTime(80, audioCtx.currentTime + 0.9);

            // Secondary harmonic
            spinDownOsc2.type = 'triangle';
            spinDownOsc2.frequency.setValueAtTime(3800, audioCtx.currentTime);
            spinDownOsc2.frequency.exponentialRampToValueAtTime(1200, audioCtx.currentTime + 0.25);
            spinDownOsc2.frequency.exponentialRampToValueAtTime(300, audioCtx.currentTime + 0.55);
            spinDownOsc2.frequency.exponentialRampToValueAtTime(100, audioCtx.currentTime + 0.85);

            spinDownFilter.type = 'bandpass';
            spinDownFilter.frequency.setValueAtTime(2000, audioCtx.currentTime);
            spinDownFilter.frequency.exponentialRampToValueAtTime(400, audioCtx.currentTime + 0.5);
            spinDownFilter.frequency.exponentialRampToValueAtTime(150, audioCtx.currentTime + 0.9);
            spinDownFilter.Q.value = 2;

            spinDownOsc.connect(spinDownFilter);
            spinDownOsc2.connect(spinDownFilter);
            spinDownFilter.connect(spinDownGain);
            spinDownGain.connect(audioCtx.destination);

            // Volume envelope: smooth decay
            spinDownGain.gain.setValueAtTime(0.08, audioCtx.currentTime);
            spinDownGain.gain.linearRampToValueAtTime(0.06, audioCtx.currentTime + 0.3);
            spinDownGain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.9);

            spinDownOsc.start();
            spinDownOsc2.start();
            spinDownOsc.stop(audioCtx.currentTime + 1.0);
            spinDownOsc2.stop(audioCtx.currentTime + 1.0);

            // === PHASE 2: SOFT PRESSURE-RELEASE WHOOF ===
            setTimeout(() => {
                // Gentle air release (not harsh)
                const whoofOsc = audioCtx.createOscillator();
                const whoofGain = audioCtx.createGain();
                const whoofFilter = audioCtx.createBiquadFilter();

                whoofOsc.type = 'sine';
                whoofOsc.frequency.setValueAtTime(300, audioCtx.currentTime);
                whoofOsc.frequency.exponentialRampToValueAtTime(60, audioCtx.currentTime + 0.35);

                whoofFilter.type = 'lowpass';
                whoofFilter.frequency.setValueAtTime(500, audioCtx.currentTime);
                whoofFilter.frequency.exponentialRampToValueAtTime(100, audioCtx.currentTime + 0.35);

                whoofOsc.connect(whoofFilter);
                whoofFilter.connect(whoofGain);
                whoofGain.connect(audioCtx.destination);

                whoofGain.gain.setValueAtTime(0.12, audioCtx.currentTime);
                whoofGain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.4);

                whoofOsc.start();
                whoofOsc.stop(audioCtx.currentTime + 0.45);

                // Soft air hiss (controlled, not harsh)
                const hissBuffer = audioCtx.createBuffer(1, audioCtx.sampleRate * 0.3, audioCtx.sampleRate);
                const hissData = hissBuffer.getChannelData(0);
                for (let i = 0; i < hissData.length; i++) {
                    // Smooth exponential decay
                    hissData[i] = (Math.random() * 2 - 1) * 0.3 * Math.exp(-i / (audioCtx.sampleRate * 0.12));
                }

                const hissSource = audioCtx.createBufferSource();
                hissSource.buffer = hissBuffer;

                const hissFilter = audioCtx.createBiquadFilter();
                hissFilter.type = 'bandpass';
                hissFilter.frequency.value = 1500;
                hissFilter.Q.value = 0.5;

                const hissGain = audioCtx.createGain();
                hissGain.gain.value = 0.06;

                hissSource.connect(hissFilter);
                hissFilter.connect(hissGain);
                hissGain.connect(audioCtx.destination);

                hissSource.start();
            }, 400);
        }

        function stopHellbatBoostSustain() {
            if (!isHellbatBoostRunning) return;
            isHellbatBoostRunning = false;

            // Fade out turbine whine smoothly
            if (hellbatBoostTurbineOsc && hellbatBoostTurbineOsc.gain) {
                hellbatBoostTurbineOsc.gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.3);
                setTimeout(() => {
                    try {
                        if (hellbatBoostTurbineOsc) hellbatBoostTurbineOsc.stop();
                        if (hellbatBoostTurbineOsc && hellbatBoostTurbineOsc.lfo) hellbatBoostTurbineOsc.lfo.stop();
                    } catch (e) { }
                    hellbatBoostTurbineOsc = null;
                }, 350);
            }

            // Fade out secondary whine
            if (hellbatBoostWhineOsc && hellbatBoostWhineOsc.gain) {
                hellbatBoostWhineOsc.gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.25);
                setTimeout(() => {
                    try { if (hellbatBoostWhineOsc) hellbatBoostWhineOsc.stop(); } catch (e) { }
                    hellbatBoostWhineOsc = null;
                }, 300);
            }

            // Fade out wind shear
            if (hellbatBoostGain) {
                hellbatBoostGain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.2);
            }
            setTimeout(() => {
                try { if (hellbatBoostWindSource) hellbatBoostWindSource.stop(); } catch (e) { }
                hellbatBoostWindSource = null;
            }, 250);
        }

        // ========== STEALTH REACTOR ENGINE SYSTEM ==========
        // Minimal, controlled audio: soft turbine hum, air-slip, low-freq vibration
        let stealthTurbineOsc = null;
        let stealthVibrationOsc = null;
        let stealthAirSlipSource = null;
        let stealthPrecisionOsc = null;
        let stealthReactorGain = null;
        let isStealthReactorRunning = false;

        function startStealthReactor() {
            if (!audioCtx) initAudio();
            if (isStealthReactorRunning) return;
            isStealthReactorRunning = true;

            // === LAYER 1: SOFT TURBINE HUM (smooth, barely audible) ===
            stealthTurbineOsc = audioCtx.createOscillator();
            const turbineGain = audioCtx.createGain();
            const turbineFilter = audioCtx.createBiquadFilter();

            stealthTurbineOsc.type = 'sine';
            stealthTurbineOsc.frequency.value = 180; // Soft high-frequency hum

            turbineFilter.type = 'lowpass';
            turbineFilter.frequency.value = 300;
            turbineFilter.Q.value = 0.5;

            stealthTurbineOsc.connect(turbineFilter);
            turbineFilter.connect(turbineGain);
            turbineGain.connect(audioCtx.destination);
            turbineGain.gain.value = 0.008; // Very quiet
            stealthReactorGain = turbineGain;

            stealthTurbineOsc.start();

            // === LAYER 2: SMOOTH AIR-SLIP NOISE (filtered white noise) ===
            const airSlipBufferSize = audioCtx.sampleRate * 2;
            const airSlipBuffer = audioCtx.createBuffer(1, airSlipBufferSize, audioCtx.sampleRate);
            const airSlipData = airSlipBuffer.getChannelData(0);
            for (let i = 0; i < airSlipBufferSize; i++) {
                // Ultra-smooth noise with minimal variation
                airSlipData[i] = (Math.random() * 2 - 1) * 0.15;
            }
            stealthAirSlipSource = audioCtx.createBufferSource();
            stealthAirSlipSource.buffer = airSlipBuffer;
            stealthAirSlipSource.loop = true;

            const airSlipFilter = audioCtx.createBiquadFilter();
            airSlipFilter.type = 'bandpass';
            airSlipFilter.frequency.value = 600;
            airSlipFilter.Q.value = 0.3; // Wide, smooth band

            const airSlipGain = audioCtx.createGain();
            airSlipGain.gain.value = 0.012;

            stealthAirSlipSource.connect(airSlipFilter);
            airSlipFilter.connect(airSlipGain);
            airSlipGain.connect(audioCtx.destination);

            stealthAirSlipSource.start();

            // === LAYER 3: LOW-FREQUENCY VIBRATION (subliminal presence) ===
            stealthVibrationOsc = audioCtx.createOscillator();
            const vibrationGain = audioCtx.createGain();
            const vibrationFilter = audioCtx.createBiquadFilter();

            stealthVibrationOsc.type = 'sine';
            stealthVibrationOsc.frequency.value = 50; // Low sub-harmonic

            vibrationFilter.type = 'lowpass';
            vibrationFilter.frequency.value = 80;

            stealthVibrationOsc.connect(vibrationFilter);
            vibrationFilter.connect(vibrationGain);
            vibrationGain.connect(audioCtx.destination);
            vibrationGain.gain.value = 0.02; // Felt more than heard

            stealthVibrationOsc.start();

            // === LAYER 4: PRECISION ELECTRONIC HUM (high-tech feel) ===
            stealthPrecisionOsc = audioCtx.createOscillator();
            const precisionGain = audioCtx.createGain();
            const precisionFilter = audioCtx.createBiquadFilter();

            stealthPrecisionOsc.type = 'triangle';
            stealthPrecisionOsc.frequency.value = 800; // Clean high-frequency

            // Subtle pitch modulation for electronic character
            const precisionLfo = audioCtx.createOscillator();
            const precisionLfoGain = audioCtx.createGain();
            precisionLfo.type = 'sine';
            precisionLfo.frequency.value = 0.15; // Very slow modulation
            precisionLfoGain.gain.value = 5;
            precisionLfo.connect(precisionLfoGain);
            precisionLfoGain.connect(stealthPrecisionOsc.frequency);
            precisionLfo.start();

            precisionFilter.type = 'bandpass';
            precisionFilter.frequency.value = 900;
            precisionFilter.Q.value = 8;

            stealthPrecisionOsc.connect(precisionFilter);
            precisionFilter.connect(precisionGain);
            precisionGain.connect(audioCtx.destination);
            precisionGain.gain.value = 0.004; // Extremely subtle

            stealthPrecisionOsc.start();

            // Store references
            stealthTurbineOsc.airSlipSource = stealthAirSlipSource;
            stealthTurbineOsc.airSlipGain = airSlipGain;
            stealthTurbineOsc.vibrationOsc = stealthVibrationOsc;
            stealthTurbineOsc.vibrationGain = vibrationGain;
            stealthTurbineOsc.precisionOsc = stealthPrecisionOsc;
            stealthTurbineOsc.precisionGain = precisionGain;
            stealthTurbineOsc.precisionLfo = precisionLfo;
        }

        function updateStealthReactor(speed, maxSpeed, isBoosting) {
            if (!isStealthReactorRunning || !stealthTurbineOsc) return;

            const speedRatio = speed / maxSpeed;

            // === TURBINE: Slightly increases with speed (controlled) ===
            stealthTurbineOsc.frequency.value = 160 + speedRatio * 40;
            if (stealthReactorGain) {
                stealthReactorGain.gain.value = 0.006 + speedRatio * 0.006;
            }

            // === AIR-SLIP: More prominent with speed ===
            if (stealthTurbineOsc.airSlipGain) {
                stealthTurbineOsc.airSlipGain.gain.value = 0.01 + speedRatio * 0.015;
            }

            // === VIBRATION: Stays consistent but intensifies slightly ===
            if (stealthTurbineOsc.vibrationGain) {
                stealthTurbineOsc.vibrationGain.gain.value = 0.015 + speedRatio * 0.01;
            }

            // === PRECISION: Clean pitch rise with speed ===
            if (stealthPrecisionOsc) {
                stealthPrecisionOsc.frequency.value = 700 + speedRatio * 200;
            }
            if (stealthTurbineOsc.precisionGain) {
                stealthTurbineOsc.precisionGain.gain.value = 0.003 + speedRatio * 0.004;
            }

            // === BOOST STATE: Controlled surge (still quiet) ===
            if (isBoosting) {
                stealthTurbineOsc.frequency.value = 200 + speedRatio * 60;
                if (stealthReactorGain) stealthReactorGain.gain.value = 0.012 + speedRatio * 0.008;
                if (stealthTurbineOsc.airSlipGain) stealthTurbineOsc.airSlipGain.gain.value = 0.02 + speedRatio * 0.015;
                if (stealthPrecisionOsc) stealthPrecisionOsc.frequency.value = 900 + speedRatio * 250;
            }
        }

        function stopStealthReactor() {
            if (!isStealthReactorRunning) return;
            isStealthReactorRunning = false;

            if (stealthTurbineOsc) {
                try {
                    stealthTurbineOsc.stop();
                    if (stealthTurbineOsc.vibrationOsc) stealthTurbineOsc.vibrationOsc.stop();
                    if (stealthTurbineOsc.precisionOsc) stealthTurbineOsc.precisionOsc.stop();
                    if (stealthTurbineOsc.precisionLfo) stealthTurbineOsc.precisionLfo.stop();
                    if (stealthTurbineOsc.airSlipSource) stealthTurbineOsc.airSlipSource.stop();
                } catch (e) { }
                stealthTurbineOsc = null;
                stealthVibrationOsc = null;
                stealthPrecisionOsc = null;
                stealthAirSlipSource = null;
            }
        }

        // ========== STEALTH TRANSFORMATION SEQUENCE ==========
        // Smooth high-tech: magnetic slide → phase shift → mechanical fold → air pressure → silence drop
        function playStealthTransformation() {
            if (!audioCtx) initAudio();

            const t = audioCtx.currentTime;

            // === PHASE 1: MAGNETIC SLIDE SOUNDS (0-300ms) ===
            // Smooth whoosh with electronic character
            const slideOsc = audioCtx.createOscillator();
            const slideGain = audioCtx.createGain();
            const slideFilter = audioCtx.createBiquadFilter();

            slideOsc.type = 'sine';
            slideOsc.frequency.setValueAtTime(400, t);
            slideOsc.frequency.exponentialRampToValueAtTime(800, t + 0.15);
            slideOsc.frequency.exponentialRampToValueAtTime(600, t + 0.3);

            slideFilter.type = 'bandpass';
            slideFilter.frequency.value = 700;
            slideFilter.Q.value = 2;

            slideOsc.connect(slideFilter);
            slideFilter.connect(slideGain);
            slideGain.connect(audioCtx.destination);

            slideGain.gain.setValueAtTime(0, t);
            slideGain.gain.linearRampToValueAtTime(0.06, t + 0.05);
            slideGain.gain.exponentialRampToValueAtTime(0.01, t + 0.3);

            slideOsc.start(t);
            slideOsc.stop(t + 0.35);

            // Magnetic hum undertone
            const magnetOsc = audioCtx.createOscillator();
            const magnetGain = audioCtx.createGain();

            magnetOsc.type = 'sine';
            magnetOsc.frequency.value = 120;

            magnetOsc.connect(magnetGain);
            magnetGain.connect(audioCtx.destination);

            magnetGain.gain.setValueAtTime(0.04, t);
            magnetGain.gain.exponentialRampToValueAtTime(0.01, t + 0.25);

            magnetOsc.start(t);
            magnetOsc.stop(t + 0.3);

            // === PHASE 2: ELECTRONIC PHASE SHIFTS (150-450ms) ===
            const phaseDelays = [150, 250, 350];
            phaseDelays.forEach((delay, i) => {
                setTimeout(() => {
                    const phaseOsc = audioCtx.createOscillator();
                    const phaseGain = audioCtx.createGain();

                    phaseOsc.type = 'sine';
                    const startFreq = 1200 + i * 300;
                    phaseOsc.frequency.setValueAtTime(startFreq, audioCtx.currentTime);
                    phaseOsc.frequency.exponentialRampToValueAtTime(startFreq * 0.5, audioCtx.currentTime + 0.08);

                    phaseOsc.connect(phaseGain);
                    phaseGain.connect(audioCtx.destination);

                    phaseGain.gain.setValueAtTime(0.03, audioCtx.currentTime);
                    phaseGain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.1);

                    phaseOsc.start();
                    phaseOsc.stop(audioCtx.currentTime + 0.12);
                }, delay);
            });

            // === PHASE 3: SOFT MECHANICAL FOLDS (300-600ms) ===
            const foldTimes = [300, 420, 540];
            foldTimes.forEach((delay, i) => {
                setTimeout(() => {
                    // Soft fold whoosh
                    const foldBuffer = audioCtx.createBuffer(1, audioCtx.sampleRate * 0.1, audioCtx.sampleRate);
                    const foldData = foldBuffer.getChannelData(0);
                    for (let j = 0; j < foldData.length; j++) {
                        foldData[j] = (Math.random() * 2 - 1) * 0.3 * Math.exp(-j / (audioCtx.sampleRate * 0.04));
                    }
                    const foldSource = audioCtx.createBufferSource();
                    foldSource.buffer = foldBuffer;

                    const foldFilter = audioCtx.createBiquadFilter();
                    foldFilter.type = 'bandpass';
                    foldFilter.frequency.value = 2000 + i * 500;
                    foldFilter.Q.value = 1;

                    const foldGain = audioCtx.createGain();
                    foldGain.gain.value = 0.04;

                    foldSource.connect(foldFilter);
                    foldFilter.connect(foldGain);
                    foldGain.connect(audioCtx.destination);

                    foldSource.start();

                    // Subtle click
                    playSound(1800 + i * 400, 'sine', 0.02, 0.02);
                }, delay);
            });

            // === PHASE 4: PRESSURE-PULL AIR EFFECT (500-800ms) ===
            setTimeout(() => {
                // Inward air suction sound
                const suctionBuffer = audioCtx.createBuffer(1, audioCtx.sampleRate * 0.25, audioCtx.sampleRate);
                const suctionData = suctionBuffer.getChannelData(0);
                for (let i = 0; i < suctionData.length; i++) {
                    // Reversed envelope - builds then cuts
                    const env = Math.min(1, i / (audioCtx.sampleRate * 0.15));
                    suctionData[i] = (Math.random() * 2 - 1) * 0.4 * env * (1 - i / suctionData.length);
                }
                const suctionSource = audioCtx.createBufferSource();
                suctionSource.buffer = suctionBuffer;

                const suctionFilter = audioCtx.createBiquadFilter();
                suctionFilter.type = 'highpass';
                suctionFilter.frequency.value = 400;

                const suctionGain = audioCtx.createGain();
                suctionGain.gain.value = 0.06;

                suctionSource.connect(suctionFilter);
                suctionFilter.connect(suctionGain);
                suctionGain.connect(audioCtx.destination);

                suctionSource.start();

                // Pressure equalization tone
                const pressureOsc = audioCtx.createOscillator();
                const pressureGain = audioCtx.createGain();

                pressureOsc.type = 'sine';
                pressureOsc.frequency.setValueAtTime(300, audioCtx.currentTime);
                pressureOsc.frequency.exponentialRampToValueAtTime(150, audioCtx.currentTime + 0.2);

                pressureOsc.connect(pressureGain);
                pressureGain.connect(audioCtx.destination);

                pressureGain.gain.setValueAtTime(0.05, audioCtx.currentTime);
                pressureGain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.25);

                pressureOsc.start();
                pressureOsc.stop(audioCtx.currentTime + 0.3);
            }, 500);

            // === PHASE 5: SILENCE DROP - Systems Dampen (800-1000ms) ===
            setTimeout(() => {
                // Brief silence indicated by very soft descending tone
                const silenceOsc = audioCtx.createOscillator();
                const silenceGain = audioCtx.createGain();

                silenceOsc.type = 'sine';
                silenceOsc.frequency.setValueAtTime(600, audioCtx.currentTime);
                silenceOsc.frequency.exponentialRampToValueAtTime(100, audioCtx.currentTime + 0.2);

                silenceOsc.connect(silenceGain);
                silenceGain.connect(audioCtx.destination);

                silenceGain.gain.setValueAtTime(0.04, audioCtx.currentTime);
                silenceGain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.25);

                silenceOsc.start();
                silenceOsc.stop(audioCtx.currentTime + 0.3);

                // Final activation chirp
                setTimeout(() => {
                    playSound(1500, 'sine', 0.08, 0.03);
                    setTimeout(() => playSound(2000, 'sine', 0.06, 0.025), 30);
                }, 150);

                // Start the stealth reactor engine
                startStealthReactor();
            }, 800);
        }

        // Stealth-specific boost sound - controlled surge
        function playStealthBoostStart() {
            if (!audioCtx) initAudio();

            // Smooth electronic surge (no harsh sounds)
            const surgeOsc = audioCtx.createOscillator();
            const surgeGain = audioCtx.createGain();
            const surgeFilter = audioCtx.createBiquadFilter();

            surgeOsc.type = 'sine';
            surgeOsc.frequency.setValueAtTime(200, audioCtx.currentTime);
            surgeOsc.frequency.exponentialRampToValueAtTime(500, audioCtx.currentTime + 0.15);
            surgeOsc.frequency.exponentialRampToValueAtTime(300, audioCtx.currentTime + 0.3);

            surgeFilter.type = 'bandpass';
            surgeFilter.frequency.value = 400;
            surgeFilter.Q.value = 1;

            surgeOsc.connect(surgeFilter);
            surgeFilter.connect(surgeGain);
            surgeGain.connect(audioCtx.destination);

            surgeGain.gain.setValueAtTime(0, audioCtx.currentTime);
            surgeGain.gain.linearRampToValueAtTime(0.06, audioCtx.currentTime + 0.05);
            surgeGain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.35);

            surgeOsc.start();
            surgeOsc.stop(audioCtx.currentTime + 0.4);

            // Soft air compression
            const airBuffer = audioCtx.createBuffer(1, audioCtx.sampleRate * 0.2, audioCtx.sampleRate);
            const airData = airBuffer.getChannelData(0);
            for (let i = 0; i < airData.length; i++) {
                airData[i] = (Math.random() * 2 - 1) * 0.2 * Math.exp(-i / (audioCtx.sampleRate * 0.1));
            }
            const airSource = audioCtx.createBufferSource();
            airSource.buffer = airBuffer;

            const airGain = audioCtx.createGain();
            const airFilter = audioCtx.createBiquadFilter();
            airFilter.type = 'highpass';
            airFilter.frequency.value = 800;

            airSource.connect(airFilter);
            airFilter.connect(airGain);
            airGain.connect(audioCtx.destination);
            airGain.gain.value = 0.05;

            airSource.start();
        }

        // ========== BOOST SOUND SYSTEM ==========
        function playBoostStart() {
            if (!audioCtx) initAudio();

            // HELLBAT MODE: Use refined turbine spin-up sound
            if (currentMode === 1) {
                playHellbatBoostStart();
                return;
            }

            // STEALTH MODE: Use quieter boost
            if (currentMode === 2) {
                playStealthBoostStart();
                return;
            }

            // NORMAL MODE: Standard boost sound
            const modeSettings = modeAudioSettings[currentMode];

            // Heavy sub-bass VOOM burst
            const bassOsc = audioCtx.createOscillator();
            const bassGain = audioCtx.createGain();

            bassOsc.type = 'sine';
            bassOsc.frequency.setValueAtTime(30, audioCtx.currentTime);
            bassOsc.frequency.exponentialRampToValueAtTime(150, audioCtx.currentTime + 0.15);

            bassOsc.connect(bassGain);
            bassGain.connect(audioCtx.destination);

            bassGain.gain.setValueAtTime(0.4 * modeSettings.bassPunch, audioCtx.currentTime);
            bassGain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.2);

            bassOsc.start();
            bassOsc.stop(audioCtx.currentTime + 0.2);

            // Whoosh layer
            const whooshOsc = audioCtx.createOscillator();
            const whooshGain = audioCtx.createGain();
            const whooshFilter = audioCtx.createBiquadFilter();

            whooshOsc.type = 'sawtooth';
            whooshOsc.frequency.setValueAtTime(100, audioCtx.currentTime);
            whooshOsc.frequency.exponentialRampToValueAtTime(300, audioCtx.currentTime + 0.1);

            whooshFilter.type = 'lowpass';
            whooshFilter.frequency.value = 600;

            whooshOsc.connect(whooshFilter);
            whooshFilter.connect(whooshGain);
            whooshGain.connect(audioCtx.destination);

            whooshGain.gain.setValueAtTime(0.15, audioCtx.currentTime);
            whooshGain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.15);

            whooshOsc.start();
            whooshOsc.stop(audioCtx.currentTime + 0.15);

            // Start sustained boost wind
            startBoostWind();
        }

        function startBoostWind() {
            if (!audioCtx) initAudio();
            if (isBoostWindRunning) return;
            isBoostWindRunning = true;

            // Wide stereo noise for boost
            const bufferSize = audioCtx.sampleRate * 2;
            const noiseBuffer = audioCtx.createBuffer(2, bufferSize, audioCtx.sampleRate);

            for (let channel = 0; channel < 2; channel++) {
                const data = noiseBuffer.getChannelData(channel);
                for (let i = 0; i < bufferSize; i++) {
                    // Slightly different noise per channel for width
                    data[i] = (Math.random() * 2 - 1) * (channel === 0 ? 0.6 : 0.65);
                }
            }

            boostWindSource = audioCtx.createBufferSource();
            boostWindSource.buffer = noiseBuffer;
            boostWindSource.loop = true;

            const boostFilter = audioCtx.createBiquadFilter();
            boostFilter.type = 'bandpass';
            boostFilter.frequency.value = 800;
            boostFilter.Q.value = 0.8;

            boostWindGain = audioCtx.createGain();
            boostWindGain.gain.setValueAtTime(0.01, audioCtx.currentTime);
            boostWindGain.gain.linearRampToValueAtTime(0.12, audioCtx.currentTime + 0.1);

            boostWindSource.connect(boostFilter);
            boostFilter.connect(boostWindGain);
            boostWindGain.connect(audioCtx.destination);

            boostWindSource.start();
        }

        function stopBoostWind() {
            if (!isBoostWindRunning) return;
            isBoostWindRunning = false;

            if (boostWindGain) {
                boostWindGain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.1);
            }

            setTimeout(() => {
                if (boostWindSource) {
                    try { boostWindSource.stop(); } catch (e) { }
                    boostWindSource = null;
                }
            }, 150);
        }

        function playBoostEnd() {
            if (!audioCtx) initAudio();

            // HELLBAT MODE: Use refined turbine spin-down sound
            if (currentMode === 1) {
                playHellbatBoostEnd();
                return;
            }

            // STEALTH MODE: Quiet exit
            if (currentMode === 2) {
                stopBoostWind();
                // Soft electronic fade
                playSound(400, 'sine', 0.15, 0.04);
                return;
            }

            // NORMAL MODE: Standard boost end
            stopBoostWind();

            // Pressure release whoof
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();
            const filter = audioCtx.createBiquadFilter();

            osc.type = 'sine';
            osc.frequency.setValueAtTime(400, audioCtx.currentTime);
            osc.frequency.exponentialRampToValueAtTime(80, audioCtx.currentTime + 0.25);

            filter.type = 'lowpass';
            filter.frequency.setValueAtTime(800, audioCtx.currentTime);
            filter.frequency.exponentialRampToValueAtTime(200, audioCtx.currentTime + 0.25);

            osc.connect(filter);
            filter.connect(gain);
            gain.connect(audioCtx.destination);

            gain.gain.setValueAtTime(0.15, audioCtx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.25);

            osc.start();
            osc.stop(audioCtx.currentTime + 0.3);

            // Air release hiss
            const hissBuffer = audioCtx.createBuffer(1, audioCtx.sampleRate * 0.2, audioCtx.sampleRate);
            const hissData = hissBuffer.getChannelData(0);
            for (let i = 0; i < hissData.length; i++) {
                hissData[i] = (Math.random() * 2 - 1) * Math.exp(-i / (audioCtx.sampleRate * 0.08));
            }

            const hissSource = audioCtx.createBufferSource();
            hissSource.buffer = hissBuffer;

            const hissGain = audioCtx.createGain();
            const hissFilter = audioCtx.createBiquadFilter();
            hissFilter.type = 'highpass';
            hissFilter.frequency.value = 2000;

            hissSource.connect(hissFilter);
            hissFilter.connect(hissGain);
            hissGain.connect(audioCtx.destination);
            hissGain.gain.value = 0.08;

            hissSource.start();
        }

        // ========== TURN/MANEUVER SOUNDS ==========
        function playTurnAirSlice(intensity) {
            if (!audioCtx) initAudio();
            if (currentMode === 2) intensity *= 0.3; // Quieter in stealth
            if (intensity < 0.3) return;

            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();
            const filter = audioCtx.createBiquadFilter();

            osc.type = 'triangle';
            osc.frequency.setValueAtTime(600 + intensity * 400, audioCtx.currentTime);
            osc.frequency.exponentialRampToValueAtTime(200, audioCtx.currentTime + 0.1);

            filter.type = 'bandpass';
            filter.frequency.value = 800;
            filter.Q.value = 2;

            osc.connect(filter);
            filter.connect(gain);
            gain.connect(audioCtx.destination);

            gain.gain.setValueAtTime(0.04 * intensity, audioCtx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.1);

            osc.start();
            osc.stop(audioCtx.currentTime + 0.12);
        }

        // Gyroscopic stabilization sound
        function playGyroStabilizeSound() {
            if (!audioCtx) initAudio();

            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();

            osc.type = 'sine';
            osc.frequency.value = 220;

            osc.connect(gain);
            gain.connect(audioCtx.destination);

            gain.gain.setValueAtTime(0.02, audioCtx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.15);

            osc.start();
            osc.stop(audioCtx.currentTime + 0.15);
        }

        // Hellbat armor clank on sharp turns
        function playArmorClank() {
            if (!audioCtx) initAudio();
            if (currentMode !== 1) return;

            // Metallic clank
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();

            osc.type = 'square';
            osc.frequency.setValueAtTime(180, audioCtx.currentTime);
            osc.frequency.exponentialRampToValueAtTime(80, audioCtx.currentTime + 0.05);

            osc.connect(gain);
            gain.connect(audioCtx.destination);

            gain.gain.setValueAtTime(0.06, audioCtx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.08);

            osc.start();
            osc.stop(audioCtx.currentTime + 0.1);

            // Metal resonance
            playSound(400, 'sine', 0.05, 0.03);
        }

        // ========== ENGINE SOUNDS ==========
        function startEngineSound() {
            if (!audioCtx) initAudio();
            if (isEngineRunning) return;
            isEngineRunning = true;

            // Main engine oscillator
            engineOsc = audioCtx.createOscillator();
            engineGain = audioCtx.createGain();
            engineFilter = audioCtx.createBiquadFilter();

            // Secondary oscillator for richer sound
            const engineOsc2 = audioCtx.createOscillator();
            const engineGain2 = audioCtx.createGain();

            // Noise generator for engine rumble
            const noiseBuffer = audioCtx.createBuffer(1, audioCtx.sampleRate * 2, audioCtx.sampleRate);
            const noiseData = noiseBuffer.getChannelData(0);
            for (let i = 0; i < noiseData.length; i++) {
                noiseData[i] = Math.random() * 2 - 1;
            }
            const noiseSource = audioCtx.createBufferSource();
            noiseSource.buffer = noiseBuffer;
            noiseSource.loop = true;

            const noiseGain = audioCtx.createGain();
            const noiseFilter = audioCtx.createBiquadFilter();
            noiseFilter.type = 'lowpass';
            noiseFilter.frequency.value = 200;

            // Configure main engine
            engineOsc.type = 'sawtooth';
            engineOsc.frequency.value = 80;
            engineFilter.type = 'lowpass';
            engineFilter.frequency.value = 400;
            engineGain.gain.value = 0.03;

            // Configure secondary engine
            engineOsc2.type = 'triangle';
            engineOsc2.frequency.value = 120;
            engineGain2.gain.value = 0.02;

            // Configure noise
            noiseGain.gain.value = 0.015;

            // Connect main engine
            engineOsc.connect(engineFilter);
            engineFilter.connect(engineGain);
            engineGain.connect(audioCtx.destination);

            // Connect secondary
            engineOsc2.connect(engineGain2);
            engineGain2.connect(audioCtx.destination);

            // Connect noise
            noiseSource.connect(noiseFilter);
            noiseFilter.connect(noiseGain);
            noiseGain.connect(audioCtx.destination);

            engineOsc.start();
            engineOsc2.start();
            noiseSource.start();

            // Store references for updates
            engineOsc.secondary = engineOsc2;
            engineOsc.noise = noiseSource;
            engineOsc.noiseGain = noiseGain;
            engineOsc.secondaryGain = engineGain2;
        }

        function updateEngineSound(speed, maxSpeed, mode) {
            if (!isEngineRunning || !engineOsc) return;

            const speedRatio = speed / maxSpeed;

            // Mode-specific engine characteristics
            switch (mode) {
                case 0: // Normal - clean jet engine roar
                    engineOsc.frequency.value = 60 + speedRatio * 80;
                    engineFilter.frequency.value = 300 + speedRatio * 400;
                    engineGain.gain.value = 0.02 + speedRatio * 0.02;
                    if (engineOsc.noiseGain) engineOsc.noiseGain.gain.value = 0.01 + speedRatio * 0.01;
                    break;

                case 1: // Hellbat - deeper, aggressive with distortion
                    engineOsc.frequency.value = 40 + speedRatio * 60;
                    engineFilter.frequency.value = 200 + speedRatio * 300;
                    engineGain.gain.value = 0.03 + speedRatio * 0.04;
                    if (engineOsc.secondary) engineOsc.secondary.frequency.value = 80 + speedRatio * 40;
                    if (engineOsc.noiseGain) engineOsc.noiseGain.gain.value = 0.02 + speedRatio * 0.02;
                    break;

                case 2: // Stealth - muted, whisper-like hum
                    engineOsc.frequency.value = 100 + speedRatio * 30;
                    engineFilter.frequency.value = 150 + speedRatio * 100;
                    engineGain.gain.value = 0.008 + speedRatio * 0.005;
                    if (engineOsc.noiseGain) engineOsc.noiseGain.gain.value = 0.003;
                    break;
            }
        }

        function stopEngineSound() {
            if (!isEngineRunning) return;
            isEngineRunning = false;

            if (engineOsc) {
                engineOsc.stop();
                if (engineOsc.secondary) engineOsc.secondary.stop();
                if (engineOsc.noise) engineOsc.noise.stop();
                engineOsc = null;
            }
        }

        // ========== MISSILE SOUNDS ==========
        let missileVariation = 0;
        function playMissileSound() {
            if (!audioCtx) initAudio();

            // Sharp launch click
            playSound(2000 + Math.random() * 500, 'square', 0.03, 0.15);

            // Fast whoosh with pitch variation to avoid repetition
            missileVariation = (missileVariation + 1) % 5;
            const pitchOffset = (missileVariation - 2) * 30;

            setTimeout(() => {
                const osc = audioCtx.createOscillator();
                const gain = audioCtx.createGain();
                const filter = audioCtx.createBiquadFilter();

                osc.type = 'sawtooth';
                osc.frequency.value = 400 + pitchOffset;
                filter.type = 'bandpass';
                filter.frequency.value = 600 + pitchOffset;
                filter.Q.value = 2;

                osc.connect(filter);
                filter.connect(gain);
                gain.connect(audioCtx.destination);

                gain.gain.setValueAtTime(0.12, audioCtx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.25);
                osc.frequency.exponentialRampToValueAtTime(200 + pitchOffset, audioCtx.currentTime + 0.25);

                osc.start();
                osc.stop(audioCtx.currentTime + 0.25);
            }, 30);
        }

        // Missile impact - heavy and satisfying
        function playMissileImpact() {
            if (!audioCtx) initAudio();

            // Low thump
            playSound(60, 'sine', 0.3, 0.3);

            // Explosion crackle
            setTimeout(() => {
                const noiseBuffer = audioCtx.createBuffer(1, audioCtx.sampleRate * 0.3, audioCtx.sampleRate);
                const noiseData = noiseBuffer.getChannelData(0);
                for (let i = 0; i < noiseData.length; i++) {
                    noiseData[i] = (Math.random() * 2 - 1) * Math.exp(-i / (audioCtx.sampleRate * 0.1));
                }
                const noiseSource = audioCtx.createBufferSource();
                noiseSource.buffer = noiseBuffer;

                const gain = audioCtx.createGain();
                const filter = audioCtx.createBiquadFilter();
                filter.type = 'lowpass';
                filter.frequency.value = 800;

                noiseSource.connect(filter);
                filter.connect(gain);
                gain.connect(audioCtx.destination);
                gain.gain.value = 0.25;

                noiseSource.start();
            }, 20);
        }

        // ========== BULLET SOUNDS ==========
        let bulletSoundCooldown = 0;
        function playBulletSound() {
            if (!audioCtx) initAudio();
            if (bulletSoundCooldown > 0) return;
            bulletSoundCooldown = 3; // Prevent sound spam

            // Rapid-fire mechanical gun - crisp and punchy
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();
            const filter = audioCtx.createBiquadFilter();

            osc.type = 'square';
            osc.frequency.value = 150 + Math.random() * 50;
            filter.type = 'highpass';
            filter.frequency.value = 100;

            osc.connect(filter);
            filter.connect(gain);
            gain.connect(audioCtx.destination);

            gain.gain.setValueAtTime(0.08, audioCtx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.04);

            osc.start();
            osc.stop(audioCtx.currentTime + 0.04);

            // Add click transient
            playSound(3000, 'square', 0.01, 0.05);
        }

        // ========== AIMING & LOCK-ON SOUNDS ==========
        function playAimEnterSound() {
            if (!audioCtx) initAudio();

            // Soft digital rise on right-click aim
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();

            osc.type = 'sine';
            osc.frequency.setValueAtTime(200, audioCtx.currentTime);
            osc.frequency.exponentialRampToValueAtTime(500, audioCtx.currentTime + 0.15);

            osc.connect(gain);
            gain.connect(audioCtx.destination);

            gain.gain.setValueAtTime(0.06, audioCtx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.2);

            osc.start();
            osc.stop(audioCtx.currentTime + 0.2);

            // Time-stretch whoomp for slow-mo activation
            playSlowMoWhoomp();
        }

        // Time-stretch whoomp when 0.25x slow-mo activates
        function playSlowMoWhoomp() {
            if (!audioCtx) initAudio();

            // Deep stretched bass
            const bassOsc = audioCtx.createOscillator();
            const bassGain = audioCtx.createGain();
            const bassFilter = audioCtx.createBiquadFilter();

            bassOsc.type = 'sine';
            bassOsc.frequency.setValueAtTime(80, audioCtx.currentTime);
            bassOsc.frequency.exponentialRampToValueAtTime(40, audioCtx.currentTime + 0.4);

            bassFilter.type = 'lowpass';
            bassFilter.frequency.value = 150;

            bassOsc.connect(bassFilter);
            bassFilter.connect(bassGain);
            bassGain.connect(audioCtx.destination);

            bassGain.gain.setValueAtTime(0.2, audioCtx.currentTime);
            bassGain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.5);

            bassOsc.start();
            bassOsc.stop(audioCtx.currentTime + 0.5);

            // Ethereal shimmer layer
            const shimmerOsc = audioCtx.createOscillator();
            const shimmerGain = audioCtx.createGain();

            shimmerOsc.type = 'sine';
            shimmerOsc.frequency.setValueAtTime(600, audioCtx.currentTime);
            shimmerOsc.frequency.exponentialRampToValueAtTime(300, audioCtx.currentTime + 0.3);

            shimmerOsc.connect(shimmerGain);
            shimmerGain.connect(audioCtx.destination);

            shimmerGain.gain.setValueAtTime(0.04, audioCtx.currentTime);
            shimmerGain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.3);

            shimmerOsc.start();
            shimmerOsc.stop(audioCtx.currentTime + 0.35);
        }

        // Tracking ticks while aiming at enemy
        function startTrackingSound() {
            if (trackingTickInterval) return;

            trackingTickInterval = setInterval(() => {
                if (!audioCtx) initAudio();
                // Subtle tick sound
                playSound(1200, 'sine', 0.02, 0.04);
            }, 400);
        }

        function stopTrackingSound() {
            if (trackingTickInterval) {
                clearInterval(trackingTickInterval);
                trackingTickInterval = null;
            }
        }

        function playAimExitSound() {
            if (!audioCtx) initAudio();
            stopTrackingSound();

            // Clean snap-back sound when slow-motion ends
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();

            osc.type = 'sine';
            osc.frequency.setValueAtTime(500, audioCtx.currentTime);
            osc.frequency.exponentialRampToValueAtTime(150, audioCtx.currentTime + 0.08);

            osc.connect(gain);
            gain.connect(audioCtx.destination);

            gain.gain.setValueAtTime(0.1, audioCtx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.1);

            osc.start();
            osc.stop(audioCtx.currentTime + 0.12);

            // Quick woosh back to normal time
            const whooshOsc = audioCtx.createOscillator();
            const whooshGain = audioCtx.createGain();

            whooshOsc.type = 'triangle';
            whooshOsc.frequency.setValueAtTime(300, audioCtx.currentTime);
            whooshOsc.frequency.exponentialRampToValueAtTime(100, audioCtx.currentTime + 0.1);

            whooshOsc.connect(whooshGain);
            whooshGain.connect(audioCtx.destination);

            whooshGain.gain.setValueAtTime(0.06, audioCtx.currentTime);
            whooshGain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.1);

            whooshOsc.start();
            whooshOsc.stop(audioCtx.currentTime + 0.12);
        }

        // Lock-on beep - sharp red alert
        function playLockBeep() {
            if (!audioCtx) initAudio();
            // Sharp alert beep
            playSound(1200, 'sine', 0.04, 0.1);
        }

        // Lock acquired - sharp red alert confirmation
        function playLockedSound() {
            if (!audioCtx) initAudio();

            // Sharp double beep - confident lock confirmation
            playSound(1000, 'square', 0.06, 0.12);
            setTimeout(() => playSound(1400, 'square', 0.08, 0.15), 100);

            // Add subtle bass confirmation
            setTimeout(() => playSound(200, 'sine', 0.1, 0.08), 50);
        }

        // Lock loss - soft decay tone
        function playLockLossSound() {
            if (!audioCtx) initAudio();

            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();

            osc.type = 'sine';
            osc.frequency.setValueAtTime(800, audioCtx.currentTime);
            osc.frequency.exponentialRampToValueAtTime(200, audioCtx.currentTime + 0.3);

            osc.connect(gain);
            gain.connect(audioCtx.destination);

            gain.gain.setValueAtTime(0.08, audioCtx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.35);

            osc.start();
            osc.stop(audioCtx.currentTime + 0.4);
        }

        // ========== DEATH RAY SOUNDS (HELLBAT ONLY) ==========
        let deathRayOsc = null;
        let deathRayGain = null;

        function playDeathRayStart() {
            if (!audioCtx) initAudio();

            // Deep energy charge-up
            const chargeOsc = audioCtx.createOscillator();
            const chargeGain = audioCtx.createGain();

            chargeOsc.type = 'sawtooth';
            chargeOsc.frequency.value = 50;
            chargeOsc.frequency.exponentialRampToValueAtTime(150, audioCtx.currentTime + 0.3);

            chargeOsc.connect(chargeGain);
            chargeGain.connect(audioCtx.destination);

            chargeGain.gain.setValueAtTime(0.2, audioCtx.currentTime);
            chargeGain.gain.linearRampToValueAtTime(0.35, audioCtx.currentTime + 0.3);

            chargeOsc.start();
            chargeOsc.stop(audioCtx.currentTime + 0.3);

            // Start continuous beam hum after charge
            setTimeout(() => {
                if (!isDeathRayActive) return;

                deathRayOsc = audioCtx.createOscillator();
                const deathRayOsc2 = audioCtx.createOscillator();
                deathRayGain = audioCtx.createGain();
                const filter = audioCtx.createBiquadFilter();

                deathRayOsc.type = 'sawtooth';
                deathRayOsc.frequency.value = 80;
                deathRayOsc2.type = 'square';
                deathRayOsc2.frequency.value = 120;

                filter.type = 'lowpass';
                filter.frequency.value = 300;

                deathRayOsc.connect(filter);
                deathRayOsc2.connect(filter);
                filter.connect(deathRayGain);
                deathRayGain.connect(audioCtx.destination);

                deathRayGain.gain.value = 0.15;

                deathRayOsc.start();
                deathRayOsc2.start();

                deathRayOsc.secondary = deathRayOsc2;
            }, 250);
        }

        function playDeathRayHit() {
            if (!audioCtx) initAudio();

            // Distortion crackle and burn
            const noiseBuffer = audioCtx.createBuffer(1, audioCtx.sampleRate * 0.1, audioCtx.sampleRate);
            const noiseData = noiseBuffer.getChannelData(0);
            for (let i = 0; i < noiseData.length; i++) {
                noiseData[i] = (Math.random() * 2 - 1) * 0.5;
            }
            const noiseSource = audioCtx.createBufferSource();
            noiseSource.buffer = noiseBuffer;

            const gain = audioCtx.createGain();
            const distortion = audioCtx.createWaveShaper();

            // Create distortion curve
            const curve = new Float32Array(256);
            for (let i = 0; i < 256; i++) {
                const x = (i / 128) - 1;
                curve[i] = Math.tanh(x * 3);
            }
            distortion.curve = curve;

            noiseSource.connect(distortion);
            distortion.connect(gain);
            gain.connect(audioCtx.destination);
            gain.gain.value = 0.1;

            noiseSource.start();
        }

        function stopDeathRaySound() {
            if (deathRayOsc) {
                deathRayGain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.1);
                setTimeout(() => {
                    if (deathRayOsc) {
                        deathRayOsc.stop();
                        if (deathRayOsc.secondary) deathRayOsc.secondary.stop();
                        deathRayOsc = null;
                    }
                }, 100);
            }
        }

        // ========== STEALTH GROUND BOUNCE ==========
        function playStealthBounceSound() {
            if (!audioCtx) initAudio();

            // Soft impact thud
            playSound(100, 'sine', 0.15, 0.2);

            // Controlled upward boost sound
            setTimeout(() => {
                const osc = audioCtx.createOscillator();
                const gain = audioCtx.createGain();

                osc.type = 'sine';
                osc.frequency.value = 200;
                osc.frequency.exponentialRampToValueAtTime(600, audioCtx.currentTime + 0.3);

                osc.connect(gain);
                gain.connect(audioCtx.destination);

                gain.gain.setValueAtTime(0.15, audioCtx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.3);

                osc.start();
                osc.stop(audioCtx.currentTime + 0.3);
            }, 50);

            // Forcefield shimmer
            setTimeout(() => playSound(800, 'sine', 0.1, 0.08), 100);
            setTimeout(() => playSound(1000, 'sine', 0.08, 0.06), 150);
        }

        // ========== CRASH SOUNDS ==========
        function playCrashSound() {
            if (!audioCtx) initAudio();

            // Metal tearing
            const noiseBuffer = audioCtx.createBuffer(1, audioCtx.sampleRate * 0.5, audioCtx.sampleRate);
            const noiseData = noiseBuffer.getChannelData(0);
            for (let i = 0; i < noiseData.length; i++) {
                noiseData[i] = (Math.random() * 2 - 1) * Math.exp(-i / (audioCtx.sampleRate * 0.2));
            }
            const noiseSource = audioCtx.createBufferSource();
            noiseSource.buffer = noiseBuffer;

            const gain = audioCtx.createGain();
            const filter = audioCtx.createBiquadFilter();
            filter.type = 'bandpass';
            filter.frequency.value = 2000;
            filter.Q.value = 0.5;

            noiseSource.connect(filter);
            filter.connect(gain);
            gain.connect(audioCtx.destination);
            gain.gain.value = 0.3;

            noiseSource.start();

            // Sparks
            for (let i = 0; i < 5; i++) {
                setTimeout(() => {
                    playSound(3000 + Math.random() * 2000, 'square', 0.02, 0.08);
                }, i * 50);
            }

            // Heavy explosion
            setTimeout(() => {
                playSound(40, 'sawtooth', 0.6, 0.5);
                playSound(60, 'square', 0.4, 0.4);
            }, 100);

            // Cut to near-silence
            setTimeout(() => {
                if (audioCtx) {
                    // Brief silence effect before game over
                }
            }, 400);
        }

        // ========== GAME OVER SOUNDS ==========
        function playGameOverSound() {
            if (!audioCtx) initAudio();

            // Low bass hit on skull appearance
            playSound(30, 'sine', 0.8, 0.4);
            playSound(50, 'triangle', 0.6, 0.3);

            // Ambient hum
            setTimeout(() => {
                const osc = audioCtx.createOscillator();
                const gain = audioCtx.createGain();

                osc.type = 'sine';
                osc.frequency.value = 60;

                osc.connect(gain);
                gain.connect(audioCtx.destination);
                gain.gain.value = 0.05;

                osc.start();

                // Fade out after 3 seconds
                setTimeout(() => {
                    gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 1);
                    setTimeout(() => osc.stop(), 1000);
                }, 3000);
            }, 200);
        }

        function playButtonHover() {
            playSound(600, 'sine', 0.05, 0.05);
        }

        function playButtonClick() {
            playSound(800, 'sine', 0.08, 0.1);
        }

        // ========== DOMAIN WARNING SOUNDS ==========
        function playDomainWarningBeep(count) {
            if (!audioCtx) initAudio();

            // Calm but firm countdown beep
            const freq = count === 1 ? 600 : (count === 2 ? 500 : 400);
            playSound(freq, 'sine', 0.2, 0.15);
            playSound(freq * 1.5, 'sine', 0.1, 0.08);
        }

        function playReturnWarpSound() {
            if (!audioCtx) initAudio();

            // Short warp sound
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();

            osc.type = 'sine';
            osc.frequency.value = 200;
            osc.frequency.exponentialRampToValueAtTime(800, audioCtx.currentTime + 0.15);
            osc.frequency.exponentialRampToValueAtTime(400, audioCtx.currentTime + 0.3);

            osc.connect(gain);
            gain.connect(audioCtx.destination);

            gain.gain.setValueAtTime(0.2, audioCtx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.3);

            osc.start();
            osc.stop(audioCtx.currentTime + 0.3);
        }

        // ========== MODE SWITCH SOUNDS ==========
        function playModeSwitch() {
            if (!audioCtx) initAudio();

            // Mode-specific transformation sound
            const baseFreq = currentMode === 1 ? 300 : (currentMode === 2 ? 500 : 400);

            playSound(baseFreq, 'sine', 0.1, 0.12);
            setTimeout(() => playSound(baseFreq + 200, 'sine', 0.1, 0.15), 50);
            setTimeout(() => playSound(baseFreq + 400, 'sine', 0.15, 0.18), 100);

            // Mechanical whir with mode personality
            setTimeout(() => {
                const osc = audioCtx.createOscillator();
                const gain = audioCtx.createGain();

                osc.type = currentMode === 1 ? 'sawtooth' : 'triangle';
                osc.frequency.setValueAtTime(80, audioCtx.currentTime);
                osc.frequency.exponentialRampToValueAtTime(250, audioCtx.currentTime + 0.2);

                osc.connect(gain);
                gain.connect(audioCtx.destination);

                const vol = currentMode === 2 ? 0.04 : 0.08; // Quieter for stealth
                gain.gain.setValueAtTime(vol, audioCtx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.2);

                osc.start();
                osc.stop(audioCtx.currentTime + 0.25);
            }, 80);

            // Hellbat armor settling clank
            if (currentMode === 1) {
                setTimeout(() => playArmorClank(), 200);
            }
        }

        // ========== ENVIRONMENTAL AUDIO ==========
        // Cloud pass-through muffled rush
        function playCloudPassSound() {
            if (!audioCtx) initAudio();
            if (currentMode === 2) return; // Silent in stealth

            // Muffled whoosh
            const noiseBuffer = audioCtx.createBuffer(1, audioCtx.sampleRate * 0.4, audioCtx.sampleRate);
            const noiseData = noiseBuffer.getChannelData(0);
            for (let i = 0; i < noiseData.length; i++) {
                noiseData[i] = (Math.random() * 2 - 1) * 0.4;
            }

            const noiseSource = audioCtx.createBufferSource();
            noiseSource.buffer = noiseBuffer;

            const filter = audioCtx.createBiquadFilter();
            filter.type = 'lowpass';
            filter.frequency.value = 400;

            const gain = audioCtx.createGain();
            gain.gain.setValueAtTime(0.06, audioCtx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.4);

            noiseSource.connect(filter);
            filter.connect(gain);
            gain.connect(audioCtx.destination);

            noiseSource.start();
        }

        // Terrain proximity rush - louder near hills
        let terrainRushGain = null;
        let terrainRushActive = false;

        function updateTerrainRush(distanceToGround, speed) {
            if (!audioCtx) return;

            // Only audible when close to terrain and moving fast
            const proximity = Math.max(0, 1 - distanceToGround / 200);
            const speedFactor = speed / 8;
            const intensity = proximity * speedFactor * 0.08;

            if (intensity > 0.01 && !terrainRushActive) {
                startTerrainRush();
            }

            if (terrainRushGain) {
                terrainRushGain.gain.value = Math.min(0.1, intensity) * modeAudioSettings[currentMode].windVol;
            }
        }

        function startTerrainRush() {
            if (!audioCtx) initAudio();
            if (terrainRushActive) return;
            terrainRushActive = true;

            const bufferSize = audioCtx.sampleRate * 2;
            const noiseBuffer = audioCtx.createBuffer(1, bufferSize, audioCtx.sampleRate);
            const data = noiseBuffer.getChannelData(0);
            for (let i = 0; i < bufferSize; i++) {
                data[i] = (Math.random() * 2 - 1) * 0.6;
            }

            terrainRumbleSource = audioCtx.createBufferSource();
            terrainRumbleSource.buffer = noiseBuffer;
            terrainRumbleSource.loop = true;

            const filter = audioCtx.createBiquadFilter();
            filter.type = 'bandpass';
            filter.frequency.value = 600;
            filter.Q.value = 1;

            terrainRushGain = audioCtx.createGain();
            terrainRushGain.gain.value = 0;

            terrainRumbleSource.connect(filter);
            filter.connect(terrainRushGain);
            terrainRushGain.connect(audioCtx.destination);

            terrainRumbleSource.start();
        }

        function stopTerrainRush() {
            if (!terrainRushActive) return;
            terrainRushActive = false;
            if (terrainRumbleSource) {
                try { terrainRumbleSource.stop(); } catch (e) { }
                terrainRumbleSource = null;
            }
        }

        // Ground rumble at high speed and low altitude
        function playGroundRumble(speed, altitude) {
            if (!audioCtx) initAudio();
            if (altitude > 150 || speed < 4) return;

            const intensity = (1 - altitude / 150) * (speed / 8);
            if (intensity < 0.2) return;

            // Low frequency rumble
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();

            osc.type = 'sine';
            osc.frequency.value = 35 + Math.random() * 15;

            osc.connect(gain);
            gain.connect(audioCtx.destination);

            const vol = 0.06 * intensity * modeAudioSettings[currentMode].bassPunch;
            gain.gain.setValueAtTime(vol, audioCtx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.2);

            osc.start();
            osc.stop(audioCtx.currentTime + 0.25);
        }

        // Domain boundary warning pulse
        function playDomainWarningPulse() {
            if (!audioCtx) initAudio();

            // Subtle warning pulse
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();

            osc.type = 'sine';
            osc.frequency.value = 150;

            osc.connect(gain);
            gain.connect(audioCtx.destination);

            // Pulsing gain
            gain.gain.setValueAtTime(0.03, audioCtx.currentTime);
            gain.gain.linearRampToValueAtTime(0.08, audioCtx.currentTime + 0.15);
            gain.gain.linearRampToValueAtTime(0.03, audioCtx.currentTime + 0.3);
            gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.5);

            osc.start();
            osc.stop(audioCtx.currentTime + 0.5);
        }

        // ========== EXPLOSION SOUND ==========
        function playExplosion() {
            if (!audioCtx) initAudio();

            // Bass thump
            playSound(50, 'sine', 0.3, 0.25);

            // Explosion noise
            const noiseBuffer = audioCtx.createBuffer(1, audioCtx.sampleRate * 0.4, audioCtx.sampleRate);
            const noiseData = noiseBuffer.getChannelData(0);
            for (let i = 0; i < noiseData.length; i++) {
                noiseData[i] = (Math.random() * 2 - 1) * Math.exp(-i / (audioCtx.sampleRate * 0.15));
            }
            const noiseSource = audioCtx.createBufferSource();
            noiseSource.buffer = noiseBuffer;

            const gain = audioCtx.createGain();
            const filter = audioCtx.createBiquadFilter();
            filter.type = 'lowpass';
            filter.frequency.value = 1000;

            noiseSource.connect(filter);
            filter.connect(gain);
            gain.connect(audioCtx.destination);
            gain.gain.value = 0.2;

            noiseSource.start();
        }

        // Game State
        let gameStarted = false;
        let score = 0, kills = 0, health = 100;
        let enemies = [], bullets = [], enemyBullets = [], missiles = [], explosions = [];
        let missileTrails = []; // Smoke trail particles for missiles
        let wingRecoil = { left: 0, right: 0 }; // Wing recoil animation state

        // Domain - Expanded for long-distance flight
        const DOMAIN_RADIUS = 15000;
        let isOutsideDomain = false, domainWarningCountdown = 3, domainCountdownTimer = 0;

        // ========== ENEMY ZONE SYSTEM ==========
        // Zone-based spawning for distributed enemy population
        const ZONE_NEAR = 800;       // 0-800: High density patrol/intercept
        const ZONE_MID = 3000;       // 800-3000: Medium density mixed
        const ZONE_FAR = 8000;       // 3000-8000: Low density assault squads
        const ZONE_FRONTIER = 15000; // 8000+: Rare stealth hunters
        const MAX_ENEMIES = 15;      // Performance cap
        const ENEMY_DESPAWN_DISTANCE = 2500; // Clean up distant enemies
        let enemySpawnTimer = 0;
        const ENEMY_SPAWN_INTERVAL = 90; // ~1.5 seconds between spawn checks

        // Modes: 0 = Normal, 1 = Hellbat, 2 = Stealth
        let currentMode = 0;
        const modeNames = ['NORMAL', 'HELLBAT', 'STEALTH'];
        let executionCharge = 100, executionCooldown = 0, isExecutionBeamActive = false, executionBeam = null;
        let forcefieldActive = false, forcefieldTimer = 0, forcefieldMaxTime = 180 * 60, absorbedDamage = 0, shockwaveReady = false;
        let dashCooldown = 0, isDashing = false, dashTimer = 0, isInvincible = false;
        let fireCooldown = 0, missileCooldown = 0;

        // Crash system
        let isCrashing = false;
        let crashDebris = [];
        let crashCause = 'TERRAIN COLLISION';
        const GROUND_LEVEL = -50;
        const CRASH_HEIGHT = 25; // Height at which crash triggers

        // Aiming system
        let isAiming = false;
        let timeScale = 1;
        let lockProgress = 0;
        let lockedEnemy = null;
        let lockTimer = 0;
        const LOCK_TIME = 40; // ~0.5-0.8 seconds at 60fps (faster with slow-mo)
        const LOCK_PERSIST_TIME = 120; // Lock persists for ~2 seconds
        let aimTarget = null;
        let lockPersistTimer = 0;

        const modeStats = {
            0: { speedMult: 1, turnMult: 1, fireRate: 8, bulletDamage: 10 },
            1: { speedMult: 2.2, turnMult: 2, fireRate: 3, bulletDamage: 18 },
            2: { speedMult: 0.8, turnMult: 1.2, fireRate: 12, bulletDamage: 8 }
        };

        // Three.js Setup
        const scene = new THREE.Scene();
        scene.fog = new THREE.Fog(0xcceebb, 2000, 18000);
        const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 25000);
        const renderer = new THREE.WebGLRenderer({ antialias: true });
        renderer.setSize(window.innerWidth, window.innerHeight);
        renderer.setClearColor(0xcceebb);
        renderer.shadowMap.enabled = true;
        renderer.shadowMap.type = THREE.PCFSoftShadowMap;
        document.getElementById('gameContainer').insertBefore(renderer.domElement, document.getElementById('gameContainer').firstChild);

        // Enhanced Lighting
        scene.add(new THREE.AmbientLight(0xffffff, 0.6));
        const sun = new THREE.DirectionalLight(0xfffaed, 1.0);
        sun.position.set(500, 600, -300);
        sun.castShadow = true;
        sun.shadow.mapSize.width = 2048;
        sun.shadow.mapSize.height = 2048;
        sun.shadow.camera.near = 100;
        sun.shadow.camera.far = 8000;
        scene.add(sun);

        // Hemisphere light for realistic outdoor lighting
        const hemiLight = new THREE.HemisphereLight(0x87ceeb, 0x3a5a2a, 0.6);
        scene.add(hemiLight);

        // Realistic sky gradient sphere
        const skyGeo = new THREE.SphereGeometry(25000, 64, 64);
        const skyMat = new THREE.ShaderMaterial({
            uniforms: {
                topColor: { value: new THREE.Color(0x1e6090) },
                midColor: { value: new THREE.Color(0x87ceeb) },
                bottomColor: { value: new THREE.Color(0xc9e4ca) },
                sunPosition: { value: new THREE.Vector3(500, 400, -300) }
            },
            vertexShader: `
                varying vec3 vWorldPosition;
                void main() {
                    vec4 worldPosition = modelMatrix * vec4(position, 1.0);
                    vWorldPosition = worldPosition.xyz;
                    gl_Position = projectionMatrix * modelViewMatrix * vec4(position, 1.0);
                }
            `,
            fragmentShader: `
                uniform vec3 topColor;
                uniform vec3 midColor;
                uniform vec3 bottomColor;
                uniform vec3 sunPosition;
                varying vec3 vWorldPosition;
                void main() {
                    float h = normalize(vWorldPosition).y;
                    vec3 color;
                    if (h > 0.0) {
                        color = mix(midColor, topColor, pow(h, 0.5));
                    } else {
                        color = mix(midColor, bottomColor, pow(-h, 0.3));
                    }
                    // Add sun glow
                    vec3 sunDir = normalize(sunPosition);
                    vec3 viewDir = normalize(vWorldPosition);
                    float sunAngle = max(dot(viewDir, sunDir), 0.0);
                    color += vec3(1.0, 0.95, 0.8) * pow(sunAngle, 32.0) * 0.5;
                    gl_FragColor = vec4(color, 1.0);
                }
            `,
            side: THREE.BackSide
        });
        scene.add(new THREE.Mesh(skyGeo, skyMat));

        // Realistic clouds - two layers
        const cloudGroups = { slow: [], fast: [] };

        function createRealisticCloud(size, opacity) {
            const group = new THREE.Group();
            const mat = new THREE.MeshLambertMaterial({
                color: 0xffffff,
                transparent: true,
                opacity: opacity,
                depthWrite: false
            });
            const count = 8 + Math.floor(Math.random() * 8);
            for (let i = 0; i < count; i++) {
                const s = size * (0.4 + Math.random() * 0.6);
                const geo = new THREE.SphereGeometry(s, 24, 24);
                const cloud = new THREE.Mesh(geo, mat);
                cloud.position.set(
                    (Math.random() - 0.5) * size * 4,
                    (Math.random() - 0.5) * size * 0.5,
                    (Math.random() - 0.5) * size * 3
                );
                cloud.scale.set(1.5 + Math.random(), 0.5 + Math.random() * 0.3, 1 + Math.random() * 0.5);
                group.add(cloud);
            }
            return group;
        }

        // Slow fluffy clouds (layer 1) - Extended for larger domain
        for (let i = 0; i < 60; i++) {
            const cloud = createRealisticCloud(60 + Math.random() * 50, 0.9);
            cloud.position.set(
                (Math.random() - 0.5) * 30000,
                450 + Math.random() * 350,
                (Math.random() - 0.5) * 30000
            );
            scene.add(cloud);
            cloudGroups.slow.push(cloud);
        }

        // Fast thin wispy clouds (layer 2) - Extended for larger domain
        for (let i = 0; i < 100; i++) {
            const cloud = createRealisticCloud(25 + Math.random() * 20, 0.4);
            cloud.position.set(
                (Math.random() - 0.5) * 30000,
                300 + Math.random() * 250,
                (Math.random() - 0.5) * 30000
            );
            cloud.scale.set(4 + Math.random() * 3, 0.2, 0.6);
            scene.add(cloud);
            cloudGroups.fast.push(cloud);
        }

        // ========== NOISE UTILITIES for TERRAIN ==========
        // Fast Simplex Noise implementation
        class SimplexNoise {
            constructor() {
                this.grad3 = [
                    [1, 1, 0], [-1, 1, 0], [1, -1, 0], [-1, -1, 0],
                    [1, 0, 1], [-1, 0, 1], [1, 0, -1], [-1, 0, -1],
                    [0, 1, 1], [0, -1, 1], [0, 1, -1], [0, -1, -1]
                ];
                this.p = [];
                for (let i = 0; i < 256; i++) {
                    this.p[i] = Math.floor(Math.random() * 256);
                }
                this.perm = [];
                for (let i = 0; i < 512; i++) {
                    this.perm[i] = this.p[i & 255];
                }
            }

            dot(g, x, y) {
                return g[0] * x + g[1] * y;
            }

            noise(xin, yin) {
                let n0, n1, n2;
                const F2 = 0.5 * (Math.sqrt(3.0) - 1.0);
                const s = (xin + yin) * F2;
                const i = Math.floor(xin + s);
                const j = Math.floor(yin + s);
                const G2 = (3.0 - Math.sqrt(3.0)) / 6.0;
                const t = (i + j) * G2;
                const X0 = i - t;
                const Y0 = j - t;
                const x0 = xin - X0;
                const y0 = yin - Y0;

                let i1, j1;
                if (x0 > y0) { i1 = 1; j1 = 0; }
                else { i1 = 0; j1 = 1; }

                const x1 = x0 - i1 + G2;
                const y1 = y0 - j1 + G2;
                const x2 = x0 - 1.0 + 2.0 * G2;
                const y2 = y0 - 1.0 + 2.0 * G2;

                const ii = i & 255;
                const jj = j & 255;
                const gi0 = this.perm[ii + this.perm[jj]] % 12;
                const gi1 = this.perm[ii + i1 + this.perm[jj + j1]] % 12;
                const gi2 = this.perm[ii + 1 + this.perm[jj + 1]] % 12;

                let t0 = 0.5 - x0 * x0 - y0 * y0;
                if (t0 < 0) n0 = 0.0;
                else {
                    t0 *= t0;
                    n0 = t0 * t0 * this.dot(this.grad3[gi0], x0, y0);
                }

                let t1 = 0.5 - x1 * x1 - y1 * y1;
                if (t1 < 0) n1 = 0.0;
                else {
                    t1 *= t1;
                    n1 = t1 * t1 * this.dot(this.grad3[gi1], x1, y1);
                }

                let t2 = 0.5 - x2 * x2 - y2 * y2;
                if (t2 < 0) n2 = 0.0;
                else {
                    t2 *= t2;
                    n2 = t2 * t2 * this.dot(this.grad3[gi2], x2, y2);
                }

                return 70.0 * (n0 + n1 + n2);
            }
        }

        const simplex = new SimplexNoise();

        // Centralized terrain height function for synchronization
        // Using multiple octaves for realistic mountains
        function getTerrainHeight(x, z) {
            // Base ground level
            let y = -50;

            // Octave 1: Large mountains
            y += simplex.noise(x * 0.0003, z * 0.0003) * 600;

            // Octave 2: Rolling hills
            y += simplex.noise(x * 0.001, z * 0.001) * 150;

            // Octave 3: Local details
            y += simplex.noise(x * 0.004, z * 0.004) * 40;

            // Flatten logic for spawn area (Safe Zone)
            const dist = Math.sqrt(x * x + z * z);
            if (dist < 1500) {
                // Smoothly blend from flat (-100) to terrain height
                const blend = Math.max(0, (dist - 500) / 1000); // 0 at 500m, 1 at 1500m
                // Target height is -100 (low ground)
                y = -100 + (y - -100) * blend;
            }

            // Ensure we don't go too low (sea level check if we had water)
            return Math.max(-150, y) - 100; // Lower overall terrain slightly
        }

        // Realistic ground with grass texture shader - Extended for larger domain
        const groundGeo = new THREE.PlaneGeometry(40000, 40000, 500, 500); // Increased resolution
        const vertices = groundGeo.attributes.position.array;
        for (let i = 0; i < vertices.length; i += 3) {
            const x = vertices[i];
            const y = vertices[i + 1];
            // Apply noise-based height
            // Note: Plane is rotated, so 'y' in loop is actually Z in world space
            vertices[i + 2] = getTerrainHeight(x, -y) + 50; // Add 50 offset because mesh is at y=-50
        }
        groundGeo.computeVertexNormals();

        // Grass shader material
        const groundMat = new THREE.ShaderMaterial({
            uniforms: {
                lightDir: { value: new THREE.Vector3(0.5, 0.8, -0.3).normalize() },
                fogColor: { value: new THREE.Color(0xcceebb) },
                fogNear: { value: 1000 },
                fogFar: { value: 8000 }
            },
            vertexShader: `
                varying vec3 vNormal;
                varying vec3 vPosition;
                varying float vFogDepth;
                void main() {
                    vNormal = normalize(normalMatrix * normal);
                    vPosition = position;
                    vec4 mvPosition = modelViewMatrix * vec4(position, 1.0);
                    vFogDepth = -mvPosition.z;
                    gl_Position = projectionMatrix * mvPosition;
                }
            `,
            fragmentShader: `
                uniform vec3 lightDir;
                uniform vec3 fogColor;
                uniform float fogNear;
                uniform float fogFar;
                varying vec3 vNormal;
                varying vec3 vPosition;
                varying float vFogDepth;
                
                // Simplex noise function for texture variation
                float hash(vec2 p) {
                    return fract(sin(dot(p, vec2(127.1, 311.7))) * 43758.5453);
                }
                
                float noise(vec2 p) {
                    vec2 i = floor(p);
                    vec2 f = fract(p);
                    f = f * f * (3.0 - 2.0 * f);
                    float a = hash(i);
                    float b = hash(i + vec2(1.0, 0.0));
                    float c = hash(i + vec2(0.0, 1.0));
                    float d = hash(i + vec2(1.0, 1.0));
                    return mix(mix(a, b, f.x), mix(c, d, f.x), f.y);
                }
                
                void main() {
                    // Height-based coloring
                    float height = vPosition.z; // In local space, Z is height before rotation
                    
                    // Colors
                    vec3 colGrass = vec3(0.2, 0.8, 0.2); // Bright Green
                    vec3 colRock = vec3(0.2, 0.3, 0.2);   // Mossy Green/Rock
                    vec3 colSnow = vec3(0.95, 0.95, 1.0);  // White Snow (Reverted)
                    
                    // Mix factors based on height
                    float rockMix = smoothstep(100.0, 300.0, height);
                    float snowMix = smoothstep(450.0, 600.0, height);
                    
                    // Base color mixing
                    vec3 finalColor = mix(colGrass, colRock, rockMix);
                    finalColor = mix(finalColor, colSnow, snowMix);
                    
                    // Detailed noise variation
                    float n = noise(vPosition.xy * 0.02); // Texture noise
                    finalColor *= (0.9 + n * 0.2); // Reduced noise contrast

                    // Slope-based rock showing through snow/grass (steep = rock)
                    // Normal.z is up in local space
                    float slope = 1.0 - vNormal.z; 
                    if (slope > 0.3) {
                        finalColor = mix(finalColor, colRock, (slope - 0.3) * 2.0);
                    }

                    // Lighting
                    float diff = max(dot(vNormal, lightDir), 0.0);
                    diff = diff * 0.7 + 0.3; // Soft shadows
                    
                    // Specular highlight (removed to avoid metallic/purple sheen)
                    if (rockMix < 0.5 || snowMix > 0.5) {
                         // Removed specular
                    }

                    vec3 color = finalColor * diff;

                    // Fog
                    float fogFactor = smoothstep(fogNear, fogFar, vFogDepth);
                    color = mix(color, fogColor, fogFactor);
                    
                    gl_FragColor = vec4(color, 1.0);
                }
            `
        });

        const ground = new THREE.Mesh(groundGeo, groundMat);
        ground.rotation.x = -Math.PI / 2;
        ground.position.y = -50;
        ground.receiveShadow = true;
        scene.add(ground);

        // ========== TERRAIN ELEMENTS ON NEW HEIGHTMAP ==========
        // (Removed old sphere hills)

        // Domain boundary ring
        const boundaryGeo = new THREE.RingGeometry(DOMAIN_RADIUS - 50, DOMAIN_RADIUS, 128);
        const boundaryMat = new THREE.MeshBasicMaterial({ color: 0x00ffaa, transparent: true, opacity: 0.08, side: THREE.DoubleSide });
        const boundary = new THREE.Mesh(boundaryGeo, boundaryMat);
        boundary.rotation.x = -Math.PI / 2;
        boundary.position.y = 0;
        scene.add(boundary);

        // ========== TERRAIN ELEMENTS ==========

        // --- ROCKY OUTCROPS ---
        function createRock(x, z, scale) {
            const rockGroup = new THREE.Group();
            const rockColors = [0x6b6b6b, 0x7a7a7a, 0x5a5a5a, 0x888888];

            // Main boulder
            const mainGeo = new THREE.DodecahedronGeometry(scale, 1);
            const verts = mainGeo.attributes.position.array;
            for (let i = 0; i < verts.length; i += 3) {
                verts[i] += (Math.random() - 0.5) * scale * 0.3;
                verts[i + 1] += (Math.random() - 0.5) * scale * 0.3;
                verts[i + 2] += (Math.random() - 0.5) * scale * 0.3;
            }
            mainGeo.computeVertexNormals();

            const rockMat = new THREE.MeshLambertMaterial({ color: rockColors[Math.floor(Math.random() * rockColors.length)] });
            const mainRock = new THREE.Mesh(mainGeo, rockMat);
            mainRock.scale.set(1 + Math.random() * 0.5, 0.5 + Math.random() * 0.3, 1 + Math.random() * 0.5);
            mainRock.castShadow = true;
            rockGroup.add(mainRock);

            // Smaller scattered rocks
            for (let i = 0; i < 3 + Math.floor(Math.random() * 4); i++) {
                const smallGeo = new THREE.DodecahedronGeometry(scale * (0.2 + Math.random() * 0.3), 0);
                const smallRock = new THREE.Mesh(smallGeo, rockMat);
                smallRock.position.set(
                    (Math.random() - 0.5) * scale * 2,
                    0,
                    (Math.random() - 0.5) * scale * 2
                );
                smallRock.rotation.set(Math.random() * Math.PI, Math.random() * Math.PI, 0);
                smallRock.castShadow = true;
                rockGroup.add(smallRock);
            }

            // Align to terrain
            const terrainH = getTerrainHeight(x, z);
            rockGroup.position.set(x, terrainH, z);

            // Random rotation to align somewhat with slope
            rockGroup.rotation.x = (Math.random() - 0.5) * 0.5;
            rockGroup.rotation.z = (Math.random() - 0.5) * 0.5;

            return rockGroup;
        }

        // Scatter rocky outcrops across battlefield
        for (let i = 0; i < 60; i++) {
            const angle = Math.random() * Math.PI * 2;
            const dist = 300 + Math.random() * 3500;
            const rock = createRock(
                Math.cos(angle) * dist,
                Math.sin(angle) * dist,
                8 + Math.random() * 20
            );
            scene.add(rock);
        }

        // --- SPARSE LOW-POLY TREES ---
        function createTree(x, z, height) {
            const tree = new THREE.Group();

            // Trunk
            const trunkMat = new THREE.MeshLambertMaterial({ color: 0x5a4030 });
            const trunk = new THREE.Mesh(new THREE.CylinderGeometry(1, 1.5, height * 0.4, 6), trunkMat);
            trunk.position.y = height * 0.2;
            trunk.castShadow = true;
            tree.add(trunk);

            // Foliage layers (conical)
            const foliageColors = [0x2a5a1a, 0x3a6a2a, 0x4a7a3a];
            const foliageMat = new THREE.MeshLambertMaterial({ color: foliageColors[Math.floor(Math.random() * 3)] });

            for (let layer = 0; layer < 3; layer++) {
                const layerHeight = height * (0.35 - layer * 0.08);
                const layerRadius = height * (0.25 - layer * 0.05);
                const foliage = new THREE.Mesh(
                    new THREE.ConeGeometry(layerRadius, layerHeight, 6),
                    foliageMat
                );
                foliage.position.y = height * (0.35 + layer * 0.18);
                foliage.castShadow = true;
                tree.add(foliage);
            }

            // Align to terrain
            const terrainH = getTerrainHeight(x, z);
            tree.position.set(x, terrainH - 1, z);
            return tree;
        }

        // Scatter sparse trees
        for (let i = 0; i < 80; i++) {
            const angle = Math.random() * Math.PI * 2;
            const dist = 400 + Math.random() * 3200;
            const treeObj = createTree(
                Math.cos(angle) * dist + (Math.random() - 0.5) * 100,
                Math.sin(angle) * dist + (Math.random() - 0.5) * 100,
                15 + Math.random() * 25
            );
            scene.add(treeObj);
        }



        // --- HOUSES AND ROADS ---
        function createHouse(x, z, scale = 1) {
            const houseGroup = new THREE.Group();

            // Base
            const baseHeight = 10 * scale;
            const baseWidth = 15 * scale;
            const baseGeo = new THREE.BoxGeometry(baseWidth, baseHeight, baseWidth);
            const baseMat = new THREE.MeshLambertMaterial({ color: 0x8B4513 }); // SaddleBrown
            const base = new THREE.Mesh(baseGeo, baseMat);
            base.position.y = baseHeight / 2;
            base.castShadow = true;
            base.receiveShadow = true;
            houseGroup.add(base);

            // Roof
            const roofHeight = 8 * scale;
            const roofGeo = new THREE.ConeGeometry(baseWidth * 0.8, roofHeight, 4); // Pyramid roof
            const roofMat = new THREE.MeshLambertMaterial({ color: 0x800000 }); // Maroon
            const roof = new THREE.Mesh(roofGeo, roofMat);
            roof.position.y = baseHeight + roofHeight / 2;
            roof.rotation.y = Math.PI / 4; // Align square
            roof.castShadow = true;
            houseGroup.add(roof);

            // Door
            const doorGeo = new THREE.BoxGeometry(4 * scale, 6 * scale, 1 * scale);
            const doorMat = new THREE.MeshLambertMaterial({ color: 0x4a3c31 });
            const door = new THREE.Mesh(doorGeo, doorMat);
            door.position.set(0, 3 * scale, baseWidth / 2 + 0.1);
            houseGroup.add(door);

            // Align to terrain
            const terrainH = getTerrainHeight(x, z);
            houseGroup.position.set(x, terrainH, z);
            return houseGroup;
        }

        function createRoad(startX, startZ, endX, endZ, width = 10) {
            const length = Math.sqrt(Math.pow(endX - startX, 2) + Math.pow(endZ - startZ, 2));
            const angle = Math.atan2(endZ - startZ, endX - startX);

            // Road segment logic
            const roadGeo = new THREE.PlaneGeometry(length, width);
            const roadMat = new THREE.MeshLambertMaterial({
                color: 0x333333,
                side: THREE.DoubleSide
            });
            const road = new THREE.Mesh(roadGeo, roadMat);

            const midX = (startX + endX) / 2;
            const midZ = (startZ + endZ) / 2;

            // Get height at midpoint + small offset
            const terrainH = getTerrainHeight(midX, midZ);

            road.position.set(midX, terrainH + 0.5, midZ); // Slightly above ground
            road.rotation.x = -Math.PI / 2;
            road.rotation.z = -angle;
            road.receiveShadow = true;

            return road;
        }

        // Add a small "town" near spawn
        const townX = 200;
        const townZ = -300;

        // Roads
        scene.add(createRoad(townX - 300, townZ, townX + 300, townZ, 20)); // Main road
        scene.add(createRoad(townX, townZ - 300, townX, townZ + 300, 20)); // Cross road

        // Houses
        scene.add(createHouse(townX + 50, townZ + 50, 1.5));
        scene.add(createHouse(townX - 50, townZ + 50, 1.2));
        scene.add(createHouse(townX + 50, townZ - 50, 1.2));
        scene.add(createHouse(townX - 50, townZ - 50, 1.5));

        // Extra houses along the road
        scene.add(createHouse(townX + 150, townZ + 50, 1.0));
        scene.add(createHouse(townX - 150, townZ + 50, 1.0));
        scene.add(createHouse(townX + 150, townZ - 50, 1.0));
        scene.add(createHouse(townX - 150, townZ - 50, 1.0));


        // Helper to create valid aerodynamic thruster plumes
        function createThrusterPlume() {
            const group = new THREE.Group();

            // Core: Hot, bright center
            const coreGeo = new THREE.CylinderGeometry(0.3, 0.05, 4.5, 8, 1, true);
            coreGeo.translate(0, 2.25, 0); // Pivot at base
            coreGeo.rotateX(-Math.PI / 2); // Point backward
            const coreMat = new THREE.MeshBasicMaterial({
                color: 0xffffff,
                transparent: true,
                opacity: 0.9,
                blending: THREE.AdditiveBlending,
                depthWrite: false
            });
            const core = new THREE.Mesh(coreGeo, coreMat);
            group.add(core);

            // Outer: Colored halo
            const outerGeo = new THREE.CylinderGeometry(0.65, 0.2, 5.0, 16, 1, true);
            outerGeo.translate(0, 2.5, 0);
            outerGeo.rotateX(-Math.PI / 2);
            const outerMat = new THREE.MeshBasicMaterial({
                color: 0x00ffff, // Default to blue
                transparent: true,
                opacity: 0.45,
                blending: THREE.AdditiveBlending,
                depthWrite: false,
                side: THREE.DoubleSide
            });
            const outer = new THREE.Mesh(outerGeo, outerMat);
            group.add(outer);

            // Store for easy access
            group.userData = { core, outer, baseScale: 1.0 };
            return group;
        }

        // ========== REALISTIC MODERN FIGHTER JET ==========
        // Clean aerodynamic shape with matte grey metallic finish
        function createPlayerJet() {
            const jet = new THREE.Group();
            jet.userData.parts = { wings: null, tails: [], hellbat: null, stealth: null };

            // === MATERIALS - Matte Grey Metallic ===
            const bodyMat = new THREE.MeshPhongMaterial({
                color: 0x6b6b70, shininess: 30, specular: 0x333333
            });
            const darkMat = new THREE.MeshPhongMaterial({
                color: 0x4a4a50, shininess: 25, specular: 0x222222
            });
            const panelMat = new THREE.MeshBasicMaterial({ color: 0x3a3a3a });
            const cockpitMat = new THREE.MeshPhongMaterial({
                color: 0x1a4a6a, transparent: true, opacity: 0.65,
                shininess: 180, specular: 0x88ccff
            });
            const engineMat = new THREE.MeshPhongMaterial({
                color: 0x2a2a30, shininess: 60, specular: 0x444444
            });

            // === FUSELAGE - Sleek multi-section body ===
            // Nose cone - sharp pointed beak shape (tip facing forward)
            const nose = new THREE.Mesh(new THREE.ConeGeometry(1.8, 10, 16), bodyMat);
            nose.rotation.x = -Math.PI / 2; // Tip points forward (-Z direction)
            nose.position.z = -8;
            nose.castShadow = true;
            jet.add(nose);

            // Main fuselage
            const fuselage = new THREE.Mesh(new THREE.BoxGeometry(3.6, 2.0, 16), bodyMat);
            fuselage.position.z = 5;
            fuselage.castShadow = true;
            fuselage.name = 'fuselage';
            jet.add(fuselage);

            // Rear section
            const rear = new THREE.Mesh(new THREE.BoxGeometry(4.2, 1.8, 4), bodyMat);
            rear.position.z = 15;
            rear.castShadow = true;
            jet.add(rear);

            // === COCKPIT CANOPY ===
            const cockpit = new THREE.Mesh(
                new THREE.SphereGeometry(1.4, 24, 16, 0, Math.PI * 2, 0, Math.PI / 2),
                cockpitMat
            );
            cockpit.position.set(0, 1.1, -3);
            cockpit.scale.set(1.0, 0.55, 2.4);
            cockpit.name = 'cockpit';
            jet.add(cockpit);

            // Canopy frame
            [-0.5, 0, 0.5].forEach(x => {
                const frame = new THREE.Mesh(new THREE.BoxGeometry(0.06, 0.4, 3), panelMat);
                frame.position.set(x * 1.4, 1.25, -3);
                jet.add(frame);
            });

            // === SWEPT WINGS ===
            const wingGrp = new THREE.Group();
            wingGrp.name = 'wings';

            const leftWing = new THREE.Group();
            leftWing.name = 'leftWing';
            const rightWing = new THREE.Group();
            rightWing.name = 'rightWing';
            wingGrp.add(leftWing);
            wingGrp.add(rightWing);

            jet.userData.parts.wings = wingGrp;

            [-1, 1].forEach(side => {
                const targetGrp = side < 0 ? leftWing : rightWing;

                // Main wing - swept back trapezoid shape
                const wing = new THREE.Mesh(new THREE.BoxGeometry(11, 0.35, 5), darkMat);
                wing.position.set(side * 7.5, -0.2, 4);
                wing.rotation.y = side * 0.25; // Sweep angle
                wing.castShadow = true;
                targetGrp.add(wing);

                // Wing tip
                const tip = new THREE.Mesh(new THREE.BoxGeometry(3, 0.25, 2.5), darkMat);
                tip.position.set(side * 13.5, -0.1, 5.5);
                tip.rotation.y = side * 0.35;
                tip.rotation.z = side * 0.15;
                targetGrp.add(tip);

                // Leading edge slat
                const slat = new THREE.Mesh(new THREE.BoxGeometry(10, 0.15, 0.6), bodyMat);
                slat.position.set(side * 7, 0, 1.2);
                slat.rotation.y = side * 0.25;
                targetGrp.add(slat);

                // Trailing edge flap
                const flap = new THREE.Mesh(new THREE.BoxGeometry(6, 0.2, 1.0),
                    new THREE.MeshPhongMaterial({ color: 0x555560, shininess: 20 }));
                flap.position.set(side * 8, -0.3, 7);
                flap.rotation.y = side * 0.2;
                targetGrp.add(flap);

                // Wing panel lines
                [4, 7, 10].forEach(dist => {
                    const line = new THREE.Mesh(new THREE.BoxGeometry(0.03, 0.4, 4), panelMat);
                    line.position.set(side * dist, -0.1, 4);
                    targetGrp.add(line);
                });

                // Navigation lights
                const navLight = new THREE.Mesh(
                    new THREE.SphereGeometry(0.12, 8, 8),
                    new THREE.MeshBasicMaterial({ color: side < 0 ? 0xff0000 : 0x00ff00 })
                );
                navLight.position.set(side * 14.5, 0, 6);
                targetGrp.add(navLight);
            });
            jet.add(wingGrp);

            // === TWIN VERTICAL STABILIZERS (Canted outward) ===
            [-1, 1].forEach(side => {
                const stabGrp = new THREE.Group();

                // Main fin
                const fin = new THREE.Mesh(new THREE.BoxGeometry(0.2, 4.5, 3), darkMat);
                fin.position.set(0, 2.25, 0);
                fin.castShadow = true;
                stabGrp.add(fin);

                // Rudder
                const rudder = new THREE.Mesh(new THREE.BoxGeometry(0.12, 4, 0.9),
                    new THREE.MeshPhongMaterial({ color: 0x505055, shininess: 20 }));
                rudder.position.set(0, 2, 1.3);
                stabGrp.add(rudder);

                // Tip
                const finTip = new THREE.Mesh(new THREE.BoxGeometry(0.15, 0.8, 2), darkMat);
                finTip.position.set(0, 4.8, 0.2);
                stabGrp.add(finTip);

                stabGrp.position.set(side * 2.0, 0.9, 13);
                stabGrp.rotation.z = side * -0.22; // Canted outward
                stabGrp.name = 'tail';
                jet.add(stabGrp);
                jet.userData.parts.tails.push(stabGrp);
            });

            // === HORIZONTAL STABILIZERS ===
            [-1, 1].forEach(side => {
                const hStab = new THREE.Mesh(new THREE.BoxGeometry(5, 0.2, 2.5), darkMat);
                hStab.position.set(side * 3.5, 0.3, 15);
                hStab.rotation.y = side * 0.12;
                hStab.castShadow = true;
                jet.add(hStab);
            });

            // === ENGINE NACELLES ===
            [-1, 1].forEach(side => {
                // Engine housing
                const housing = new THREE.Mesh(new THREE.CylinderGeometry(1.0, 1.15, 9, 16), engineMat);
                housing.rotation.x = Math.PI / 2;
                housing.position.set(side * 1.6, -0.4, 12);
                housing.castShadow = true;
                jet.add(housing);

                // Exhaust nozzle
                const nozzle = new THREE.Mesh(new THREE.CylinderGeometry(0.75, 1.05, 1.8, 16),
                    new THREE.MeshPhongMaterial({ color: 0x222228, shininess: 40 }));
                nozzle.rotation.x = Math.PI / 2;
                nozzle.position.set(side * 1.6, -0.4, 17);
                jet.add(nozzle);

                // THRUSTER PLUME (New)
                const plume = createThrusterPlume();
                plume.position.set(side * 1.6, -0.4, 18);
                jet.add(plume);
                if (!jet.userData.thrusters) jet.userData.thrusters = [];
                jet.userData.thrusters.push(plume);

                // Engine glow - soft blue-white
                const glowCore = new THREE.Mesh(
                    new THREE.CircleGeometry(0.55, 20),
                    new THREE.MeshBasicMaterial({ color: 0xe8f4ff })
                );
                glowCore.position.set(side * 1.6, -0.4, 18);
                glowCore.name = side < 0 ? 'glow1' : 'glow2';
                jet.add(glowCore);

                const glowRing = new THREE.Mesh(
                    new THREE.RingGeometry(0.55, 0.85, 20),
                    new THREE.MeshBasicMaterial({ color: 0x7799dd, transparent: true, opacity: 0.6 })
                );
                glowRing.position.set(side * 1.6, -0.4, 17.9);
                jet.add(glowRing);

                // Air intake
                const intake = new THREE.Mesh(new THREE.BoxGeometry(0.9, 1.4, 3.5),
                    new THREE.MeshPhongMaterial({ color: 0x1a1a1e, shininess: 15 }));
                intake.position.set(side * 2.5, 0, 3);
                jet.add(intake);

                // Intake ramp
                const ramp = new THREE.Mesh(new THREE.BoxGeometry(0.7, 0.12, 3),
                    new THREE.MeshPhongMaterial({ color: 0x444448, shininess: 30 }));
                ramp.position.set(side * 2.5, 0.7, 3);
                jet.add(ramp);
            });

            // === PANEL LINES (Subtle details) ===
            // Longitudinal lines
            [[-1.8, 0, 5], [1.8, 0, 5], [0, 1.0, 2], [0, 1.0, 8]].forEach(p => {
                const line = new THREE.Mesh(new THREE.BoxGeometry(0.02, 0.02, 10), panelMat);
                line.position.set(p[0], p[1], p[2]);
                jet.add(line);
            });

            // Cross panel lines
            [-4, 0, 4, 8, 12].forEach(z => {
                const cross = new THREE.Mesh(new THREE.BoxGeometry(3.5, 0.02, 0.02), panelMat);
                cross.position.set(0, 1.01, z);
                jet.add(cross);
            });

            // === WEAPON HARDPOINTS ===
            [-1, 1].forEach(side => {
                // Wing pylon
                const pylon = new THREE.Mesh(new THREE.BoxGeometry(0.35, 0.7, 1.4),
                    new THREE.MeshPhongMaterial({ color: 0x505055, shininess: 25 }));
                pylon.position.set(side * 5.5, -0.7, 4);
                jet.add(pylon);

                // Missile rail
                const rail = new THREE.Mesh(new THREE.BoxGeometry(0.25, 0.15, 2.2),
                    new THREE.MeshPhongMaterial({ color: 0x404045, shininess: 20 }));
                rail.position.set(side * 5.5, -1.15, 4);
                jet.add(rail);
            });

            // Centerline pylon
            const centerPylon = new THREE.Mesh(new THREE.BoxGeometry(0.45, 0.6, 1.6),
                new THREE.MeshPhongMaterial({ color: 0x505055, shininess: 25 }));
            centerPylon.position.set(0, -1.2, 6);
            jet.add(centerPylon);

            // === HELLBAT PARTS (Hidden by default) ===
            const hellbatGroup = new THREE.Group();
            hellbatGroup.name = 'hellbatParts';
            hellbatGroup.visible = false;

            // Material: Dark, menacing, ultra-smooth for cutting
            const batMat = new THREE.MeshPhongMaterial({
                color: 0x050505,
                shininess: 300,
                specular: 0x880000,
                emissive: 0x220000,
                emissiveIntensity: 0.2
            });

            // Blade Edge Material: Glowing red-hot cutting edge
            const bladeEdgeMat = new THREE.MeshBasicMaterial({
                color: 0xff3300,
                blending: THREE.AdditiveBlending
            });

            [-1, 1].forEach(side => {
                const bladeGroup = new THREE.Group();

                // 1. Main Wing Blade (Massive forward-swept cutter)
                // Using a thin, wide box that tapers to a point
                const bladeGeo = new THREE.BoxGeometry(14, 0.1, 8);
                // Custom vertex manipulation for razor shape
                const pos = bladeGeo.attributes.position;
                for (let i = 0; i < pos.count; i++) {
                    const x = pos.getX(i);
                    const z = pos.getZ(i);

                    // Taper width towards tip
                    if (x * side > 2) {
                        pos.setZ(i, z * 0.2); // Sharp tip
                    }

                    // Sharpen leading/trailing edges
                    if (Math.abs(z) > 3) {
                        pos.setY(i, 0); // Flatten edges to razor thin
                    }
                }
                bladeGeo.computeVertexNormals();

                const blade = new THREE.Mesh(bladeGeo, batMat);
                blade.position.set(side * 9, 0, 4);
                blade.rotation.y = side * 0.4; // Forward sweep
                blade.rotation.z = side * 0.1; // Dihedral
                bladeGroup.add(blade);

                // 2. Glowing Cutting Edge (Leading edge)
                const edgeGeo = new THREE.BoxGeometry(14.5, 0.05, 0.2);
                const edge = new THREE.Mesh(edgeGeo, bladeEdgeMat);
                edge.position.set(side * 9, 0, 0.5); // Front of wing
                edge.rotation.y = side * 0.4;
                edge.rotation.z = side * 0.1;
                bladeGroup.add(edge);

                // 3. Reinforced Combat Spikes (projecting from wingtips)
                const spikeGeo = new THREE.ConeGeometry(0.4, 8, 8);
                spikeGeo.rotateZ(side * -Math.PI / 2); // Point outward
                const spike = new THREE.Mesh(spikeGeo, batMat);
                spike.position.set(side * 16, 0, 2);
                bladeGroup.add(spike);

                // 4. Hydraulic Ram / Reinforcement bar
                const bar = new THREE.Mesh(new THREE.CylinderGeometry(0.4, 0.3, 10), batMat);
                bar.rotation.z = Math.PI / 2;
                bar.position.set(side * 6, 0.2, 4);
                bar.rotation.y = side * 0.4;
                bladeGroup.add(bar);

                bladeGroup.position.set(side * 2, 0, 2);
                hellbatGroup.add(bladeGroup);
            });

            // Central dorsal spine/blade
            const spineGeo = new THREE.BoxGeometry(0.2, 2, 12);
            // Taper top
            const spinePos = spineGeo.attributes.position;
            for (let i = 0; i < spinePos.count; i++) {
                if (spinePos.getY(i) > 0) spinePos.setX(i, 0); // Sharp top edge
            }
            spineGeo.computeVertexNormals();
            const spine = new THREE.Mesh(spineGeo, batMat);
            spine.position.set(0, 1.5, 4);
            hellbatGroup.add(spine);

            // Glowing spine edge
            const spineEdge = new THREE.Mesh(new THREE.BoxGeometry(0.05, 2.1, 12.2), bladeEdgeMat);
            spineEdge.position.set(0, 1.55, 4);
            hellbatGroup.add(spineEdge);

            jet.add(hellbatGroup);
            jet.userData.parts.hellbat = hellbatGroup;

            // === STEALTH PARTS (Hidden by default) ===
            const stealthGroup = new THREE.Group();
            stealthGroup.name = 'stealthParts';
            stealthGroup.visible = false;

            // Gap fillers/Smoothers for stealth profile
            const smoothMat = new THREE.MeshPhongMaterial({
                color: 0x333338,
                shininess: 10,
                shading: THREE.FlatShading
            });

            [-1, 1].forEach(side => {
                // Main body blending plates
                const plate = new THREE.Mesh(new THREE.BoxGeometry(4, 0.4, 12), smoothMat);
                plate.position.set(side * 2.5, 0.2, 6);
                plate.rotation.z = side * 0.1;
                stealthGroup.add(plate);

                // Sensor/Jammer pods (replace weapons)
                const pod = new THREE.Mesh(new THREE.CylinderGeometry(0.5, 0.8, 6, 8), darkMat);
                pod.rotation.x = Math.PI / 2;
                pod.position.set(side * 6, -0.5, 6);
                stealthGroup.add(pod);
            });

            jet.add(stealthGroup);
            jet.userData.parts.stealth = stealthGroup;

            // === FORCEFIELD (Stealth mode) ===
            const forcefield = new THREE.Mesh(
                new THREE.SphereGeometry(22, 40, 40),
                new THREE.MeshBasicMaterial({ color: 0x00ccff, transparent: true, opacity: 0, side: THREE.DoubleSide, wireframe: true })
            );
            forcefield.name = 'forcefield';
            jet.add(forcefield);

            return jet;
        }

        // ========== 3D GYRO HUD (HORIZON ARC) ==========
        function createGyroHUD() {
            const group = new THREE.Group();
            group.name = 'gyroHUD';

            // Semi-circular arc (Ring)
            // Arc from -110 to +110 deg (approx) centered on top?
            // A Horizon arc typically sits "below" or "around".
            // Let's make a ring section that mimics a horizon bar.
            // 220 degree arc
            const arcGeo = new THREE.RingGeometry(3.8, 3.9, 64, 1, Math.PI * 0.2, Math.PI * 1.6);

            const ringMat = new THREE.MeshBasicMaterial({
                color: 0x0088ff,
                transparent: true,
                opacity: 0.5,
                side: THREE.DoubleSide,
                blending: THREE.AdditiveBlending,
                depthTest: false // Draw on top
            });

            const ring = new THREE.Mesh(arcGeo, ringMat);
            ring.name = 'gyroRing';
            ring.rotation.z = Math.PI / 2; // Orient upright
            group.add(ring);

            // Add some "ticks" to the ring for tech feel
            for (let i = -6; i <= 6; i += 2) {
                if (i === 0) continue;
                const tick = new THREE.Mesh(new THREE.BoxGeometry(0.05, 0.4, 0.01), ringMat);
                const angle = i * 0.2;
                tick.position.set(Math.cos(angle) * 3.85, Math.sin(angle) * 3.85, 0);
                tick.rotation.z = angle + Math.PI / 2;
                ring.add(tick);
            }

            return group;
        }

        function initGyroHUD() {
            const gyroHUD = createGyroHUD();
            gyroHUD.position.z = -10; // In front of camera
            camera.add(gyroHUD); // Attach to camera
            window.gyroRef = gyroHUD;
        }

        const playerJet = createPlayerJet();
        scene.add(playerJet);

        // Init 3D Gyro
        initGyroHUD();

        const player = {
            position: new THREE.Vector3(0, 300, 0), // Spawn at normal height (terrain is now flat)
            speed: 3, maxSpeed: 8, minSpeed: 2,
            pitchSpeed: 0, rollSpeed: 0, yawSpeed: 0,
            // Gyroscopic auto-level system
            targetBankAngle: 0,
            currentBankAngle: 0,
            isRolling: false,
            autoLevelSpeed: 0.0083 // Returns to 0° over ~2 seconds (0.5 radians / 60 fps / 2 sec)
        };

        // Enemy types configuration
        const ENEMY_TYPES = {
            PATROL: { name: 'Scout', color: 0xc2c2bd, hp: 30, speed: 1.2, turn: 0.008, score: 100 },
            INTERCEPTOR: { name: 'Ace', color: 0x4a5052, hp: 60, speed: 2.2, turn: 0.02, score: 250 },
            ASSAULT: { name: 'Tank', color: 0x4b5320, hp: 120, speed: 1.0, turn: 0.005, score: 500 },
            STEALTH: { name: 'Ghost', color: 0x1a1a1a, hp: 40, speed: 1.8, turn: 0.015, score: 800 },
            BOSS: { name: 'Ace Commander', color: 0x8b0000, hp: 500, speed: 0.8, turn: 0.003, score: 5000, scale: 2.5 }
        };

        function createEnemyJet(type = 'PATROL') {
            const config = ENEMY_TYPES[type];
            const jet = new THREE.Group();
            jet.userData = {
                type: type,
                health: config.hp,
                maxHealth: config.hp,
                speed: config.speed,
                turnSpeed: config.turn,
                plumeScale: 1.0,
                shootCooldown: 60 + Math.random() * 60,
                aiState: 'IDLE',
                stateTimer: 0
            };

            // Common shader/material for that sleek look
            const bodyMat = new THREE.MeshPhongMaterial({
                color: config.color,
                emissive: 0x000000,
                shininess: type === 'STEALTH' ? 10 : 80, // Matte for stealth
                shading: THREE.FlatShading
            });
            const cockpitMat = new THREE.MeshPhongMaterial({ color: 0x111111, shininess: 120, specular: 0xffffff });
            const engineGlowMat = new THREE.MeshBasicMaterial({ color: 0xff4400 });

            if (type === 'PATROL') {
                // LIGHT PATROL JET: Standardized Size (Length ~28, Width ~26)
                // Fuselage
                const fuselage = new THREE.Mesh(new THREE.ConeGeometry(2.0, 28, 8), bodyMat);
                fuselage.rotation.x = Math.PI / 2;
                fuselage.castShadow = true;
                jet.add(fuselage);

                // Wings
                const wings = new THREE.Mesh(new THREE.BoxGeometry(26, 0.4, 6), bodyMat);
                wings.position.set(0, 0, 2);
                wings.castShadow = true;
                jet.add(wings);

                // Tail
                const tail = new THREE.Mesh(new THREE.BoxGeometry(0.4, 7, 5), bodyMat);
                tail.position.set(0, 3, 11); // Rear placement
                tail.rotation.x = -0.2;
                jet.add(tail);

                // Cockpit
                const cockpit = new THREE.Mesh(new THREE.BoxGeometry(1.8, 1.5, 6), cockpitMat);
                cockpit.position.set(0, 1.2, -3);
                jet.add(cockpit);

                // Single Engine
                const engine = new THREE.Mesh(new THREE.CylinderGeometry(1.2, 1.6, 3, 12), new THREE.MeshPhongMaterial({ color: 0x333333 }));
                engine.rotation.x = Math.PI / 2;
                engine.position.z = 14;
                jet.add(engine);

                const glow = new THREE.Mesh(new THREE.CircleGeometry(1.0, 8), engineGlowMat);
                glow.position.z = 15.51;
                jet.add(glow);

            } else if (type === 'INTERCEPTOR') {
                // INTERCEPTOR JET: Longer, Swept (Length ~32, Width ~24)
                const fuselage = new THREE.Mesh(new THREE.ConeGeometry(2.2, 32, 6), bodyMat);
                fuselage.rotation.x = Math.PI / 2;
                fuselage.castShadow = true;
                jet.add(fuselage);

                // Swept wings
                [-1, 1].forEach(side => {
                    const wing = new THREE.Mesh(new THREE.BoxGeometry(12, 0.3, 10), bodyMat);
                    wing.position.set(side * 6, -0.2, 4);
                    wing.rotation.y = side * -0.5; // Sweep back
                    wing.castShadow = true;
                    jet.add(wing);
                });

                // Twin tails (V-Tail)
                [-1, 1].forEach(side => {
                    const tail = new THREE.Mesh(new THREE.BoxGeometry(0.3, 5, 6), bodyMat);
                    tail.position.set(side * 2.5, 2.5, 12);
                    tail.rotation.z = side * 0.4; // V angled
                    tail.rotation.x = -0.3;
                    jet.add(tail);
                });

                // Pointy Cockpit
                const cockpit = new THREE.Mesh(new THREE.ConeGeometry(1.5, 8, 4), cockpitMat);
                cockpit.rotation.x = -0.1;
                cockpit.position.set(0, 1.8, -3);
                cockpit.scale.set(1, 0.5, 1); // Flattened
                jet.add(cockpit);

                // Twin Engines
                [-2.0, 2.0].forEach(x => {
                    const glow = new THREE.Mesh(new THREE.CircleGeometry(0.8, 8), engineGlowMat);
                    glow.position.set(x, 0, 16);
                    jet.add(glow);
                });

            } else if (type === 'ASSAULT') {
                // ASSAULT JET: Heavy, Bulkier (Length ~28, Width ~30)
                // Main body block
                const fuselage = new THREE.Mesh(new THREE.BoxGeometry(5.5, 3.5, 28), bodyMat);
                fuselage.castShadow = true;
                jet.add(fuselage);

                // Large Wings
                const wings = new THREE.Mesh(new THREE.BoxGeometry(32, 0.6, 12), bodyMat);
                wings.position.set(0, -0.5, 2);
                wings.castShadow = true;
                jet.add(wings);

                // Canards (front wings)
                const canards = new THREE.Mesh(new THREE.BoxGeometry(14, 0.3, 4), bodyMat);
                canards.position.set(0, 0.5, -9);
                jet.add(canards);

                // Heavy Twin Tails
                [-4, 4].forEach(x => {
                    const tail = new THREE.Mesh(new THREE.BoxGeometry(0.8, 6, 8), bodyMat);
                    tail.position.set(x, 2.5, 12);
                    jet.add(tail);
                });

                // Armored Cockpit
                const cockpit = new THREE.Mesh(new THREE.BoxGeometry(3.5, 1.8, 7), cockpitMat);
                cockpit.position.set(0, 2.0, -5);
                jet.add(cockpit);

                // Large engine glow
                const glow = new THREE.Mesh(new THREE.PlaneGeometry(4.5, 2.0), engineGlowMat);
                glow.position.set(0, 0, 14.1);
                jet.add(glow);

            } else if (type === 'STEALTH') {
                // STEALTH JET: Flat, Wide (Length ~28, Width ~32)
                const mainBody = new THREE.Mesh(new THREE.ConeGeometry(5, 18, 3), bodyMat);
                mainBody.scale.set(1.5, 1, 0.3); // Very flat
                mainBody.rotation.x = Math.PI / 2;
                mainBody.castShadow = true;
                jet.add(mainBody);

                // Delta wing appearance
                const delta = new THREE.Mesh(new THREE.CylinderGeometry(0, 16, 22, 3), bodyMat);
                delta.rotation.x = Math.PI / 2;
                delta.rotation.y = Math.PI; // Point forward
                delta.scale.set(2, 0.1, 1.5); // Wide span
                delta.position.set(0, 0, 2);
                delta.castShadow = true;
                jet.add(delta);

                const cockpit = new THREE.Mesh(new THREE.ConeGeometry(1.2, 4, 4), cockpitMat);
                cockpit.rotation.x = -0.4;
                cockpit.position.set(0, 0.8, -3);
                cockpit.scale.set(1, 0.6, 1);
                jet.add(cockpit);

                // Hidden engines (slits)
                const glow = new THREE.Mesh(new THREE.PlaneGeometry(2.5, 0.4), new THREE.MeshBasicMaterial({ color: 0x4444ff })); // Blue ion glow
                glow.position.set(0, 0, 10);
                jet.add(glow);

            } else if (type === 'BOSS') {
                // BOSS JET: Massive, Menacing (2.5x scale applied at end)
                // Heavy armored fuselage
                const fuselage = new THREE.Mesh(new THREE.BoxGeometry(7, 4, 35), bodyMat);
                fuselage.castShadow = true;
                jet.add(fuselage);

                // Intimidating pointed nose
                const nose = new THREE.Mesh(new THREE.ConeGeometry(3.5, 12, 8), bodyMat);
                nose.rotation.x = -Math.PI / 2;
                nose.position.z = -23;
                nose.castShadow = true;
                jet.add(nose);

                // Massive Wings with blade tips
                const wings = new THREE.Mesh(new THREE.BoxGeometry(40, 0.8, 14), bodyMat);
                wings.position.set(0, -0.5, 2);
                wings.castShadow = true;
                jet.add(wings);

                // Sharp wing blade tips
                [-1, 1].forEach(side => {
                    const bladeTip = new THREE.Mesh(new THREE.ConeGeometry(1.5, 8, 4), bodyMat);
                    bladeTip.rotation.z = side * -Math.PI / 2;
                    bladeTip.position.set(side * 24, -0.5, 2);
                    jet.add(bladeTip);
                });

                // Heavy armored canards (front wings)
                const canards = new THREE.Mesh(new THREE.BoxGeometry(18, 0.5, 5), bodyMat);
                canards.position.set(0, 0.5, -12);
                jet.add(canards);

                // Dual heavy vertical tails
                [-5, 5].forEach(x => {
                    const tail = new THREE.Mesh(new THREE.BoxGeometry(1.2, 8, 10), bodyMat);
                    tail.position.set(x, 4, 14);
                    jet.add(tail);
                });

                // Armored command cockpit
                const cockpit = new THREE.Mesh(new THREE.BoxGeometry(4.5, 2.5, 10), cockpitMat);
                cockpit.position.set(0, 2.5, -6);
                jet.add(cockpit);

                // Quad engines with intense red glow
                [-3, -1.5, 1.5, 3].forEach((x, i) => {
                    const engine = new THREE.Mesh(new THREE.CylinderGeometry(1.8, 2.2, 6, 12), new THREE.MeshPhongMaterial({ color: 0x222222 }));
                    engine.rotation.x = Math.PI / 2;
                    engine.position.set(x * 2.5, i % 2 === 0 ? 0.5 : -0.5, 17);
                    jet.add(engine);

                    const glow = new THREE.Mesh(new THREE.CircleGeometry(1.5, 12), new THREE.MeshBasicMaterial({ color: 0xff2200 }));
                    glow.position.set(x * 2.5, i % 2 === 0 ? 0.5 : -0.5, 20.1);
                    jet.add(glow);
                });

                // Mark as boss for special handling
                jet.userData.isBoss = true;
            }

            // Apply scale for boss enemies to make them bigger than player
            if (config.scale) {
                jet.scale.set(config.scale, config.scale, config.scale);
            }

            jet.castShadow = true;
            return jet;
        }

        // Controls
        const keys = {};
        let isDeathRayActive = false;
        let deathRayBeam = null;

        document.addEventListener('keydown', e => {
            keys[e.code] = true;
            if (!gameStarted) return;

            if (e.code === 'Digit1') setMode(0);
            if (e.code === 'Digit2') setMode(1);
            if (e.code === 'Digit3') setMode(2);
            // Developer toggle (keep for debug)
            if (e.code === 'KeyX') setMode((currentMode + 1) % 3);

            // F key activates Death Ray in HELLBAT MODE ONLY
            if (e.code === 'KeyF' && currentMode === 1 && executionCharge >= 20) {
                startDeathRay();
            }
            if (e.code === 'KeyG' && currentMode === 2 && shockwaveReady) releaseShockwave();
            if (e.code === 'KeyC' && currentMode === 1 && dashCooldown <= 0) performDash();
            if (e.code === 'KeyR') returnToCenter();
        });

        document.addEventListener('keyup', e => {
            keys[e.code] = false;
            // Stop Death Ray when F is released
            if (e.code === 'KeyF') {
                stopDeathRay();
            }
        });

        // Mouse controls for aiming and firing
        document.addEventListener('mousedown', e => {
            if (!gameStarted) return;

            if (e.button === 0) { // Left click - fire missile
                if (lockedEnemy && enemies.includes(lockedEnemy)) {
                    // Fire locked missile at target
                    if (currentMode === 1) {
                        // HELLBAT MODE: Fire dual missiles at locked target
                        fireDualMissiles(lockedEnemy);
                    } else {
                        fireLockedMissile(lockedEnemy);
                    }
                    // Reset lock after firing
                    lockedEnemy = null;
                    lockProgress = 0;
                    lockPersistTimer = 0;
                    // Exit aim mode
                    exitAimMode();
                } else {
                    // Fire auto-homing missile
                    if (currentMode === 1) {
                        // HELLBAT MODE: Always fire dual missiles from wings
                        fireDualMissiles();
                    } else {
                        fireAutoHomingMissile();
                    }
                }
            }

            if (e.button === 2) { // Right click - enter aim mode
                enterAimMode();
            }
        });

        document.addEventListener('mouseup', e => {
            if (e.button === 2) { // Right click released
                exitAimMode();
            }
        });

        document.addEventListener('contextmenu', e => e.preventDefault());

        function enterAimMode() {
            if (isAiming) return;
            isAiming = true;
            timeScale = 0.25; // Slow motion

            // Show aim lens and slow-mo overlay
            document.getElementById('aimLens').classList.add('active');
            document.getElementById('aimLens').classList.add('rotating');
            document.getElementById('slowMoOverlay').classList.add('active');

            // Play enter aim sound and start tracking ticks
            playAimEnterSound();
            startTrackingSound();
        }

        function exitAimMode() {
            if (!isAiming) return;
            isAiming = false;
            timeScale = 1; // Normal speed

            // Hide aim lens and slow-mo overlay
            document.getElementById('aimLens').classList.remove('active');
            document.getElementById('aimLens').classList.remove('rotating');
            document.getElementById('aimLens').classList.remove('locked');
            document.getElementById('slowMoOverlay').classList.remove('active');
            document.getElementById('lockedIndicator').style.display = 'none';
            document.getElementById('targetBox').style.display = 'none';

            // Play exit aim sound
            playAimExitSound();

            // Reset lock progress if not fully locked
            if (lockPersistTimer <= 0) {
                lockProgress = 0;
                lockedEnemy = null;
            }
        }

        function updateAimingSystem() {
            // Update lock persist timer
            if (lockPersistTimer > 0) {
                lockPersistTimer -= timeScale;
                if (lockPersistTimer <= 0 && !isAiming) {
                    lockedEnemy = null;
                    lockProgress = 0;
                }
            }

            if (!isAiming) {
                // Update target box for locked enemy even when not aiming
                if (lockedEnemy && enemies.includes(lockedEnemy) && lockPersistTimer > 0) {
                    updateTargetBox(lockedEnemy);
                    document.getElementById('lockedIndicator').style.display = 'block';
                } else {
                    document.getElementById('targetBox').style.display = 'none';
                    document.getElementById('lockedIndicator').style.display = 'none';
                }
                return;
            }

            // Find enemy in center of screen (within aim lens)
            const forward = new THREE.Vector3(0, 0, -1).applyQuaternion(playerJet.quaternion);
            let bestTarget = null;
            let bestAngle = 0.15; // Max angle for lock (about 8.5 degrees)

            enemies.forEach(enemy => {
                const toEnemy = new THREE.Vector3().subVectors(enemy.position, playerJet.position);
                const dist = toEnemy.length();

                if (dist < 800 && dist > 30) {
                    toEnemy.normalize();
                    const angle = forward.angleTo(toEnemy);

                    if (angle < bestAngle) {
                        bestAngle = angle;
                        bestTarget = enemy;
                    }
                }
            });

            // Update lock progress
            if (bestTarget) {
                if (aimTarget === bestTarget) {
                    // Same target, increase lock progress
                    lockProgress += 2.5; // Faster locking in slow-mo

                    // Play locking beep at intervals
                    if (Math.floor(lockProgress) % 15 === 0 && lockProgress < LOCK_TIME) {
                        playLockBeep();
                    }

                    if (lockProgress >= LOCK_TIME && lockedEnemy !== bestTarget) {
                        // Lock achieved!
                        lockedEnemy = bestTarget;
                        lockPersistTimer = LOCK_PERSIST_TIME;
                        playLockedSound();
                        document.getElementById('aimLens').classList.add('locked');
                    }
                } else {
                    // New target, reset progress
                    lockProgress = 0;
                    aimTarget = bestTarget;
                }
            } else {
                // No target, decay progress
                lockProgress = Math.max(0, lockProgress - 1);
                if (lockProgress === 0) {
                    aimTarget = null;
                }
            }

            // Update UI
            const progressFill = document.querySelector('.lock-progress-fill');
            if (progressFill) {
                const circumference = 2 * Math.PI * 38; // r=38
                const offset = circumference * (1 - Math.min(lockProgress / LOCK_TIME, 1));
                progressFill.style.strokeDashoffset = offset;
            }

            // Show locked indicator
            if (lockedEnemy && enemies.includes(lockedEnemy)) {
                document.getElementById('lockedIndicator').style.display = 'block';
                document.getElementById('aimLens').classList.add('locked');
                updateTargetBox(lockedEnemy);
            } else {
                document.getElementById('lockedIndicator').style.display = 'none';
                document.getElementById('aimLens').classList.remove('locked');
                document.getElementById('targetBox').style.display = 'none';
            }
        }

        function updateTargetBox(enemy) {
            const screenPos = getScreenPosition(enemy.position);
            if (screenPos) {
                const targetBox = document.getElementById('targetBox');
                targetBox.style.display = 'block';
                targetBox.style.left = (screenPos.x - 30) + 'px';
                targetBox.style.top = (screenPos.y - 30) + 'px';
            } else {
                document.getElementById('targetBox').style.display = 'none';
            }
        }

        function fireLockedMissile(target) {
            if (missileCooldown > 0) return;
            missileCooldown = 8; // Faster fire rate for locked missiles

            const missile = createMissileObject();
            missile.position.copy(playerJet.position);
            missile.quaternion.copy(playerJet.quaternion);

            const dir = new THREE.Vector3(0, 0, -1).applyQuaternion(playerJet.quaternion);
            missile.userData = {
                velocity: dir.multiplyScalar(18),
                life: 250,
                speed: 28, // Faster for locked missiles
                target: target,
                homingStrength: 0.25 // Very strong homing for locked target
            };

            scene.add(missile);
            missiles.push(missile);
            playMissileSound();
            playSound(600, 'sine', 0.1, 0.15); // Extra confirmation sound
        }

        // Sound functions are defined in the audio system section above

        // Mode switching
        // ========== MECHANICAL TRANSFORMATION SYSTEM ==========
        const mechState = {
            wingSweep: 0.2,
            wingWidth: 1.0,
            tailAngle: -0.22,
            hellbatOpen: 0,
            stealthOpen: 0
        };

        const mechTargets = {
            0: { sweep: 0.2, width: 1.0, tail: -0.22, hb: 0, st: 0 }, // Normal
            1: { sweep: -0.5, width: 1.0, tail: -0.35, hb: 1, st: 0 }, // Hellbat (Forward sweep)
            2: { sweep: 1.1, width: 0.6, tail: -1.3, hb: 0, st: 1 }   // Stealth (Folded Delta)
        };

        function setMode(newMode) {
            if (currentMode === newMode) return;
            const previousMode = currentMode;
            currentMode = newMode;

            // Stop mode-specific reactors logic
            if (previousMode === 1) stopHellbatReactor();
            if (previousMode === 2) stopStealthReactor();

            // Audio & FX
            if (currentMode === 1) playHellbatTransformation();
            else if (currentMode === 2) playStealthTransformation();
            else playModeSwitch();

            // Stats Update
            const modeEl = document.getElementById('modeIndicator');
            modeEl.textContent = modeNames[currentMode];
            modeEl.className = ['normal', 'hellbat', 'stealth'][currentMode];
            document.getElementById('crosshair').className = ['', 'hellbat', 'stealth'][currentMode];

            // Hide Overlays
            ['motionBlur', 'hellbatTint', 'forcefieldOverlay', 'stealthTint'].forEach(id => {
                const el = document.getElementById(id);
                if (el) { el.style.display = 'none'; el.classList.remove('active'); }
            });

            // Material Updates (Immediate color change, geometry is tweened)
            updateModeMaterials(currentMode);
        }

        function updateModeMaterials(mode) {
            const fuselage = playerJet.getObjectByName('fuselage');
            // Quick helper to safely traverse
            const setMat = (name, color, opacity = 1) => {
                const obj = playerJet.getObjectByName(name);
                if (obj) {
                    if (obj.material) {
                        obj.material.color.setHex(color);
                        obj.material.opacity = opacity;
                        obj.material.transparent = opacity < 1;
                    }
                    obj.traverse(c => {
                        if (c.material) {
                            c.material.color.setHex(color);
                            c.material.opacity = opacity;
                            c.material.transparent = opacity < 1;
                        }
                    });
                }
            };

            const forcefield = playerJet.getObjectByName('forcefield');
            if (forcefield) {
                forcefield.visible = (mode === 2);
                if (mode !== 2) {
                    forcefield.material.opacity = 0;
                }
            }

            if (mode === 0) { // Normal
                setMat('fuselage', 0x6b6b70);
                setMat('wings', 0x4a4a50);
                setMat('cockpit', 0x1a4a6a, 0.65);
            } else if (mode === 1) { // Hellbat
                document.getElementById('hellbatTint').style.display = 'block';
                document.getElementById('motionBlur').style.display = 'block';
                setMat('fuselage', 0x0a0a0a);
                setMat('wings', 0x0a0a0a);
                setMat('cockpit', 0x660000, 0.85);
            } else { // Stealth
                document.getElementById('forcefieldOverlay').style.display = 'block';
                document.getElementById('stealthTint').style.display = 'block';
                activateForcefield();
                setMat('fuselage', 0x2244aa);
                setMat('wings', 0x2244aa);
                setMat('cockpit', 0x00ccff, 0.5);
            }
        }

        function updateJetTransformation() {
            const target = mechTargets[currentMode];
            const lerpSpeed = 0.08; // Smooth mechanical speed

            // Lerp State
            mechState.wingSweep += (target.sweep - mechState.wingSweep) * lerpSpeed;
            mechState.wingWidth += (target.width - mechState.wingWidth) * lerpSpeed;
            mechState.tailAngle += (target.tail - mechState.tailAngle) * lerpSpeed;
            mechState.hellbatOpen += (target.hb - mechState.hellbatOpen) * lerpSpeed;
            mechState.stealthOpen += (target.st - mechState.stealthOpen) * lerpSpeed;

            const parts = playerJet.userData.parts;
            if (!parts) return;

            // Apply Wings
            if (parts.wings) {
                // Assuming child 0 is left (-1) and child 1 is right (1) or checking position
                parts.wings.children.forEach(wing => {
                    const side = wing.name === 'rightWing' ? 1 : -1;
                    wing.rotation.y = side * mechState.wingSweep;

                    // Specific scale for stealth width reduction
                    // Only scale on X to tuck them in? 
                    // Actually, wings are BoxGeometry, scale.x affects length.
                    // Let's use rotation primarily for visual folding.
                });
            }

            // Apply Tails
            if (parts.tails) {
                parts.tails.forEach(tail => {
                    // Check original side based on creation logic (or store it)
                    // They are at z rot side * -0.22
                    // We can infer side from current position or just check the target sign
                    // But easier to just traverse and assume they were added in order or check x pos
                    const side = tail.position.x > 0 ? 1 : -1;
                    tail.rotation.z = side * mechState.tailAngle;
                });
            }

            // Hellbat Parts (Reveal/Hide)
            if (parts.hellbat) {
                parts.hellbat.visible = mechState.hellbatOpen > 0.01;
                parts.hellbat.scale.setScalar(mechState.hellbatOpen);
                parts.hellbat.traverse(c => {
                    if (c.material) {
                        c.material.opacity = mechState.hellbatOpen;
                        c.material.transparent = true;
                    }
                });
            }

            // Stealth Parts
            if (parts.stealth) {
                parts.stealth.visible = mechState.stealthOpen > 0.01;
                // Animate them sliding out?
                parts.stealth.position.y = (1 - mechState.stealthOpen) * -2; // Pop up from body
            }
        }

        function activateForcefield() {
            forcefieldActive = true;
            forcefieldTimer = forcefieldMaxTime;
            absorbedDamage = 0;
            shockwaveReady = false;

            playerJet.traverse(child => {
                if (child.material && child.name !== 'forcefield') {
                    child.material.transparent = true;
                    child.material.opacity = 0.35;
                }
            });

            const forcefield = playerJet.getObjectByName('forcefield');
            if (forcefield) forcefield.material.opacity = 0.12;
        }

        function releaseShockwave() {
            shockwaveReady = false;
            playSound(150, 'sawtooth', 0.5, 0.4);

            const shockGeo = new THREE.RingGeometry(5, 12, 64);
            const shockMat = new THREE.MeshBasicMaterial({ color: 0x00ffff, transparent: true, opacity: 0.9, side: THREE.DoubleSide });
            const shockwave = new THREE.Mesh(shockGeo, shockMat);
            shockwave.position.copy(playerJet.position);
            shockwave.userData = { life: 60, damage: absorbedDamage * 2, radius: 5 };
            scene.add(shockwave);

            const interval = setInterval(() => {
                shockwave.scale.multiplyScalar(1.15);
                shockwave.material.opacity -= 0.02;
                shockwave.userData.radius *= 1.15;
                shockwave.userData.life--;

                enemies.forEach(enemy => {
                    const dist = shockwave.position.distanceTo(enemy.position);
                    if (dist < shockwave.userData.radius * 10 && !enemy.userData.shockwaveHit) {
                        enemy.userData.shockwaveHit = true;
                        enemy.userData.health -= shockwave.userData.damage;
                        if (enemy.userData.health <= 0) {
                            createExplosion(enemy.position);
                            playExplosion();
                            scene.remove(enemy);
                            enemies.splice(enemies.indexOf(enemy), 1);
                            score += 150;
                            kills++;
                        }
                    }
                });

                if (shockwave.userData.life <= 0) {
                    clearInterval(interval);
                    scene.remove(shockwave);
                }
            }, 16);

            absorbedDamage = 0;
            updateDial('dial-shockwave', 0, false);
        }

        function performDash() {
            isDashing = true;
            dashTimer = 15;
            dashCooldown = 90;
            isInvincible = true;
            document.getElementById('invincibilityFlash').style.display = 'block';
            setTimeout(() => document.getElementById('invincibilityFlash').style.display = 'none', 200);
        }

        function returnToCenter() {
            playerJet.position.set(0, 300, 0);
            playerJet.rotation.set(0, 0, 0);
            playerJet.quaternion.set(0, 0, 0, 1);
            player.pitchSpeed = player.rollSpeed = player.yawSpeed = 0;
            player.speed = player.minSpeed;
            isOutsideDomain = false;
            domainWarningCountdown = 3;
            document.getElementById('domainWarning').classList.remove('active');
            document.getElementById('domainEdgeGlow').style.display = 'none';
            playReturnWarpSound();
        }

        function shoot() {
            if (fireCooldown > 0) return;
            const stats = modeStats[currentMode];
            fireCooldown = stats.fireRate;

            const bulletColor = [0xffff00, 0xff6600, 0x00ccff][currentMode];
            const bulletMat = new THREE.MeshBasicMaterial({ color: bulletColor });
            const bulletGeo = new THREE.SphereGeometry(0.5, 8, 8);
            const count = currentMode === 1 ? 3 : 2;

            for (let i = 0; i < count; i++) {
                const bullet = new THREE.Mesh(bulletGeo, bulletMat);
                bullet.position.copy(playerJet.position);
                const offset = new THREE.Vector3((i - (count - 1) / 2) * 3, 0, -6).applyQuaternion(playerJet.quaternion);
                bullet.position.add(offset);
                const dir = new THREE.Vector3(0, 0, -1).applyQuaternion(playerJet.quaternion);
                bullet.velocity = dir.multiplyScalar(25);
                bullet.life = 80;
                bullet.damage = stats.bulletDamage;
                scene.add(bullet);
                bullets.push(bullet);
            }

            playBulletSound();
        }

        // ========== DEATH RAY (HELLBAT MODE ONLY) ==========
        function startDeathRay() {
            if (isDeathRayActive || currentMode !== 1 || executionCharge < 20) return;
            isDeathRayActive = true;

            // Create the CROSS-SHAPED DEATH BEAM
            deathRayBeam = new THREE.Group();

            // 1. Horizontal Beam (Wide sweep) - Extended to 3000
            const hGeo = new THREE.BoxGeometry(12, 0.4, 3000);
            const beamMat = new THREE.MeshBasicMaterial({
                color: 0xff0000,
                transparent: true,
                opacity: 0.9,
                blending: THREE.AdditiveBlending
            });
            const hBeam = new THREE.Mesh(hGeo, beamMat);
            hBeam.position.z = -1500; // Center at half length
            deathRayBeam.add(hBeam);

            // 2. Vertical Beam (Focused power) - Extended to 3000
            const vGeo = new THREE.BoxGeometry(0.4, 12, 3000);
            const vBeam = new THREE.Mesh(vGeo, beamMat);
            vBeam.position.z = -1500;
            deathRayBeam.add(vBeam);

            // 3. Core Beam (White hot center) - Extended to 3000
            const coreGeo = new THREE.CylinderGeometry(0.2, 0.2, 3000, 8);
            coreGeo.rotateX(-Math.PI / 2);
            const coreMat = new THREE.MeshBasicMaterial({ color: 0xffffff, blending: THREE.AdditiveBlending });
            const coreBeam = new THREE.Mesh(coreGeo, coreMat);
            coreBeam.position.z = -1500;
            deathRayBeam.add(coreBeam);

            // 4. Energy Rings (Pulsing visuals along the beam) - Increased count for longer beam
            for (let i = 0; i < 15; i++) {
                const ring = new THREE.Mesh(new THREE.TorusGeometry(3, 0.2, 8, 16), beamMat);
                ring.position.z = -200 * (i + 1);
                ring.userData = { offset: i };
                deathRayBeam.add(ring);
            }

            scene.add(deathRayBeam);

            // Minimal screen shake for controlled feel
            document.body.classList.add('shake');
            setTimeout(() => document.body.classList.remove('shake'), 400); // Short initial kick

            // Play death ray sound
            playDeathRayStart();
        }

        function stopDeathRay() {
            if (!isDeathRayActive) return;
            isDeathRayActive = false;

            if (deathRayBeam) {
                scene.remove(deathRayBeam);
                deathRayBeam = null;
            }

            document.body.classList.remove('shake');
            stopDeathRaySound();
        }

        function updateDeathRay() {
            if (!isDeathRayActive || !deathRayBeam || currentMode !== 1) {
                stopDeathRay();
                return;
            }

            // Drain charge - faster drain for higher power
            executionCharge -= 0.8;
            if (executionCharge <= 0) {
                executionCharge = 0;
                stopDeathRay();
                executionCooldown = 200;
                return;
            }

            // Position beam locked to player
            deathRayBeam.position.copy(playerJet.position);
            deathRayBeam.quaternion.copy(playerJet.quaternion);

            // Animate Beam Parts
            const pulse = 1 + Math.sin(Date.now() * 0.05) * 0.1;
            deathRayBeam.scale.set(pulse, pulse, 1);

            deathRayBeam.children.forEach(child => {
                if (child.geometry.type === 'TorusGeometry') {
                    child.rotation.z += 0.1;
                    child.scale.setScalar(1 + Math.sin(Date.now() * 0.01 + child.userData.offset) * 0.2);
                }
            });

            // === SCREEN WIPE LOGIC (FRUSTUM CULLING) ===
            // Create frustum from current camera state
            const frustum = new THREE.Frustum();
            const projScreenMatrix = new THREE.Matrix4();
            projScreenMatrix.multiplyMatrices(camera.projectionMatrix, camera.matrixWorldInverse);
            frustum.setFromProjectionMatrix(projScreenMatrix);

            const killList = [];

            enemies.forEach((enemy) => {
                // 1. Check Distance (Max Range Cap to avoid killing infinite distance bugs)
                // 4000 is slightly further than typical visibility
                const dist = playerJet.position.distanceTo(enemy.position);

                if (dist < 4000) {
                    // 2. Check Visibility (Frustum)
                    // We verify if the enemy is inside the camera's view frustum
                    if (frustum.containsPoint(enemy.position)) {
                        killList.push(enemy);
                    }
                }
            });

            // Execute synchronized annihilation
            if (killList.length > 0) {
                killList.forEach(enemy => {
                    // Instant destruction
                    createExplosion(enemy.position);

                    // Extra "Beam Burn" effect
                    const burn = new THREE.Mesh(
                        new THREE.SphereGeometry(6, 8, 8),
                        new THREE.MeshBasicMaterial({ color: 0xff0000, transparent: true, opacity: 0.8 })
                    );
                    burn.position.copy(enemy.position);
                    burn.velocity = new THREE.Vector3(0, 0, 0); // REQUIRED to prevent crash in explosions loop
                    scene.add(burn);

                    // Simple burn fade logic needs to be handled in animate or locally
                    // Ideally, add to an 'effects' array. For now, let's treat it as a quick flash.
                    // We'll reuse the explosion array but give it a short life
                    const burnGroup = new THREE.Group();
                    burnGroup.add(burn);
                    burnGroup.life = 10;
                    explosions.push(burnGroup);

                    // Remove enemy
                    scene.remove(enemy);
                    const idx = enemies.indexOf(enemy);
                    if (idx > -1) enemies.splice(idx, 1);

                    // Boss check
                    if (enemy === bossEnemy) {
                        bossEnemy = null;
                        document.getElementById('bossHealthContainer').style.display = 'none';
                    }

                    score += 500;
                    kills++;
                });

                // ONE impactful sound for the group wipe
                playDeathRayHit();

                // Screen flash for impact
                const flash = document.getElementById('invincibilityFlash');
                if (flash) {
                    flash.style.display = 'block';
                    flash.style.background = 'rgba(255, 50, 0, 0.4)'; // Slightly reduced opacity to not blind fully
                    setTimeout(() => flash.style.display = 'none', 100);
                }
            }
        }

        function createSpark(position) {
            const sparkGeo = new THREE.SphereGeometry(0.5, 4, 4);
            const sparkMat = new THREE.MeshBasicMaterial({ color: 0xffaa00, transparent: true, opacity: 1 });
            const spark = new THREE.Mesh(sparkGeo, sparkMat);
            spark.position.copy(position);
            spark.velocity = new THREE.Vector3(
                (Math.random() - 0.5) * 5,
                (Math.random() - 0.5) * 5,
                (Math.random() - 0.5) * 5
            );
            spark.life = 15;
            scene.add(spark);

            // Add to explosions for cleanup
            const sparkGroup = new THREE.Group();
            sparkGroup.add(spark);
            sparkGroup.life = 15;
            explosions.push(sparkGroup);
        }

        // ========== AUTO-HOMING MISSILES (LEFT CLICK - ALL MODES) ==========
        function fireAutoHomingMissile() {
            if (missileCooldown > 0) return;
            missileCooldown = 12; // Fast fire rate for spamming

            const missile = createMissileObject();
            missile.position.copy(playerJet.position);
            missile.quaternion.copy(playerJet.quaternion);

            // Find nearest enemy in forward cone
            const forward = new THREE.Vector3(0, 0, -1).applyQuaternion(playerJet.quaternion);
            let bestTarget = null;
            let bestScore = -1;

            enemies.forEach(enemy => {
                const toEnemy = new THREE.Vector3().subVectors(enemy.position, playerJet.position);
                const dist = toEnemy.length();

                if (dist < 800) {
                    toEnemy.normalize();
                    const angle = forward.angleTo(toEnemy);

                    // Score based on distance and angle (closer and more forward = better)
                    const angleScore = Math.max(0, 1 - angle / Math.PI);
                    const distScore = 1 - dist / 800;
                    const score = angleScore * 0.7 + distScore * 0.3;

                    if (score > bestScore && angle < Math.PI / 3) { // Within 60 degree cone
                        bestScore = score;
                        bestTarget = enemy;
                    }
                }
            });

            const dir = new THREE.Vector3(0, 0, -1).applyQuaternion(playerJet.quaternion);
            missile.userData = {
                velocity: dir.multiplyScalar(15),
                life: 200,
                speed: 22,
                target: bestTarget,
                homingStrength: 0.15 // Strong homing for high hit probability
            };

            scene.add(missile);
            missiles.push(missile);
            playMissileSound();
        }

        function createMissileObject() {
            const missile = new THREE.Group();
            const body = new THREE.Mesh(new THREE.CylinderGeometry(0.35, 0.45, 3.5, 8), new THREE.MeshPhongMaterial({ color: 0x555566, shininess: 100 }));
            body.rotation.x = Math.PI / 2;
            body.castShadow = true;
            missile.add(body);

            const nose = new THREE.Mesh(new THREE.ConeGeometry(0.35, 1.2, 8), new THREE.MeshPhongMaterial({ color: 0xff4444 }));
            nose.rotation.x = -Math.PI / 2;
            nose.position.z = -2.3;
            missile.add(nose);

            // Fins
            const finMat = new THREE.MeshPhongMaterial({ color: 0x444444 });
            for (let i = 0; i < 4; i++) {
                const fin = new THREE.Mesh(new THREE.BoxGeometry(0.6, 0.08, 0.5), finMat);
                fin.position.z = 1.5;
                fin.rotation.z = (Math.PI / 2) * i;
                fin.position.x = Math.cos((Math.PI / 2) * i) * 0.4;
                fin.position.y = Math.sin((Math.PI / 2) * i) * 0.4;
                missile.add(fin);
            }

            const trail = new THREE.Mesh(new THREE.CircleGeometry(0.3, 12), new THREE.MeshBasicMaterial({ color: 0xff6600 }));
            trail.position.z = 2;
            missile.add(trail);

            return missile;
        }

        // ========== HELLBAT DUAL MISSILE SYSTEM ==========
        function fireDualMissiles(target = null) {
            if (currentMode !== 1) return; // HELLBAT mode only
            if (missileCooldown > 0) return;
            missileCooldown = 15; // Slightly longer cooldown for dual fire

            // Find targets if not provided
            const forward = new THREE.Vector3(0, 0, -1).applyQuaternion(playerJet.quaternion);
            let targets = [];

            if (target) {
                targets = [target, target]; // Both missiles track same target
            } else {
                // Find two nearest enemies in forward cone
                const enemiesByScore = enemies.map(enemy => {
                    const toEnemy = new THREE.Vector3().subVectors(enemy.position, playerJet.position);
                    const dist = toEnemy.length();
                    if (dist > 800 || dist < 30) return null;
                    toEnemy.normalize();
                    const angle = forward.angleTo(toEnemy);
                    if (angle > Math.PI / 3) return null;
                    const angleScore = Math.max(0, 1 - angle / Math.PI);
                    const distScore = 1 - dist / 800;
                    return { enemy, score: angleScore * 0.7 + distScore * 0.3 };
                }).filter(e => e !== null).sort((a, b) => b.score - a.score);

                targets = [
                    enemiesByScore[0]?.enemy || null,
                    enemiesByScore[1]?.enemy || enemiesByScore[0]?.enemy || null
                ];
            }

            // Spawn missiles from each wing with directional separation
            [-1, 1].forEach((side, index) => {
                const missile = createMissileObject();

                // Calculate wing position in world space
                // HELLBAT mode uses extended wings at x=±14 (between normal x=±5.5 and batWing x=±18)
                const wingOffset = new THREE.Vector3(side * 10, -0.5, 4);
                wingOffset.applyQuaternion(playerJet.quaternion);
                missile.position.copy(playerJet.position).add(wingOffset);

                // Initial direction with slight outward angle for clean separation
                const dir = new THREE.Vector3(side * 0.08, 0, -1).normalize();
                dir.applyQuaternion(playerJet.quaternion);

                missile.quaternion.copy(playerJet.quaternion);
                missile.userData = {
                    velocity: dir.multiplyScalar(20), // Strong forward motion
                    life: 220,
                    speed: 26,
                    target: targets[index],
                    homingStrength: target ? 0.22 : 0.15, // Stronger homing for locked targets
                    isHellbatMissile: true,
                    launchSide: side // Track which wing it came from
                };

                scene.add(missile);
                missiles.push(missile);

                // Trigger wing recoil
                if (side < 0) {
                    wingRecoil.left = 1.0;
                } else {
                    wingRecoil.right = 1.0;
                }
            });

            playMissileSound();
            // Play a second layered launch sound for dramatic dual effect
            setTimeout(() => playSound(280, 'sawtooth', 0.12, 0.1), 30);
        }

        // Smoke trail particle creation
        function createSmokeTrail(position, velocity) {
            const particleCount = 3;
            for (let i = 0; i < particleCount; i++) {
                const size = 0.4 + Math.random() * 0.5;
                const smokeMat = new THREE.MeshBasicMaterial({
                    color: 0xaaaaaa,
                    transparent: true,
                    opacity: 0.7
                });
                const smokeGeo = new THREE.SphereGeometry(size, 6, 6);
                const smoke = new THREE.Mesh(smokeGeo, smokeMat);

                // Randomize position slightly for natural look
                smoke.position.copy(position);
                smoke.position.x += (Math.random() - 0.5) * 0.8;
                smoke.position.y += (Math.random() - 0.5) * 0.8;
                smoke.position.z += (Math.random() - 0.5) * 0.8;

                // Inherit some velocity for aerodynamic effect
                const trailVel = velocity.clone().multiplyScalar(-0.05);
                trailVel.x += (Math.random() - 0.5) * 0.5;
                trailVel.y += (Math.random() - 0.5) * 0.5;

                smoke.userData = {
                    velocity: trailVel,
                    life: 60, // 1 second at 60fps
                    maxLife: 60,
                    baseScale: size
                };

                scene.add(smoke);
                missileTrails.push(smoke);
            }
        }

        // Update smoke trails
        function updateSmokeTrails() {
            for (let i = missileTrails.length - 1; i >= 0; i--) {
                const smoke = missileTrails[i];
                smoke.userData.life--;

                // Smooth fade out
                const lifeRatio = smoke.userData.life / smoke.userData.maxLife;
                smoke.material.opacity = lifeRatio * 0.7;

                // Expand slightly as it fades
                const scale = smoke.userData.baseScale * (1 + (1 - lifeRatio) * 0.8);
                smoke.scale.setScalar(scale);

                // Apply velocity with drag
                smoke.position.add(smoke.userData.velocity);
                smoke.userData.velocity.multiplyScalar(0.95);

                // Remove when expired
                if (smoke.userData.life <= 0) {
                    scene.remove(smoke);
                    missileTrails.splice(i, 1);
                }
            }
        }

        // Update wing recoil animation
        function updateWingRecoil() {
            if (currentMode !== 1) {
                wingRecoil.left = wingRecoil.right = 0;
                return;
            }

            // Decay recoil smoothly
            const decay = 0.12;
            wingRecoil.left = Math.max(0, wingRecoil.left - decay);
            wingRecoil.right = Math.max(0, wingRecoil.right - decay);

            // Apply recoil to hellbat wing parts
            const hellbatParts = playerJet.getObjectByName('hellbatParts');
            if (hellbatParts && hellbatParts.visible) {
                hellbatParts.children.forEach(child => {
                    if (child.geometry && child.geometry.type === 'BoxGeometry') {
                        // Check if this is a bat wing (positioned at x=±18)
                        const originalX = child.position.x;
                        if (Math.abs(originalX) > 15) {
                            const side = originalX > 0 ? 1 : -1;
                            const recoilAmount = side > 0 ? wingRecoil.right : wingRecoil.left;
                            // Brief backward rotation for recoil effect
                            child.rotation.x = recoilAmount * 0.15;
                        }
                    }
                });
            }
        }

        // Legacy function for backward compatibility
        function fireMissile() {
            fireDirectMissile();
        }

        function createExplosion(position) {
            const particles = new THREE.Group();
            const colors = [0xff6600, 0xff3300, 0xffaa00, 0xffff00, 0xff8800];
            for (let i = 0; i < 30; i++) {
                const mat = new THREE.MeshBasicMaterial({ color: colors[Math.floor(Math.random() * colors.length)], transparent: true, opacity: 1 });
                const particle = new THREE.Mesh(new THREE.SphereGeometry(1 + Math.random() * 2.5, 6, 6), mat);
                particle.position.copy(position);
                particle.velocity = new THREE.Vector3((Math.random() - 0.5) * 20, (Math.random() - 0.5) * 20, (Math.random() - 0.5) * 20);
                particles.add(particle);
            }
            particles.life = 45;
            scene.add(particles);
            explosions.push(particles);
        }

        // ========== ZONE-BASED ENEMY SPAWNING SYSTEM ==========
        // Spawns enemies at different distances with zone-appropriate types
        function spawnZoneEnemy(zone) {
            let type, minDist, maxDist, altMin, altMax;

            switch (zone) {
                case 'NEAR':
                    // Near zone: Fast patrols and interceptors
                    type = Math.random() > 0.5 ? 'PATROL' : 'INTERCEPTOR';
                    minDist = 400;
                    maxDist = ZONE_NEAR;
                    altMin = 150;
                    altMax = 350;
                    break;
                case 'MID':
                    // Mid zone: Mixed combat
                    const midRand = Math.random();
                    if (midRand > 0.7) type = 'ASSAULT';
                    else if (midRand > 0.3) type = 'INTERCEPTOR';
                    else type = 'PATROL';
                    minDist = ZONE_NEAR;
                    maxDist = ZONE_MID;
                    altMin = 200;
                    altMax = 500;
                    break;
                case 'FAR':
                    // Far zone: Heavy assault squads
                    type = Math.random() > 0.4 ? 'ASSAULT' : 'INTERCEPTOR';
                    minDist = ZONE_MID;
                    maxDist = ZONE_FAR;
                    altMin = 250;
                    altMax = 600;
                    break;
                case 'FRONTIER':
                    // Frontier: Rare stealth hunters
                    type = Math.random() > 0.3 ? 'STEALTH' : 'ASSAULT';
                    minDist = ZONE_FAR;
                    maxDist = ZONE_FRONTIER - 1000;
                    altMin = 400;
                    altMax = 800;
                    break;
                default:
                    return;
            }

            const enemy = createEnemyJet(type);
            const angle = Math.random() * Math.PI * 2;
            const dist = minDist + Math.random() * (maxDist - minDist);
            const alt = altMin + Math.random() * (altMax - altMin);

            enemy.position.set(
                playerJet.position.x + Math.cos(angle) * dist,
                alt,
                playerJet.position.z + Math.sin(angle) * dist
            );

            // Set initial AI state based on zone
            if (zone === 'NEAR' || zone === 'MID') {
                enemy.lookAt(playerJet.position); // Face player aggressively
                enemy.userData.aiState = 'INTERCEPT';
            } else {
                // Far enemies patrol, may not immediately face player
                enemy.rotation.y = Math.random() * Math.PI * 2;
                enemy.userData.aiState = zone === 'FRONTIER' ? 'AMBUSH' : 'PATROL';
            }

            scene.add(enemy);
            enemies.push(enemy);
        }

        // Main zone management - called from game loop
        function manageEnemyZones() {
            enemySpawnTimer++;
            if (enemySpawnTimer < ENEMY_SPAWN_INTERVAL) return;
            enemySpawnTimer = 0;

            // Don't spawn if at capacity
            if (enemies.length >= MAX_ENEMIES) return;

            // Count enemies in each zone
            let nearCount = 0, midCount = 0, farCount = 0, frontierCount = 0;
            enemies.forEach(e => {
                const dist = e.position.distanceTo(playerJet.position);
                if (dist < ZONE_NEAR) nearCount++;
                else if (dist < ZONE_MID) midCount++;
                else if (dist < ZONE_FAR) farCount++;
                else frontierCount++;
            });

            // Target densities (scaled so total ≈ MAX_ENEMIES at full)
            const nearTarget = 4;
            const midTarget = 5;
            const farTarget = 4;
            const frontierTarget = 2;

            // Spawn in underpopulated zones (priority: near > mid > far > frontier)
            if (nearCount < nearTarget && Math.random() > 0.3) {
                spawnZoneEnemy('NEAR');
            } else if (midCount < midTarget && Math.random() > 0.4) {
                spawnZoneEnemy('MID');
            } else if (farCount < farTarget && Math.random() > 0.5) {
                spawnZoneEnemy('FAR');
            } else if (frontierCount < frontierTarget && Math.random() > 0.7) {
                spawnZoneEnemy('FRONTIER');
            }
        }

        // Cull enemies that are too far (called from game loop)
        function cullDistantEnemies() {
            for (let i = enemies.length - 1; i >= 0; i--) {
                const dist = enemies[i].position.distanceTo(playerJet.position);
                if (dist > ENEMY_DESPAWN_DISTANCE) {
                    scene.remove(enemies[i]);
                    enemies.splice(i, 1);
                }
            }
        }

        // Legacy function for compatibility - now spawns nearby
        function spawnEnemy() {
            if (enemies.length >= MAX_ENEMIES) return;
            spawnZoneEnemy(Math.random() > 0.5 ? 'NEAR' : 'MID');
        }

        function updateRadar() {
            const blips = document.getElementById('radarBlips');
            blips.innerHTML = '';

            // Get jet's yaw heading from quaternion
            const euler = new THREE.Euler().setFromQuaternion(playerJet.quaternion, 'YXZ');
            const heading = euler.y; // Yaw angle in radians
            const headingDeg = -heading * (180 / Math.PI);

            // ========== EPIC PLAYER INDICATOR UPDATES ==========
            const radarContainer = document.getElementById('radarContainer');
            const radarCenter = document.getElementById('radarCenter');
            const radarCenterCore = document.getElementById('radarCenterCore');
            const radarPlayerSystem = document.getElementById('radarPlayerSystem');
            const speedArcLeft = document.getElementById('radarSpeedArcLeft');
            const speedArcRight = document.getElementById('radarSpeedArcRight');
            const boostTrailLeft = document.getElementById('radarBoostTrailLeft');
            const boostTrailRight = document.getElementById('radarBoostTrailRight');
            const radarPing = document.getElementById('radarPing');
            const radarLockIndicator = document.getElementById('radarLockIndicator');

            // Rotate the core triangles based on heading
            if (radarCenter) {
                radarCenter.style.transform = `translate(-50%, -50%) rotate(${headingDeg}deg)`;
            }
            if (radarCenterCore) {
                radarCenterCore.style.transform = `translate(-50%, -50%) rotate(${headingDeg}deg)`;
            }

            // Calculate speed ratio for visual effects
            const stats = modeStats[currentMode];
            const maxSpeed = player.maxSpeed * stats.speedMult;
            const speedRatio = player.speed / maxSpeed;
            const isBoosting = player.isBoosting || isDashing;
            const isHighSpeed = speedRatio > 0.6;

            // Speed arcs - activate at high speed
            if (speedArcLeft && speedArcRight) {
                if (isHighSpeed) {
                    speedArcLeft.classList.add('active');
                    speedArcRight.classList.add('active');
                } else {
                    speedArcLeft.classList.remove('active');
                    speedArcRight.classList.remove('active');
                }
            }

            // Boost trails - DISABLED (User Request)
            if (boostTrailLeft && boostTrailRight) {
                boostTrailLeft.classList.remove('active');
                boostTrailRight.classList.remove('active');
            }

            // Detection ping - always active, creates ambient radar feel
            if (radarPing) {
                radarPing.classList.add('active');
            }

            // Lock indicator - activate when locked onto enemy
            if (radarLockIndicator) {
                if (lockedEnemy && enemies.includes(lockedEnemy)) {
                    radarLockIndicator.classList.add('active');
                } else {
                    radarLockIndicator.classList.remove('active');
                }
            }

            // Mode-specific styling
            if (radarContainer) {
                radarContainer.classList.remove('radar-hellbat', 'radar-stealth');
                if (currentMode === 1) {
                    radarContainer.classList.add('radar-hellbat');
                } else if (currentMode === 2) {
                    radarContainer.classList.add('radar-stealth');
                }
            }

            // ========== ENEMY BLIPS ==========
            enemies.forEach(enemy => {
                // Get relative position in world space
                const rel = new THREE.Vector3().subVectors(enemy.position, playerJet.position);
                const dist = rel.length();

                if (dist < 3000) {
                    // Calculate angle from jet to enemy in world space
                    const worldAngle = Math.atan2(rel.x, -rel.z);

                    // Rotate by jet's heading to make it heading-relative
                    const relativeAngle = worldAngle - heading;

                    // Calculate radar position (forward = up on radar)
                    const radarDist = (dist / 3000) * 80;
                    const rx = Math.sin(relativeAngle) * radarDist;
                    const rz = -Math.cos(relativeAngle) * radarDist;

                    // Distance-based sizing and intensity
                    const intensity = 1 - (dist / 3000);
                    const size = 4 + intensity * 4; // 4-8px based on proximity

                    // Check if this enemy is locked
                    const isLocked = lockedEnemy === enemy;

                    // Check if this is a boss enemy
                    const isBoss = enemy.userData.isBoss === true;

                    // Enemy blip - special styling for boss
                    if (isBoss) {
                        // Boss gets a much larger, pulsing blip
                        const bossSize = 12; // Larger than regular enemies
                        const blip = document.createElement('div');
                        blip.style.cssText = `
                            position: absolute;
                            width: ${bossSize}px;
                            height: ${bossSize}px;
                            background: #ff0000;
                            border: 2px solid #ffaa00;
                            border-radius: 50%;
                            left: calc(50% + ${rx}px - ${bossSize / 2}px);
                            top: calc(50% + ${rz}px - ${bossSize / 2}px);
                            box-shadow: 0 0 20px #ff0000, 0 0 30px #ff3300;
                            animation: bossPulse 1s infinite;
                            z-index: 10;
                        `;
                        blips.appendChild(blip);

                        // Add skull symbol inside boss blip
                        const skull = document.createElement('div');
                        skull.style.cssText = `
                            position: absolute;
                            left: 50%;
                            top: 50%;
                            transform: translate(-50%, -50%);
                            font-size: 10px;
                            line-height: 1;
                        `;
                        skull.textContent = '💀';
                        blip.appendChild(skull);
                    } else {
                        // Regular enemy blip
                        const blip = document.createElement('div');
                        blip.style.cssText = `
                            position: absolute;
                            width: ${size}px;
                            height: ${size}px;
                            background: ${isLocked ? '#ffaa00' : '#ff3300'};
                            border-radius: 50%;
                            left: calc(50% + ${rx}px - ${size / 2}px);
                            top: calc(50% + ${rz}px - ${size / 2}px);
                            box-shadow: 0 0 ${8 + intensity * 8}px ${isLocked ? '#ffaa00' : '#ff3300'};
                            transition: left 0.1s ease-out, top 0.1s ease-out;
                            ${isLocked ? 'animation: blink 0.3s infinite;' : ''}
                        `;
                        blips.appendChild(blip);
                    }
                }
            });

            // Heading indicator on radar edge (compass bearing)
            const headingIndicatorAngle = -heading;
            const indicatorRadius = 68;
            const indicatorX = Math.sin(headingIndicatorAngle) * indicatorRadius;
            const indicatorY = -Math.cos(headingIndicatorAngle) * indicatorRadius;

            // Mode-based color for heading indicator
            const indicatorColor = currentMode === 1 ? '#ff3300' : (currentMode === 2 ? '#00ffff' : '#00ffaa');

            const headingIndicator = document.createElement('div');
            headingIndicator.style.cssText = `
                position: absolute;
                width: 0;
                height: 0;
                border-left: 6px solid transparent;
                border-right: 6px solid transparent;
                border-bottom: 12px solid ${indicatorColor};
                left: calc(50% + ${indicatorX}px - 6px);
                top: calc(50% + ${indicatorY}px - 6px);
                transform: rotate(${headingDeg}deg);
                filter: drop-shadow(0 0 8px ${indicatorColor});
                transition: left 0.1s ease-out, top 0.1s ease-out, transform 0.1s ease-out;
            `;
            blips.appendChild(headingIndicator);

            // Forward indicator line
            const forwardLineColor = currentMode === 1 ? '#ff6600' : (currentMode === 2 ? '#00ffff' : '#00ffaa');
            const forwardLine = document.createElement('div');
            forwardLine.style.cssText = `
                position: absolute;
                width: 2px;
                height: 20px;
                background: linear-gradient(to top, transparent, ${forwardLineColor});
                left: calc(50% - 1px);
                top: calc(50% - 28px);
                opacity: ${isHighSpeed ? 1 : 0.5};
                transition: opacity 0.2s;
            `;
            blips.appendChild(forwardLine);
        }

        function updateDomainBoundary() {
            const dist2D = new THREE.Vector2(playerJet.position.x, playerJet.position.z).length();
            const normalized = dist2D / DOMAIN_RADIUS;

            const indicator = document.getElementById('domainIndicator');

            if (normalized > 0.85) {
                indicator.classList.add('warning');
                indicator.textContent = `⚠ BOUNDARY: ${Math.max(0, Math.floor((1 - normalized) * 100 / 0.15))}% ⚠`;
            } else {
                indicator.classList.remove('warning');
                indicator.textContent = 'FLIGHT DOMAIN: SAFE';
            }

            if (dist2D > DOMAIN_RADIUS) {
                if (!isOutsideDomain) {
                    isOutsideDomain = true;
                    domainWarningCountdown = 3;
                    domainCountdownTimer = 60;
                }

                document.getElementById('domainWarning').classList.add('active');
                document.getElementById('domainEdgeGlow').style.display = 'block';
                document.getElementById('domainCountdown').textContent = domainWarningCountdown;

                domainCountdownTimer--;
                if (domainCountdownTimer <= 0) {
                    domainWarningCountdown--;
                    domainCountdownTimer = 60;
                    playSound(400, 'square', 0.2);
                    if (domainWarningCountdown <= 0) returnToCenter();
                }
            } else {
                isOutsideDomain = false;
                domainWarningCountdown = 3;
                document.getElementById('domainWarning').classList.remove('active');
                document.getElementById('domainEdgeGlow').style.display = 'none';
            }
        }

        // Helper to get screen position of 3D object
        function getScreenPosition(position) {
            const vector = position.clone().project(camera);

            if (vector.z > 1) return null; // Behind camera

            const x = (vector.x * 0.5 + 0.5) * window.innerWidth;
            const y = (vector.y * -0.5 + 0.5) * window.innerHeight;

            return { x, y };
        }

        // ========== NEW HUD UPDATE HELPERS ==========
        function updateHP(percent) {
            const hpFill = document.getElementById('hud-hp-fill');
            if (!hpFill) return;

            // Clamp percent
            percent = Math.max(0, Math.min(100, percent));
            hpFill.style.width = percent + '%';

            // Clear all state classes first
            hpFill.classList.remove('state-healthy', 'state-warning', 'state-critical');

            // Apply new state based on percentage
            if (percent > 50) {
                hpFill.classList.add('state-healthy');
                // Remove inline overrides if any existed previously
                hpFill.style.backgroundColor = '';
                hpFill.style.boxShadow = '';
            } else if (percent > 25) {
                hpFill.classList.add('state-warning');
                hpFill.style.backgroundColor = '';
                hpFill.style.boxShadow = '';
            } else {
                hpFill.classList.add('state-critical');
                hpFill.style.backgroundColor = '';
                hpFill.style.boxShadow = '';
            }
        }

        function updateDial(dialId, percent, isReady = false) {
            const dial = document.getElementById(dialId);
            if (!dial) return;

            const fillCircle = dial.querySelector('.dial-fg');

            // Calculate stroke-dashoffset based on percent (0-100)
            // Circumference is approx 100 in the CSS (stroke-dasharray: 100)
            const offset = 100 - (Math.max(0, Math.min(100, percent)));
            fillCircle.style.strokeDashoffset = offset;

            // Readiness glow
            if (isReady || percent >= 100) {
                dial.classList.add('glow');
            } else {
                dial.classList.remove('glow');
            }
        }

        // ========== COCKPIT GAUGE UPDATE SYSTEM ==========
        function updateCockpitGauges(speed, altitude) {
            // SPEED DIAL
            // Map speed 0-8 to 0-300 degrees (approx)
            // Lets say 0 is at -135deg (7 o'clock) and max is at +135deg (5 o'clock)
            // Normalized speed 0-1
            const maxSpeedDisplay = 10; // slightly higher than actual max 8 for headroom
            const speedRatio = Math.min(1, speed / maxSpeedDisplay);
            const speedAngle = -135 + (speedRatio * 270);

            const speedNeedle = document.getElementById('dialSpeedNeedle');
            const speedReadout = document.getElementById('dialSpeedReadout');

            if (speedNeedle && speedReadout) {
                speedNeedle.style.transform = `translateX(-50%) rotate(${speedAngle}deg)`;

                // Motion blur when fast
                if (speed > 6) {
                    speedNeedle.classList.add('blur-active');
                    speedReadout.classList.add('blur-active');
                } else {
                    speedNeedle.classList.remove('blur-active');
                    speedReadout.classList.remove('blur-active');
                }

                // Display speed as "Units" (x100 for effect)
                speedReadout.textContent = Math.round(speed * 100);
            }

            // ALTITUDE DIAL
            // 0 is bottom (-135), 20000 is max (+135)
            const altMax = 25000;
            const altRatio = Math.min(1, Math.max(0, altitude / altMax));
            const altAngle = -135 + (altRatio * 270);

            const altNeedle = document.getElementById('dialAltNeedle');
            const altReadout = document.getElementById('dialAltReadout');
            const altContainer = document.getElementById('altDial');
            const altWarning = document.getElementById('altWarning');

            if (altNeedle && altContainer) {
                altNeedle.style.transform = `translateX(-50%) rotate(${altAngle}deg)`;
                altReadout.textContent = Math.round(altitude);

                // Dynamic Danger Zones
                altContainer.classList.remove('alt-danger-high', 'alt-danger-low');
                altWarning.style.display = 'none';

                if (altitude > 4000) {
                    altContainer.classList.add('alt-danger-high'); // Solid red + pulse
                    altWarning.style.display = 'block';
                } else if (altitude < 40 && speed > 2) {
                    // Low altitude warning (only if moving, to avoid annoyance on spawn)
                    altContainer.classList.add('alt-danger-low'); // Solid red
                }
            }
        }

        // Game loop
        function animate() {
            requestAnimationFrame(animate);

            if (gameStarted) {
                // Skip game logic if paused (still render)
                if (gamePaused) {
                    renderer.render(scene, camera);
                    return;
                }

                const stats = modeStats[currentMode];
                const rotSpeed = 0.025 * stats.turnMult * timeScale;

                // Controls
                if (keys['KeyW']) player.pitchSpeed = Math.min(player.pitchSpeed + 0.002, rotSpeed);
                else if (keys['KeyS']) player.pitchSpeed = Math.max(player.pitchSpeed - 0.002, -rotSpeed);
                else player.pitchSpeed *= 0.92;

                // Roll control with gyroscopic auto-level
                if (keys['KeyA']) {
                    player.rollSpeed = Math.min(player.rollSpeed + 0.002, rotSpeed);
                    player.isRolling = true;
                } else if (keys['KeyD']) {
                    player.rollSpeed = Math.max(player.rollSpeed - 0.002, -rotSpeed);
                    player.isRolling = true;
                } else {
                    player.isRolling = false;

                    // === GYROSCOPIC AUTO-LEVELING ===
                    const euler = new THREE.Euler().setFromQuaternion(playerJet.quaternion, 'YXZ');
                    const currentRoll = euler.z;

                    // Calculate damping factor based on speed (Higher speed = stiffer stabilizer)
                    const dampingStrength = 0.01 + (player.speed / player.maxSpeed) * 0.03;

                    // Apply counter-torque to return to level (0 radians)
                    // We want it to be smooth, so we dampen existing rollSpeed and gently nudge towards 0
                    if (Math.abs(currentRoll) > 0.001) {
                        // Spring force towards 0
                        const levelingForce = -currentRoll * dampingStrength * 0.5;
                        player.rollSpeed += levelingForce;

                        // Damping (air resistance)
                        player.rollSpeed *= 0.94;
                    } else {
                        player.rollSpeed *= 0.8; // Just friction near zero
                    }
                }

                if (keys['KeyQ']) player.yawSpeed = Math.min(player.yawSpeed + 0.001, rotSpeed * 0.5);
                else if (keys['KeyE']) player.yawSpeed = Math.max(player.yawSpeed - 0.001, -rotSpeed * 0.5);
                else player.yawSpeed *= 0.92;

                // Boost with audio feedback
                const wasBoosting = player.isBoosting || false;
                player.isBoosting = keys['ShiftLeft'] || keys['ShiftRight'];

                if (player.isBoosting) {
                    player.speed = Math.min(player.speed + 0.15 * timeScale, player.maxSpeed * stats.speedMult);
                    // Trigger boost start sound on boost begin
                    if (!wasBoosting) {
                        playBoostStart();
                    }
                } else if (keys['KeyZ']) {
                    // Decelerate
                    player.speed = Math.max(player.speed - 0.2 * timeScale, 0);
                } else {
                    player.speed = Math.max(player.speed - 0.05 * timeScale, player.minSpeed * stats.speedMult);
                    // Trigger boost end sound when stopping boost
                    if (wasBoosting) {
                        playBoostEnd();
                    }
                }

                // Turn air-slice sounds on sharp maneuvers
                const totalTurnIntensity = Math.abs(player.rollSpeed) + Math.abs(player.yawSpeed);
                if (totalTurnIntensity > 0.015 && Math.random() < 0.1) {
                    playTurnAirSlice(totalTurnIntensity * 20);
                    // Hellbat armor clanks on sharp turns
                    if (currentMode === 1 && totalTurnIntensity > 0.02 && Math.random() < 0.15) {
                        playArmorClank();
                    }
                }

                if (isDashing) {
                    player.speed = player.maxSpeed * stats.speedMult * 3;
                    if (--dashTimer <= 0) { isDashing = false; isInvincible = false; }
                }
                if (dashCooldown > 0) dashCooldown--;

                playerJet.rotateX(player.pitchSpeed);
                playerJet.rotateZ(player.rollSpeed);
                playerJet.rotateY(player.yawSpeed);

                // Gyroscopic auto-level system - smoothly returns to 0° bank over 2 seconds
                if (!player.isRolling && !isDashing) {
                    // Get current euler angles
                    const euler = new THREE.Euler().setFromQuaternion(playerJet.quaternion, 'YXZ');
                    const currentRoll = euler.z;

                    // Only auto-level if there's significant roll
                    if (Math.abs(currentRoll) > 0.01) {
                        // Calculate the correction amount (smooth lerp toward 0)
                        // Auto-level speed: returns to neutral over ~2 seconds
                        const correctionSpeed = player.autoLevelSpeed * timeScale;

                        // Ease out the correction for natural feel
                        const rollCorrection = currentRoll * correctionSpeed * 3;

                        // Apply a smooth, natural roll-back
                        const targetRoll = currentRoll - rollCorrection;

                        // Clamp to prevent overshooting
                        const newRoll = Math.abs(targetRoll) < 0.005 ? 0 : targetRoll;

                        // Update the euler and apply back to quaternion
                        euler.z = newRoll;
                        playerJet.quaternion.setFromEuler(euler);
                    }
                }

                const forward = new THREE.Vector3(0, 0, -1).applyQuaternion(playerJet.quaternion);
                playerJet.position.add(forward.multiplyScalar(player.speed));

                // ========== CONTINUOUS AUDIO UPDATES ==========
                // Update engine sound based on speed and mode
                updateEngineSound(player.speed, player.maxSpeed * stats.speedMult, currentMode);

                // Update wind sound based on speed, altitude, and boost state
                updateWindSound(player.speed, player.maxSpeed * stats.speedMult, playerJet.position.y, player.isBoosting);

                // Update gauges - altitude is calculated relative to ground level for correct display
                const altitudeAboveGround = playerJet.position.y - GROUND_LEVEL; // GROUND_LEVEL is -50
                updateCockpitGauges(player.speed, altitudeAboveGround);

                // THRUSTER TRAIL ANIMATION
                if (playerJet.userData.thrusters) {
                    const isBoosting = player.isBoosting;
                    // Target scale: Short (1.0) normally, Long (3.5) when boosting
                    // We can also scale slightly based on raw speed for non-boost variance
                    const baseTarget = isBoosting ? 2.5 : (1.0 + (player.speed / player.maxSpeed) * 0.5);

                    playerJet.userData.thrusters.forEach(plume => {
                        // 1. Lerp scale for smooth transition
                        const currentScale = plume.userData.baseScale;
                        const lerpSpeed = 0.1;
                        const newScale = currentScale + (baseTarget - currentScale) * lerpSpeed;
                        plume.userData.baseScale = newScale;

                        // 2. Add high-frequency flicker for thrust energy effect
                        const flicker = 0.9 + Math.random() * 0.2;
                        let modeScaleMult = 1.0;
                        if (currentMode === 1) modeScaleMult = 1.3; // Hellbat larger plume
                        else if (currentMode === 2) modeScaleMult = 0.7; // Stealth smaller plume

                        const finalScale = newScale * flicker * modeScaleMult;

                        // Apply scale mainly to Z (length), slightly to X/Y (width) for expansion
                        const widthScale = isBoosting ? 1.2 : 1.0;
                        plume.scale.set(widthScale, widthScale, finalScale);

                        // 3. Color update based on Mode
                        if (plume.userData.outer) {
                            let targetColor, targetOpacity;

                            if (currentMode === 1) {
                                // Hellbat: Red-Hot
                                targetColor = 0xff3300;
                                targetOpacity = isBoosting ? 0.8 : 0.55;
                            } else if (currentMode === 2) {
                                // Stealth: Dim Purple/Blue
                                targetColor = 0x5500ff;
                                targetOpacity = isBoosting ? 0.3 : 0.15; // Hard to see
                            } else {
                                // Normal: Cyan
                                targetColor = 0x00ffff;
                                targetOpacity = isBoosting ? 0.7 : 0.45;
                            }

                            plume.userData.outer.material.color.setHex(targetColor);
                            plume.userData.outer.material.opacity = targetOpacity;
                        }
                    });
                }

                // Update mode-specific reactor engines
                if (currentMode === 1) {
                    updateHellbatReactor(player.speed, player.maxSpeed * stats.speedMult, player.isBoosting);
                } else if (currentMode === 2) {
                    updateStealthReactor(player.speed, player.maxSpeed * stats.speedMult, player.isBoosting);
                }

                // Gyroscopic stabilization audio feedback
                if (!player.isRolling && !isDashing && Math.abs(playerJet.rotation.z) > 0.05) {
                    // Play subtle gyro sound occasionally during auto-level
                    if (Math.random() < 0.02) {
                        playGyroStabilizeSound();
                    }
                }

                // Environmental audio - terrain proximity and ground rumble
                const distanceToGround = playerJet.position.y - (-50); // Ground level is -50
                updateTerrainRush(distanceToGround, player.speed);

                // Occasional ground rumble at high speed and low altitude
                if (Math.random() < 0.05) {
                    playGroundRumble(player.speed, playerJet.position.y);
                }

                // Check for terrain collision (crash)
                checkTerrainCollision();

                if (keys['Space']) shoot();
                if (fireCooldown > 0) fireCooldown--;
                if (missileCooldown > 0) missileCooldown--;

                // === HELLBAT WING COLLISION CHECK ===
                if (currentMode === 1) {
                    for (let i = enemies.length - 1; i >= 0; i--) {
                        const enemy = enemies[i];
                        // 60 units = approx wing blade reach
                        if (playerJet.position.distanceTo(enemy.position) < 60) {
                            const enemyType = enemy.userData.type || 'ENEMY';
                            const isBoss = enemy.userData.isBoss === true;

                            // Visuals
                            createExplosion(enemy.position);
                            playExplosion();

                            // Boss enemies take damage from wing collision
                            if (isBoss) {
                                if (!enemy.userData.health) enemy.userData.health = 2000;
                                enemy.userData.health -= 200; // Wing collision does heavy damage
                                updateBossHealth();

                                // Only kill boss when health reaches 0
                                if (enemy.userData.health <= 0) {
                                    const earnedScore = recordEnemyKill(enemyType, 1500); // Higher bonus for melee boss kill
                                    score += earnedScore;
                                    kills++;
                                    scene.remove(enemy);
                                    enemies.splice(i, 1);
                                    bossEnemy = null;
                                    document.getElementById('bossHealthContainer').style.display = 'none';
                                }
                            } else {
                                // Regular enemies die instantly
                                const earnedScore = recordEnemyKill(enemyType, 500); // 500pts Melee Bonus
                                score += earnedScore;
                                kills++;
                                scene.remove(enemy);
                                enemies.splice(i, 1);
                            }

                            continue;
                        }
                    }
                }

                // Update enemies (with timeScale for slow-mo)
                enemies.forEach(enemy => {
                    const data = enemy.userData;
                    const toPlayer = new THREE.Vector3().subVectors(playerJet.position, enemy.position);
                    const dist = toPlayer.length();

                    // Stats from data
                    const speed = data.speed * (timeScale || 1);
                    const turnRate = data.turnSpeed * (timeScale || 1);

                    // AI Visual Targeting - Smoothly look at target direction
                    const targetPos = new THREE.Vector3().copy(playerJet.position);
                    let desiredSpeed = speed;

                    // === AI BEHAVIORS ===
                    if (data.type === 'PATROL') {
                        // PATROL: Circles around player at a distance, engages if close
                        if (dist > 600) {
                            // Fly towards player but offset (circle behavior)
                            const offset = new THREE.Vector3(toPlayer.z, 0, -toPlayer.x).normalize().multiplyScalar(400);
                            targetPos.add(offset);
                        }
                        // Easy target, minimal evasion
                    }
                    else if (data.type === 'INTERCEPTOR') {
                        // INTERCEPTOR: High speed passes. If too close, break away.
                        if (dist < 300) {
                            // Too close! Break off!
                            const evade = toPlayer.clone().normalize().negate().multiplyScalar(1000);
                            targetPos.copy(enemy.position).add(evade);
                            desiredSpeed *= 1.5; // Boost away
                        } else {
                            // Lead the target slightly
                            const lead = forward.clone().multiplyScalar(player.speed * 20);
                            targetPos.add(lead);
                        }
                        // Roll into turns
                        const rollAmt = Math.sin(Date.now() * 0.005) * 0.5;
                        enemy.rotateZ(rollAmt * 0.05);
                    }
                    else if (data.type === 'ASSAULT') {
                        // ASSAULT: Relentless pursuit. Slow but steady.
                        // Just default behavior (chase)
                    }
                    else if (data.type === 'STEALTH') {
                        // STEALTH: Try to stay behind or above
                        const behindPos = playerJet.position.clone().add(forward.clone().multiplyScalar(-400));
                        behindPos.y += 200; // Attack from above

                        if (dist > 800) targetPos.copy(behindPos); // Flank

                        // Break lock if aimed at
                        if (lockedEnemy === enemy && Math.random() < 0.05) {
                            lockedEnemy = null; // Cloak engaged
                            lockProgress = 0;
                        }
                    }

                    // Steering Logic (Quaternion Slerp)
                    const targetQuat = new THREE.Quaternion();
                    const m = new THREE.Matrix4().lookAt(enemy.position, targetPos, new THREE.Vector3(0, 1, 0));
                    m.decompose(new THREE.Vector3(), targetQuat, new THREE.Vector3());
                    enemy.quaternion.slerp(targetQuat, turnRate);

                    // Move forward
                    const fwd = new THREE.Vector3(0, 0, -1).applyQuaternion(enemy.quaternion);
                    enemy.position.add(fwd.multiplyScalar(desiredSpeed * (timeScale || 1)));

                    // Shooting Logic
                    data.shootCooldown -= timeScale;
                    // Visibility check for shooting (dot product)
                    fwd.normalize();
                    toPlayer.normalize();
                    const angle = fwd.dot(toPlayer); // 1 = facing player

                    if (data.shootCooldown <= 0 && dist < 700 && angle > 0.8) {
                        // Create bullet
                        const bullet = new THREE.Mesh(new THREE.SphereGeometry(0.5, 8, 8), new THREE.MeshBasicMaterial({ color: 0xff0000 }));
                        bullet.position.copy(enemy.position);

                        // Interceptor leads shots better
                        const accuracy = data.type === 'INTERCEPTOR' ? 0.02 : 0.08;
                        const dir = new THREE.Vector3().subVectors(playerJet.position, enemy.position).normalize();

                        dir.x += (Math.random() - 0.5) * accuracy;
                        dir.y += (Math.random() - 0.5) * accuracy;
                        dir.z += (Math.random() - 0.5) * accuracy;

                        bullet.velocity = dir.normalize().multiplyScalar(10);
                        bullet.life = 150;
                        scene.add(bullet);
                        enemyBullets.push(bullet);

                        // Burst fire logic
                        const burstDelay = data.type === 'ASSAULT' ? 5 : 20;
                        data.shootCooldown = data.type === 'ASSAULT' ? 10 : (60 + Math.random() * 60);
                    }

                    if (enemy.position.y < 50) enemy.position.y = 50;
                    if (enemy.position.y > 800) enemy.position.y = 800; // Higher ceiling
                });

                // Update player bullets (with timeScale)
                for (let i = bullets.length - 1; i >= 0; i--) {
                    const b = bullets[i];
                    b.position.add(b.velocity.clone().multiplyScalar(timeScale));
                    b.life -= timeScale;

                    let hit = false;
                    for (let j = enemies.length - 1; j >= 0; j--) {
                        // Increased hit radius for larger enemy models (2.5x scale)
                        if (b.position.distanceTo(enemies[j].position) < 30) {
                            enemies[j].userData.health -= b.damage || 10;
                            hit = true;
                            if (enemies[j].userData.health <= 0) {
                                const killedEnemy = enemies[j];
                                const enemyType = killedEnemy.userData.type || 'ENEMY';
                                createExplosion(killedEnemy.position);
                                playExplosion();
                                scene.remove(killedEnemy);
                                enemies.splice(j, 1);
                                const earnedScore = recordEnemyKill(enemyType, 100);
                                score += earnedScore;
                                kills++;
                            }
                            break;
                        }
                    }

                    if (hit || b.life <= 0) { scene.remove(b); bullets.splice(i, 1); }
                }

                // Update enemy bullets (with timeScale)
                for (let i = enemyBullets.length - 1; i >= 0; i--) {
                    const b = enemyBullets[i];
                    b.position.add(b.velocity.clone().multiplyScalar(timeScale));
                    b.life -= timeScale;

                    if (b.position.distanceTo(playerJet.position) < 10 && !isInvincible) {
                        if (forcefieldActive && currentMode === 2) {
                            absorbedDamage += 10;
                            const pct = Math.min(absorbedDamage / 100, 1) * 100;
                            if (absorbedDamage >= 50) shockwaveReady = true;
                            updateDial('dial-shockwave', pct, shockwaveReady);
                        } else {
                            health -= 10;
                            updateHP(health);
                            showDamageDirection(b.position);
                            resetKillStreak();
                            if (health <= 0) gameOver();
                        }
                        scene.remove(b);
                        enemyBullets.splice(i, 1);
                        continue;
                    }

                    if (b.life <= 0) { scene.remove(b); enemyBullets.splice(i, 1); }
                }

                // Update missiles with strong auto-homing (with timeScale)
                for (let i = missiles.length - 1; i >= 0; i--) {
                    const m = missiles[i];
                    m.userData.life -= timeScale;

                    // Find target - prefer assigned target, otherwise find nearest
                    let target = m.userData.target;
                    if (!target || !enemies.includes(target)) {
                        // Find new nearest enemy
                        let nearestDist = 600;
                        enemies.forEach(e => {
                            const d = m.position.distanceTo(e.position);
                            if (d < nearestDist) {
                                nearestDist = d;
                                target = e;
                            }
                        });
                        m.userData.target = target;
                    }

                    // Strong homing towards target
                    if (target) {
                        const toTarget = new THREE.Vector3().subVectors(target.position, m.position).normalize();
                        const curDir = m.userData.velocity.clone().normalize();

                        // Use strong homing strength for high hit probability
                        const homingStrength = m.userData.homingStrength || 0.12;
                        curDir.lerp(toTarget, homingStrength).normalize();
                        m.userData.velocity = curDir.multiplyScalar(m.userData.speed);

                        // Rotate missile to face direction
                        const matrix = new THREE.Matrix4().lookAt(m.position, m.position.clone().add(m.userData.velocity), new THREE.Vector3(0, 1, 0));
                        m.quaternion.setFromRotationMatrix(matrix);
                    }

                    m.position.add(m.userData.velocity.clone().multiplyScalar(timeScale));

                    // Generate smoke trails for missiles (enhanced for HELLBAT)
                    if (m.userData.isHellbatMissile || Math.random() < 0.3) {
                        createSmokeTrail(m.position.clone(), m.userData.velocity);
                    }

                    // Check for hits
                    let hitEnemy = false;
                    for (let j = enemies.length - 1; j >= 0; j--) {
                        if (m.position.distanceTo(enemies[j].position) < 18) { // Slightly larger hit radius
                            const enemy = enemies[j];
                            const enemyType = enemy.userData.type || 'ENEMY';
                            const isBoss = enemy.userData.isBoss === true;

                            // Boss enemies take damage instead of instant death
                            if (isBoss) {
                                if (!enemy.userData.health) enemy.userData.health = 2000;
                                enemy.userData.health -= 100; // Each missile does 100 damage

                                createExplosion(enemy.position); // Visual feedback
                                playExplosion();
                                updateBossHealth(); // Update the health bar

                                // Only kill boss when health reaches 0
                                if (enemy.userData.health <= 0) {
                                    scene.remove(enemy);
                                    enemies.splice(j, 1);
                                    const earnedScore = recordEnemyKill(enemyType, 1000); // Boss worth more
                                    score += earnedScore;
                                    kills++;
                                    bossEnemy = null; // Clear boss reference
                                    document.getElementById('bossHealthContainer').style.display = 'none';
                                }
                            } else {
                                // Regular enemies die in one hit
                                createExplosion(enemy.position);
                                playExplosion();
                                scene.remove(enemy);
                                enemies.splice(j, 1);
                                const earnedScore = recordEnemyKill(enemyType, 200);
                                score += earnedScore;
                                kills++;
                            }
                            hitEnemy = true;
                            break;
                        }
                    }

                    if (hitEnemy || m.userData.life <= 0) { scene.remove(m); missiles.splice(i, 1); }
                }

                // Update Death Ray
                updateDeathRay();

                // Update smoke trails (missile exhaust)
                updateSmokeTrails();

                // Update wing recoil animation (HELLBAT)
                updateWingRecoil();

                // Update aiming system
                updateAimingSystem();

                // Update crash debris (if any)
                updateCrashDebris();

                // Update explosions
                for (let i = explosions.length - 1; i >= 0; i--) {
                    const e = explosions[i];
                    e.life--;
                    e.children.forEach(p => {
                        p.position.add(p.velocity);
                        p.velocity.multiplyScalar(0.92);
                        p.scale.multiplyScalar(0.95);
                        if (p.material) p.material.opacity = e.life / 45;
                    });
                    if (e.life <= 0) { scene.remove(e); explosions.splice(i, 1); }
                }

                // Forcefield
                if (forcefieldActive && currentMode === 2) {
                    forcefieldTimer--;
                    updateDial('dial-forcefield', (forcefieldTimer / forcefieldMaxTime * 100));
                    const ff = playerJet.getObjectByName('forcefield');
                    if (ff) ff.material.opacity = 0.08 + Math.sin(Date.now() * 0.005) * 0.06;
                    if (forcefieldTimer <= 0) {
                        forcefieldActive = false;
                        playerJet.traverse(c => { if (c.material && c.name !== 'forcefield') { c.material.transparent = false; c.material.opacity = 1; } });
                    }
                }

                // Death Ray charge (recharges when not in use)
                if (executionCooldown > 0) {
                    executionCooldown--;
                    executionCharge = Math.min(100, (1 - executionCooldown / 180) * 100);
                } else if (!isDeathRayActive && executionCharge < 100) {
                    executionCharge = Math.min(100, executionCharge + 0.2); // Slow recharge
                }
                updateDial('dial-hellbat', executionCharge, executionCharge >= 100);

                // Camera
                const camOffset = new THREE.Vector3(0, 10, 40).applyQuaternion(playerJet.quaternion);
                camera.position.lerp(playerJet.position.clone().add(camOffset), 0.08);
                camera.lookAt(playerJet.position);

                updateRadar();
                updateDomainBoundary();
                updateCreativeSystems();
                updateJetTransformation();

                // Zone-based enemy management
                manageEnemyZones();
                cullDistantEnemies();

                // HUD updates
                document.getElementById('speedFill').style.height = (player.speed / (player.maxSpeed * stats.speedMult) * 100) + '%';
                document.getElementById('speedValue').textContent = Math.floor(player.speed * 100);
                document.getElementById('altFill').style.height = Math.min(playerJet.position.y / 800 * 100, 100) + '%';
                document.getElementById('altValue').textContent = Math.floor(playerJet.position.y);
                document.getElementById('score').textContent = score;
                document.getElementById('kills').textContent = kills;
                document.getElementById('warning').style.display = enemies.some(e => e.position.distanceTo(playerJet.position) < 200) ? 'block' : 'none';

                // Bank indicator update
                const euler = new THREE.Euler().setFromQuaternion(playerJet.quaternion, 'YXZ');
                const bankAngleDeg = THREE.MathUtils.radToDeg(euler.z);
                const clampedBank = Math.max(-45, Math.min(45, bankAngleDeg));
                document.getElementById('bankNeedle').style.transform = `rotate(${-clampedBank}deg)`;

                // Gyro status indicator (2D Fallback / Debug)
                const gyroStatus = document.getElementById('gyroStatus');
                if (gyroStatus) {
                    if (!player.isRolling && Math.abs(euler.z) > 0.02) {
                        gyroStatus.textContent = 'GYRO LEVELING';
                        gyroStatus.classList.add('active');
                    } else if (Math.abs(euler.z) < 0.02) {
                        gyroStatus.textContent = 'GYRO LEVEL';
                        gyroStatus.classList.remove('active');
                    } else {
                        gyroStatus.textContent = 'GYRO STANDBY';
                        gyroStatus.classList.remove('active');
                    }
                }

                // === 3D GYRO HUD UPDATE ===
                if (window.gyroRef) {
                    // Counter-rotate the Horizon Arc so it stays parallel to the world horizon
                    window.gyroRef.rotation.z = -playerJet.rotation.z;

                    // Visual Feedback: Glow when locked/level
                    const isLevel = Math.abs(playerJet.rotation.z) < 0.05;
                    const isStabilizing = !player.isRolling && !isLevel;

                    const ring = window.gyroRef.getObjectByName('gyroRing');
                    if (ring) {
                        if (isLevel) {
                            ring.material.opacity = 0.8;
                            ring.material.color.setHex(0x00ffaa); // Greenish lock
                            ring.scale.setScalar(1.0);
                        } else if (isStabilizing) {
                            ring.material.opacity = 0.6;
                            ring.material.color.setHex(0x00ffff); // Cyan stabilizing
                            ring.scale.setScalar(1.0 + Math.sin(Date.now() * 0.01) * 0.02); // Subtle pulse
                        } else {
                            ring.material.opacity = 0.3; // Dim when manual
                            ring.material.color.setHex(0x0088ff);
                        }
                    }
                }
            }

            // Continue updating crash debris even when game is stopped
            if (isCrashing) {
                updateCrashDebris();

                // Update explosions during crash
                for (let i = explosions.length - 1; i >= 0; i--) {
                    const e = explosions[i];
                    e.life--;
                    e.children.forEach(p => {
                        p.position.add(p.velocity);
                        p.velocity.multiplyScalar(0.95);
                        p.velocity.y -= 0.2; // Gravity
                        p.scale.multiplyScalar(0.97);
                        if (p.material) p.material.opacity = e.life / 80;
                    });
                    if (e.life <= 0) { scene.remove(e); explosions.splice(i, 1); }
                }
            }

            checkTerrainCollision();
            renderer.render(scene, camera);
        }

        // ========== CRASH SYSTEM ==========
        let isRebounding = false;
        let reboundTimer = 0;

        function checkTerrainCollision() {
            if (isCrashing || !gameStarted || isRebounding) return;

            // Get terrain height at player position via Simplex Noise
            const playerX = playerJet.position.x;
            const playerZ = playerJet.position.z;

            // Accurate noise-based terrain height
            const terrainHeight = getTerrainHeight(playerX, playerZ);

            // Check if below crash threshold
            if (playerJet.position.y < terrainHeight + CRASH_HEIGHT) {
                // STEALTH MODE - Controlled rebound instead of crash
                if (currentMode === 2 && forcefieldActive) {
                    triggerStealthRebound(terrainHeight);
                    return;
                }

                // Check angle and speed for severity (Normal and Hellbat modes)
                const euler = new THREE.Euler().setFromQuaternion(playerJet.quaternion, 'YXZ');
                const pitchAngle = Math.abs(euler.x);
                const isSteepDive = pitchAngle > 0.5; // More than ~30 degrees
                const isHighSpeed = player.speed > player.maxSpeed * 0.6;

                if (isSteepDive || isHighSpeed || playerJet.position.y < terrainHeight + 10) {
                    crashCause = isSteepDive ? 'STEEP DIVE INTO TERRAIN' :
                        isHighSpeed ? 'HIGH-SPEED GROUND IMPACT' :
                            'CONTROLLED FLIGHT INTO TERRAIN';
                    triggerCrash();
                }
            }
        }

        // ========== STEALTH MODE REBOUND SYSTEM ==========
        function triggerStealthRebound(terrainHeight) {
            if (isRebounding) return;
            isRebounding = true;
            reboundTimer = 45; // ~0.75 seconds of rebound animation

            // Play rebound sound - technological bounce effect
            playStealthBounceSound();

            // Flash the forcefield brightly
            const forcefield = playerJet.getObjectByName('forcefield');
            if (forcefield) {
                forcefield.material.opacity = 0.5;
                forcefield.material.color.setHex(0x00ffff);
            }

            // Create rebound particle effect
            createReboundEffect(playerJet.position.clone());

            // Reduce speed significantly
            player.speed *= 0.3;

            // Set position safely above terrain
            playerJet.position.y = terrainHeight + CRASH_HEIGHT + 30;

            // Auto-level the jet smoothly
            const euler = new THREE.Euler().setFromQuaternion(playerJet.quaternion, 'YXZ');

            // Store original orientation for smooth interpolation
            const originalPitch = euler.x;
            const originalRoll = euler.z;

            // Animate the rebound
            let reboundFrame = 0;
            const reboundAnimation = setInterval(() => {
                reboundFrame++;

                // Smooth upward momentum
                playerJet.position.y += (1 - reboundFrame / 45) * 3;

                // Smoothly auto-level the jet
                const t = reboundFrame / 30; // Normalize to 0-1 over 30 frames
                if (t <= 1) {
                    euler.setFromQuaternion(playerJet.quaternion, 'YXZ');

                    // Lerp pitch and roll toward 0
                    euler.x = originalPitch * (1 - easeOutCubic(t));
                    euler.z = originalRoll * (1 - easeOutCubic(t));

                    // Apply a slight nose-up attitude
                    if (t > 0.5) {
                        euler.x = Math.max(euler.x, -0.15); // Slight nose up
                    }

                    playerJet.quaternion.setFromEuler(euler);
                }

                // Fade forcefield back to normal
                if (forcefield) {
                    const fadeT = reboundFrame / 45;
                    forcefield.material.opacity = 0.5 * (1 - fadeT) + 0.12 * fadeT;

                    // Pulse effect during rebound
                    const pulse = Math.sin(reboundFrame * 0.3) * 0.1;
                    forcefield.material.opacity += pulse;
                }

                // Brief screen effect
                if (reboundFrame < 10) {
                    document.getElementById('invincibilityFlash').style.display = 'block';
                    document.getElementById('invincibilityFlash').style.background = 'rgba(0, 200, 255, 0.2)';
                } else {
                    document.getElementById('invincibilityFlash').style.display = 'none';
                }

                if (reboundFrame >= 45) {
                    clearInterval(reboundAnimation);
                    isRebounding = false;
                    reboundTimer = 0;

                    // Reset forcefield color
                    if (forcefield) {
                        forcefield.material.color.setHex(0x00ccff);
                        forcefield.material.opacity = 0.12;
                    }

                    document.getElementById('invincibilityFlash').style.display = 'none';
                }
            }, 16);
        }

        // Easing function for smooth animation
        function easeOutCubic(t) {
            return 1 - Math.pow(1 - t, 3);
        }

        // Create visual effect for rebound
        function createReboundEffect(position) {
            // Forcefield pulse ring
            const ringGeo = new THREE.RingGeometry(5, 8, 32);
            const ringMat = new THREE.MeshBasicMaterial({
                color: 0x00ffff,
                transparent: true,
                opacity: 0.8,
                side: THREE.DoubleSide
            });
            const pulseRing = new THREE.Mesh(ringGeo, ringMat);
            pulseRing.position.copy(position);
            pulseRing.rotation.x = -Math.PI / 2;
            scene.add(pulseRing);

            // Animate the pulse ring
            let ringLife = 30;
            const ringInterval = setInterval(() => {
                ringLife--;
                pulseRing.scale.multiplyScalar(1.15);
                pulseRing.material.opacity = ringLife / 30 * 0.8;
                pulseRing.position.y -= 0.5;

                if (ringLife <= 0) {
                    clearInterval(ringInterval);
                    scene.remove(pulseRing);
                }
            }, 16);

            // Energy particles
            const particles = new THREE.Group();
            for (let i = 0; i < 20; i++) {
                const particleMat = new THREE.MeshBasicMaterial({
                    color: Math.random() > 0.5 ? 0x00ffff : 0x0088ff,
                    transparent: true,
                    opacity: 1
                });
                const particle = new THREE.Mesh(new THREE.SphereGeometry(0.5, 6, 6), particleMat);
                particle.position.copy(position);
                particle.velocity = new THREE.Vector3(
                    (Math.random() - 0.5) * 15,
                    Math.random() * 10 + 5,
                    (Math.random() - 0.5) * 15
                );
                particles.add(particle);
            }
            particles.life = 40;
            scene.add(particles);
            explosions.push(particles);

            // Hexagonal shield flash
            const hexGeo = new THREE.CircleGeometry(15, 6);
            const hexMat = new THREE.MeshBasicMaterial({
                color: 0x00ffff,
                transparent: true,
                opacity: 0.6,
                side: THREE.DoubleSide,
                wireframe: true
            });
            const hexFlash = new THREE.Mesh(hexGeo, hexMat);
            hexFlash.position.copy(position);
            hexFlash.rotation.x = -Math.PI / 2;
            scene.add(hexFlash);

            let hexLife = 20;
            const hexInterval = setInterval(() => {
                hexLife--;
                hexFlash.scale.multiplyScalar(1.1);
                hexFlash.material.opacity = hexLife / 20 * 0.6;
                hexFlash.rotation.z += 0.05;

                if (hexLife <= 0) {
                    clearInterval(hexInterval);
                    scene.remove(hexFlash);
                }
            }, 16);
        }

        function triggerCrash() {
            if (isCrashing) return;
            isCrashing = true;
            gameStarted = false;

            // Stop all flight audio immediately
            stopEngineSound();
            stopWindSound();
            stopHellbatReactor();
            stopStealthReactor();

            // Force stop all boost-related sounds
            if (typeof stopBoostWind === 'function') stopBoostWind();
            if (typeof stopHellbatBoostSustain === 'function') stopHellbatBoostSustain();

            // Kill any lingering Hellbat oscillators explicitly
            if (window.hellbatBoostWhineOsc) {
                try { window.hellbatBoostWhineOsc.stop(); } catch (e) { }
                window.hellbatBoostWhineOsc = null;
            }
            if (window.hellbatBoostTurbineOsc) {
                try { window.hellbatBoostTurbineOsc.stop(); } catch (e) { }
                window.hellbatBoostTurbineOsc = null;
            }

            // Kill Death Ray sound
            if (window.deathRayOsc) {
                try { window.deathRayOsc.stop(); } catch (e) { }
                window.deathRayOsc = null;
            }

            // Play crash sounds
            playCrashSound();

            // Show crash overlay
            document.getElementById('crashOverlay').style.display = 'block';

            // Create massive explosion at crash site
            createCrashExplosion(playerJet.position.clone());

            // Create debris
            createCrashDebris(playerJet.position.clone());

            // Hide the player jet
            playerJet.visible = false;

            // Screen shake
            document.body.classList.add('shake');

            // Stop death ray if active
            stopDeathRay();

            // Transition to game over after crash animation
            setTimeout(() => {
                document.body.classList.remove('shake');
            }, 500);

            setTimeout(() => {
                showGameOver();
            }, 2000);
        }

        function createCrashExplosion(position) {
            // Primary explosion
            const colors = [0xff6600, 0xff3300, 0xffaa00, 0xffff00, 0xff0000, 0xff8800];

            // Multiple explosion waves
            for (let wave = 0; wave < 3; wave++) {
                setTimeout(() => {
                    const particles = new THREE.Group();

                    for (let i = 0; i < 50; i++) {
                        const size = 2 + Math.random() * 5;
                        const mat = new THREE.MeshBasicMaterial({
                            color: colors[Math.floor(Math.random() * colors.length)],
                            transparent: true,
                            opacity: 1
                        });
                        const particle = new THREE.Mesh(new THREE.SphereGeometry(size, 6, 6), mat);
                        particle.position.copy(position);
                        particle.position.y = Math.max(particle.position.y, GROUND_LEVEL + 20);
                        particle.velocity = new THREE.Vector3(
                            (Math.random() - 0.5) * 30,
                            Math.random() * 25 + 5,
                            (Math.random() - 0.5) * 30
                        );
                        particles.add(particle);
                    }

                    particles.life = 80;
                    scene.add(particles);
                    explosions.push(particles);

                    playExplosion();
                }, wave * 150);
            }

            // Fire burst
            const fireGeo = new THREE.SphereGeometry(15, 16, 16);
            const fireMat = new THREE.MeshBasicMaterial({
                color: 0xff4400,
                transparent: true,
                opacity: 0.9
            });
            const fireBall = new THREE.Mesh(fireGeo, fireMat);
            fireBall.position.copy(position);
            fireBall.position.y = Math.max(fireBall.position.y, GROUND_LEVEL + 15);
            scene.add(fireBall);

            // Animate fireball
            let fireLife = 60;
            const fireInterval = setInterval(() => {
                fireLife--;
                fireBall.scale.multiplyScalar(1.05);
                fireBall.material.opacity = fireLife / 60 * 0.9;
                fireBall.position.y += 0.5;

                if (fireLife <= 0) {
                    clearInterval(fireInterval);
                    scene.remove(fireBall);
                }
            }, 16);

            // Smoke column
            for (let i = 0; i < 20; i++) {
                setTimeout(() => {
                    const smokeGeo = new THREE.SphereGeometry(3 + Math.random() * 4, 8, 8);
                    const smokeMat = new THREE.MeshBasicMaterial({
                        color: 0x333333,
                        transparent: true,
                        opacity: 0.7
                    });
                    const smoke = new THREE.Mesh(smokeGeo, smokeMat);
                    smoke.position.copy(position);
                    smoke.position.y = Math.max(smoke.position.y, GROUND_LEVEL + 10) + i * 3;
                    smoke.position.x += (Math.random() - 0.5) * 10;
                    smoke.position.z += (Math.random() - 0.5) * 10;
                    scene.add(smoke);

                    let smokeLife = 100;
                    const smokeInterval = setInterval(() => {
                        smokeLife--;
                        smoke.position.y += 1;
                        smoke.scale.multiplyScalar(1.02);
                        smoke.material.opacity = smokeLife / 100 * 0.7;

                        if (smokeLife <= 0) {
                            clearInterval(smokeInterval);
                            scene.remove(smoke);
                        }
                    }, 16);
                }, i * 50);
            }
        }

        function createCrashDebris(position) {
            // Jet parts flying off
            const debrisColors = [0x333333, 0x444444, 0x555555, 0x222222, 0x666666];
            const debrisShapes = [
                new THREE.BoxGeometry(3, 0.5, 2),
                new THREE.BoxGeometry(2, 2, 0.5),
                new THREE.ConeGeometry(0.8, 3, 6),
                new THREE.CylinderGeometry(0.5, 0.5, 2, 8),
                new THREE.BoxGeometry(4, 0.3, 1.5)
            ];

            for (let i = 0; i < 25; i++) {
                const geo = debrisShapes[Math.floor(Math.random() * debrisShapes.length)];
                const mat = new THREE.MeshPhongMaterial({
                    color: debrisColors[Math.floor(Math.random() * debrisColors.length)],
                    shininess: 50
                });
                const debris = new THREE.Mesh(geo, mat);
                debris.position.copy(position);
                debris.position.y = Math.max(debris.position.y, GROUND_LEVEL + 15);

                debris.velocity = new THREE.Vector3(
                    (Math.random() - 0.5) * 25,
                    Math.random() * 20 + 5,
                    (Math.random() - 0.5) * 25
                );
                debris.rotationVel = new THREE.Vector3(
                    (Math.random() - 0.5) * 0.3,
                    (Math.random() - 0.5) * 0.3,
                    (Math.random() - 0.5) * 0.3
                );
                debris.life = 150;
                debris.castShadow = true;

                scene.add(debris);
                crashDebris.push(debris);
            }

            // Sparks
            for (let i = 0; i < 40; i++) {
                const sparkGeo = new THREE.SphereGeometry(0.3, 4, 4);
                const sparkMat = new THREE.MeshBasicMaterial({
                    color: Math.random() > 0.5 ? 0xffaa00 : 0xffff00,
                    transparent: true,
                    opacity: 1
                });
                const spark = new THREE.Mesh(sparkGeo, sparkMat);
                spark.position.copy(position);
                spark.position.y = Math.max(spark.position.y, GROUND_LEVEL + 10);

                spark.velocity = new THREE.Vector3(
                    (Math.random() - 0.5) * 40,
                    Math.random() * 30,
                    (Math.random() - 0.5) * 40
                );
                spark.life = 40 + Math.random() * 30;

                scene.add(spark);
                crashDebris.push(spark);
            }
        }

        function updateCrashDebris() {
            for (let i = crashDebris.length - 1; i >= 0; i--) {
                const debris = crashDebris[i];
                debris.life--;

                // Apply velocity
                debris.position.add(debris.velocity);

                // Apply gravity
                debris.velocity.y -= 0.3;

                // Apply rotation if it exists
                if (debris.rotationVel) {
                    debris.rotation.x += debris.rotationVel.x;
                    debris.rotation.y += debris.rotationVel.y;
                    debris.rotation.z += debris.rotationVel.z;
                }

                // Ground collision
                if (debris.position.y < GROUND_LEVEL + 5) {
                    debris.position.y = GROUND_LEVEL + 5;
                    debris.velocity.y *= -0.3;
                    debris.velocity.x *= 0.8;
                    debris.velocity.z *= 0.8;
                    if (debris.rotationVel) {
                        debris.rotationVel.multiplyScalar(0.5);
                    }
                }

                // Fade out
                if (debris.material && debris.life < 30) {
                    debris.material.opacity = debris.life / 30;
                    debris.material.transparent = true;
                }

                // Remove when life expires
                if (debris.life <= 0) {
                    scene.remove(debris);
                    crashDebris.splice(i, 1);
                }
            }
        }

        function showGameOver() {
            document.getElementById('crashOverlay').style.display = 'none';
            document.getElementById('gameOver').style.display = 'flex';
            document.getElementById('crashCause').textContent = crashCause;
            document.getElementById('finalScore').textContent = 'SCORE: ' + score;
            document.getElementById('finalKills').textContent = 'KILLS: ' + kills;
        }

        function gameOver() {
            // Health-based death
            crashCause = 'CRITICAL DAMAGE';
            triggerCrash();
        }

        function restartGame() {
            try {
                // Safely remove objects
                const objectsToRemove = [
                    ...(typeof enemies !== 'undefined' ? enemies : []),
                    ...(typeof bullets !== 'undefined' ? bullets : []),
                    ...(typeof enemyBullets !== 'undefined' ? enemyBullets : []),
                    ...(typeof missiles !== 'undefined' ? missiles : []),
                    ...(typeof explosions !== 'undefined' ? explosions : []),
                    ...(typeof crashDebris !== 'undefined' ? crashDebris : [])
                ];
                objectsToRemove.forEach(o => {
                    if (o && o.parent) o.parent.remove(o);
                    else scene.remove(o);
                });
            } catch (e) {
                console.error("Error clearing scene:", e);
            }

            enemies = []; bullets = []; enemyBullets = []; missiles = []; explosions = []; crashDebris = [];

            // Stop death ray if active
            stopDeathRay();

            // Reset crash state
            isCrashing = false;
            crashCause = 'TERRAIN COLLISION';
            document.getElementById('crashOverlay').style.display = 'none';
            document.body.classList.remove('shake');

            playerJet.position.set(0, 300, 0);
            playerJet.rotation.set(0, 0, 0);
            playerJet.quaternion.set(0, 0, 0, 1);
            player.speed = 3;
            player.pitchSpeed = player.rollSpeed = player.yawSpeed = 0;
            player.isRolling = false;
            player.currentBankAngle = 0;

            health = 100; score = 0; kills = 0;
            currentMode = 0; executionCharge = 100; executionCooldown = 0;
            forcefieldActive = false; absorbedDamage = 0; shockwaveReady = false;
            dashCooldown = 0; isDashing = false; isInvincible = false;
            isOutsideDomain = false; domainWarningCountdown = 3;
            isAiming = false; timeScale = 1; lockProgress = 0;
            lockedEnemy = null; lockPersistTimer = 0; aimTarget = null;
            isRebounding = false; reboundTimer = 0;
            player.isBoosting = false;

            // Restart audio systems
            stopTrackingSound();
            stopBoostWind();
            stopTerrainRush();
            if (!isEngineRunning) startEngineSound();
            if (!isWindRunning) startWindSound();

            const hp = playerJet.getObjectByName('hellbatParts');
            if (hp) hp.visible = false;

            // Make jet visible again after crash
            playerJet.visible = true;

            // Reset forcefield to invisible
            const forcefield = playerJet.getObjectByName('forcefield');
            if (forcefield) {
                forcefield.material.opacity = 0;
            }

            // Reset all materials to fully opaque (except forcefield)
            playerJet.traverse(c => {
                if (c.material && c.name !== 'forcefield' && c.name !== 'cockpit') {
                    c.material.transparent = false;
                    c.material.opacity = 1;
                }
            });

            const fuselage = playerJet.getObjectByName('fuselage');
            const wings = playerJet.getObjectByName('wings');
            const cockpit = playerJet.getObjectByName('cockpit');
            const glow1 = playerJet.getObjectByName('glow1');
            const glow2 = playerJet.getObjectByName('glow2');

            // Reset to NORMAL mode matte grey colors
            if (fuselage) { fuselage.material.color.setHex(0x6b6b70); fuselage.material.transparent = false; fuselage.material.opacity = 1; }
            if (wings) { wings.traverse(c => { if (c.material) { c.material.color.setHex(0x4a4a50); c.material.transparent = false; c.material.opacity = 1; } }); }
            if (cockpit) { cockpit.material.color.setHex(0x1a4a6a); cockpit.material.opacity = 0.65; cockpit.material.transparent = true; }
            if (glow1) glow1.material.color.setHex(0xe8f4ff);
            if (glow2) glow2.material.color.setHex(0xe8f4ff);

            document.getElementById('healthFill').style.width = '100%';
            document.getElementById('modeIndicator').textContent = 'NORMAL';
            document.getElementById('modeIndicator').className = 'normal';
            document.getElementById('crosshair').className = '';

            // Hide ALL mode overlays
            ['hellbatTint', 'forcefieldOverlay', 'stealthTint', 'motionBlur', 'domainEdgeGlow', 'invincibilityFlash'].forEach(id => {
                const el = document.getElementById(id);
                if (el) {
                    el.style.display = 'none';
                    el.classList.remove('active');
                }
            });

            // Reset ability bars
            document.getElementById('hellbatBar').querySelector('.ability-fill').style.width = '100%';
            document.getElementById('forcefieldBar').querySelector('.ability-fill').style.width = '0%';
            document.getElementById('shockwaveBar').querySelector('.ability-fill').style.width = '0%';
            document.getElementById('domainWarning').classList.remove('active');

            // Hide aim lens and related UI
            document.getElementById('aimLens').classList.remove('active', 'rotating', 'locked');
            document.getElementById('slowMoOverlay').classList.remove('active');
            document.getElementById('lockedIndicator').style.display = 'none';
            document.getElementById('targetBox').style.display = 'none';

            document.getElementById('gameOver').style.display = 'none';
            gameStarted = true;
        }

        // Title Screen Audio
        let titleAudioNodes = [];

        function startTitleAudio() {
            if (titleAudioNodes.length > 0) return;
            if (!audioCtx) audioCtx = new (window.AudioContext || window.webkitAudioContext)();
            if (audioCtx.state === 'suspended') audioCtx.resume();

            // Wind Noise (Procedural)
            const bufferSize = audioCtx.sampleRate * 2;
            const buffer = audioCtx.createBuffer(1, bufferSize, audioCtx.sampleRate);
            const data = buffer.getChannelData(0);
            for (let i = 0; i < bufferSize; i++) {
                data[i] = Math.random() * 2 - 1;
            }

            const noise = audioCtx.createBufferSource();
            noise.buffer = buffer;
            noise.loop = true;

            const noiseFilter = audioCtx.createBiquadFilter();
            noiseFilter.type = 'lowpass';
            noiseFilter.frequency.value = 400;

            const noiseGain = audioCtx.createGain();
            noiseGain.gain.value = 0.1; // Subtle wind

            noise.connect(noiseFilter);
            noiseFilter.connect(noiseGain);
            noiseGain.connect(audioCtx.destination);
            noise.start();
            titleAudioNodes.push(noise);

            // Engine Hum (Low Drone)
            const hum = audioCtx.createOscillator();
            hum.type = 'sawtooth';
            hum.frequency.value = 50;

            const humFilter = audioCtx.createBiquadFilter();
            humFilter.type = 'lowpass';
            humFilter.frequency.value = 120;

            const humGain = audioCtx.createGain();
            humGain.gain.value = 0.05; // Faint

            hum.connect(humFilter);
            humFilter.connect(humGain);
            humGain.connect(audioCtx.destination);
            hum.start();
            titleAudioNodes.push(hum);
        }

        function stopTitleAudio() {
            titleAudioNodes.forEach(node => {
                try { node.stop(); } catch (e) { }
            });
            titleAudioNodes = [];
        }

        // Init audio on interaction
        window.addEventListener('click', () => {
            if (!gameStarted && titleAudioNodes.length === 0) {
                try { startTitleAudio(); } catch (e) { }
            }
        }, { once: true });

        // Menu clouds
        function createMenuClouds() {
            const container = document.getElementById('menuClouds');
            for (let i = 0; i < 12; i++) {
                const cloud = document.createElement('div');
                cloud.className = 'menu-cloud';
                const size = 120 + Math.random() * 200;
                cloud.style.width = size + 'px';
                cloud.style.height = size * 0.4 + 'px';
                cloud.style.left = Math.random() * 100 + '%';
                cloud.style.top = 5 + Math.random() * 35 + '%';
                cloud.style.opacity = 0.7 + Math.random() * 0.3;
                container.appendChild(cloud);
            }
        }
        createMenuClouds();

        function startGame() {
            if (gameStarted) return;

            triggerConfirmFeedback();

            document.getElementById('startScreen').style.display = 'none';
            if (!audioCtx) audioCtx = new AudioContext();

            stopTitleAudio();

            gameStarted = true;

            // Initialize cinematic audio systems
            startEngineSound();
            startWindSound();

            document.body.classList.add('no-cursor');
        }
        function triggerConfirmFeedback() {
            playConfirmSound();
            const flash = document.getElementById('confirmFlash');
            if (flash) {
                flash.classList.add('active');
                setTimeout(() => flash.classList.remove('active'), 150);
            }
        }

        function playConfirmSound() {
            if (!audioCtx) return;
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();
            osc.type = 'triangle';
            osc.frequency.setValueAtTime(400, audioCtx.currentTime);
            osc.frequency.exponentialRampToValueAtTime(800, audioCtx.currentTime + 0.1);

            osc.connect(gain);
            gain.connect(audioCtx.destination);

            gain.gain.setValueAtTime(0.3, audioCtx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.2);

            osc.start();
            osc.stop(audioCtx.currentTime + 0.2);
        }

        document.getElementById('startBtn').addEventListener('click', startGame);

        document.getElementById('restartBtn').addEventListener('click', () => {
            console.log("Respawn button clicked");
            try {
                triggerConfirmFeedback();
                restartGame();
            } catch (e) {
                console.error("Respawn failed:", e);
                // Force reload if game state is corrupted
                location.reload();
            }
        });

        // ========== PAUSE SYSTEM ==========
        let gamePaused = false;

        function playPauseSound() {
            if (!audioCtx) return;
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();
            osc.type = 'sine';
            osc.frequency.setValueAtTime(800, audioCtx.currentTime);
            osc.frequency.exponentialRampToValueAtTime(400, audioCtx.currentTime + 0.1);
            osc.connect(gain);
            gain.connect(audioCtx.destination);
            gain.gain.setValueAtTime(0.08, audioCtx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.15);
            osc.start();
            osc.stop(audioCtx.currentTime + 0.15);
        }

        function playResumeSound() {
            if (!audioCtx) return;
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();
            osc.type = 'sine';
            osc.frequency.setValueAtTime(400, audioCtx.currentTime);
            osc.frequency.exponentialRampToValueAtTime(800, audioCtx.currentTime + 0.1);
            osc.connect(gain);
            gain.connect(audioCtx.destination);
            gain.gain.setValueAtTime(0.08, audioCtx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + 0.15);
            osc.start();
            osc.stop(audioCtx.currentTime + 0.15);
        }

        function togglePause() {
            gamePaused = !gamePaused;

            if (gamePaused) {
                playPauseSound();
                document.getElementById('pauseOverlay').classList.add('active');
                document.body.classList.remove('no-cursor');

                // Only suspend audio if game is actually running (not title screen)
                if (gameStarted && audioCtx && audioCtx.state === 'running') {
                    // Delay suspension slightly to let pause sound play
                    setTimeout(() => {
                        if (gamePaused && audioCtx.state === 'running') audioCtx.suspend();
                    }, 100);
                }
            } else {
                if (audioCtx && audioCtx.state === 'suspended') {
                    audioCtx.resume().then(() => {
                        playResumeSound();
                    });
                } else {
                    playResumeSound();
                }
                document.getElementById('pauseOverlay').classList.remove('active');
                document.body.classList.add('no-cursor');
            }
        }

        // Pause button click handler
        document.getElementById('pauseBtn').addEventListener('click', () => {
            togglePause();
        });

        // Resume button click handler
        document.getElementById('resumeBtn').addEventListener('click', () => {
            if (gamePaused) togglePause();
        });

        // P key to toggle pause
        document.addEventListener('keydown', (e) => {
            if (e.code === 'KeyP') {
                togglePause();
            }

            if (e.code === 'Enter') {
                if (!gameStarted && document.getElementById('startScreen').style.display !== 'none') {
                    // Start Game from Title
                    startGame();
                } else if (document.getElementById('gameOver').style.display !== 'none') {
                    // Respawn from Game Over
                    try {
                        triggerConfirmFeedback();
                        restartGame();
                    } catch (e) {
                        console.error("Respawn shortcut failed:", e);
                        location.reload();
                    }
                }
            }
        });

        // Spawn enemies
        setInterval(() => { if (gameStarted && enemies.length < 10) spawnEnemy(); }, 3000);
        setTimeout(() => { for (let i = 0; i < 4; i++) spawnEnemy(); }, 1500);

        window.addEventListener('resize', () => {
            camera.aspect = window.innerWidth / window.innerHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth, window.innerHeight);
        });


        // ========== CREATIVE UPGRADES SYSTEM ==========
        // Combo & Kill Streak State
        let comboCount = 0;
        let comboTimer = 0;
        const COMBO_TIMEOUT = 180; // 3 seconds at 60fps
        let killStreak = 0;
        let lastKillTime = 0;
        let isOverdriveActive = false;
        let overdriveTimer = 0;
        const OVERDRIVE_DURATION = 600; // 10 seconds at 60fps
        let rapidFireActive = false;
        let rapidFireTimer = 0;
        const RAPID_FIRE_DURATION = 480; // 8 seconds

        // Power-up drops
        let powerUps = [];

        // Speed lines
        let speedLinesGenerated = false;

        // Boss tracking
        let bossEnemy = null;
        let totalKillsForBoss = 0;
        const BOSS_SPAWN_KILLS = 20;

        // Initialize speed lines
        function initSpeedLines() {
            const container = document.getElementById('speedLinesInner');
            if (!container || speedLinesGenerated) return;

            for (let i = 0; i < 40; i++) {
                const line = document.createElement('div');
                line.className = 'speed-line';
                const angle = (i / 40) * 360;
                const length = 100 + Math.random() * 200;
                const width = 1 + Math.random() * 2;
                const delay = Math.random() * 0.5;

                line.style.cssText = `
                    left: 50%;
                    top: 50%;
                    width: ${width}px;
                    height: ${length}px;
                    transform: rotate(${angle}deg) translateY(-${100 + Math.random() * 50}%);
                    opacity: ${0.2 + Math.random() * 0.3};
                    animation-delay: ${delay}s;
                `;
                container.appendChild(line);
            }
            speedLinesGenerated = true;
        }

        // Call on game start
        setTimeout(initSpeedLines, 100);

        // Record enemy kill with combo and streak
        function recordEnemyKill(enemyType, baseScore) {
            const now = Date.now();

            // Combo system - kills within 3 seconds build combo
            if (now - lastKillTime < 3000) {
                comboCount++;
            } else {
                comboCount = 1;
            }
            lastKillTime = now;
            comboTimer = COMBO_TIMEOUT;

            // Calculate multiplier
            const multiplier = Math.min(5, Math.floor(comboCount / 2) + 1);
            const finalScore = baseScore * multiplier;

            // Update combo UI
            updateComboUI(comboCount, multiplier);

            // Kill streak
            killStreak++;
            totalKillsForBoss++;

            // Streak milestones
            checkStreakMilestone(killStreak);

            // Add kill to feed
            addKillToFeed(enemyType, finalScore);

            // Check for boss spawn
            // First boss at 20 kills, then every 10 kills (40, 50, 60, 70, etc.)
            let nextBossThreshold = totalKillsForBoss < 20 ? 20 : 10;
            if (totalKillsForBoss >= nextBossThreshold && !bossEnemy) {
                spawnBoss();
                totalKillsForBoss = 0;
            }

            // Chance to drop power-up
            if (Math.random() < 0.15) {
                // 15% chance for power-up
                dropPowerUp();
            }

            return finalScore;
        }

        function updateComboUI(count, multiplier) {
            const container = document.getElementById('comboContainer');
            const countEl = document.getElementById('comboCount');
            const multEl = document.getElementById('comboMultiplier');

            if (count >= 2) {
                container.classList.add('active');
                countEl.textContent = count;
                countEl.style.animation = 'none';
                void countEl.offsetWidth; // Trigger reflow
                countEl.style.animation = 'comboPulse 0.3s ease-out';
                multEl.textContent = `×${multiplier}`;

                // Color escalation
                container.className = 'active';
                if (count >= 10) container.classList.add('combo-5');
                else if (count >= 6) container.classList.add('combo-4');
                else if (count >= 4) container.classList.add('combo-3');
            }
        }

        function checkStreakMilestone(streak) {
            const streakBanner = document.getElementById('streakBanner');
            const streakText = document.getElementById('streakText');
            const streakSubtext = document.getElementById('streakSubtext');

            let showBanner = false;
            let bannerClass = '';

            if (streak === 3) {
                streakText.textContent = 'KILLING SPREE!';
                streakSubtext.textContent = '+10 HP RESTORED';
                bannerClass = 'streak-3';
                showBanner = true;
                // Heal reward
                health = Math.min(100, health + 10);
                updateHP(health);
                playStreakSound(3);
            } else if (streak === 5) {
                streakText.textContent = 'RAMPAGE!';
                streakSubtext.textContent = '+15 HP RESTORED';
                bannerClass = 'streak-5';
                showBanner = true;
                health = Math.min(100, health + 15);
                updateHP(health);
                playStreakSound(5);
            } else if (streak === 10) {
                streakText.textContent = 'GODLIKE!';
                streakSubtext.textContent = 'OVERDRIVE ACTIVATED';
                bannerClass = 'streak-10';
                showBanner = true;
                activateOverdrive();
                playStreakSound(10);
            } else if (streak === 15) {
                streakText.textContent = 'UNSTOPPABLE!';
                streakSubtext.textContent = '+25 HP RESTORED';
                bannerClass = 'streak-10';
                showBanner = true;
                health = Math.min(100, health + 25);
                updateHP(health);
                playStreakSound(10);
            }

            if (showBanner) {
                streakBanner.className = `active ${bannerClass}`;
                setTimeout(() => {
                    streakBanner.classList.remove('active');
                    streakBanner.classList.add('fadeOut');
                }, 2000);
            }
        }

        function activateOverdrive() {
            isOverdriveActive = true;
            overdriveTimer = OVERDRIVE_DURATION;
            document.getElementById('overdriveOverlay').style.display = 'block';
        }

        function addKillToFeed(enemyType, score) {
            const feed = document.getElementById('killFeed');
            const item = document.createElement('div');
            item.className = 'kill-feed-item';
            item.innerHTML = `<span class="enemy-type">${enemyType}</span> DESTROYED <span class="score">+${score}</span>`;

            feed.insertBefore(item, feed.firstChild);

            // Keep only last 3 items
            while (feed.children.length > 3) {
                feed.removeChild(feed.lastChild);
            }

            // Auto-remove after 3 seconds
            setTimeout(() => {
                if (item.parentNode) {
                    item.remove();
                }
            }, 3000);
        }

        // Damage direction indicator
        function showDamageDirection(damageSource) {
            if (!damageSource) return;

            // Calculate direction from player to damage source
            const toSource = new THREE.Vector3().subVectors(damageSource, playerJet.position);
            const forward = new THREE.Vector3(0, 0, -1).applyQuaternion(playerJet.quaternion);
            const right = new THREE.Vector3(1, 0, 0).applyQuaternion(playerJet.quaternion);

            const forwardDot = toSource.normalize().dot(forward);
            const rightDot = toSource.dot(right);

            let arcClass = 'damage-arc-rear';
            if (forwardDot > 0.5) arcClass = 'damage-arc-top'; // Front
            else if (forwardDot < -0.5) arcClass = 'damage-arc-bottom'; // Behind  
            else if (rightDot > 0) arcClass = 'damage-arc-right';
            else arcClass = 'damage-arc-left';

            const arc = document.querySelector(`.${arcClass}`);
            if (arc) {
                arc.classList.add('active');
                setTimeout(() => arc.classList.remove('active'), 400);
            }
        }

        // Speed lines update
        function updateSpeedLines() {
            const speedLines = document.getElementById('speedLines');
            if (!speedLines) return;

            const stats = modeStats[currentMode];
            const maxSpeed = player.maxSpeed * stats.speedMult;
            const speedRatio = player.speed / maxSpeed;

            if (speedRatio > 0.7) {
                speedLines.classList.add('active');
                speedLines.style.opacity = (speedRatio - 0.7) * 3; // 0-0.9 opacity
            } else {
                speedLines.classList.remove('active');
            }

            // Mode class for colors
            document.body.classList.remove('hellbat-mode', 'stealth-mode');
            if (currentMode === 1) document.body.classList.add('hellbat-mode');
            else if (currentMode === 2) document.body.classList.add('stealth-mode');
        }

        // Power-up system
        function dropPowerUp() {
            // Random position near last kill
            const pos = playerJet.position.clone();
            pos.x += (Math.random() - 0.5) * 100;
            pos.z += (Math.random() - 0.5) * 100;
            pos.y = Math.max(100, pos.y);

            // Random type: Health (70%) or Rapid Fire (30%)
            const type = Math.random() < 0.7 ? 'health' : 'rapidfire';
            const color = type === 'health' ? 0x00ff00 : 0xff4400;

            const geo = new THREE.SphereGeometry(8, 16, 16);
            const mat = new THREE.MeshBasicMaterial({
                color: color,
                transparent: true,
                opacity: 0.8
            });
            const powerup = new THREE.Mesh(geo, mat);
            powerup.position.copy(pos);
            powerup.userData = { type: type, life: 600 }; // 10 seconds

            // Add glow ring
            const ringGeo = new THREE.RingGeometry(10, 12, 32);
            const ringMat = new THREE.MeshBasicMaterial({
                color: color,
                transparent: true,
                opacity: 0.5,
                side: THREE.DoubleSide
            });
            const ring = new THREE.Mesh(ringGeo, ringMat);
            powerup.add(ring);

            scene.add(powerup);
            powerUps.push(powerup);
        }

        function updatePowerUps() {
            for (let i = powerUps.length - 1; i >= 0; i--) {
                const pu = powerUps[i];
                pu.userData.life--;
                pu.rotation.y += 0.05;

                // Bobbing motion
                pu.position.y += Math.sin(Date.now() * 0.005) * 0.2;

                // Check collection
                const dist = pu.position.distanceTo(playerJet.position);
                if (dist < 30) {
                    collectPowerUp(pu.userData.type);
                    scene.remove(pu);
                    powerUps.splice(i, 1);
                    continue;
                }

                // Timeout removal
                if (pu.userData.life <= 0) {
                    scene.remove(pu);
                    powerUps.splice(i, 1);
                }
            }
        }

        function collectPowerUp(type) {
            if (type === 'health') {
                health = Math.min(100, health + 25);
                updateHP(health);
                showPowerUpIndicator('health');
                playPowerUpSound();
            } else if (type === 'rapidfire') {
                rapidFireActive = true;
                rapidFireTimer = RAPID_FIRE_DURATION;
                showPowerUpIndicator('rapidfire');
                playPowerUpSound();
            }
        }

        function showPowerUpIndicator(type) {
            const indicator = type === 'health'
                ? document.getElementById('healthBoostIndicator')
                : document.getElementById('rapidFireIndicator');

            if (indicator) {
                indicator.style.display = 'block';
                setTimeout(() => indicator.style.display = 'none', 2000);
            }
        }

        // Boss spawn
        function spawnBoss() {
            const boss = createEnemyJet('BOSS'); // Use BOSS type, not ASSAULT
            boss.scale.set(3.5, 3.5, 3.5); // Much bigger - 3.5x scale (was 2x)
            boss.userData.health = 2000; // Much higher health - takes multiple hits
            boss.userData.maxHealth = 2000;
            boss.userData.isBoss = true;
            boss.userData.type = 'BOSS';

            // Spawn boss directly in front of player at a dramatic distance
            const forward = new THREE.Vector3(0, 0, -1).applyQuaternion(playerJet.quaternion);
            const spawnDistance = 800; // Distance in front of player
            boss.position.set(
                playerJet.position.x + forward.x * spawnDistance,
                playerJet.position.y + 50, // Slightly above player
                playerJet.position.z + forward.z * spawnDistance
            );
            // Make boss face the player
            boss.lookAt(playerJet.position);

            scene.add(boss);
            enemies.push(boss);
            bossEnemy = boss;

            // Show boss health bar
            document.getElementById('bossHealthContainer').style.display = 'block';
            updateBossHealth();

            playBossSpawnSound();
        }

        function updateBossHealth() {
            if (!bossEnemy) {
                document.getElementById('bossHealthContainer').style.display = 'none';
                return;
            }

            const fill = document.getElementById('bossHealthFill');
            const text = document.getElementById('bossHealthText');

            const hp = bossEnemy.userData.health;
            const maxHp = bossEnemy.userData.maxHealth;
            const pct = (hp / maxHp) * 100;

            fill.style.width = pct + '%';
            text.textContent = `${Math.max(0, Math.floor(hp))} / ${maxHp}`;

            if (hp <= 0) {
                bossEnemy = null;
                document.getElementById('bossHealthContainer').style.display = 'none';
            }
        }

        // Audio for streaks
        function playStreakSound(level) {
            if (!audioCtx) return;

            const baseFreq = 400 + level * 50;
            for (let i = 0; i < 3; i++) {
                setTimeout(() => {
                    playSound(baseFreq + i * 100, 'sine', 0.15, 0.2);
                }, i * 80);
            }
        }

        function playPowerUpSound() {
            if (!audioCtx) return;
            playSound(600, 'sine', 0.1, 0.1);
            setTimeout(() => playSound(800, 'sine', 0.1, 0.1), 50);
            setTimeout(() => playSound(1000, 'sine', 0.15, 0.15), 100);
        }

        function playBossSpawnSound() {
            if (!audioCtx) return;
            playSound(100, 'sawtooth', 0.3, 0.5);
            setTimeout(() => playSound(80, 'sawtooth', 0.4, 0.6), 200);
        }

        // Update creative systems in game loop
        function updateCreativeSystems() {
            // Combo timer decay
            if (comboTimer > 0) {
                comboTimer--;
                if (comboTimer <= 0) {
                    comboCount = 0;
                    document.getElementById('comboContainer').classList.remove('active');
                }
            }

            // Overdrive timer
            if (isOverdriveActive) {
                overdriveTimer--;
                if (overdriveTimer <= 0) {
                    isOverdriveActive = false;
                    document.getElementById('overdriveOverlay').style.display = 'none';
                }
            }

            // Rapid fire timer
            if (rapidFireActive) {
                rapidFireTimer--;
                if (rapidFireTimer <= 0) {
                    rapidFireActive = false;
                    document.getElementById('rapidFireIndicator').style.display = 'none';
                }
            }

            // Speed lines
            updateSpeedLines();

            // Power-ups
            updatePowerUps();

            // Boss health
            if (bossEnemy) updateBossHealth();
        }

        // Reset streak on damage
        function resetKillStreak() {
            killStreak = 0;
        }

        animate();

    </script>
</body>

</html>
