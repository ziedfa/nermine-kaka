<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nermineee's Ultimate Birthday Bash!</title>
    <link href="https://fonts.googleapis.com/css2?family=Baloo+2:wght@700&family=Pacifico&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #FF4081;
            --secondary: #FF9100;
            --accent: #00B0FF;
            --light: #FFF9C4;
            --dark: #7B1FA2;
            --text: #333;
            --bg: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            --card-bg: rgba(255, 255, 255, 0.9);
        }
        
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }
        
        body {
            font-family: 'Baloo 2', cursive;
            background: var(--bg);
            overflow-x: hidden;
            color: var(--text);
            transition: all 0.5s ease;
            min-height: 100vh;
        }
        
        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            background: linear-gradient(rgba(0,0,0,0.3), rgba(0,0,0,0.3)), url('https://images.unsplash.com/photo-1530103862676-de8c9debad1d?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            position: relative;
            overflow: hidden;
            perspective: 1000px;
            padding: 20px;
        }
        
        .hero-content {
            transform-style: preserve-3d;
            animation: float 6s ease-in-out infinite;
            max-width: 90%;
        }
        
        .hero h1 {
            font-size: 5rem;
            margin: 0;
            text-shadow: 3px 3px 10px rgba(0,0,0,0.5);
            font-family: 'Pacifico', cursive;
            background: linear-gradient(45deg, #ff9a9e, #fad0c4, #a1c4fd, #c2e9fb);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradient 8s ease infinite;
            line-height: 1.2;
        }
        
        .hero p {
            font-size: 1.5rem;
            max-width: 800px;
            margin: 20px auto;
            text-shadow: 1px 1px 3px rgba(0,0,0,0.5);
            background: rgba(0,0,0,0.5);
            padding: 15px;
            border-radius: 20px;
            line-height: 1.5;
        }
        
        .scroll-down {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 2rem;
            animation: bounce 2s infinite;
            cursor: pointer;
            background: rgba(255,255,255,0.2);
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            backdrop-filter: blur(5px);
            border: 2px solid white;
            transition: all 0.3s ease;
        }
        
        .scroll-down:hover {
            background: rgba(255,255,255,0.3);
            transform: translateX(-50%) scale(1.1);
        }
        
        /* Container & Sections */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
        }
        
        section {
            margin: 80px 0;
            position: relative;
            scroll-margin-top: 80px;
        }
        
        h2 {
            text-align: center;
            font-size: 3rem;
            color: var(--dark);
            margin-bottom: 40px;
            position: relative;
            text-transform: uppercase;
            letter-spacing: 2px;
        }
        
        h2:after {
            content: '';
            display: block;
            width: 100px;
            height: 5px;
            background: var(--primary);
            margin: 15px auto;
            border-radius: 5px;
        }
        
        /* Countdown Section */
        .countdown {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 40px 0;
            flex-wrap: wrap;
        }
        
        .countdown-item {
            background: var(--card-bg);
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            text-align: center;
            min-width: 100px;
            transition: all 0.3s ease;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255,255,255,0.3);
        }
        
        .countdown-item:hover {
            transform: translateY(-10px) scale(1.05);
            box-shadow: 0 15px 30px rgba(0,0,0,0.2);
        }
        
        .countdown-number {
            font-size: 3rem;
            font-weight: bold;
            color: var(--primary);
        }
        
        .countdown-label {
            font-size: 1rem;
            color: #666;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        /* Gallery Section */
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 40px;
        }
        
        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            height: 300px;
            transition: all 0.3s ease;
            cursor: pointer;
            transform-style: preserve-3d;
        }
        
        .gallery-item:hover {
            transform: translateY(-10px) rotateY(10deg);
            box-shadow: 0 15px 30px rgba(0,0,0,0.3);
        }
        
        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .gallery-item:hover img {
            transform: scale(1.1) rotate(1deg);
        }
        
        .gallery-caption {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(transparent, rgba(0,0,0,0.8));
            color: white;
            padding: 20px;
            transform: translateY(100%);
            transition: transform 0.3s ease;
            backdrop-filter: blur(5px);
        }
        
        .gallery-item:hover .gallery-caption {
            transform: translateY(0);
        }
        
        /* Wishes Section */
        .wishes {
            background: linear-gradient(135deg, var(--light) 0%, #FFECB3 100%);
            padding: 60px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            position: relative;
            overflow: hidden;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255,255,255,0.3);
        }
        
        .wishes:before {
            content: '';
            position: absolute;
            top: -50px;
            right: -50px;
            width: 200px;
            height: 200px;
            background: var(--primary);
            border-radius: 50%;
            opacity: 0.2;
            filter: blur(30px);
        }
        
        .wishes:after {
            content: '';
            position: absolute;
            bottom: -80px;
            left: -80px;
            width: 300px;
            height: 300px;
            background: var(--accent);
            border-radius: 50%;
            opacity: 0.2;
            filter: blur(40px);
        }
        
        .wish {
            position: relative;
            z-index: 1;
            font-size: 1.2rem;
            line-height: 1.6;
            margin-bottom: 20px;
            padding: 15px 20px 15px 50px;
            border-left: 5px solid var(--primary);
            background: var(--card-bg);
            border-radius: 0 10px 10px 0;
            box-shadow: 5px 5px 15px rgba(0,0,0,0.05);
            animation: fadeIn 0.5s ease;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .wish:hover {
            transform: translateX(10px);
            box-shadow: 5px 5px 20px rgba(0,0,0,0.1);
        }
        
        .wish:before {
            content: '❤️';
            position: absolute;
            left: 15px;
            top: 15px;
            font-size: 1.5rem;
        }
        
        /* Interactive Elements */
        .interactive {
            text-align: center;
            margin: 30px 0;
        }
        
        .btn {
            display: inline-block;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            color: white;
            padding: 15px 30px;
            border-radius: 50px;
            font-size: 1.2rem;
            text-decoration: none;
            margin: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            position: relative;
            overflow: hidden;
            font-weight: bold;
            letter-spacing: 1px;
            text-transform: uppercase;
        }
        
        .btn:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 10px 20px rgba(0,0,0,0.3);
            background: linear-gradient(45deg, var(--secondary), var(--primary));
        }
        
        .btn:active {
            transform: translateY(0) scale(0.98);
        }
        
        .btn:after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 5px;
            height: 5px;
            background: rgba(255, 255, 255, 0.5);
            opacity: 0;
            border-radius: 100%;
            transform: scale(1, 1) translate(-50%);
            transform-origin: 50% 50%;
        }
        
        .btn:focus:not(:active)::after {
            animation: ripple 1s ease-out;
        }
        
        .btn-secondary {
            background: white;
            color: var(--primary);
            border: 2px solid var(--primary);
        }
        
        .btn-secondary:hover {
            background: var(--primary);
            color: white;
        }
        
        /* Cake Section */
        .cake-container {
            font-size: 8rem;
            margin: 30px 0;
            cursor: pointer;
            transition: all 0.3s ease;
            position: relative;
            display: inline-block;
            text-shadow: 0 5px 10px rgba(0,0,0,0.2);
            animation: pulse 2s infinite;
            user-select: none;
        }
        
        .cake-container:hover {
            transform: scale(1.2) rotate(5deg);
            animation: none;
        }
        
        .cake-container:active {
            transform: scale(0.9);
        }
        
        /* Balloons */
        .balloon {
            position: absolute;
            width: 60px;
            height: 80px;
            background: var(--primary);
            border-radius: 50%;
            animation: float 15s linear infinite;
            opacity: 0.8;
            z-index: -1;
            box-shadow: inset -5px -5px 10px rgba(0,0,0,0.2);
            filter: drop-shadow(0 5px 5px rgba(0,0,0,0.3));
        }
        
        .balloon:before {
            content: '';
            position: absolute;
            width: 2px;
            height: 120px;
            background: linear-gradient(to bottom, #ccc, transparent);
            bottom: -120px;
            left: 50%;
            transform: translateX(-50%);
        }
        
        /* Hearts */
        .heart {
            position: absolute;
            font-size: 2rem;
            animation: float 10s linear infinite;
            z-index: -1;
            filter: drop-shadow(0 3px 5px rgba(0,0,0,0.3));
        }
        
        /* Confetti */
        .confetti {
            position: fixed;
            width: 15px;
            height: 15px;
            background-color: var(--primary);
            opacity: 0;
            z-index: 9999;
            animation: confetti-fall 5s linear forwards;
            filter: drop-shadow(0 0 5px rgba(0,0,0,0.3));
        }
        
        /* Theme Selector */
        .theme-selector {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 1000;
            background: rgba(255,255,255,0.9);
            padding: 15px;
            border-radius: 20px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255,255,255,0.3);
            transform: translateY(0);
            transition: all 0.3s ease;
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            max-width: 120px;
        }
        
        .theme-selector:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
        }
        
        .theme-btn {
            width: 35px;
            height: 35px;
            border-radius: 50%;
            margin: 8px;
            cursor: pointer;
            border: 3px solid white;
            transition: all 0.3s ease;
            box-shadow: 0 3px 6px rgba(0,0,0,0.1);
        }
        
        .theme-btn:hover {
            transform: scale(1.1);
        }
        
        .theme-btn.active {
            transform: scale(1.2);
            box-shadow: 0 0 0 3px var(--text), 0 5px 15px rgba(0,0,0,0.2);
        }
        
        /* Music Control */
        #music-control {
            position: fixed;
            bottom: 20px;
            right: 20px;
            z-index: 1000;
            background: rgba(255,255,255,0.9);
            border-radius: 50%;
            width: 60px;
            height: 60px;
            display: flex;
            justify-content: center;
            align-items: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            cursor: pointer;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255,255,255,0.3);
            transform: translateY(0);
            transition: all 0.3s ease;
        }
        
        #music-control:hover {
            transform: translateY(-5px) scale(1.1);
            background: var(--primary);
            color: white;
        }
        
        #music-icon {
            font-size: 24px;
            transition: all 0.3s ease;
        }
        
        /* Progress Bar */
        .progress-container {
            width: 100%;
            height: 10px;
            background: rgba(0,0,0,0.1);
            border-radius: 5px;
            margin: 20px 0;
            overflow: hidden;
            box-shadow: inset 0 1px 3px rgba(0,0,0,0.2);
        }
        
        .progress-bar {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            width: 0%;
            transition: width 0.5s ease;
            border-radius: 5px;
        }
        
        /* Memory Game */
        .memory-game {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 15px;
            margin: 30px auto;
            max-width: 800px;
            perspective: 1000px;
        }
        
        .memory-card {
            height: 120px;
            background: var(--primary);
            border-radius: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 2.5rem;
            color: white;
            cursor: pointer;
            transition: all 0.3s ease;
            transform-style: preserve-3d;
            position: relative;
            box-shadow: 0 5px 10px rgba(0,0,0,0.2);
            transform: rotateY(180deg);
        }
        
        .memory-card .front-face,
        .memory-card .back-face {
            position: absolute;
            width: 100%;
            height: 100%;
            backface-visibility: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            border-radius: 10px;
        }
        
        .memory-card .front-face {
            background: white;
            color: var(--primary);
            transform: rotateY(180deg);
        }
        
        .memory-card .back-face {
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            color: white;
        }
        
        .memory-card.flipped {
            transform: rotateY(0deg);
        }
        
        .memory-card.matched {
            visibility: hidden;
            opacity: 0;
            transform: scale(0);
            transition: all 0.5s ease;
        }
        
        /* Video Message */
        .video-message {
            background: var(--card-bg);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            margin: 40px 0;
            text-align: center;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255,255,255,0.3);
        }
        
        .video-container {
            position: relative;
            padding-bottom: 56.25%;
            height: 0;
            overflow: hidden;
            max-width: 800px;
            margin: 20px auto;
            border-radius: 15px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
        }
        
        .video-container iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: none;
        }
        
        /* Guest Book */
        .guest-book {
            background: var(--card-bg);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            margin: 40px 0;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255,255,255,0.3);
        }
        
        .guest-entry {
            background: white;
            border-radius: 10px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            animation: fadeIn 0.5s ease;
        }
        
        .guest-name {
            font-weight: bold;
            color: var(--primary);
            margin-bottom: 5px;
        }
        
        .guest-message {
            color: var(--text);
        }
        
        .guest-form input,
        .guest-form textarea {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-family: 'Baloo 2', cursive;
            font-size: 1rem;
            transition: all 0.3s ease;
        }
        
        .guest-form input:focus,
        .guest-form textarea:focus {
            border-color: var(--primary);
            outline: none;
            box-shadow: 0 0 0 3px rgba(255, 64, 129, 0.2);
        }
        
        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.8);
            z-index: 2000;
            justify-content: center;
            align-items: center;
            animation: modalFadeIn 0.3s ease;
            backdrop-filter: blur(5px);
        }
        
        .modal-content {
            background: var(--card-bg);
            padding: 30px;
            border-radius: 20px;
            max-width: 90%;
            width: 500px;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
            box-shadow: 0 15px 40px rgba(0,0,0,0.3);
            animation: modalFadeIn 0.5s ease;
        }
        
        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--text);
            transition: all 0.3s ease;
        }
        
        .close-modal:hover {
            color: var(--primary);
            transform: rotate(90deg);
        }
        
        /* Animations */
        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-20px);
            }
        }
        
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateY(0) translateX(-50%);
            }
            40% {
                transform: translateY(-20px) translateX(-50%);
            }
            60% {
                transform: translateY(-10px) translateX(-50%);
            }
        }
        
        @keyframes gradient {
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
        
        @keyframes modalFadeIn {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes confetti-fall {
            0% {
                transform: translateY(-100vh) rotate(0deg) scale(1);
                opacity: 1;
            }
            100% {
                transform: translateY(100vh) rotate(360deg) scale(0.5);
                opacity: 0;
            }
        }
        
        @keyframes ripple {
            0% {
                transform: scale(0, 0);
                opacity: 1;
            }
            20% {
                transform: scale(25, 25);
                opacity: 1;
            }
            100% {
                opacity: 0;
                transform: scale(40, 40);
            }
        }
        
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes pulse {
            0% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.1);
            }
            100% {
                transform: scale(1);
            }
        }
        
        @keyframes spin {
            0% {
                transform: rotate(0deg);
            }
            100% {
                transform: rotate(360deg);
            }
        }
        
        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            10%, 30%, 50%, 70%, 90% { transform: translateX(-5px); }
            20%, 40%, 60%, 80% { transform: translateX(5px); }
        }
        
        /* Responsive adjustments */
        @media (max-width: 1024px) {
            .hero h1 {
                font-size: 4rem;
            }
            
            .memory-game {
                grid-template-columns: repeat(4, 1fr);
                max-width: 600px;
            }
            
            .memory-card {
                height: 100px;
                font-size: 2rem;
            }
        }
        
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 3rem;
            }
            
            .hero p {
                font-size: 1.2rem;
                padding: 10px;
            }
            
            h2 {
                font-size: 2rem;
            }
            
            .countdown {
                flex-wrap: wrap;
            }
            
            .countdown-item {
                min-width: 80px;
                padding: 15px;
            }
            
            .countdown-number {
                font-size: 2rem;
            }
            
            .wishes {
                padding: 30px;
            }
            
            .memory-game {
                grid-template-columns: repeat(3, 1fr);
            }
            
            .cake-container {
                font-size: 6rem;
            }
            
            .modal-content {
                width: 90%;
                padding: 20px;
            }
        }
        
        @media (max-width: 480px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .memory-game {
                grid-template-columns: repeat(2, 1fr);
                gap: 10px;
            }
            
            .memory-card {
                height: 80px;
                font-size: 1.5rem;
            }
            
            .btn {
                padding: 12px 20px;
                font-size: 1rem;
                margin: 5px;
            }
            
            .theme-selector {
                top: 10px;
                right: 10px;
                padding: 10px;
                max-width: 100px;
            }
            
            .theme-btn {
                width: 25px;
                height: 25px;
                margin: 5px;
            }
            
            .guest-book, .video-message, .wishes {
                padding: 20px;
            }
            
            .wish {
                padding: 10px 15px 10px 40px;
                font-size: 1rem;
            }
            
            .wish:before {
                left: 10px;
                top: 10px;
                font-size: 1.2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Theme Selector -->
    <div class="theme-selector">
        <div class="theme-btn active" style="background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);" onclick="changeTheme('default')" title="Default Theme"></div>
        <div class="theme-btn" style="background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%);" onclick="changeTheme('romantic')" title="Romantic Theme"></div>
        <div class="theme-btn" style="background: linear-gradient(135deg, #a1c4fd 0%, #c2e9fb 100%);" onclick="changeTheme('cool')" title="Cool Theme"></div>
        <div class="theme-btn" style="background: linear-gradient(135deg, #84fab0 0%, #8fd3f4 100%);" onclick="changeTheme('fresh')" title="Fresh Theme"></div>
    </div>
    
    <div class="hero">
        <div class="hero-content">
            <h1 id="birthday-title">Happy Birthday, Nermineee!</h1>
            <p id="birthday-subtitle">Today is all about you! Let's celebrate this special day in style<br>hevi mini hdiyet 3id miledik min "Hamza".</p>
        </div>
        <div class="scroll-down" onclick="scrollToContent()">
            <i class="fas fa-chevron-down"></i>
        </div>
        
        <!-- Floating balloons -->
        <div class="balloon" style="left: 10%; background: var(--primary); animation-delay: 0s;"></div>
        <div class="balloon" style="left: 20%; background: var(--secondary); animation-delay: 2s;"></div>
        <div class="balloon" style="left: 30%; background: var(--accent); animation-delay: 4s;"></div>
        <div class="balloon" style="left: 70%; background: var(--primary); animation-delay: 1s;"></div>
        <div class="balloon" style="left: 80%; background: var(--secondary); animation-delay: 3s;"></div>
        <div class="balloon" style="left: 90%; background: var(--accent); animation-delay: 5s;"></div>
        
        <!-- Floating hearts -->
        <div class="heart" style="left: 15%; animation-delay: 1.5s;"></div>
        <div class="heart" style="left: 25%; animation-delay: 3.5s;"></div>
        <div class="heart" style="left: 85%; animation-delay: 2.5s;"></div>
        <div class="heart" style="left: 75%; animation-delay: 4.5s;"></div>
    </div>
    
    <div class="container">
        <!-- Video Message Section -->
        <section id="video-section">
            <h2>Special Video Message</h2>
            <div class="video-message">
                <p>A heartfelt message from your loved ones!</p>
                <div class="video-container">
                    <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
                </div>
                <button class="btn" onclick="recordVideoMessage()">
                    <i class="fas fa-video"></i> Record Your Message
                </button>
            </div>
        </section>
        
        <!-- Countdown Section -->
        <section id="countdown-section">
            <h2>Ready for the Party?</h2>
            <div class="interactive">
                <button class="btn" onclick="startCountdown()">
                    <i class="fas fa-play"></i> Start Countdown Timer
                </button>
            </div>
            <div id="countdown-container" style="display: none;">
                <div class="countdown">
                    <div class="countdown-item">
                        <div class="countdown-number" id="days">00</div>
                        <div class="countdown-label">Days</div>
                    </div>
                    <div class="countdown-item">
                        <div class="countdown-number" id="hours">00</div>
                        <div class="countdown-label">Hours</div>
                    </div>
                    <div class="countdown-item">
                        <div class="countdown-number" id="minutes">00</div>
                        <div class="countdown-label">Minutes</div>
                    </div>
                    <div class="countdown-item">
                        <div class="countdown-number" id="seconds">00</div>
                        <div class="countdown-label">Seconds</div>
                    </div>
                </div>
                <div class="progress-container">
                    <div class="progress-bar" id="countdown-progress"></div>
                </div>
                <div class="interactive">
                    <button class="btn" onclick="showReminderModal()">
                        <i class="fas fa-bell"></i> Set Reminder
                    </button>
                    <button class="btn btn-secondary" onclick="playBirthdaySong()">
                        <i class="fas fa-music"></i> Play Birthday Song
                    </button>
                </div>
            </div>
        </section>
        
        <!-- Gallery Section -->
        <section id="gallery-section">
            <h2>Memory Lane</h2>
            <div class="gallery">
                <div class="gallery-item" onclick="openPhotoModal('kk.jpg', 'Our amazing time together!')">
                    <img src="kk.jpg" alt="Happy moment">
                    <div class="gallery-caption">Our amazing time together!</div>
                </div>
                <div class="gallery-item" onclick="openPhotoModal('kk.jpg', 'Last year\'s celebration')">
                    <img src="kk.jpg" alt="Celebration">
                    <div class="gallery-caption">Last year's celebration</div>
                </div>
                <div class="gallery-item" onclick="openPhotoModal('hazmz.jpg', 'So much fun!')">
                    <img src="hazmz.jpg" alt="Fun times">
                    <div class="gallery-caption">So much fun!</div>
                </div>
                <div class="gallery-item" onclick="openPhotoModal('hazmz.jpg', 'A special moment')">
                    <img src="hazmz.jpg" alt="Special moment">
                    <div class="gallery-caption">A special moment</div>
                </div>
                <div class="gallery-item" onclick="openPhotoModal('kk.jpg', 'With friends')">
                    <img src="kk.jpg" alt="Friends">
                    <div class="gallery-caption">With friends</div>
                </div>
                <div class="gallery-item" onclick="openPhotoModal('kk.jpg', 'That beautiful smile')">
                    <img src="kk.jpg" alt="Smiling">
                    <div class="gallery-caption">That beautiful smile</div>
                </div>
            </div>
        </section>
        
        <!-- Memory Game Section -->
        <section id="memory-game-section">
            <h2>Memory Challenge</h2>
            <p>Test your memory with this birthday-themed game! Find all matching pairs.</p>
            <div class="memory-game" id="memory-game">
                <!-- Cards will be generated by JavaScript -->
            </div>
            <div class="interactive">
                <button class="btn" onclick="resetMemoryGame()">
                    <i class="fas fa-sync-alt"></i> Reset Game
                </button>
                <button class="btn btn-secondary" onclick="showMemoryHint()">
                    <i class="fas fa-lightbulb"></i> Get Hint
                </button>
            </div>
        </section>
        
        <!-- Guest Book Section -->
        <section id="guest-book-section">
            <h2>Guest Book</h2>
            <div class="guest-book">
                <div id="guest-entries">
                    <div class="guest-entry">
                        <div class="guest-name">Hamza</div>
                        <div class="guest-message">Wishing you the happiest of birthdays! May all your dreams come true this year.</div>
                    </div>
                    <div class="guest-entry">
                        <div class="guest-name">Your Friends</div>
                        <div class="guest-message">We're so lucky to have you in our lives! Happy birthday!</div>
                    </div>
                </div>
                
                <div class="guest-form">
                    <h3>Leave Your Message</h3>
                    <input type="text" id="guest-name" placeholder="Your Name">
                    <textarea id="guest-message" placeholder="Your Birthday Message"></textarea>
                    <button class="btn" onclick="addGuestEntry()">
                        <i class="fas fa-paper-plane"></i> Submit Message
                    </button>
                </div>
            </div>
        </section>
        
        <!-- Wishes Section -->
        <section id="wishes-section">
            <h2>Birthday Wishes</h2>
            <div class="wishes">
                <div class="wish">Wishing you a day filled with happiness and a year filled with joy!</div>
                <div class="wish">May all your dreams and wishes come true this year.</div>
                <div class="wish">You're an amazing person who deserves all the best in life.</div>
                <div class="wish">Here's to another year of great memories and adventures together!</div>
                <div class="wish">May this birthday be the start of your most successful year yet.</div>
                <div class="interactive">
                    <button class="btn" onclick="showWishModal()">
                        <i class="fas fa-star"></i> Add Your Wish
                    </button>
                </div>
            </div>
        </section>
        
        <!-- Interactive Section -->
        <section id="interactive-section">
            <h2>Make a Wish!</h2>
            <div class="interactive">
                <div class="cake-container" onclick="blowCandles()">🎂</div>
                <p>Click on the cake to blow the candles and make a wish!</p>
                <button class="btn" onclick="createConfetti()">
                    <i class="fas fa-birthday-cake"></i> More Celebration!
                </button>
            </div>
        </section>
    </div>
    
    <!-- Audio Elements -->
    <audio id="bg-music" loop>
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>
    
    <audio id="birthday-song">
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-2.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>
    
    <audio id="candle-sound">
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-3.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>
    
    <audio id="confetti-sound">
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-4.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>
    
    <audio id="match-sound">
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-5.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>
    
    <!-- Music control button -->
    <div id="music-control">
        <span id="music-icon">🔇</span>
    </div>
    
    <!-- Modals -->
    <div class="modal" id="reminder-modal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('reminder-modal')">&times;</span>
            <h2><i class="fas fa-bell"></i> Set Party Reminder</h2>
            <p>Enter your email to get a reminder before the party starts:</p>
            <input type="email" id="reminder-email" placeholder="Your email">
            <button class="btn" onclick="setReminder()">
                <i class="fas fa-check"></i> Set Reminder
            </button>
        </div>
    </div>
    
    <div class="modal" id="wish-modal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('wish-modal')">&times;</span>
            <h2><i class="fas fa-star"></i> Add Your Wish</h2>
            <textarea id="new-wish" placeholder="Write your birthday wish here..."></textarea>
            <button class="btn" onclick="addWish()">
                <i class="fas fa-paper-plane"></i> Add Wish
            </button>
        </div>
    </div>
    
    <div class="modal" id="candle-modal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('candle-modal')">&times;</span>
            <h2>Your Wish Will Come True!</h2>
            <p style="font-size: 5rem;">✨</p>
            <p>We've sent your wish to the universe. Stay positive and it will come true!</p>
            <button class="btn" onclick="createConfetti()">
                <i class="fas fa-birthday-cake"></i> More Celebration!
            </button>
        </div>
    </div>
    
    <div class="modal" id="photo-modal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('photo-modal')">&times;</span>
            <img id="modal-photo" src="" alt="" style="width: 100%; border-radius: 10px;">
            <div class="photo-caption" id="modal-caption" style="text-align: center; margin-top: 15px; font-weight: bold;"></div>
        </div>
    </div>
    
    <div class="modal" id="video-modal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('video-modal')">&times;</span>
            <h2><i class="fas fa-video"></i> Record Your Video Message</h2>
            <div id="video-preview" style="width: 100%; height: 300px; background: #eee; margin: 20px 0; border-radius: 10px; display: flex; justify-content: center; align-items: center;">
                <i class="fas fa-camera" style="font-size: 3rem; color: #999;"></i>
            </div>
            <button class="btn" id="start-recording">
                <i class="fas fa-circle"></i> Start Recording
            </button>
            <button class="btn btn-secondary" id="stop-recording" style="display: none;">
                <i class="fas fa-stop"></i> Stop Recording
            </button>
            <button class="btn" id="send-video" style="display: none;">
                <i class="fas fa-paper-plane"></i> Send Video
            </button>
        </div>
    </div>
    
    <div class="modal" id="hint-modal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('hint-modal')">&times;</span>
            <h2><i class="fas fa-lightbulb"></i> Memory Game Hint</h2>
            <p id="hint-text">Try to remember where you saw the <span id="hint-emoji">🎂</span> emoji!</p>
            <div id="hint-card" style="font-size: 3rem; margin: 20px 0;"></div>
            <button class="btn" onclick="closeModal('hint-modal')">
                <i class="fas fa-thumbs-up"></i> Got It!
            </button>
        </div>
    </div>
    
    <script>
        // Enhanced JavaScript for the ultimate birthday experience
        
        // Theme management
        function changeTheme(theme) {
            document.querySelector('.theme-btn.active').classList.remove('active');
            event.target.classList.add('active');
            
            const root = document.documentElement;
            
            switch(theme) {
                case 'romantic':
                    root.style.setProperty('--primary', '#FF4081');
                    root.style.setProperty('--secondary', '#FF6B6B');
                    root.style.setProperty('--accent', '#FF9E7D');
                    root.style.setProperty('--light', '#FFE3E3');
                    root.style.setProperty('--dark', '#D23669');
                    root.style.setProperty('--bg', 'linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%)');
                    root.style.setProperty('--card-bg', 'rgba(255, 255, 255, 0.85)');
                    break;
                case 'cool':
                    root.style.setProperty('--primary', '#00B0FF');
                    root.style.setProperty('--secondary', '#00E5FF');
                    root.style.setProperty('--accent', '#00BFA5');
                    root.style.setProperty('--light', '#E0F7FA');
                    root.style.setProperty('--dark', '#00838F');
                    root.style.setProperty('--bg', 'linear-gradient(135deg, #a1c4fd 0%, #c2e9fb 100%)');
                    root.style.setProperty('--card-bg', 'rgba(255, 255, 255, 0.85)');
                    break;
                case 'fresh':
                    root.style.setProperty('--primary', '#4CAF50');
                    root.style.setProperty('--secondary', '#8BC34A');
                    root.style.setProperty('--accent', '#CDDC39');
                    root.style.setProperty('--light', '#F1F8E9');
                    root.style.setProperty('--dark', '#689F38');
                    root.style.setProperty('--bg', 'linear-gradient(135deg, #84fab0 0%, #8fd3f4 100%)');
                    root.style.setProperty('--card-bg', 'rgba(255, 255, 255, 0.85)');
                    break;
                default:
                    root.style.setProperty('--primary', '#FF4081');
                    root.style.setProperty('--secondary', '#FF9100');
                    root.style.setProperty('--accent', '#00B0FF');
                    root.style.setProperty('--light', '#FFF9C4');
                    root.style.setProperty('--dark', '#7B1FA2');
                    root.style.setProperty('--bg', 'linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%)');
                    root.style.setProperty('--card-bg', 'rgba(255, 255, 255, 0.9)');
            }
            
            // Update balloons to match new theme
            updateBalloonColors();
        }
        
        function updateBalloonColors() {
            const balloons = document.querySelectorAll('.balloon');
            const colors = [
                getComputedStyle(document.documentElement).getPropertyValue('--primary').trim(),
                getComputedStyle(document.documentElement).getPropertyValue('--secondary').trim(),
                getComputedStyle(document.documentElement).getPropertyValue('--accent').trim(),
                getComputedStyle(document.documentElement).getPropertyValue('--dark').trim()
            ];
            
            balloons.forEach(balloon => {
                balloon.style.background = colors[Math.floor(Math.random() * colors.length)];
            });
        }
        
        // Countdown functionality
        let countdownTimer;
        let birthdayDate = new Date();
        birthdayDate.setMonth(birthdayDate.getMonth() + 1);
        birthdayDate.setDate(15);
        birthdayDate.setHours(19, 0, 0, 0);
        
        function startCountdown() {
            // Show the countdown container
            document.getElementById('countdown-container').style.display = 'block';
            // Hide the start button
            event.target.style.display = 'none';
            // Update the heading
            document.querySelector('#countdown-section h2').textContent = 'Countdown to the Party!';
            
            // Start the countdown
            updateCountdown();
            countdownTimer = setInterval(updateCountdown, 1000);
            
            // Create celebration effect
            createConfetti();
        }
        
        function updateCountdown() {
            const now = new Date().getTime();
            const distance = birthdayDate - now;
            
            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);
            
            document.getElementById('days').textContent = days.toString().padStart(2, '0');
            document.getElementById('hours').textContent = hours.toString().padStart(2, '0');
            document.getElementById('minutes').textContent = minutes.toString().padStart(2, '0');
            document.getElementById('seconds').textContent = seconds.toString().padStart(2, '0');
            
            // Update progress bar
            const totalDuration = birthdayDate - new Date(birthdayDate.getFullYear(), birthdayDate.getMonth() - 1, 15);
            const progress = ((totalDuration - distance) / totalDuration) * 100;
            document.getElementById('countdown-progress').style.width = `${progress}%`;
            
            // Change color when close
            if (distance < 86400000) { // Less than 1 day
                document.getElementById('countdown-progress').style.background = 'linear-gradient(90deg, #FF4081, #FF0000)';
            }
            
            if (distance < 0) {
                clearInterval(countdownTimer);
                document.getElementById('countdown-container').innerHTML = `
                    <h3 class="animate__animated animate__bounce">The Celebration Has Started!</h3>
                    <p>Join us now for the birthday party!</p>
                    <button class="btn" onclick="createConfetti()">
                        <i class="fas fa-birthday-cake"></i> Celebrate!
                    </button>
                `;
                playBirthdaySong();
                createConfetti();
            }
        }
        
        // Modal functions
        function showReminderModal() {
            document.getElementById('reminder-modal').style.display = 'flex';
        }
        
        function showWishModal() {
            document.getElementById('wish-modal').style.display = 'flex';
        }
        
        function closeModal(id) {
            document.getElementById(id).style.display = 'none';
        }
        
        function setReminder() {
            const email = document.getElementById('reminder-email').value;
            if (email && email.includes('@')) {
                // Show success animation
                const btn = event.target;
                btn.innerHTML = '<i class="fas fa-check"></i> Reminder Set!';
                btn.style.backgroundColor = '#4CAF50';
                
                setTimeout(() => {
                    closeModal('reminder-modal');
                    btn.innerHTML = '<i class="fas fa-check"></i> Set Reminder';
                    btn.style.backgroundColor = '';
                    document.getElementById('reminder-email').value = '';
                    
                    // Show success message
                    const successMsg = document.createElement('div');
                    successMsg.className = 'wish';
                    successMsg.innerHTML = `<i class="fas fa-bell"></i> Reminder set for ${email}`;
                    document.querySelector('.wishes').insertBefore(successMsg, document.querySelector('.wishes').lastElementChild);
                }, 1500);
            } else {
                // Show error animation
                const input = document.getElementById('reminder-email');
                input.style.borderColor = '#FF4081';
                input.style.animation = 'shake 0.5s';
                
                setTimeout(() => {
                    input.style.animation = '';
                }, 500);
            }
        }
        
        function addWish() {
            const wishText = document.getElementById('new-wish').value;
            if (wishText.trim() !== '') {
                const wishesContainer = document.querySelector('.wishes');
                const newWish = document.createElement('div');
                newWish.className = 'wish';
                newWish.innerHTML = wishText;
                wishesContainer.insertBefore(newWish, wishesContainer.lastElementChild);
                document.getElementById('new-wish').value = '';
                
                // Show success animation
                const btn = event.target;
                btn.innerHTML = '<i class="fas fa-check"></i> Wish Added!';
                btn.style.backgroundColor = '#4CAF50';
                
                setTimeout(() => {
                    closeModal('wish-modal');
                    btn.innerHTML = '<i class="fas fa-paper-plane"></i> Add Wish';
                    btn.style.backgroundColor = '';
                }, 1500);
                
                // Create celebration effect
                createHearts();
            } else {
                // Show error animation
                const textarea = document.getElementById('new-wish');
                textarea.style.borderColor = '#FF4081';
                textarea.style.animation = 'shake 0.5s';
                
                setTimeout(() => {
                    textarea.style.animation = '';
                }, 500);
            }
        }
        
        // Interactive elements
        function scrollToContent() {
            document.querySelector('.container').scrollIntoView({ behavior: 'smooth' });
        }
        
        function playBirthdaySong() {
            const song = document.getElementById('birthday-song');
            song.currentTime = 0;
            song.play();
            
            // Update music control icon
            document.getElementById('music-icon').textContent = '🔊';
            document.getElementById('music-control').style.backgroundColor = getComputedStyle(document.documentElement).getPropertyValue('--primary');
            document.getElementById('music-control').style.color = 'white';
            
            // Create floating music notes
            for (let i = 0; i < 15; i++) {
                setTimeout(() => createMusicNote(), i * 300);
            }
        }
        
        function createMusicNote() {
            const notes = ['♪', '♫', '♩', '♬', '♭'];
            const note = document.createElement('div');
            note.style.position = 'fixed';
            note.style.fontSize = `${Math.random() * 30 + 20}px`;
            note.style.left = `${Math.random() * 100}vw`;
            note.style.top = '100vh';
            note.style.zIndex = '1000';
            note.style.pointerEvents = 'none';
            note.style.color = getComputedStyle(document.documentElement).getPropertyValue('--primary');
            note.textContent = notes[Math.floor(Math.random() * notes.length)];
            
            document.body.appendChild(note);
            
            const animation = note.animate([
                { transform: 'translateY(0) rotate(0deg)', opacity: 1 },
                { transform: `translateY(-${Math.random() * 300 + 100}px) translateX(${Math.random() * 200 - 100}px) rotate(${Math.random() * 360}deg)`, opacity: 0 }
            ], {
                duration: 2000 + Math.random() * 3000,
                easing: 'cubic-bezier(0.4, 0, 0.2, 1)'
            });
            
            animation.onfinish = () => note.remove();
        }
        
        function blowCandles() {
            const sound = document.getElementById('candle-sound');
            sound.currentTime = 0;
            sound.play();
            document.getElementById('candle-modal').style.display = 'flex';
            
            // Create floating candles effect
            for (let i = 0; i < 25; i++) {
                setTimeout(() => createFloatingParticle(), i * 100);
            }
        }
        
        function createFloatingParticle() {
            const particle = document.createElement('div');
            particle.style.position = 'fixed';
            particle.style.width = '8px';
            particle.style.height = '8px';
            particle.style.backgroundColor = `hsl(${Math.random() * 60 + 10}, 100%, 50%)`;
            particle.style.borderRadius = '50%';
            particle.style.left = `${Math.random() * 100}vw`;
            particle.style.top = '50vh';
            particle.style.pointerEvents = 'none';
            particle.style.zIndex = '1000';
            particle.style.boxShadow = '0 0 10px 2px gold';
            particle.style.filter = 'blur(1px)';
            
            document.body.appendChild(particle);
            
            const animation = particle.animate([
                { transform: 'translateY(0) scale(1)', opacity: 1 },
                { transform: `translateY(-${Math.random() * 200 + 100}px) translateX(${Math.random() * 100 - 50}px) scale(0)`, opacity: 0 }
            ], {
                duration: 1000 + Math.random() * 2000,
                easing: 'cubic-bezier(0.4, 0, 0.2, 1)'
            });
            
            animation.onfinish = () => particle.remove();
        }
        
        // Photo modal
        function openPhotoModal(src, caption) {
            document.getElementById('modal-photo').src = src;
            document.getElementById('modal-caption').textContent = caption;
            document.getElementById('photo-modal').style.display = 'flex';
        }
        
        // Confetti effect
        function createConfetti() {
            const confettiSound = document.getElementById('confetti-sound');
            confettiSound.currentTime = 0;
            confettiSound.play();
            
            for (let i = 0; i < 150; i++) {
                setTimeout(() => createConfettiPiece(), i * 20);
            }
        }
        
        function createConfettiPiece() {
            const confetti = document.createElement('div');
            confetti.className = 'confetti';
            
            // Random color from theme
            const colors = [
                getComputedStyle(document.documentElement).getPropertyValue('--primary').trim(),
                getComputedStyle(document.documentElement).getPropertyValue('--secondary').trim(),
                getComputedStyle(document.documentElement).getPropertyValue('--accent').trim(),
                getComputedStyle(document.documentElement).getPropertyValue('--dark').trim(),
                '#FFEB3B', '#4CAF50', '#9C27B0'
            ];
            
            confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
            
            // Random shape
            if (Math.random() > 0.7) {
                confetti.style.borderRadius = '0';
                confetti.style.transform = 'rotate(45deg)';
            } else {
                confetti.style.borderRadius = '50%';
            }
            
            // Random size
            const size = Math.random() * 15 + 5;
            confetti.style.width = `${size}px`;
            confetti.style.height = `${size}px`;
            
            // Random position
            confetti.style.left = `${Math.random() * 100}vw`;
            confetti.style.top = `-${size}px`;
            
            // Random animation duration
            const duration = Math.random() * 3 + 2;
            confetti.style.animationDuration = `${duration}s`;
            
            // Random animation delay
            confetti.style.animationDelay = `${Math.random() * 2}s`;
            
            document.body.appendChild(confetti);
            
            // Remove after animation
            setTimeout(() => {
                confetti.remove();
            }, duration * 1000);
        }
        
        // Create floating hearts
        function createHearts() {
            for (let i = 0; i < 10; i++) {
                setTimeout(() => createHeart(), i * 300);
            }
        }
        
        function createHeart() {
            const heart = document.createElement('div');
            heart.style.position = 'fixed';
            heart.style.fontSize = `${Math.random() * 30 + 20}px`;
            heart.style.left = `${Math.random() * 100}vw`;
            heart.style.bottom = '-50px';
            heart.style.zIndex = '1000';
            heart.style.pointerEvents = 'none';
            heart.style.color = getComputedStyle(document.documentElement).getPropertyValue('--primary');
            heart.textContent = '❤️';
            heart.style.textShadow = '0 0 10px rgba(255,255,255,0.5)';
            heart.style.transform = 'translateY(0)';
            
            document.body.appendChild(heart);
            
            const animation = heart.animate([
                { transform: 'translateY(0)', opacity: 1 },
                { transform: 'translateY(-100vh)', opacity: 0 }
            ], {
                duration: 3000 + Math.random() * 2000,
                easing: 'cubic-bezier(0.4, 0, 0.2, 1)'
            });
            
            animation.onfinish = () => heart.remove();
        }
        
        // Memory game
        const memoryCards = ['🎂', '🎁', '🎈', '🎉', '🥳', '🍰', '🎊', '❤️'];
        let flippedCards = [];
        let matchedPairs = 0;
        let canFlip = true;
        
        function initializeMemoryGame() {
            const gameContainer = document.getElementById('memory-game');
            gameContainer.innerHTML = '';
            flippedCards = [];
            matchedPairs = 0;
            canFlip = true;
            
            // Duplicate and shuffle cards
            const cards = [...memoryCards, ...memoryCards].sort(() => Math.random() - 0.5);
            
            cards.forEach((card, index) => {
                const cardElement = document.createElement('div');
                cardElement.className = 'memory-card';
                cardElement.dataset.index = index;
                cardElement.dataset.value = card;
                
                const frontFace = document.createElement('div');
                frontFace.className = 'front-face';
                frontFace.textContent = card;
                
                const backFace = document.createElement('div');
                backFace.className = 'back-face';
                backFace.innerHTML = '<i class="fas fa-question"></i>';
                
                cardElement.appendChild(frontFace);
                cardElement.appendChild(backFace);
                cardElement.addEventListener('click', flipCard);
                gameContainer.appendChild(cardElement);
            });
        }
        
        function flipCard() {
            if (!canFlip || this.classList.contains('flipped') || this.classList.contains('matched')) {
                return;
            }
            
            if (flippedCards.length >= 2) {
                return;
            }
            
            this.classList.add('flipped');
            flippedCards.push(this);
            
            // Play flip sound
            const flipSound = document.getElementById('candle-sound');
            flipSound.currentTime = 0;
            flipSound.play();
            
            // Check for match if two cards are flipped
            if (flippedCards.length === 2) {
                canFlip = false;
                setTimeout(checkForMatch, 500);
            }
        }
        
        function checkForMatch() {
            const [card1, card2] = flippedCards;
            
            if (card1.dataset.value === card2.dataset.value) {
                // Match found
                card1.classList.add('matched');
                card2.classList.add('matched');
                matchedPairs++;
                
                // Play match sound
                const matchSound = document.getElementById('match-sound');
                matchSound.currentTime = 0;
                matchSound.play();
                
                // Create celebration effect
                createConfettiPieceAtElement(card1);
                createConfettiPieceAtElement(card2);
                
                // Check if game is complete
                if (matchedPairs === memoryCards.length) {
                    setTimeout(() => {
                        const gameContainer = document.getElementById('memory-game');
                        gameContainer.innerHTML = `
                            <div style="grid-column: 1 / -1; text-align: center; padding: 20px;">
                                <h3 style="color: var(--primary); font-size: 2rem;">Congratulations!</h3>
                                <p>You won the memory game!</p>
                                <button class="btn" onclick="resetMemoryGame()">
                                    <i class="fas fa-redo"></i> Play Again
                                </button>
                            </div>
                        `;
                        createConfetti();
                        playBirthdaySong();
                    }, 500);
                }
            } else {
                // No match - flip back
                card1.classList.remove('flipped');
                card2.classList.remove('flipped');
            }
            
            flippedCards = [];
            canFlip = true;
        }
        
        function createConfettiPieceAtElement(element) {
            const rect = element.getBoundingClientRect();
            const x = rect.left + rect.width / 2;
            const y = rect.top + rect.height / 2;
            
            for (let i = 0; i < 10; i++) {
                setTimeout(() => {
                    const confetti = document.createElement('div');
                    confetti.style.position = 'fixed';
                    confetti.style.width = '8px';
                    confetti.style.height = '8px';
                    confetti.style.backgroundColor = getComputedStyle(document.documentElement).getPropertyValue('--primary');
                    confetti.style.borderRadius = '50%';
                    confetti.style.left = `${x}px`;
                    confetti.style.top = `${y}px`;
                    confetti.style.zIndex = '1000';
                    confetti.style.pointerEvents = 'none';
                    
                    document.body.appendChild(confetti);
                    
                    const animation = confetti.animate([
                        { transform: 'translate(0, 0) scale(1)', opacity: 1 },
                        { transform: `translate(${Math.random() * 100 - 50}px, ${Math.random() * -100 - 50}px) scale(0)`, opacity: 0 }
                    ], {
                        duration: 1000 + Math.random() * 1000,
                        easing: 'cubic-bezier(0.4, 0, 0.2, 1)'
                    });
                    
                    animation.onfinish = () => confetti.remove();
                }, i * 100);
            }
        }
        
        function resetMemoryGame() {
            initializeMemoryGame();
        }
        
        function showMemoryHint() {
            if (flippedCards.length === 1) {
                // Show where the match is for the first flipped card
                const firstCardValue = flippedCards[0].dataset.value;
                const allCards = document.querySelectorAll('.memory-card:not(.flipped):not(.matched)');
                let matchFound = false;
                
                allCards.forEach(card => {
                    if (!matchFound && card.dataset.value === firstCardValue) {
                        matchFound = true;
                        document.getElementById('hint-emoji').textContent = firstCardValue;
                        document.getElementById('hint-card').textContent = firstCardValue;
                        document.getElementById('hint-modal').style.display = 'flex';
                        
                        // Highlight the matching card
                        card.style.boxShadow = '0 0 0 3px gold';
                        setTimeout(() => {
                            card.style.boxShadow = '';
                        }, 3000);
                    }
                });
                
                if (!matchFound) {
                    alert("No matching card found yet. Keep looking!");
                }
            } else {
                alert("Flip one card first to get a hint for its match!");
            }
        }
        
        // Guest book functionality
        function addGuestEntry() {
            const name = document.getElementById('guest-name').value.trim();
            const message = document.getElementById('guest-message').value.trim();
            
            if (name && message) {
                const guestEntries = document.getElementById('guest-entries');
                const newEntry = document.createElement('div');
                newEntry.className = 'guest-entry';
                newEntry.innerHTML = `
                    <div class="guest-name">${name}</div>
                    <div class="guest-message">${message}</div>
                `;
                guestEntries.appendChild(newEntry);
                
                // Clear form
                document.getElementById('guest-name').value = '';
                document.getElementById('guest-message').value = '';
                
                // Show success animation
                const btn = event.target;
                btn.innerHTML = '<i class="fas fa-check"></i> Message Sent!';
                btn.style.backgroundColor = '#4CAF50';
                
                setTimeout(() => {
                    btn.innerHTML = '<i class="fas fa-paper-plane"></i> Submit Message';
                    btn.style.backgroundColor = '';
                }, 1500);
                
                // Create celebration effect
                createHearts();
            } else {
                // Show error animation
                const inputs = [document.getElementById('guest-name'), document.getElementById('guest-message')];
                inputs.forEach(input => {
                    if (!input.value.trim()) {
                        input.style.borderColor = '#FF4081';
                        input.style.animation = 'shake 0.5s';
                        
                        setTimeout(() => {
                            input.style.animation = '';
                        }, 500);
                    }
                });
            }
        }
        
        // Video message functionality
        function recordVideoMessage() {
            document.getElementById('video-modal').style.display = 'flex';
            // In a real implementation, we would set up the camera here
        }
        
        // Background music control
        const bgMusic = document.getElementById('bg-music');
        const musicControl = document.getElementById('music-control');
        const musicIcon = document.getElementById('music-icon');
        
        musicControl.addEventListener('click', function() {
            if (bgMusic.paused) {
                bgMusic.play();
                musicIcon.textContent = '🔊';
                musicControl.style.backgroundColor = getComputedStyle(document.documentElement).getPropertyValue('--primary');
                musicControl.style.color = 'white';
            } else {
                bgMusic.pause();
                musicIcon.textContent = '🔇';
                musicControl.style.backgroundColor = '';
                musicControl.style.color = '';
            }
        });
        
        // Initialize the page
        document.addEventListener('DOMContentLoaded', function() {
            // Try to play music (will fail in most browsers due to autoplay policies)
            const playPromise = bgMusic.play();
            
            if (playPromise !== undefined) {
                playPromise.catch(error => {
                    // Autoplay was prevented, show muted icon
                    musicIcon.textContent = '🔇';
                });
            }
            
            // Initialize memory game
            initializeMemoryGame();
            
            // Create more balloons
            createBalloons();
            
            // Create floating hearts
            setInterval(createHeart, 3000);
            
            // Add hover effect to wishes
            document.querySelectorAll('.wish').forEach(wish => {
                wish.addEventListener('mouseenter', () => {
                    wish.style.transform = 'translateX(10px)';
                    wish.style.boxShadow = '5px 5px 20px rgba(0,0,0,0.1)';
                });
                
                wish.addEventListener('mouseleave', () => {
                    wish.style.transform = '';
                    wish.style.boxShadow = '5px 5px 15px rgba(0,0,0,0.05)';
                });
            });
            
            // Close modal when clicking outside
            document.querySelectorAll('.modal').forEach(modal => {
                modal.addEventListener('click', function(e) {
                    if (e.target === this) {
                        closeModal(this.id);
                    }
                });
            });
        });
        
        // Create more balloons
        function createBalloons() {
            const colors = [
                getComputedStyle(document.documentElement).getPropertyValue('--primary').trim(),
                getComputedStyle(document.documentElement).getPropertyValue('--secondary').trim(),
                getComputedStyle(document.documentElement).getPropertyValue('--accent').trim(),
                getComputedStyle(document.documentElement).getPropertyValue('--dark').trim()
            ];
            
            for (let i = 0; i < 20; i++) {
                const balloon = document.createElement('div');
                balloon.className = 'balloon';
                balloon.style.left = `${Math.random() * 100}%`;
                balloon.style.background = colors[Math.floor(Math.random() * colors.length)];
                balloon.style.animationDuration = `${10 + Math.random() * 20}s`;
                balloon.style.animationDelay = `${Math.random() * 10}s`;
                document.body.appendChild(balloon);
            }
        }
        
        // Create floating hearts
        function createHeart() {
            const heart = document.createElement('div');
            heart.className = 'heart';
            heart.style.left = `${Math.random() * 100}%`;
            heart.style.animationDuration = `${15 + Math.random() * 15}s`;
            heart.style.animationDelay = `${Math.random() * 5}s`;
            heart.innerHTML = '❤️';
            document.body.appendChild(heart);
            
            // Remove after animation
            setTimeout(() => {
                heart.remove();
            }, 30000);
        }
        
        // Handle keyboard events
        document.addEventListener('keydown', function(e) {
            // Space to create confetti
            if (e.code === 'Space') {
                createConfetti();
                e.preventDefault();
            }
            
            // M to toggle music
            if (e.code === 'KeyM') {
                musicControl.click();
                e.preventDefault();
            }
        });
    </script>
</body>
</html>
