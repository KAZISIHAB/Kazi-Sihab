<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tom Boom - আয় করুন সহজেই</title>
    <style>
        :root {
            --primary: #8B5CF6;
            --primary-dark: #7C3AED;
            --primary-light: #A78BFA;
            --secondary: #06D6A0;
            --secondary-dark: #05C793;
            --accent: #FFD166;
            --dark: #1F2937;
            --darker: #111827;
            --light: #FFFFFF;
            --gray: #F3F4F6;
            --gray-dark: #E5E7EB;
            --text: #374151;
            --text-light: #6B7280;
            --shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            --gradient: linear-gradient(135deg, #8B5CF6 0%, #7C3AED 100%);
        }

        .dark-mode {
            --primary: #A78BFA;
            --primary-dark: #8B5CF6;
            --primary-light: #C4B5FD;
            --secondary: #34D399;
            --secondary-dark: #10B981;
            --accent: #FBBF24;
            --dark: #F9FAFB;
            --darker: #F3F4F6;
            --light: #1F2937;
            --gray: #374151;
            --gray-dark: #4B5563;
            --text: #F9FAFB;
            --text-light: #D1D5DB;
            --shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
            --gradient: linear-gradient(135deg, #1F2937 0%, #374151 100%);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', 'Nikosh', 'SolaimanLipi', sans-serif;
        }

        body {
            background: var(--light);
            color: var(--text);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
            transition: all 0.3s ease;
        }

        .app-container {
            width: 100%;
            max-width: 400px;
            background: var(--light);
            border-radius: 20px;
            box-shadow: var(--shadow);
            overflow: hidden;
            display: flex;
            flex-direction: column;
            height: 95vh;
            position: relative;
        }

        /* Header Styles */
        .header {
            background: var(--gradient);
            color: white;
            padding: 20px;
            text-align: center;
            position: relative;
        }

        .header-controls {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }

        .theme-toggle, .language-toggle {
            background: rgba(255, 255, 255, 0.2);
            border: none;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2em;
            color: white;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        .theme-toggle:hover, .language-toggle:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: scale(1.1);
        }

        .app-title {
            font-size: 1.6em;
            font-weight: bold;
            margin-bottom: 5px;
        }

        .app-subtitle {
            font-size: 0.9em;
            opacity: 0.9;
        }

        /* Balance Display - Only in Home */
        .balance-display {
            background: rgba(255, 255, 255, 0.15);
            padding: 20px;
            border-radius: 15px;
            margin: 15px 0;
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            text-align: center;
        }

        .balance-label {
            font-size: 0.9em;
            opacity: 0.9;
            margin-bottom: 8px;
        }

        .balance-amount {
            font-size: 2.5em;
            font-weight: bold;
            margin: 5px 0;
        }

        .min-withdrawal {
            font-size: 0.8em;
            opacity: 0.8;
        }

        /* Main Content */
        .main-content {
            flex: 1;
            padding: 0;
            overflow-y: auto;
            background: var(--light);
        }

        .content-section {
            display: none;
            height: 100%;
            padding: 20px;
        }

        .content-section.active {
            display: block;
        }

        /* Home Section */
        .home-section {
            text-align: center;
        }

        .character-container {
            position: relative;
            margin: 0 auto 25px;
            width: 120px;
            height: 120px;
        }

        .character {
            width: 100%;
            height: 100%;
            background: var(--gradient);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3em;
            color: white;
            box-shadow: 0 10px 25px rgba(139, 92, 246, 0.3);
            border: 4px solid var(--light);
        }

        .character-level {
            position: absolute;
            bottom: -8px;
            right: -8px;
            background: var(--secondary);
            color: white;
            padding: 4px 10px;
            border-radius: 12px;
            font-size: 0.7em;
            font-weight: bold;
            border: 2px solid var(--light);
        }

        .feed-btn {
            background: var(--gradient);
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 1.1em;
            font-weight: bold;
            border-radius: 25px;
            cursor: pointer;
            margin: 15px 0;
            box-shadow: 0 8px 20px rgba(139, 92, 246, 0.4);
            transition: all 0.3s ease;
            width: 100%;
            max-width: 250px;
        }

        .feed-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 12px 25px rgba(139, 92, 246, 0.5);
        }

        .feed-btn:disabled {
            background: var(--text-light);
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }

        .click-counter {
            font-size: 0.9em;
            margin: 10px 0 20px;
            color: var(--text-light);
        }

        .stats-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 12px;
            margin: 20px 0;
        }

        .stat-card {
            background: var(--gray);
            padding: 15px;
            border-radius: 12px;
            text-align: center;
            border: 1px solid var(--gray-dark);
        }

        .stat-value {
            font-size: 1.4em;
            font-weight: bold;
            color: var(--primary);
            margin: 5px 0;
        }

        .stat-label {
            font-size: 0.8em;
            color: var(--text-light);
        }

        .welcome-card {
            background: var(--gradient);
            color: white;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
            text-align: center;
            box-shadow: 0 8px 20px rgba(139, 92, 246, 0.3);
        }

        .welcome-title {
            font-size: 1.2em;
            font-weight: bold;
            margin-bottom: 5px;
        }

        /* Ads Section */
        .ad-card {
            background: var(--gray);
            padding: 20px;
            margin: 15px 0;
            border-radius: 15px;
            text-align: center;
            border: 1px solid var(--gray-dark);
        }

        .ad-title {
            font-size: 1.2em;
            font-weight: bold;
            margin-bottom: 8px;
            color: var(--primary);
        }

        .ad-description {
            color: var(--text-light);
            margin: 10px 0;
            font-size: 0.9em;
        }

        .countdown-timer {
            font-size: 1em;
            color: var(--primary);
            font-weight: bold;
            margin: 12px 0;
            padding: 8px;
            background: rgba(139, 92, 246, 0.1);
            border-radius: 8px;
            display: none;
        }

        .progress-container {
            margin: 15px 0;
        }

        .progress-label {
            display: flex;
            justify-content: space-between;
            margin-bottom: 6px;
            font-size: 0.85em;
            color: var(--text-light);
        }

        .progress-bar {
            width: 100%;
            height: 8px;
            background: var(--gray-dark);
            border-radius: 4px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            background: var(--gradient);
            border-radius: 4px;
            transition: width 0.3s ease;
        }

        /* Tasks Section */
        .task-card {
            background: var(--gray);
            padding: 20px;
            margin: 15px 0;
            border-radius: 15px;
            border: 1px solid var(--gray-dark);
        }

        .task-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 10px;
        }

        .task-title {
            font-weight: bold;
            font-size: 1.1em;
            color: var(--text);
        }

        .task-reward {
            background: var(--primary);
            color: white;
            padding: 5px 10px;
            border-radius: 12px;
            font-size: 0.8em;
            font-weight: bold;
        }

        .task-description {
            color: var(--text-light);
            margin-bottom: 12px;
            font-size: 0.9em;
        }

        .task-button {
            background: var(--secondary);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            font-size: 0.9em;
        }

        .task-button:hover {
            background: var(--secondary-dark);
            transform: translateY(-1px);
        }

        .task-status {
            display: inline-block;
            padding: 5px 10px;
            border-radius: 10px;
            font-size: 0.75em;
            margin-top: 8px;
            font-weight: bold;
        }

        .status-active {
            background: var(--secondary);
            color: white;
        }

        /* Withdraw Section */
        .withdraw-card {
            background: var(--gray);
            padding: 20px;
            margin: 15px 0;
            border-radius: 15px;
            border: 1px solid var(--gray-dark);
        }

        .info-grid {
            display: grid;
            gap: 12px;
            margin: 15px 0;
        }

        .info-item {
            display: flex;
            justify-content: space-between;
            padding: 10px 0;
            border-bottom: 1px solid var(--gray-dark);
            font-size: 0.9em;
        }

        .payment-methods {
            display: grid;
            gap: 10px;
            margin: 15px 0;
        }

        .payment-method {
            padding: 15px;
            border: 2px solid var(--gray-dark);
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s ease;
            background: var(--light);
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .payment-method:hover {
            border-color: var(--primary);
            transform: translateY(-1px);
        }

        .payment-method.active {
            border-color: var(--primary);
            background: rgba(139, 92, 246, 0.05);
        }

        .payment-icon {
            font-size: 1.8em;
        }

        .payment-details {
            flex: 1;
        }

        .payment-name {
            font-weight: bold;
            margin-bottom: 3px;
            font-size: 0.95em;
        }

        .min-amount {
            font-size: 0.75em;
            color: var(--primary);
        }

        .payment-input {
            width: 100%;
            padding: 10px;
            border: 1px solid var(--gray-dark);
            border-radius: 8px;
            margin-top: 8px;
            background: var(--light);
            color: var(--text);
            display: none;
            font-size: 0.9em;
        }

        .payment-method.active .payment-input {
            display: block;
        }

        .warning-card {
            background: rgba(239, 68, 68, 0.1);
            color: #EF4444;
            padding: 12px;
            border-radius: 8px;
            margin: 15px 0;
            text-align: center;
            border: 1px solid rgba(239, 68, 68, 0.2);
            font-size: 0.85em;
        }

        .withdraw-btn {
            background: var(--gradient);
            color: white;
            border: none;
            padding: 15px;
            width: 100%;
            border-radius: 12px;
            font-size: 1em;
            font-weight: bold;
            cursor: pointer;
            margin-top: 10px;
            box-shadow: 0 8px 20px rgba(139, 92, 246, 0.3);
            transition: all 0.3s ease;
        }

        .withdraw-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 12px 25px rgba(139, 92, 246, 0.4);
        }

        /* Navigation */
        .navigation {
            display: flex;
            background: var(--light);
            border-top: 1px solid var(--gray-dark);
            padding: 8px 12px;
            gap: 4px;
        }

        .nav-item {
            flex: 1;
            text-align: center;
            padding: 10px 4px;
            cursor: pointer;
            transition: all 0.3s ease;
            border-radius: 12px;
            background: var(--gray);
            border: 2px solid transparent;
            font-size: 0.75em;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 4px;
        }

        .nav-item.home {
            flex: 1.2;
            padding: 12px 4px;
            font-size: 0.8em;
            font-weight: bold;
        }

        .nav-item.active {
            background: var(--gradient);
            color: white;
            border-color: var(--primary);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(139, 92, 246, 0.3);
        }

        .nav-item:hover:not(.active) {
            background: var(--gray-dark);
        }

        .nav-icon {
            font-size: 1.2em;
        }

        .nav-item.home .nav-icon {
            font-size: 1.4em;
        }

        /* Animations */
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        .pulse {
            animation: pulse 0.5s ease-in-out;
        }

        /* Responsive */
        @media (max-width: 480px) {
            .app-container {
                height: 100vh;
                border-radius: 0;
            }
            
            .header {
                border-radius: 0;
            }
            
            .balance-amount {
                font-size: 2em;
            }
            
            .character-container {
                width: 100px;
                height: 100px;
            }
            
            .feed-btn {
                padding: 12px 25px;
                font-size: 1em;
            }
        }
    </style>
