<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>এড ভিউ এবং অর্থ ব্যবস্থাপনা</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #6a11cb 0%, #2575fc 100%);
            color: #333;
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 800px;
            margin: 0 auto;
            background: white;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            overflow: hidden;
            min-height: 90vh;
            position: relative;
        }
        
        header {
            background: #4e54c8;
            color: white;
            padding: 20px;
            text-align: center;
            position: relative;
        }
        
        .balance-container {
            background: white;
            color: #333;
            padding: 15px;
            border-radius: 10px;
            margin: 15px auto;
            width: 90%;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .balance {
            font-size: 28px;
            font-weight: bold;
            color: #4e54c8;
            margin: 10px 0;
        }
        
        .page {
            padding: 20px;
            display: none;
        }
        
        .active {
            display: block;
        }
        
        .nav {
            display: flex;
            justify-content: space-around;
            background: #f8f9fa;
            padding: 15px 0;
            border-top: 1px solid #eee;
        }
        
        .nav-btn {
            background: none;
            border: none;
            color: #4e54c8;
            font-size: 16px;
            padding: 10px 15px;
            border-radius: 20px;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .nav-btn:hover {
            background: #4e54c8;
            color: white;
        }
        
        .card {
            background: white;
            border-radius: 10px;
            padding: 20px;
            margin: 15px 0;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            border: 1px solid #eee;
        }
        
        h2 {
            color: #4e54c8;
            margin-bottom: 15px;
        }
        
        .btn {
            background: #4e54c8;
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 16px;
            margin: 10px 5px;
            transition: all 0.3s;
        }
        
        .btn:hover {
            background: #3a3eb3;
            transform: translateY(-2px);
        }
        
        .btn-secondary {
            background: #6c757d;
        }
        
        .btn-secondary:hover {
            background: #5a6268;
        }
        
        .btn-success {
            background: #28a745;
        }
        
        .btn-success:hover {
            background: #218838;
        }
        
        .ad-container {
            background: #f8f9fa;
            border-radius: 10px;
            padding: 20px;
            text-align: center;
            margin: 20px 0;
            min-height: 200px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        
        .ad-placeholder {
            width: 100%;
            max-width: 300px;
            height: 250px;
            background: linear-gradient(45deg, #ff9a9e 0%, #fad0c4 99%, #fad0c4 100%);
            border-radius: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            font-weight: bold;
            font-size: 20px;
            margin-bottom: 15px;
        }
        
        .countdown {
            font-size: 24px;
            font-weight: bold;
            color: #4e54c8;
            margin: 15px 0;
        }
        
        .transaction-list {
            list-style: none;
            margin-top: 15px;
        }
        
        .transaction-list li {
            padding: 10px 15px;
            border-bottom: 1px solid #eee;
            display: flex;
            justify-content: space-between;
        }
        
        .transaction-list li:last-child {
            border-bottom: none;
        }
        
        .income {
            color: #28a745;
        }
        
        .expense {
            color: #dc3545;
        }
        
        .referral-box {
            background: #e9ecef;
            padding: 15px;
            border-radius: 10px;
            margin: 15px 0;
            word-break: break-all;
        }
        
        .form-group {
            margin-bottom: 15px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }
        
        .form-group input {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
        }
        
        .notification {
            position: fixed;
            top: 20px;
            right: 20px;
            background: #28a745;
            color: white;
            padding: 15px 20px;
            border-radius: 8px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            transform: translateX(100%);
            transition: transform 0.3s;
            z-index: 1000;
        }
        
        .notification.show {
            transform: translateX(0);
        }
        
        .withdraw-info {
            background: #f8d7da;
            color: #721c24;
            padding: 10px;
            border-radius: 5px;
            margin: 10px 0;
            font-size: 14px;
        }
        
        .publishing-guide {
            background: white;
            border-radius: 10px;
            padding: 20px;
            margin: 20px auto;
            max-width: 800px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .publishing-guide h2 {
            color: #4e54c8;
            margin-bottom: 15px;
        }
        
        .publishing-options {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin: 20px 0;
        }
        
        .publishing-option {
            flex: 1;
            min-width: 250px;
            background: #f8f9fa;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
        }
        
        .publishing-option h3 {
            color: #4e54c8;
            margin-bottom: 10px;
        }
        
        .steps {
            margin-left: 20px;
            margin-bottom: 15px;
        }
        
        .steps li {
            margin-bottom: 8px;
        }
        
        @media (max-width: 600px) {
            .nav {
                flex-wrap: wrap;
            }
            
            .nav-btn {
                margin: 5px;
                font-size: 14px;
            }
            
            .publishing-options {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>এড ভিউ এবং অর্থ ব্যবস্থাপনা</h1>
            <div class="balance-container">
                <div>আপনার ব্যালেন্স</div>
                <div class="balance" id="balance">৫০ টাকা</div>
            </div>
        </header>
        
        <div class="nav">
            <button class="nav-btn" onclick="showPage('home')">হোম</button>
            <button class="nav-btn" onclick="showPage('ads')">এড ভিউ</button>
            <button class="nav-btn" onclick="showPage('withdraw')">উত্তোলন</button>
            <button class="nav-btn" onclick="showPage('referral')">রেফার</button>
            <button class="nav-btn" onclick="showPage('history')">ইতিহাস</button>
            <button class="nav-btn" onclick="showPage('publish')">পাবলিশ</button>
        </div>
        
        <!-- হোম পৃষ্ঠা -->
        <div id="home" class="page active">
            <div class="card">
                <h2>স্বাগতম!</h2>
                <p>এই অ্যাপ্লিকেশনের মাধ্যমে আপনি ভিডিও এড দেখে আয় করতে পারবেন, রেফারেলের মাধ্যমে অতিরিক্ত আয় করতে পারবেন এবং আপনার আয় উত্তোলন করতে পারবেন।</p>
                
                <div class="withdraw-info">
                    ন্যূনতম উত্তোলনের পরিমাণ: ৫০০ টাকা
                </div>
                
                <h3>দ্রুত স্টার্ট</h3>
                <button class="btn" onclick="showPage('ads')">এড দেখুন</button>
                <button class="btn" onclick="showPage('referral')">রেফার করুন</button>
            </div>
            
            <div class="card">
                <h3>আজকের স্ট্যাটাস</h3>
                <p>আজ দেখেছেন: <span id="today-ads">০</span>টি এড</p>
                <p>আজকের আয়: <span id="today-income">০</span> টাকা</p>
            </div>
        </div>
        
        <!-- এড ভিউ পৃষ্ঠা -->
        <div id="ads" class="page">
            <div class="card">
                <h2>ভিডিও এড দেখুন</h2>
                <p>নিচের ভিডিওটি সম্পূর্ণ দেখুন এবং পুরস্কার পান। প্রতিটি এড দেখলে আপনি ১০ টাকা পাবেন।</p>
            </div>
            
            <div class="ad-container">
                <div class="ad-placeholder">ভিডিও এড</div>
                <div class="countdown" id="countdown">৩০</div>
                <button class="btn" id="watch-btn" onclick="startAd()">এড দেখুন</button>
            </div>
            
            <div class="card">
                <h3>এড দেখার নিয়ম</h3>
                <p>• প্রতিদিন সর্বোচ্চ ১০টি এড দেখতে পারবেন</p>
                <p>• প্রতিটি এড সম্পূর্ণ দেখতে হবে</p>
                <p>• এড দেখার সময় অন্য কাজ করা যাবে না</p>
            </div>
        </div>
        
        <!-- উত্তোলন পৃষ্ঠা -->
        <div id="withdraw" class="page">
            <div class="card">
                <h2>টাকা উত্তোলন</h2>
                <p>আপনার আয় করা টাকা উত্তোলন করুন। উত্তোলনের জন্য ন্যূনতম ৫০০ টাকা প্রয়োজন।</p>
                
                <div class="withdraw-info">
                    ন্যূনতম উত্তোলনের পরিমাণ: ৫০০ টাকা
                </div>
                
                <div class="form-group">
                    <label for="withdraw-amount">উত্তোলনের পরিমাণ</label>
                    <input type="number" id="withdraw-amount" placeholder="উত্তোলনের পরিমাণ লিখুন">
                </div>
                
                <div class="form-group">
                    <label for="payment-method">পেমেন্ট মethod</label>
                    <select id="payment-method" class="form-control">
                        <option value="bkash">bKash</option>
                        <option value="nagad">Nagad</option>
                        <option value="rocket">Rocket</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label for="account-number">অ্যাকাউন্ট নম্বর</label>
                    <input type="text" id="account-number" placeholder="আপনার অ্যাকাউন্ট নম্বর লিখুন">
                </div>
                
                <button class="btn" onclick="withdrawMoney()">উত্তোলন অনুরোধ করুন</button>
            </div>
        </div>
        
        <!-- রেফারেল পৃষ্ঠা -->
        <div id="referral" class="page">
            <div class="card">
                <h2>রেফারেল সিস্টেম</h2>
                <p>আপনার বন্ধুদের邀请 করুন এবং প্রতিটি রেফারেলের জন্য ৪০ টাকা পান।</p>
                
                <div class="referral-box">
                    আপনার রেফারেল লিংক: <span id="referral-link">https://example.com/ref/12345</span>
                </div>
                
                <button class="btn" onclick="copyReferralLink()">লিংক কপি করুন</button>
            </div>
            
            <div class="card">
                <h3>আপনার রেফারেলগুলি</h3>
                <p>মোট রেফারেল: <span id="total-referrals">০</span></p>
                <p>রেফারেল থেকে আয়: <span id="referral-income">০</span> টাকা</p>
            </div>
            
            <div class="card">
                <h3>রেফারেল如何 কাজ করে</h3>
                <p>1. আপনার রেফারেল লিংকটি শেয়ার করুন</p>
                <p>2. যখন有人 আপনার লিংক ব্যবহার করে নিবন্ধন করে</p>
                <p>3. আপনি立刻 ৪০ টাকা পান</p>
                <p>4. আপনার বন্ধুও ৫০ টাকা বোনাস পায়</p>
            </div>
        </div>
        
        <!-- ইতিহাস পৃষ্ঠা -->
        <div id="history" class="page">
            <div class="card">
                <h2>লেনদেনের ইতিহাস</h2>
                <ul class="transaction-list" id="transaction-list">
                    <li>
                        <div>প্রথম লগইন বোনাস</div>
                        <div class="income">+৫০ টাকা</div>
                        <div>৬/১২/২০২৩</div>
                    </li>
                </ul>
            </div>
            
            <div class="card">
                <h2>আয়ের সারাংশ</h2>
                <p>এড দেখে আয়: <span id="total-ad-income">০</span> টাকা</p>
                <p>রেফারেল আয়: <span id="total-referral-income">০</span> টাকা</p>
                <p>বোনাস: <span id="total-bonus">৫০</span> টাকা</p>
                <p>মোট আয়: <span id="total-income">৫০</span> টাকা</p>
                <p>মোট উত্তোলন: <span id="total-withdraw">০</span> টাকা</p>
            </div>
        </div>
        
        <!-- পাবলিশ পৃষ্ঠা -->
        <div id="publish" class="page">
            <div class="card">
                <h2>আপনার অ্যাপ্লিকেশন পাবলিশ করুন</h2>
                <p>নিচের প্ল্যাটফর্ম গুলো ব্যবহার করে আপনি সহজেই আপনার ওয়েব অ্যাপ্লিকেশনটি পাবলিশ করতে পারেন:</p>
                
                <div class="publishing-options">
                    <div class="publishing-option">
                        <h3>GitHub Pages</h3>
                        <ol class="steps">
                            <li>GitHub অ্যাকাউন্ট তৈরি করুন</li>
                            <li>একটি নতুন রিপোজিটরি তৈরি করুন</li>
                            <li>আপনার HTML ফাইল আপলোড করুন</li>
                            <li>Settings থেকে GitHub Pages এক্টিভেট করুন</li>
                        </ol>
                        <button class="btn" onclick="window.open('https://pages.github.com/', '_blank')">বিস্তারিত জানুন</button>
                    </div>
                    
                    <div class="publishing-option">
                        <h3>Netlify</h3>
                        <ol class="steps">
                            <li>Netlify অ্যাকাউন্ট তৈরি করুন</li>
                            <li>আপনার ফাইল ড্র্যাগ অ্যান্ড ড্রপ করুন</li>
                            <li>অটোমেটিকভাবে ডেপ্লয় হবে</li>
                            <li>কাস্টম ডোমেইন সেট আপ করুন (ঐচ্ছিক)</li>
                        </ol>
                        <button class="btn" onclick="window.open('https://www.netlify.com/', '_blank')">বিস্তারিত জানুন</button>
                    </div>
                    
                    <div class="publishing-option">
                        <h3>Vercel</h3>
                        <ol class="steps">
                            <li>Vercel অ্যাকাউন্ট তৈরি করুন</li>
                            <li>GitHub রিপোজিটরি কানেক্ট করুন</li>
                            <li>অটো ডেপ্লয়মেন্ট সেট আপ হবে</li>
                            <li>কাস্টম ডোমেইন যোগ করুন (ঐচ্ছিক)</li>
                        </ol>
                        <button class="btn" onclick="window.open('https://vercel.com/', '_blank')">বিস্তারিত জানুন</button>
                    </div>
                </div>
                
                <div class="card">
                    <h3>পাবলিশ করার আগে করণীয়</h3>
                    <ul class="steps">
                        <li>সমস্ত ফিচার টেস্ট করুন</li>
                        <li>মোবাইল এবং ডেস্কটাপে রেসপনসিভনেস চেক করুন</li>
                        <li>মেটা ট্যাগ আপডেট করুন (SEO এর জন্য)</li>
                        <li>একটি ফ্যাভিকন যোগ করুন</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
    
    <div class="notification" id="notification">অপারেশন সফল হয়েছে!</div>

    <script>
        // ব্যবহারকারীর ডেটা
        let userData = {
            balance: 50, // প্রথমবার লগইনে ৫০ টাকা বোনাস
            adWatchedToday: 0,
            totalAdsWatched: 0,
            totalEarnings: 50,
            totalWithdrawals: 0,
            referrals: 0,
            referralIncome: 0,
            transactions: [
                { type: 'bonus', amount: 50, description: 'প্রথম লগইন বোনাস', date: new Date().toLocaleDateString() }
            ]
        };
        
        // DOM এলিমেন্ট
        const balanceEl = document.getElementById('balance');
        const todayAdsEl = document.getElementById('today-ads');
        const todayIncomeEl = document.getElementById('today-income');
        const countdownEl = document.getElementById('countdown');
        const watchBtn = document.getElementById('watch-btn');
        const transactionListEl = document.getElementById('transaction-list');
        const totalAdIncomeEl = document.getElementById('total-ad-income');
        const totalReferralIncomeEl = document.getElementById('total-referral-income');
        const totalBonusEl = document.getElementById('total-bonus');
        const totalIncomeEl = document.getElementById('total-income');
        const totalWithdrawEl = document.getElementById('total-withdraw');
        const totalReferralsEl = document.getElementById('total-referrals');
        const referralIncomeEl = document.getElementById('referral-income');
        const notificationEl = document.getElementById('notification');
        
        // পৃষ্ঠা প্রদর্শন ফাংশন
        function showPage(pageId) {
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById(pageId).classList.add('active');
        }
        
        // ব্যালেন্স আপডেট ফাংশন
        function updateBalance() {
            balanceEl.textContent = `${userData.balance} টাকা`;
            todayAdsEl.textContent = userData.adWatchedToday;
            todayIncomeEl.textContent = userData.adWatchedToday * 10;
            
            // ইতিহাস পৃষ্ঠা আপডেট
            updateHistoryPage();
        }
        
        // এড দেখা শুরু ফাংশন
        function startAd() {
            if (userData.adWatchedToday >= 10) {
                showNotification('আজ আপনি সর্বোচ্চ এড দেখেছেন। আগামীকাল আবার চেষ্টা করুন।');
                return;
            }
            
            let timeLeft = 30;
            watchBtn.disabled = true;
            
            const countdownInterval = setInterval(() => {
                countdownEl.textContent = timeLeft;
                timeLeft--;
                
                if (timeLeft < 0) {
                    clearInterval(countdownInterval);
                    completeAdView();
                }
            }, 1000);
        }
        
        // এড দেখা সম্পূর্ণ ফাংশন
        function completeAdView() {
            userData.adWatchedToday++;
            userData.totalAdsWatched++;
            userData.balance += 10;
            userData.totalEarnings += 10;
            
            countdownEl.textContent = '৩০';
            watchBtn.disabled = false;
            
            // লেনদেন ইতিহাসে যোগ
            userData.transactions.push({
                type: 'ad',
                amount: 10,
                description: 'এড দেখে আয়',
                date: new Date().toLocaleDateString()
            });
            
            showNotification('অভিনন্দন! আপনি ১০ টাকা পেয়েছেন।');
            updateBalance();
        }
        
        // টাকা উত্তোলন ফাংশন
        function withdrawMoney() {
            const amount = parseInt(document.getElementById('withdraw-amount').value);
            const paymentMethod = document.getElementById('payment-method').value;
            const accountNumber = document.getElementById('account-number').value;
            
            if (!amount || amount < 500) {
                showNotification('ন্যূনতম ৫০০ টাকা উত্তোলন করতে হবে।');
                return;
            }
            
            if (amount > userData.balance) {
                showNotification('আপনার পর্যাপ্ত ব্যালেন্স নেই।');
                return;
            }
            
            if (!accountNumber) {
                showNotification('অ্যাকাউন্ট নম্বর প্রদান করুন।');
                return;
            }
            
            userData.balance -= amount;
            userData.totalWithdrawals += amount;
            
            // লেনদেন ইতিহাসে যোগ
            userData.transactions.push({
                type: 'withdraw',
                amount: amount,
                description: `${paymentMethod} এ উত্তোলন`,
                date: new Date().toLocaleDateString()
            });
            
            showNotification(`আপনার উত্তোলন অনুরোধ প্রক্রিয়াকরণ হচ্ছে। ${amount} টাকা ${paymentMethod} (${accountNumber}) এ পাঠানো হবে।`);
            updateBalance();
            
            // ফর্ম রিসেট
            document.getElementById('withdraw-amount').value = '';
            document.getElementById('account-number').value = '';
        }
        
        // রেফারেল লিংক কপি ফাংশন
        function copyReferralLink() {
            const referralLink = document.getElementById('referral-link');
            const tempTextArea = document.createElement('textarea');
            tempTextArea.value = referralLink.textContent;
            document.body.appendChild(tempTextArea);
            tempTextArea.select();
            document.execCommand('copy');
            document.body.removeChild(tempTextArea);
            
            showNotification('রেফারেল লিংক কপি করা হয়েছে!');
        }
        
        // ইতিহাস পৃষ্ঠা আপডেট ফাংশন
        function updateHistoryPage() {
            // লেনদেন তালিকা আপডেট
            if (userData.transactions.length > 0) {
                transactionListEl.innerHTML = '';
                userData.transactions.forEach(transaction => {
                    const li = document.createElement('li');
                    const amountClass = transaction.type === 'withdraw' ? 'expense' : 'income';
                    
                    li.innerHTML = `
                        <div>${transaction.description}</div>
                        <div class="${amountClass}">${transaction.type === 'withdraw' ? '-' : '+'}${transaction.amount} টাকা</div>
                        <div>${transaction.date}</div>
                    `;
                    transactionListEl.appendChild(li);
                });
            }
            
            // সারাংশ আপডেট
            const adIncome = userData.totalAdsWatched * 10;
            const bonus = userData.transactions.filter(t => t.type === 'bonus').reduce((sum, t) => sum + t.amount, 0);
            
            totalAdIncomeEl.textContent = adIncome;
            totalReferralIncomeEl.textContent = userData.referralIncome;
            totalBonusEl.textContent = bonus;
            totalIncomeEl.textContent = userData.totalEarnings;
            totalWithdrawEl.textContent = userData.totalWithdrawals;
            
            // রেফারেল পৃষ্ঠা আপডেট
            totalReferralsEl.textContent = userData.referrals;
            referralIncomeEl.textContent = userData.referralIncome;
        }
        
        // বিজ্ঞপ্তি প্রদর্শন ফাংশন
        function showNotification(message) {
            notificationEl.textContent = message;
            notificationEl.classList.add('show');
            
            setTimeout(() => {
                notificationEl.classList.remove('show');
            }, 3000);
        }
        
        // প্রারম্ভিক সেটআপ
        updateBalance();
    </script>
</body>
</html> 