</head>
<body>
    <div class="app-container">
        <!-- Header Section -->
        <div class="header">
            <div class="header-controls">
                <button class="language-toggle" id="languageToggle">EN</button>
                <button class="theme-toggle" id="themeToggle">🌙</button>
            </div>
            <h1 class="app-title" id="appTitle">টম বুম</h1>
            <p class="app-subtitle" id="appSubtitle">খেলতে খেলতে আয় করুন</p>
            
            <!-- Balance Display - Only visible in Home section -->
            <div class="balance-display" id="balanceDisplay">
                <div class="balance-label" id="currentBalanceText">বর্তমান ব্যালেন্স</div>
                <div class="balance-amount" id="currentBalance">০ টাকা</div>
                <div class="min-withdrawal" id="minWithdrawalText">সর্বনিম্ন উত্তোলন: ১৫০০ টাকা</div>
            </div>
        </div>

        <!-- Main Content -->
        <div class="main-content">
            <!-- Home Section -->
            <div id="home-section" class="content-section active">
                <div class="home-section">
                    <div class="character-container">
                        <div class="character">😊</div>
                        <div class="character-level">লেভেল ১</div>
                    </div>
                    
                    <button class="feed-btn" id="feedButton">FEED ME! (5 TK)</button>
                    <div class="click-counter" id="todayClicksText">আজকের ক্লিক: <strong>০/৩</strong></div>
                    
                    <div class="stats-grid">
                        <div class="stat-card">
                            <div class="stat-label" id="levelText">লেভেল</div>
                            <div class="stat-value">১</div>
                        </div>
                        <div class="stat-card">
                            <div class="stat-label" id="totalEarnedText">মোট আয়</div>
                            <div class="stat-value">০ টাকা</div>
                        </div>
                    </div>

                    <div class="welcome-card">
                        <h3 class="welcome-title" id="welcomeTitle">স্বাগতম!</h3>
                        <p id="welcomeSubtitle">প্রতিদিন বিজ্ঞাপন দেখে আয় করুন</p>
                    </div>
                </div>
            </div>

            <!-- Ads Section -->
            <div id="ads-section" class="content-section">
                <div class="ad-card">
                    <h3 class="ad-title" id="watchVideoText">ভিডিও বিজ্ঞাপন দেখুন</h3>
                    <p class="ad-description">৩০ সেকেন্ড = ৫ টাকা</p>
                    <button class="feed-btn" id="watchAdButton">WATCH AD (5 TK)</button>
                    <div class="countdown-timer" id="countdownTimer"></div>
                    
                    <div class="progress-container">
                        <div class="progress-label">
                            <span id="dailyLimitText">দৈনিক সীমা: ০/৩০ বিজ্ঞাপন</span>
                            <span id="potentialEarningText">১৫০ টাকা/দিন</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill" style="width: 0%"></div>
                        </div>
                    </div>
                </div>
                
                <div class="ad-card">
                    <h3 class="ad-title" id="todayOfferText">আজকের অফার</h3>
                    <p class="ad-description" id="offerDescription">প্রতিটি বিজ্ঞাপন দেখে ৫ টাকা করে আয় করুন</p>
                    <div style="margin: 15px 0; padding: 12px; background: rgba(6, 214, 160, 0.1); border-radius: 8px;">
                        <div style="margin: 5px 0;">✅ ৩০ সেকেন্ডের ভিডিও</div>
                        <div style="margin: 5px 0;">✅ সহজ প্রক্রিয়া</div>
                        <div style="margin: 5px 0;">✅ তাৎক্ষণিক পেমেন্ট</div>
                    </div>
                </div>
            </div>

            <!-- Tasks Section -->
            <div id="tasks-section" class="content-section">
                <div class="task-card">
                    <div class="task-header">
                        <div class="task-title" id="task1Title">টেলিগ্রাম চ্যানেলে যোগ দিন</div>
                        <div class="task-reward">১৫ টাকা</div>
                    </div>
                    <p class="task-description" id="task1Description">আমাদের অফিসিয়াল টেলিগ্রাম চ্যানেলে যোগ দিন</p>
                    <a href="https://t.me/onlinefreeincomebdjr" target="_blank" class="task-button" id="joinTelegramButton">যোগ দিন</a>
                    <span class="task-status status-active" id="task1Status">চালু</span>
                </div>
            </div>

            <!-- Withdraw Section -->
            <div id="withdraw-section" class="content-section">
                <div class="withdraw-card">
                    <div class="info-grid">
                        <div class="info-item">
                            <span id="minWithdrawalLabel">সর্বনিম্ন উত্তোলন:</span>
                            <span>১৫০০ টাকা</span>
                        </div>
                        <div class="info-item">
                            <span id="currentRateLabel">বর্তমান রেট:</span>
                            <span>১ USD = ১২৪ টাকা</span>
                        </div>
                        <div class="info-item">
                            <span id="yourBalanceLabel">আপনার ব্যালেন্স:</span>
                            <span id="withdrawBalance">০ টাকা</span>
                        </div>
                    </div>

                    <h3 style="text-align: center; margin: 20px 0 15px;" id="selectPaymentMethod">পেমেন্ট মাধ্যম নির্বাচন করুন</h3>
                    
                    <div class="payment-methods">
                        <div class="payment-method" data-method="bkash">
                            <div class="payment-icon">📱</div>
                            <div class="payment-details">
                                <div class="payment-name">বিকাশ</div>
                                <div class="min-amount">ন্যূনতম: ১২০০ টাকা</div>
                                <input type="text" class="payment-input" placeholder="বিকাশ নম্বর লিখুন" id="bkashNumber">
                            </div>
                        </div>
                        
                        <div class="payment-method" data-method="nagad">
                            <div class="payment-icon">💳</div>
                            <div class="payment-details">
                                <div class="payment-name">নগদ</div>
                                <div class="min-amount">ন্যূনতম: ১০০০ টাকা</div>
                                <input type="text" class="payment-input" placeholder="নগদ নম্বর লিখুন" id="nagadNumber">
                            </div>
                        </div>
                        
                        <div class="payment-method" data-method="binance">
                            <div class="payment-icon">₿</div>
                            <div class="payment-details">
                                <div class="payment-name">বাইনান্স</div>
                                <div class="min-amount">ন্যূনতম: ১০ USD</div>
                                <input type="text" class="payment-input" placeholder="বাইনান্স আইডি লিখুন" id="binanceId">
                            </div>
                        </div>
                    </div>

                    <div class="warning-card">
                        ⚠️ <span id="withdrawalWarning">উত্তোলনের জন্য আপনার অ্যাকাউন্টে কমপক্ষে ১৫০০ টাকা থাকতে হবে</span>
                    </div>

                    <button class="withdraw-btn" id="withdrawButton">উত্তোলন অনুরোধ জমা দিন</button>
                </div>
            </div>
        </div>

        <!-- Navigation -->
        <div class="navigation">
            <div class="nav-item home active" onclick="showSection('home')">
                <div class="nav-icon">🏠</div>
                <div id="navHome">হোম</div>
            </div>
            <div class="nav-item" onclick="showSection('ads')">
                <div class="nav-icon">📺</div>
                <div id="navAds">বিজ্ঞাপন</div>
            </div>
            <div class="nav-item" onclick="showSection('tasks')">
                <div class="nav-icon">✅</div>
                <div id="navTasks">টাস্ক</div>
            </div>
            <div class="nav-item" onclick="showSection('withdraw')">
                <div class="nav-icon">💰</div>
                <div id="navWithdraw">উত্তোলন</div>
            </div>
        </div>
    </div>

    <!-- GigaPub Ad Script -->
    <script src="https://ad.gigapub.tech/script?id=3262"></script>

    <script>
        // App State
        let currentLanguage = 'bn';
        let currentTheme = 'light';
        let currentBalance = 0;
        let totalEarnings = 0;
        let adCount = 0;
        let maxAdsPerDay = 30;
        let feedClickCount = 0;
        let isAdInProgress = false;
        let countdownInterval;
        let feedTimerActive = false;

        // Language texts
        const texts = {
            bn: {
                appTitle: 'টম বুম',
                appSubtitle: 'খেলতে খেলতে আয় করুন',
                currentBalanceText: 'বর্তমান ব্যালেন্স',
                minWithdrawalText: 'সর্বনিম্ন উত্তোলন: ১৫০০ টাকা',
                feedButton: 'FEED ME! (5 TK)',
                todayClicksText: 'আজকের ক্লিক: ০/৩',
                levelText: 'লেভেল',
                totalEarnedText: 'মোট আয়',
                welcomeTitle: 'স্বাগতম!',
                welcomeSubtitle: 'প্রতিদিন বিজ্ঞাপন দেখে আয় করুন',
                watchVideoText: 'ভিডিও বিজ্ঞাপন দেখুন',
                dailyLimitText: 'দৈনিক সীমা: ০/৩০ বিজ্ঞাপন',
                potentialEarningText: '১৫০ টাকা/দিন',
                todayOfferText: 'আজকের অফার',
                offerDescription: 'প্রতিটি বিজ্ঞাপন দেখে ৫ টাকা করে আয় করুন',
                task1Title: 'টেলিগ্রাম চ্যানেলে যোগ দিন',
                task1Description: 'আমাদের অফিসিয়াল টেলিগ্রাম চ্যানেলে যোগ দিন',
                task1Status: 'চালু',
                minWithdrawalLabel: 'সর্বনিম্ন উত্তোলন:',
                currentRateLabel: 'বর্তমান রেট:',
                yourBalanceLabel: 'আপনার ব্যালেন্স:',
                selectPaymentMethod: 'পেমেন্ট মাধ্যম নির্বাচন করুন',
                withdrawalWarning: 'উত্তোলনের জন্য আপনার অ্যাকাউন্টে কমপক্ষে ১৫০০ টাকা থাকতে হবে',
                withdrawButton: 'উত্তোলন অনুরোধ জমা দিন',
                navHome: 'হোম',
                navAds: 'বিজ্ঞাপন',
                navTasks: 'টাস্ক',
                navWithdraw: 'উত্তোলন',
                successMessage: 'আপনি ৫ টাকা আয় করেছেন! 🎉',
                withdrawSuccess: 'উত্তোলনের অনুরোধ জমা দেওয়া হয়েছে!',
                insufficientBalance: 'আপনার ব্যালেন্স অপর্যাপ্ত!',
                adLimitReached: 'আজকের বিজ্ঞাপন সীমা শেষ হয়েছে!',
                adInProgress: 'একটি বিজ্ঞাপন ইতিমধ্যে চলছে!',
                feedTimerActive: '২৪ ঘন্টার টাইমার সক্রিয়! আগামী দিন আবার চেষ্টা করুন।',
                adLoading: 'বিজ্ঞাপন লোড হচ্ছে...',
                adError: 'বিজ্ঞাপন লোড করতে সমস্যা হয়েছে! পরে আবার চেষ্টা করুন।'
            },
            en: {
                appTitle: 'Tom Boom',
                appSubtitle: 'Earn while playing',
                currentBalanceText: 'Current Balance',
                minWithdrawalText: 'Minimum Withdrawal: 1500 Taka',
                feedButton: 'FEED ME! (5 TK)',
                todayClicksText: "Today's Clicks: 0/3",
                levelText: 'Level',
                totalEarnedText: 'Total Earned',
                welcomeTitle: 'Welcome!',
                welcomeSubtitle: 'Earn daily by watching ads',
                watchVideoText: 'Watch Video Ads',
                dailyLimitText: 'Daily Limit: 0/30 Ads',
                potentialEarningText: '150 Taka/Day',
                todayOfferText: "Today's Offer",
                offerDescription: 'Earn 5 Taka for each ad you watch',
                task1Title: 'Join Telegram Channel',
                task1Description: 'Join our official Telegram channel',
                task1Status: 'Active',
                minWithdrawalLabel: 'Minimum Withdrawal:',
                currentRateLabel: 'Current Rate:',
                yourBalanceLabel: 'Your Balance:',
                selectPaymentMethod: 'Select Payment Method',
                withdrawalWarning: 'You need at least 1500 Taka in your account to withdraw',
                withdrawButton: 'Submit Withdrawal Request',
                navHome: 'Home',
                navAds: 'Ads',
                navTasks: 'Tasks',
                navWithdraw: 'Withdraw',
                successMessage: 'You earned 5 Taka! 🎉',
                withdrawSuccess: 'Withdrawal request submitted!',
                insufficientBalance: 'Insufficient balance!',
                adLimitReached: "Today's ad limit reached!",
                adInProgress: 'An ad is already in progress!',
                feedTimerActive: '24-hour timer active! Try again tomorrow.',
                adLoading: 'Loading ad...',
                adError: 'Failed to load ad! Please try again later.'
            }
        };

        // Initialize App
        document.addEventListener('DOMContentLoaded', function() {
            initializeApp();
        });

        function initializeApp() {
            // Theme toggle
            document.getElementById('themeToggle').addEventListener('click', toggleTheme);
            
            // Language toggle
            document.getElementById('languageToggle').addEventListener('click', toggleLanguage);
            
            // Feed button
            document.getElementById('feedButton').addEventListener('click', handleFeedClick);
            
            // Watch ad button
            document.getElementById('watchAdButton').addEventListener('click', handleAdWatch);
            
            // Payment method selection
            document.querySelectorAll('.payment-method').forEach(method => {
                method.addEventListener('click', function() {
                    selectPaymentMethod(this);
                });
            });
            
            // Withdraw button
            document.getElementById('withdrawButton').addEventListener('click', handleWithdraw);
            
            // Initialize UI
            updateLanguage();
            updateBalanceDisplay();
            updateProgressBar();
            
            // Select first payment method
            document.querySelector('.payment-method').click();
            
            // Check if feed timer is active
            checkFeedTimer();
        }

        function toggleTheme() {
            if (currentTheme === 'light') {
                document.body.classList.add('dark-mode');
                currentTheme = 'dark';
                this.textContent = '☀️';
            } else {
                document.body.classList.remove('dark-mode');
                currentTheme = 'light';
                this.textContent = '🌙';
            }
        }

        function toggleLanguage() {
            if (currentLanguage === 'bn') {
                currentLanguage = 'en';
                this.textContent = 'BN';
            } else {
                currentLanguage = 'bn';
                this.textContent = 'EN';
            }
            updateLanguage();
        }

        function updateLanguage() {
            const lang = texts[currentLanguage];
            for (const [key, value] of Object.entries(lang)) {
                const element = document.getElementById(key);
                if (element) {
                    element.textContent = value;
                }
            }
            updateBalanceDisplay();
            updateProgressBar();
        }

        function showSection(sectionName) {
            // Hide all sections
            document.querySelectorAll('.content-section').forEach(section => {
                section.classList.remove('active');
            });
            
            // Remove active class from all nav items
            document.querySelectorAll('.nav-item').forEach(nav => {
                nav.classList.remove('active');
            });
            
            // Show selected section
            document.getElementById(sectionName + '-section').classList.add('active');
            
            // Add active class to clicked nav item
            event.currentTarget.classList.add('active');
            
            // Show/hide balance display based on section
            const balanceDisplay = document.getElementById('balanceDisplay');
            if (sectionName === 'home') {
                balanceDisplay.style.display = 'block';
            } else {
                balanceDisplay.style.display = 'none';
            }
        }

        function selectPaymentMethod(element) {
            document.querySelectorAll('.payment-method').forEach(m => {
                m.classList.remove('active');
            });
            element.classList.add('active');
        }

        function handleFeedClick() {
            if (feedTimerActive) {
                alert(texts[currentLanguage].feedTimerActive);
                return;
            }
            
            feedClickCount++;
            
            // Add animation
            this.classList.add('pulse');
            setTimeout(() => {
                this.classList.remove('pulse');
            }, 500);
            
            // Update balance
            currentBalance += 5;
            totalEarnings += 5;
            
            // Update display
            updateBalanceDisplay();
            
            // Update click counter
            document.getElementById('todayClicksText').textContent = 
                currentLanguage === 'bn' ? 
                `আজকের ক্লিক: ${feedClickCount}/৩` : 
                `Today's Clicks: ${feedClickCount}/3`;
            
            // Check if 3 clicks reached
            if (feedClickCount >= 3) {
                activateFeedTimer();
            }
            
            // Show success message
            alert(texts[currentLanguage].successMessage);
        }

        function activateFeedTimer() {
            feedTimerActive = true;
            feedClickCount = 0;
            
            // Store timer activation time
            localStorage.setItem('feedTimerStart', Date.now());
            
            // Update UI
            document.getElementById('feedButton').disabled = true;
            document.getElementById('feedButton').textContent = 
                currentLanguage === 'bn' ? 'টাইমার সক্রিয়' : 'Timer Active';
            
            // Set timeout to reset after 24 hours
            setTimeout(() => {
                resetFeedTimer();
            }, 24 * 60 * 60 * 1000); // 24 hours
        }

        function checkFeedTimer() {
            const timerStart = localStorage.getItem('feedTimerStart');
            if (timerStart) {
                const elapsed = Date.now() - parseInt(timerStart);
                if (elapsed < 24 * 60 * 60 * 1000) {
                    // Timer still active
                    activateFeedTimer();
                    
                    // Set timeout for remaining time
                    setTimeout(() => {
                        resetFeedTimer();
                    }, 24 * 60 * 60 * 1000 - elapsed);
                } else {
                    // Timer expired
                    resetFeedTimer();
                }
            }
        }

        function resetFeedTimer() {
            feedTimerActive = false;
            feedClickCount = 0;
            localStorage.removeItem('feedTimerStart');
            
            // Update UI
            document.getElementById('feedButton').disabled = false;
            document.getElementById('feedButton').textContent = texts[currentLanguage].feedButton;
            document.getElementById('todayClicksText').textContent = 
                currentLanguage === 'bn' ? 'আজকের ক্লিক: ০/৩' : "Today's Clicks: 0/3";
        }

        function handleAdWatch() {
            if (isAdInProgress) {
                alert(texts[currentLanguage].adInProgress);
                return;
            }
            
            if (adCount >= maxAdsPerDay) {
                alert(texts[currentLanguage].adLimitReached);
                return;
            }
            
            // Add animation
            this.classList.add('pulse');
            setTimeout(() => {
                this.classList.remove('pulse');
            }, 500);
            
            // Show GigaPub ad
            showGigaPubAd();
        }

        function showGigaPubAd() {
            isAdInProgress = true;
            const adButton = document.getElementById('watchAdButton');
            adButton.disabled = true;
            adButton.textContent = texts[currentLanguage].adLoading;
            
            // Check if GigaPub is available
            if (typeof window.showGiga !== 'undefined') {
                window.showGiga()
                    .then(() => {
                        // Ad completed successfully
                        adCount++;
                        currentBalance += 5;
                        totalEarnings += 5;
                        
                        updateBalanceDisplay();
                        updateProgressBar();
                        
                        // Start countdown timer
                        startCountdown();
                        
                        // Show success message
                        alert(texts[currentLanguage].successMessage);
                    })
                    .catch(error => {
                        // Ad failed or was closed
                        console.error('GigaPub ad error:', error);
                        alert(texts[currentLanguage].adError);
                    })
                    .finally(() => {
                        // Reset button
                        adButton.disabled = false;
                        adButton.textContent = 'WATCH AD (5 TK)';
                        isAdInProgress = false;
                    });
            } else {
                // GigaPub not available, use fallback
                setTimeout(() => {
                    // Simulate ad completion
                    adCount++;
                    currentBalance += 5;
                    totalEarnings += 5;
                    
                    updateBalanceDisplay();
                    updateProgressBar();
                    
                    // Start countdown timer
                    startCountdown();
                    
                    // Reset button
                    adButton.disabled = false;
                    adButton.textContent = 'WATCH AD (5 TK)';
                    isAdInProgress = false;
                    
                    // Show success message
                    alert(texts[currentLanguage].successMessage);
                }, 3000);
            }
        }

        function startCountdown() {
            let countdown = 5;
            const timerElement = document.getElementById('countdownTimer');
            timerElement.style.display = 'block';
            timerElement.textContent = currentLanguage === 'bn' ? 
                `পরবর্তী বিজ্ঞাপন: ${countdown} সেকেন্ড` : 
                `Next ad: ${countdown} seconds`;
            
            clearInterval(countdownInterval);
            countdownInterval = setInterval(() => {
                countdown--;
                timerElement.textContent = currentLanguage === 'bn' ? 
                    `পরবর্তী বিজ্ঞাপন: ${countdown} সেকেন্ড` : 
                    `Next ad: ${countdown} seconds`;
                
                if (countdown <= 0) {
                    clearInterval(countdownInterval);
                    timerElement.style.display = 'none';
                }
            }, 1000);
        }

        function updateBalanceDisplay() {
            document.getElementById('currentBalance').textContent = 
                currentLanguage === 'bn' ? `${currentBalance} টাকা` : `${currentBalance} Taka`;
            
            document.getElementById('withdrawBalance').textContent = 
                currentLanguage === 'bn' ? `${currentBalance} টাকা` : `${currentBalance} Taka`;
            
            // Update total earned in stats
            document.querySelectorAll('.stat-value')[1].textContent = 
                currentLanguage === 'bn' ? `${totalEarnings} টাকা` : `${totalEarnings} Taka`;
        }

        function updateProgressBar() {
            const progress = (adCount / maxAdsPerDay) * 100;
            document.querySelector('.progress-fill').style.width = `${progress}%`;
            
            document.getElementById('dailyLimitText').textContent = 
                currentLanguage === 'bn' ? 
                `দৈনিক সীমা: ${adCount}/${maxAdsPerDay} বিজ্ঞাপন` : 
                `Daily Limit: ${adCount}/${maxAdsPerDay} Ads`;
        }

        function handleWithdraw() {
            if (currentBalance < 1500) {
                alert(texts[currentLanguage].insufficientBalance);
                return;
            }
            
            const selectedMethod = document.querySelector('.payment-method.active');
            if (!selectedMethod) {
                alert('Please select a payment method');
                return;
            }
            
            const method = selectedMethod.dataset.method;
            let inputField;
            
            switch(method) {
                case 'bkash':
                    inputField = document.getElementById('bkashNumber');
                    break;
                case 'nagad':
                    inputField = document.getElementById('nagadNumber');
                    break;
                case 'binance':
                    inputField = document.getElementById('binanceId');
                    break;
            }
            
            if (!inputField || !inputField.value) {
                alert('Please enter your payment details');
                return;
            }
            
            alert(texts[currentLanguage].withdrawSuccess);
        }
    </script>
</body>
</html>