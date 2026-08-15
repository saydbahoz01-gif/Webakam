<html lang="ku" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SAYD 4 Digital</title>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Arabic:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
    <style>
        :root {
            --bg: #e0e5ec;
            --bg-dark: #2d3436;
            --text: #2d3436;
            --text-dark: #f5f6fa;
            --accent: #7c3aed;
            --accent-glow: rgba(124,58,237,0.3);
            --shadow-light: #ffffff;
            --shadow-dark: #a3b1c6;
            --shadow-dark-d: #1a1d21;
            --shadow-light-d: #3d4449;
            --card-bg: #e0e5ec;
            --card-bg-dark: #2d3436;
            --border: rgba(124,58,237,0.15);
            --success: #10b981;
            --whatsapp: #25D366;
            --ios-color: #007AFF;
            --android-color: #3DDC84;
            --appstore-color: #0A84FF;
            --download-ios: #007AFF;
            --download-android: #3DDC84;
            --download-appstore: #0A84FF;
        }
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: 'Noto Sans Arabic', sans-serif;
            background: var(--bg);
            color: var(--text);
            min-height: 100vh;
            overflow-x: hidden;
            transition: background 0.5s, color 0.5s;
        }
        body.dark-mode {
            --bg: #2d3436;
            --text: #f5f6fa;
            --card-bg: #2d3436;
            --shadow-light: #3d4449;
            --shadow-dark: #1a1d21;
            --border: rgba(124,58,237,0.25);
        }
        body.arabic-mode {
            font-family: 'Noto Sans Arabic', sans-serif;
        }
        body.english-mode {
            font-family: 'Noto Sans Arabic', sans-serif;
            direction: ltr;
        }

        /* Header */
        .header {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            z-index: 100;
            padding: 12px 20px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            background: var(--bg);
            transition: background 0.5s;
        }
        .logo {
            font-size: 1.3rem;
            font-weight: 800;
            color: var(--accent);
            letter-spacing: 1px;
        }
        .logo span {
            color: var(--text);
            font-weight: 400;
        }
        .header-controls {
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .ctrl-btn {
            width: 38px;
            height: 38px;
            border: none;
            border-radius: 12px;
            background: var(--card-bg);
            color: var(--text);
            font-size: 0.85rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
            box-shadow: 5px 5px 10px var(--shadow-dark), -5px -5px 10px var(--shadow-light);
        }
        .ctrl-btn:hover {
            box-shadow: 2px 2px 5px var(--shadow-dark), -2px -2px 5px var(--shadow-light);
        }
        .ctrl-btn.active-ctrl {
            box-shadow: inset 3px 3px 6px var(--shadow-dark), inset -3px -3px 6px var(--shadow-light);
            color: var(--accent);
        }
        .lang-select {
            height: 38px;
            padding: 0 12px;
            border: none;
            border-radius: 12px;
            background: var(--card-bg);
            color: var(--text);
            font-family: 'Noto Sans Arabic', sans-serif;
            font-size: 0.75rem;
            cursor: pointer;
            box-shadow: 5px 5px 10px var(--shadow-dark), -5px -5px 10px var(--shadow-light);
            appearance: none;
            -webkit-appearance: none;
            padding-left: 28px;
            background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 24 24' fill='none' stroke='%237c3aed' stroke-width='2'%3E%3Cpath d='M6 9l6 6 6-6'/%3E%3C/svg%3E");
            background-repeat: no-repeat;
            background-position: 8px center;
        }

        /* Main Container */
        .main-container {
            padding-top: 70px;
            padding-bottom: 100px;
            min-height: 100vh;
        }

        /* Tab Content */
        .tab-content {
            display: none;
            padding: 20px;
            max-width: 900px;
            margin: 0 auto;
            animation: fadeUp 0.4s ease;
        }
        .tab-content.active {
            display: block;
        }
        @keyframes fadeUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Neu Cards */
        .neu-card {
            background: var(--card-bg);
            border-radius: 20px;
            padding: 24px;
            margin-bottom: 20px;
            box-shadow: 8px 8px 16px var(--shadow-dark), -8px -8px 16px var(--shadow-light);
            transition: all 0.3s;
            border: 1px solid var(--border);
        }
        .neu-card:hover {
            box-shadow: 4px 4px 8px var(--shadow-dark), -4px -4px 8px var(--shadow-light);
        }

        /* App Sub-Tabs */
        .app-subtabs {
            display: flex;
            gap: 10px;
            margin-bottom: 24px;
            overflow-x: auto;
            padding-bottom: 4px;
            scrollbar-width: none;
        }
        .app-subtabs::-webkit-scrollbar { display: none; }
        .app-subtab {
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 12px 20px;
            border: none;
            border-radius: 16px;
            background: var(--card-bg);
            color: var(--text);
            font-family: 'Noto Sans Arabic', sans-serif;
            font-size: 0.85rem;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.35s;
            white-space: nowrap;
            box-shadow: 5px 5px 10px var(--shadow-dark), -5px -5px 10px var(--shadow-light);
            border: 2px solid transparent;
            position: relative;
            overflow: hidden;
        }
        .app-subtab::before {
            content: '';
            position: absolute;
            inset: 0;
            opacity: 0;
            transition: opacity 0.35s;
            border-radius: 14px;
        }
        .app-subtab.sub-ios::before { background: linear-gradient(135deg, rgba(0,122,255,0.12), rgba(0,122,255,0.04)); }
        .app-subtab.sub-android::before { background: linear-gradient(135deg, rgba(61,220,132,0.12), rgba(61,220,132,0.04)); }
        .app-subtab.sub-appstore::before { background: linear-gradient(135deg, rgba(10,132,255,0.12), rgba(10,132,255,0.04)); }
        .app-subtab.active::before { opacity: 1; }
        .app-subtab.active {
            border-color: var(--accent);
            box-shadow: inset 3px 3px 6px var(--shadow-dark), inset -3px -3px 6px var(--shadow-light);
        }
        .app-subtab.sub-ios.active { border-color: var(--ios-color); }
        .app-subtab.sub-android.active { border-color: var(--android-color); }
        .app-subtab.sub-appstore.active { border-color: var(--appstore-color); }
        .app-subtab i {
            font-size: 1.1rem;
            position: relative;
            z-index: 1;
        }
        .app-subtab span {
            position: relative;
            z-index: 1;
        }
        .app-subtab.sub-ios.active i { color: var(--ios-color); }
        .app-subtab.sub-android.active i { color: var(--android-color); }
        .app-subtab.sub-appstore.active i { color: var(--appstore-color); }
        .app-subtab:hover:not(.active) {
            transform: translateY(-2px);
            box-shadow: 3px 3px 6px var(--shadow-dark), -3px -3px 6px var(--shadow-light);
        }

        /* App Sub-Content */
        .app-subcontent {
            display: none;
            animation: fadeUp 0.35s ease;
        }
        .app-subcontent.active {
            display: block;
        }

        /* Platform Header */
        .platform-header {
            display: flex;
            align-items: center;
            gap: 14px;
            margin-bottom: 20px;
            padding: 18px 20px;
            border-radius: 18px;
            background: var(--card-bg);
            box-shadow: 6px 6px 12px var(--shadow-dark), -6px -6px 12px var(--shadow-light);
            border: 1px solid var(--border);
        }
        .platform-icon {
            width: 52px;
            height: 52px;
            min-width: 52px;
            border-radius: 14px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: #fff;
        }
        .platform-icon.ios-icon { background: linear-gradient(135deg, #007AFF, #5856D6); }
        .platform-icon.android-icon { background: linear-gradient(135deg, #3DDC84, #2BAF6A); }
        .platform-icon.appstore-icon { background: linear-gradient(135deg, #0A84FF, #5E5CE6); }
        .platform-info h3 {
            font-size: 1.05rem;
            font-weight: 800;
            margin-bottom: 2px;
        }
        .platform-info p {
            font-size: 0.75rem;
            opacity: 0.55;
            line-height: 1.5;
        }
        .platform-count {
            margin-right: auto;
            background: var(--accent);
            color: #fff;
            width: 36px;
            height: 36px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.85rem;
            font-weight: 800;
        }

        /* Product Cards */
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
            gap: 20px;
        }
        .product-card {
            background: var(--card-bg);
            border-radius: 20px;
            padding: 0;
            overflow: hidden;
            box-shadow: 8px 8px 16px var(--shadow-dark), -8px -8px 16px var(--shadow-light);
            transition: all 0.4s;
            border: 1px solid var(--border);
            cursor: pointer;
            position: relative;
        }
        .product-card:hover {
            transform: translateY(-4px);
            box-shadow: 12px 12px 24px var(--shadow-dark), -12px -12px 24px var(--shadow-light);
        }
        .product-img {
            width: 100%;
            height: 180px;
            object-fit: cover;
            display: block;
        }
        .product-info {
            padding: 16px 20px 20px;
        }
        .product-name {
            font-size: 1.05rem;
            font-weight: 700;
            margin-bottom: 6px;
            color: var(--text);
        }
        .product-desc {
            font-size: 0.82rem;
            color: var(--text);
            opacity: 0.7;
            margin-bottom: 12px;
            line-height: 1.6;
        }
        .product-price {
            font-size: 1.15rem;
            font-weight: 800;
            color: var(--accent);
            margin-bottom: 14px;
        }
        .product-btn {
            width: 100%;
            padding: 12px;
            border: none;
            border-radius: 14px;
            background: var(--accent);
            color: #fff;
            font-family: 'Noto Sans Arabic', sans-serif;
            font-size: 0.9rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            box-shadow: 4px 4px 10px var(--shadow-dark), -4px -4px 10px var(--shadow-light);
            text-decoration: none;
        }
        .product-btn:hover {
            background: #6d28d9;
            transform: scale(0.97);
        }
        .product-btn i {
            font-size: 1rem;
        }

        /* Download Button Variants */
        .product-btn.btn-download-ios {
            background: linear-gradient(135deg, #007AFF, #5856D6);
            box-shadow: 4px 4px 10px var(--shadow-dark), -4px -4px 10px var(--shadow-light);
        }
        .product-btn.btn-download-ios:hover {
            background: linear-gradient(135deg, #0062cc, #4a47c7);
            transform: scale(0.97);
        }
        .product-btn.btn-download-android {
            background: linear-gradient(135deg, #3DDC84, #2BAF6A);
            box-shadow: 4px 4px 10px var(--shadow-dark), -4px -4px 10px var(--shadow-light);
            color: #fff;
        }
        .product-btn.btn-download-android:hover {
            background: linear-gradient(135deg, #2ec474, #239e5b);
            transform: scale(0.97);
        }
        .product-btn.btn-download-appstore {
            background: linear-gradient(135deg, #0A84FF, #5E5CE6);
            box-shadow: 4px 4px 10px var(--shadow-dark), -4px -4px 10px var(--shadow-light);
        }
        .product-btn.btn-download-appstore:hover {
            background: linear-gradient(135deg, #0870d9, #4f4dc4);
            transform: scale(0.97);
        }

        /* Download progress bar */
        .download-bar {
            width: 100%;
            height: 4px;
            background: var(--shadow-dark);
            border-radius: 4px;
            margin-top: 10px;
            overflow: hidden;
            opacity: 0;
            transition: opacity 0.3s;
        }
        .download-bar.active {
            opacity: 1;
        }
        .download-bar-inner {
            height: 100%;
            width: 0%;
            border-radius: 4px;
            transition: width 0.1s linear;
        }
        .download-bar-inner.bar-ios { background: linear-gradient(90deg, #007AFF, #5856D6); }
        .download-bar-inner.bar-android { background: linear-gradient(90deg, #3DDC84, #2BAF6A); }
        .download-bar-inner.bar-appstore { background: linear-gradient(90deg, #0A84FF, #5E5CE6); }

        /* Download toast */
        .download-toast {
            position: fixed;
            top: 80px;
            left: 50%;
            transform: translateX(-50%) translateY(-30px);
            padding: 16px 28px;
            border-radius: 16px;
            font-size: 0.88rem;
            font-weight: 700;
            font-family: 'Noto Sans Arabic', sans-serif;
            box-shadow: 8px 8px 16px var(--shadow-dark), -8px -8px 16px var(--shadow-light);
            border: 1px solid var(--border);
            z-index: 350;
            opacity: 0;
            transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
            pointer-events: none;
            display: flex;
            align-items: center;
            gap: 10px;
            background: var(--bg);
            color: var(--text);
        }
        .download-toast.show {
            opacity: 1;
            transform: translateX(-50%) translateY(0);
        }
        .download-toast i {
            font-size: 1.1rem;
        }
        .download-toast .dt-ios { color: var(--ios-color); }
        .download-toast .dt-android { color: var(--android-color); }
        .download-toast .dt-appstore { color: var(--appstore-color); }

        /* Bottom Nav */
        .bottom-nav {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            z-index: 100;
            padding: 12px 16px 18px;
            background: var(--bg);
            transition: background 0.5s;
        }
        .nav-inner {
            max-width: 500px;
            margin: 0 auto;
            display: flex;
            align-items: center;
            justify-content: space-around;
            background: var(--card-bg);
            border-radius: 22px;
            padding: 10px 6px;
            box-shadow: 8px 8px 16px var(--shadow-dark), -8px -8px 16px var(--shadow-light);
            border: 1px solid var(--border);
        }
        .nav-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 4px;
            padding: 8px 6px;
            border-radius: 16px;
            cursor: pointer;
            transition: all 0.3s;
            min-width: 56px;
            border: none;
            background: none;
            color: var(--text);
            opacity: 0.5;
            font-family: 'Noto Sans Arabic', sans-serif;
        }
        .nav-item i {
            font-size: 1.15rem;
            transition: all 0.3s;
        }
        .nav-item span {
            font-size: 0.65rem;
            font-weight: 600;
            white-space: nowrap;
        }
        .nav-item.active {
            opacity: 1;
            color: var(--accent);
            box-shadow: inset 4px 4px 8px var(--shadow-dark), inset -4px -4px 8px var(--shadow-light);
        }
        .nav-item:hover:not(.active) {
            opacity: 0.75;
        }

        /* Home Hero */
        .hero-section {
            text-align: center;
            padding: 40px 20px 30px;
        }
        .hero-icon {
            width: 90px;
            height: 90px;
            border-radius: 50%;
            background: var(--card-bg);
            box-shadow: 8px 8px 16px var(--shadow-dark), -8px -8px 16px var(--shadow-light);
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 2.2rem;
            color: var(--accent);
            border: 2px solid var(--border);
        }
        .hero-title {
            font-size: 1.8rem;
            font-weight: 900;
            margin-bottom: 8px;
            background: linear-gradient(135deg, var(--accent), #a78bfa);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        .hero-subtitle {
            font-size: 0.95rem;
            opacity: 0.65;
            line-height: 1.7;
            max-width: 400px;
            margin: 0 auto;
        }

        /* Stats */
        .stats-row {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 14px;
            margin-top: 30px;
        }
        .stat-card {
            background: var(--card-bg);
            border-radius: 18px;
            padding: 20px 12px;
            text-align: center;
            box-shadow: 6px 6px 12px var(--shadow-dark), -6px -6px 12px var(--shadow-light);
            border: 1px solid var(--border);
        }
        .stat-num {
            font-size: 1.6rem;
            font-weight: 900;
            color: var(--accent);
        }
        .stat-label {
            font-size: 0.72rem;
            opacity: 0.6;
            margin-top: 4px;
            font-weight: 500;
        }

        /* Services */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 14px;
            margin-top: 24px;
        }
        .service-card {
            background: var(--card-bg);
            border-radius: 18px;
            padding: 24px 16px;
            text-align: center;
            box-shadow: 6px 6px 12px var(--shadow-dark), -6px -6px 12px var(--shadow-light);
            border: 1px solid var(--border);
            cursor: pointer;
            transition: all 0.3s;
        }
        .service-card:hover {
            transform: translateY(-3px);
        }
        .service-card i {
            font-size: 1.8rem;
            color: var(--accent);
            margin-bottom: 10px;
        }
        .service-card h3 {
            font-size: 0.9rem;
            font-weight: 700;
            margin-bottom: 4px;
        }
        .service-card p {
            font-size: 0.72rem;
            opacity: 0.55;
            line-height: 1.5;
        }

        /* Section Title */
        .section-title {
            font-size: 1.3rem;
            font-weight: 800;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .section-title i {
            color: var(--accent);
            font-size: 1.1rem;
        }
        .section-title::after {
            content: '';
            flex: 1;
            height: 2px;
            background: linear-gradient(to left, transparent, var(--border));
            border-radius: 2px;
        }

        /* Info Page */
        .info-item {
            display: flex;
            align-items: flex-start;
            gap: 16px;
            padding: 18px;
            background: var(--card-bg);
            border-radius: 16px;
            margin-bottom: 12px;
            box-shadow: 5px 5px 10px var(--shadow-dark), -5px -5px 10px var(--shadow-light);
            border: 1px solid var(--border);
        }
        .info-icon {
            width: 46px;
            height: 46px;
            min-width: 46px;
            border-radius: 14px;
            background: var(--card-bg);
            box-shadow: inset 3px 3px 6px var(--shadow-dark), inset -3px -3px 6px var(--shadow-light);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--accent);
            font-size: 1.1rem;
        }
        .info-text h4 {
            font-size: 0.95rem;
            font-weight: 700;
            margin-bottom: 3px;
        }
        .info-text p {
            font-size: 0.8rem;
            opacity: 0.6;
            line-height: 1.6;
        }

        /* About Page */
        .about-avatar {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            background: var(--card-bg);
            box-shadow: 8px 8px 16px var(--shadow-dark), -8px -8px 16px var(--shadow-light);
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 3rem;
            color: var(--accent);
            border: 3px solid var(--border);
        }
        .about-name {
            text-align: center;
            font-size: 1.4rem;
            font-weight: 800;
            margin-bottom: 4px;
        }
        .about-role {
            text-align: center;
            font-size: 0.9rem;
            opacity: 0.55;
            margin-bottom: 24px;
        }
        .social-links {
            display: flex;
            justify-content: center;
            gap: 12px;
            margin-top: 20px;
        }
        .social-btn {
            width: 48px;
            height: 48px;
            border-radius: 16px;
            background: var(--card-bg);
            border: 1px solid var(--border);
            color: var(--text);
            font-size: 1.2rem;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 4px 4px 8px var(--shadow-dark), -4px -4px 8px var(--shadow-light);
            text-decoration: none;
        }
        .social-btn:hover {
            color: var(--accent);
            transform: translateY(-2px);
        }

        /* WhatsApp Modal */
        .modal-overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.5);
            z-index: 200;
            align-items: center;
            justify-content: center;
            padding: 20px;
            backdrop-filter: blur(4px);
        }
        .modal-overlay.show {
            display: flex;
            animation: fadeIn 0.3s ease;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        .modal-box {
            background: var(--bg);
            border-radius: 24px;
            padding: 32px 24px;
            width: 100%;
            max-width: 420px;
            box-shadow: 12px 12px 24px var(--shadow-dark), -12px -12px 24px var(--shadow-light);
            border: 1px solid var(--border);
            animation: scaleIn 0.3s ease;
        }
        @keyframes scaleIn {
            from { transform: scale(0.9); opacity: 0; }
            to { transform: scale(1); opacity: 1; }
        }
        .modal-title {
            font-size: 1.2rem;
            font-weight: 800;
            margin-bottom: 6px;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .modal-title i {
            color: var(--whatsapp);
        }
        .modal-subtitle {
            font-size: 0.8rem;
            opacity: 0.55;
            margin-bottom: 24px;
        }
        .modal-input {
            width: 100%;
            padding: 14px 16px;
            border: none;
            border-radius: 14px;
            background: var(--card-bg);
            color: var(--text);
            font-family: 'Noto Sans Arabic', sans-serif;
            font-size: 0.9rem;
            margin-bottom: 14px;
            box-shadow: inset 4px 4px 8px var(--shadow-dark), inset -4px -4px 8px var(--shadow-light);
            outline: none;
            transition: all 0.3s;
        }
        .modal-input:focus {
            box-shadow: inset 4px 4px 8px var(--shadow-dark), inset -4px -4px 8px var(--shadow-light), 0 0 0 2px var(--accent-glow);
        }
        .modal-input::placeholder {
            opacity: 0.4;
        }
        .modal-input:read-only {
            opacity: 0.7;
        }
        .modal-actions {
            display: flex;
            gap: 10px;
            margin-top: 20px;
        }
        .modal-cancel {
            flex: 1;
            padding: 14px;
            border: none;
            border-radius: 14px;
            background: var(--card-bg);
            color: var(--text);
            font-family: 'Noto Sans Arabic', sans-serif;
            font-size: 0.9rem;
            font-weight: 600;
            cursor: pointer;
            box-shadow: 4px 4px 8px var(--shadow-dark), -4px -4px 8px var(--shadow-light);
            transition: all 0.3s;
        }
        .modal-cancel:hover {
            box-shadow: 2px 2px 4px var(--shadow-dark), -2px -2px 4px var(--shadow-light);
        }
        .modal-send {
            flex: 2;
            padding: 14px;
            border: none;
            border-radius: 14px;
            background: var(--whatsapp);
            color: #fff;
            font-family: 'Noto Sans Arabic', sans-serif;
            font-size: 0.9rem;
            font-weight: 700;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            box-shadow: 4px 4px 10px var(--shadow-dark), -4px -4px 10px var(--shadow-light);
            transition: all 0.3s;
        }
        .modal-send:hover {
            background: #20bd5a;
            transform: scale(0.97);
        }

        /* Toast */
        .toast {
            position: fixed;
            top: 80px;
            left: 50%;
            transform: translateX(-50%) translateY(-20px);
            background: var(--card-bg);
            color: var(--text);
            padding: 14px 24px;
            border-radius: 14px;
            font-size: 0.85rem;
            font-weight: 600;
            box-shadow: 8px 8px 16px var(--shadow-dark), -8px -8px 16px var(--shadow-light);
            border: 1px solid var(--border);
            z-index: 300;
            opacity: 0;
            transition: all 0.4s;
            pointer-events: none;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .toast.show {
            opacity: 1;
            transform: translateX(-50%) translateY(0);
        }
        .toast i {
            color: var(--success);
        }

        /* Decorative */
        .deco-circle {
            position: fixed;
            border-radius: 50%;
            background: radial-gradient(circle, var(--accent-glow), transparent 70%);
            pointer-events: none;
            z-index: 0;
            opacity: 0.3;
        }
        .deco-1 {
            width: 300px;
            height: 300px;
            top: -80px;
            right: -80px;
        }
        .deco-2 {
            width: 200px;
            height: 200px;
            bottom: 120px;
            left: -60px;
        }

        /* Empty state */
        .empty-state {
            text-align: center;
            padding: 60px 20px;
            opacity: 0.5;
        }
        .empty-state i {
            font-size: 3rem;
            margin-bottom: 12px;
            color: var(--accent);
        }
        .empty-state p {
            font-size: 0.9rem;
        }

        /* Feature badge */
        .badge {
            display: inline-block;
            padding: 4px 10px;
            border-radius: 8px;
            font-size: 0.65rem;
            font-weight: 700;
            background: var(--accent);
            color: #fff;
            margin-bottom: 8px;
        }
        .badge-ios { background: var(--ios-color); }
        .badge-android { background: var(--android-color); color: #1a1d21; }
        .badge-appstore { background: var(--appstore-color); }

        /* Scrollbar */
        ::-webkit-scrollbar { width: 6px; }
        ::-webkit-scrollbar-track { background: var(--bg); }
        ::-webkit-scrollbar-thumb { background: var(--accent); border-radius: 3px; }

        @media (max-width: 480px) {
            .products-grid { grid-template-columns: 1fr; }
            .stats-row { grid-template-columns: repeat(3, 1fr); gap: 8px; }
            .stat-card { padding: 14px 8px; }
            .stat-num { font-size: 1.3rem; }
            .hero-title { font-size: 1.5rem; }
            .services-grid { grid-template-columns: 1fr; }
            .nav-item span { font-size: 0.6rem; }
            .nav-item { min-width: 48px; padding: 6px 4px; }
            .app-subtab { padding: 10px 14px; font-size: 0.78rem; }
            .platform-header { padding: 14px 16px; }
            .platform-icon { width: 44px; height: 44px; min-width: 44px; font-size: 1.2rem; }
        }
    </style>
</head>
<body>

<!-- Decorative -->
<div class="deco-circle deco-1"></div>
<div class="deco-circle deco-2"></div>

<!-- Toast -->
<div class="toast" id="toast">
    <i class="fas fa-check-circle"></i>
    <span id="toastMsg"></span>
</div>

<!-- Download Toast -->
<div class="download-toast" id="downloadToast">
    <i class="fas fa-circle-notch fa-spin"></i>
    <span id="downloadToastMsg"></span>
</div>

<!-- Header -->
<header class="header">
    <div class="logo">SAYD <span>4 DIGITAL</span></div>
    <div class="header-controls">
        <select class="lang-select" id="langSelect" onchange="changeLang(this.value)">
            <option value="ku" selected>کوردی</option>
            <option value="ar">العربية</option>
            <option value="en">English</option>
        </select>
        <button class="ctrl-btn" id="themeBtn" onclick="toggleTheme()" title="Toggle Theme">
            <i class="fas fa-moon"></i>
        </button>
    </div>
</header>

<!-- Main -->
<main class="main-container">

    <!-- Tab 1: Home -->
    <div class="tab-content active" id="tab-home">
        <div class="hero-section">
            <div class="hero-icon">
                <i class="fas fa-rocket"></i>
            </div>
            <h1 class="hero-title" data-ku="SAYD 4 DIGITAL" data-ar="SAYD 4 DIGITAL" data-en="SAYD 4 DIGITAL">SAYD 4 DIGITAL</h1>
            <p class="hero-subtitle" data-ku="خزمەتگوزاریی دیجیتاڵی تەواو بۆ بزنسەکەت" data-ar="خدمات رقمية كاملة لعملك" data-en="Complete digital services for your business">خزمەتگوزاریی دیجیتاڵی </p>
        </div>

        <div class="stats-row">
            <div class="stat-card">
                <div class="stat-num">+15</div>
                <div class="stat-label" data-ku="پرۆژە" data-ar="مشروع" data-en="Projects">پرۆژە</div>
            </div>
            <div class="stat-card">
                <div class="stat-num">+11</div>
                <div class="stat-label" data-ku="کڕیار" data-ar="عميل" data-en="Clients">کڕیار</div>
            </div>
            <div class="stat-card">
                <div class="stat-num">+5</div>
                <div class="stat-label" data-ku="ساڵ ئەزموون" data-ar="سنوات خبرة" data-en="Years Exp">+5 ساڵ ئەزموون</div>
            </div>
        </div>

        <div class="services-grid">
            <div class="service-card" onclick="switchTab('tab-websites')">
                <i class="fas fa-globe"></i>
                <h3 data-ku="وێبسایت" data-ar="موقع إلكتروني" data-en="Website">وێبسایت</h3>
                <p data-ku="دیزاین و پرۆگرامکردن" data-ar="تصميم وبرمجة" data-en="Design & Dev">دیزاین و پرۆگرامکردن</p>
            </div>
            <div class="service-card" onclick="switchTab('tab-apps')">
                <i class="fas fa-mobile-alt"></i>
                <h3 data-ku="بەرنامە" data-ar="تطبيق" data-en="App">بەرنامە</h3>
                <p data-ku="ئەندرۆید و iOS" data-ar="أندرويد و iOS" data-en="Android & iOS">ئەندرۆید و iOS</p>
            </div>
            <div class="service-card" onclick="switchTab('tab-snap')">
                <i class="fas fa-ghost"></i>
                <h3 data-ku="سناپ پڵەس" data-ar="سناب شات" data-en="Snapchat">سناپ پڵەس</h3>
                <p data-ku="دیزاین و بەرەوپێشبردن" data-ar="تصميم وتطوير" data-en="Design & Growth">دیزاین و بەرەوپێشبردن</p>
            </div>
            <div class="service-card" onclick="switchTab('tab-info')">
                <i class="fas fa-headset"></i>
                <h3 data-ku="پشتگیری" data-ar="دعم فني" data-en="Support">پشتگیری</h3>
                <p data-ku="٢٤ کاتژمێر" data-ar="٢٤ ساعة" data-en="24/7">٢٤ کاتژمێر</p>
            </div>
        </div>
    </div>

    <!-- Tab 2: Websites -->
    <div class="tab-content" id="tab-websites">
        <h2 class="section-title">
            <i class="fas fa-globe"></i>
            <span data-ku="وێبسایتەکانم" data-ar="مواقعي الإلكترونية" data-en="My Websites">وێبسایتەکانم</span>
        </h2>
        <div class="products-grid" id="websitesGrid"></div>
    </div>

    <!-- Tab 3: Apps (with sub-tabs + download) -->
    <div class="tab-content" id="tab-apps">
        <h2 class="section-title">
            <i class="fas fa-mobile-alt"></i>
            <span data-ku="بەرنامەکان" data-ar="التطبيقات" data-en="Applications">بەرنامەکان</span>
        </h2>

        <!-- Sub-Tabs -->
        <div class="app-subtabs">
            <button class="app-subtab sub-ios active" onclick="switchAppSub('ios')" id="subtab-ios">
                <i class="fab fa-apple"></i>
                <span data-ku="IOS.ipa" data-ar="IOS.ipa" data-en="IOS.ipa">IOS.ipa</span>
            </button>
            <button class="app-subtab sub-android" onclick="switchAppSub('android')" id="subtab-android">
                <i class="fab fa-android"></i>
                <span data-ku="ANDROID" data-ar="ANDROID" data-en="ANDROID">ANDROID</span>
            </button>
            <button class="app-subtab sub-appstore" onclick="switchAppSub('appstore')" id="subtab-appstore">
                <i class="fas fa-store"></i>
                <span data-ku="APP STORE" data-ar="APP STORE" data-en="APP STORE">APP STORE</span>
            </button>
        </div>

        <!-- iOS Sub-Content -->
        <div class="app-subcontent active" id="subcontent-ios">
            <div class="platform-header">
                <div class="platform-icon ios-icon"><i class="fab fa-apple"></i></div>
                <div class="platform-info">
                    <h3 data-ku="فایلی IPA بۆ iOS" data-ar="ملف IPA لنظام iOS" data-en="IPA Files for iOS">فایلی IPA بۆ iOS</h3>
                    <p data-ku="بەرنامەکانی تاقیکردنەوە و تایبەت بۆ ئایفۆن" data-ar="تطبيقات تجريبية وخاصة للآيفون" data-en="Test & custom apps for iPhone">بەرنامەکانی تاقیکردنەوە و تایبەت بۆ ئایفۆن</p>
                </div>
                <div class="platform-count" id="ios-count">0</div>
            </div>
            <div class="products-grid" id="iosGrid"></div>
        </div>

        <!-- Android Sub-Content -->
        <div class="app-subcontent" id="subcontent-android">
            <div class="platform-header">
                <div class="platform-icon android-icon"><i class="fab fa-android"></i></div>
                <div class="platform-info">
                    <h3 data-ku="فایلی APK بۆ ئەندرۆید" data-ar="ملف APK لنظام أندرويد" data-en="APK Files for Android">فایلی APK بۆ ئەندرۆید</h3>
                    <p data-ku="بەرنامەکانی ئەندرۆید بە فۆرماتی APK" data-ar="تطبيقات أندرويد بصيغة APK" data-en="Android apps in APK format">بەرنامەکانی ئەندرۆید بە فۆرماتی APK</p>
                </div>
                <div class="platform-count" id="android-count">0</div>
            </div>
            <div class="products-grid" id="androidGrid"></div>
        </div>

        <!-- App Store Sub-Content -->
        <div class="app-subcontent" id="subcontent-appstore">
            <div class="platform-header">
                <div class="platform-icon appstore-icon"><i class="fas fa-store"></i></div>
                <div class="platform-info">
                    <h3 data-ku="APP STORE" data-ar="APP STORE" data-en="APP STORE">APP STORE</h3>
                    <p data-ku="بەرنامە فەرمییەکان لە ئاپ ستۆر" data-ar="تطبيقات رسمية من المتجر" data-en="Official apps from the store">بەرنامە فەرمییەکان لە ئاپ ستۆر</p>
                </div>
                <div class="platform-count" id="appstore-count">0</div>
            </div>
            <div class="products-grid" id="appstoreGrid"></div>
        </div>
    </div>

    <!-- Tab 4: Snapchat -->
    <div class="tab-content" id="tab-snap">
        <h2 class="section-title">
            <i class="fas fa-ghost"></i>
            <span data-ku="سناپ پڵەس" data-ar="سناب شات بلس" data-en="Snapchat Plus">سناپ پڵەس</span>
        </h2>
        <div class="products-grid" id="snapGrid"></div>
    </div>

    <!-- Tab 5: Info -->
    <div class="tab-content" id="tab-info">
        <h2 class="section-title">
            <i class="fas fa-info-circle"></i>
            <span data-ku="زانیاری" data-ar="معلومات" data-en="Information">زانیاری</span>
        </h2>
        <div class="info-item">
            <div class="info-icon"><i class="fas fa-clock"></i></div>
            <div class="info-text">
                <h4 data-ku="کاتی کارکردن" data-ar="ساعات العمل" data-en="Working Hours">کاتی کارکردن</h4>
                <p data-ku="هەموو ڕۆژێک لە کاتژمێر ٩ بۆ ١١ شەو" data-ar="كل يوم من الساعة ٩ صباحاً إلى ١١ مساءً" data-en="Every day from 9 AM to 11 PM">هەموو ڕۆژێک لە کاتژمێر ٩ بۆ ١١ شەو</p>
            </div>
        </div>
        <div class="info-item">
            <div class="info-icon"><i class="fas fa-credit-card"></i></div>
            <div class="info-text">
                <h4 data-ku="شێوازی پارەدان" data-ar="طرق الدفع" data-en="Payment Methods">شێوازی پارەدان</h4>
                <p data-ku="نەقد، زرین کارت، مەحیا کارت، فەرسەت" data-ar="نقدي، زرين كارت، محيا كارت، فرست" data-en="Cash, Zain Card, Meehya Card, Fast">FIB، FASTPAY ، QI CARD ، </p>
            </div>
        </div>
        <div class="info-item">
            <div class="info-icon"><i class="fas fa-truck"></i></div>
            <div class="info-text">
                <h4 data-ku="ناردن و گەیاندن" data-ar="التوصيل" data-en="Delivery">ناردن و گەیاندن</h4>
                <p data-ku="خزمەتگوزاری خێرا، دەستگەیشتن بە خێرایی" data-ar="خدمة سريعة، توصيل سريع" data-en="Fast service, quick delivery">خزمەتگوزاری خێرا، دەستگەیشتن بە خێرایی</p>
            </div>
        </div>
        <div class="info-item">
            <div class="info-icon"><i class="fas fa-shield-alt"></i></div>
            <div class="info-text">
                <h4 data-ku="گەرەنتی" data-ar="ضمان" data-en="Guarantee">گەرەنتی</h4>
                <p data-ku="هەموو کارێک گەرەنتی تەواوی هەیە" data-ar="كل عمل له ضمان كامل" data-en="All work has full guarantee">هەموو کارێک گەرەنتی تەواوی هەیە</p>
            </div>
        </div>
        <div class="info-item">
            <div class="info-icon"><i class="fas fa-undo"></i></div>
            <div class="info-text">
                <h4 data-ku="گەڕاندنەوە" data-ar="الاسترجاع" data-en="Returns">گەڕاندنەوە</h4>
                <p data-ku="گەڕاندنەوەی پارە لە ماوەی ٣ ڕۆژ" data-ar="استرجاع المال خلال ٣ أيام" data-en="Money back within 3 days">گەڕاندنەوەی  دوای هەر کێدەیەک و پارە گەڕاندنەوە   </p>
            </div>
        </div>
        <div class="info-item">
            <div class="info-icon"><i class="fab fa-whatsapp"></i></div>
            <div class="info-text">
                <h4 data-ku="پەیوەندیمان پێوە بکە" data-ar="تواصل معنا" data-en="Contact Us">پەیوەندیمان پێوە بکە</h4>
                <p dir="ltr" style="text-align:right">+964 750 585 0338</p>
            </div>
        </div>
    </div>

    <!-- Tab 6: About -->
    <div class="tab-content" id="tab-about">
        <div class="neu-card" style="text-align:center;">
            <div class="about-avatar">
                <i class="fas fa-user"></i>
            </div>
            <h2 class="about-name" data-ku="سەید دیجیتاڵ" data-ar="سيد الرقمي" data-en="SAYD Digital">سەید </h2>
            <p class="about-role" data-ku="پرۆگرامەر و دیزاینەر" data-ar="مبرمج ومصمم" data-en="Programmer & Designer">پرۆگرامەر و دیزاینەر</p>
            <p style="font-size:0.85rem; opacity:0.6; line-height:1.8; max-width:500px; margin:0 auto;" data-ku="سەید ٤ دیجیتاڵ تایبەتە بە دیزاین و پرۆگرامکردنی وێبسایت، بەرنامەی مۆبایل، و خزمەتگوزاریی سناپ پڵەس. ئامانجمان ئەوەیە باشترین خزمەتگوزاری بە کڕیارانمان پێشکەش بکەین بە نرخی گونجاو و کوالیتی بەرز." data-ar="سيد ٤ الرقمي متخصص في تصميم وبرمجة المواقع الإلكترونية، تطبيقات الجوال، وخدمات سناب شات بلس. هدفنا تقديم أفضل الخدمات لعملائنا بأسعار مناسبة وجودة عالية." data-en="SAYD 4 DIGITAL specializes in website design and development, mobile apps, and Snapchat Plus services. Our goal is to provide the best services to our clients at affordable prices and high quality.">سەید ٤ دیجیتاڵ تایبەتە بە دیزاین و پرۆگرامکردنی وێبسایت، بەرنامەی مۆبایل، و خزمەتگوزاریی سناپ پڵەس. ئامانجمان ئەوەیە باشترین خزمەتگوزاری بە کڕیارانمان پێشکەش بکەین بە نرخی گونجاو و کوالیتی بەرز.</p>
            <div class="social-links">
                <a href="#" class="social-btn"><i class="fab fa-instagram"></i></a>
                <a href="#" class="social-btn"><i class="fab fa-telegram"></i></a>
                <a href="#" class="social-btn"><i class="fab fa-tiktok"></i></a>
                <a href="#" class="social-btn"><i class="fab fa-facebook"></i></a>
                <a href="#" class="social-btn"><i class="fab fa-whatsapp"></i></a>
            </div>
        </div>
    </div>

</main>

<!-- Bottom Navigation -->
<nav class="bottom-nav">
    <div class="nav-inner">
        <button class="nav-item active" onclick="switchTab('tab-home')" data-tab="tab-home">
            <i class="fas fa-home"></i>
            <span data-ku="سەرەکی" data-ar="الرئيسية" data-en="Home">سەرەکی</span>
        </button>
        <button class="nav-item" onclick="switchTab('tab-websites')" data-tab="tab-websites">
            <i class="fas fa-globe"></i>
            <span data-ku="وێبسایت" data-ar="موقع" data-en="Website">وێبسایت</span>
        </button>
        <button class="nav-item" onclick="switchTab('tab-apps')" data-tab="tab-apps">
            <i class="fas fa-mobile-alt"></i>
            <span data-ku="بەرنامە" data-ar="تطبيق" data-en="App">بەرنامە</span>
        </button>
        <button class="nav-item" onclick="switchTab('tab-snap')" data-tab="tab-snap">
            <i class="fas fa-ghost"></i>
            <span data-ku="سناپ" data-ar="سناب" data-en="Snap">سناپ</span>
        </button>
        <button class="nav-item" onclick="switchTab('tab-info')" data-tab="tab-info">
            <i class="fas fa-info-circle"></i>
            <span data-ku="زانیاری" data-ar="معلومات" data-en="Info">زانیاری</span>
        </button>
        <button class="nav-item" onclick="switchTab('tab-about')" data-tab="tab-about">
            <i class="fas fa-user"></i>
            <span data-ku="دەربارە" data-ar="حول" data-en="About">دەربارە</span>
        </button>
    </div>
</nav>

<!-- WhatsApp Modal -->
<div class="modal-overlay" id="whatsappModal">
    <div class="modal-box">
        <div class="modal-title">
            <i class="fab fa-whatsapp"></i>
            <span data-ku="ناردن بۆ واتساپ" data-ar="إرسال لواتساب" data-en="Send to WhatsApp">ناردن بۆ واتساپ</span>
        </div>
        <p class="modal-subtitle" data-ku="زانیارییەکانت پڕ بکەرەوە" data-ar="أكمل معلوماتك" data-en="Fill in your details">زانیارییەکانت پڕ بکەرەوە</p>
        <input class="modal-input" type="text" id="customerName" data-ph-ku="ناوت بنووسە" data-ph-ar="اكتب اسمك" data-ph-en="Your name" placeholder="ناوت بنووسە">
        <input class="modal-input" type="tel" id="customerPhone" data-ph-ku="ژمارەی مۆبایل" data-ph-ar="رقم الهاتف" data-ph-en="Phone number" placeholder="ژمارەی مۆبایل">
        <input class="modal-input" type="text" id="modalProductName" readonly>
        <input class="modal-input" type="text" id="modalProductPrice" readonly>
        <div class="modal-actions">
            <button class="modal-cancel" onclick="closeModal()" data-ku="هەڵوەشاندنەوە" data-ar="إلغاء" data-en="Cancel">هەڵوەشاندنەوە</button>
            <button class="modal-send" onclick="sendWhatsApp()">
                <i class="fab fa-whatsapp"></i>
                <span data-ku="ناردن" data-ar="إرسال" data-en="Send">ناردن</span>
            </button>
        </div>
    </div>
</div>

<script>
    // ╔══════════════════════════════════════════════════════════╗
    // ║  لێرە لینکی داونلۆدی هەر بەرنامەیەک دابنێ                           ║
    // ║  تەنها بەهای "link" بگۆڕە بۆ لینکی ڕاستەقینەی خۆت       ║
    // ╚══════════════════════════════════════════════════════════╝
    const products = {
        websites: [
            {
                name_ku: "وێبسایتی فرۆشگا",
                name_ar: "موقع متجر",
                name_en: "Store Website",
                desc_ku: "وێبسایتی فرۆشگا بە سیستەمی کڕین و فرۆشتنی تەواو",
                desc_ar: "موقع متجر بنظام شراء وبيع كامل",
                desc_en: "Full e-commerce store website",
                price: "١٥٠,٠٠٠ دینار",
                price_en: "150,000 IQD",
                img: "https://picsum.photos/seed/store-web/400/300.jpg"
            },
            {
                name_ku: "وێبسایتی کۆمپانیا",
                name_ar: "موقع شركة",
                name_en: "Company Website",
                desc_ku: "وێبسایتی فەرمی بۆ کۆمپانیا و دامەزراوەکان",
                desc_ar: "موقع رسمي للشركات والمؤسسات",
                desc_en: "Official website for companies",
                price: "١٢٠,٠٠٠ دینار",
                price_en: "120,000 IQD",
                img: "https://picsum.photos/seed/company-web/400/300.jpg"
            },
            {
                name_ku: "وێبسایتی بلۆگ",
                name_ar: "موقع مدونة",
                name_en: "Blog Website",
                desc_ku: "بلۆگی تایبەت بە بابەت و وتارەکانت",
                desc_ar: "مدونة مخصصة لمواضيعك ومقالاتك",
                desc_en: "Personal blog for articles",
                price: "٨٠,٠٠٠ دینار",
                price_en: "80,000 IQD",
                img: "https://picsum.photos/seed/blog-web/400/300.jpg"
            },
            {
                name_ku: "لانادینگ پەیج",
                name_ar: "صفحة هبوط",
                name_en: "Landing Page",
                desc_ku: "پەیجی تایبەت بۆ بازاڕکردن و ئاشناکردن",
                desc_ar: "صفحة مخصصة للتسويق والتعريف",
                desc_en: "Marketing landing page",
                price: "٥٠,٠٠٠ دینار",
                price_en: "50,000 IQD",
                img: "https://picsum.photos/seed/landing-web/400/300.jpg"
            },
            {
                name_ku: "وێبسایتی پانێل",
                name_ar: "موقع لوحة تحكم",
                name_en: "Dashboard Website",
                desc_ku: "وێبسایت بە پانێلی کارەبایی و ئەدمین",
                desc_ar: "موقع بلوحة تحكم إلكترونية",
                desc_en: "Website with admin dashboard",
                price: "٢٠٠,٠٠٠ دینار",
                price_en: "200,000 IQD",
                img: "https://picsum.photos/seed/dashboard-web/400/300.jpg"
            },
            {
                name_ku: "وێبسایتی فۆرم",
                name_ar: "موقع نموذج",
                name_en: "Form Website",
                desc_ku: "وێبسایت بۆ پڕکردنەوەی فۆرم و تۆمارکردن",
                desc_ar: "موقع لملء النماذج والتسجيل",
                desc_en: "Registration form website",
                price: "٦٠,٠٠٠ دینار",
                price_en: "60,000 IQD",
                img: "https://picsum.photos/seed/form-web/400/300.jpg"
            }
        ],
        ios: [
            {
                name_ku: "بەرنامەی فرۆشگا - IPA",
                name_ar: "تطبيق متجر - IPA",
                name_en: "Store App - IPA",
                desc_ku: "فایلی IPA بۆ فرۆشگا، دەستگیری لە ئایفۆن",
                desc_ar: "ملف IPA للمتجر، يدعم الآيفون",
                desc_en: "IPA file for store, supports iPhone",
                price: "٣٠٠,٠٠٠ دینار",
                price_en: "300,000 IQD",
                img: "https://picsum.photos/seed/ios-store/400/300.jpg",
                badge_ku: "IPA", badge_ar: "IPA", badge_en: "IPA",
                link: "https://example.com/download/ios-store.ipa"
            },
            {
                name_ku: "بەرنامەی داواکاری - IPA",
                name_ar: "تطبيق طلبات - IPA",
                name_en: "Order App - IPA",
                desc_ku: "بەرنامەی داواکاری بە فۆرماتی IPA",
                desc_ar: "تطبيق طلبات بصيغة IPA",
                desc_en: "Order app in IPA format",
                price: "٢٢٠,٠٠٠ دینار",
                price_en: "220,000 IQD",
                img: "https://picsum.photos/seed/ios-order/400/300.jpg",
                badge_ku: "IPA", badge_ar: "IPA", badge_en: "IPA",
                link: "https://example.com/download/ios-order.ipa"
            },
            {
                name_ku: "بەرنامەی فێرکردن - IPA",
                name_ar: "تطبيق تعليمي - IPA",
                name_en: "Education App - IPA",
                desc_ku: "بەرنامەی خوێندن بۆ iOS بە فایلی IPA",
                desc_ar: "تطبيق تعليم لنظام iOS بملف IPA",
                desc_en: "Learning app for iOS in IPA format",
                price: "٢٥٠,٠٠٠ دینار",
                price_en: "250,000 IQD",
                img: "https://picsum.photos/seed/ios-edu/400/300.jpg",
                badge_ku: "IPA", badge_ar: "IPA", badge_en: "IPA",
                link: "https://example.com/download/ios-edu.ipa"
            },
            {
                name_ku: "بەرنامەی تایبەت - IPA",
                name_ar: "تطبيق مخصص - IPA",
                name_en: "Custom App - IPA",
                desc_ku: "هەر بەرنامەیەک بەپێی داواکاری بکە بە IPA",
                desc_ar: "أي تطبيق حسب طلبك بصيغة IPA",
                desc_en: "Any custom app in IPA format",
                price: "٢٠٠,٠٠٠ دینار",
                price_en: "200,000 IQD",
                img: "https://picsum.photos/seed/ios-custom/400/300.jpg",
                badge_ku: "تایبەت", badge_ar: "مخصص", badge_en: "Custom",
                link: "https://example.com/download/ios-custom.ipa"
            }
        ],
        android: [
            {
                name_ku: "بەرنامەی فرۆشگا - APK",
                name_ar: "تطبيق متجر - APK",
                name_en: "Store App - APK",
                desc_ku: "فایلی APK بۆ فرۆشگا، دەستگیری لە هەموو ئامێرەکانی ئەندرۆید",
                desc_ar: "ملف APK للمتجر، يدعم جميع أجهزة أندرويد",
                desc_en: "APK file for store, supports all Android devices",
                price: "٢٥٠,٠٠٠ دینار",
                price_en: "250,000 IQD",
                img: "https://picsum.photos/seed/and-store/400/300.jpg",
                badge_ku: "APK", badge_ar: "APK", badge_en: "APK",
                link: "https://example.com/download/android-store.apk"
            },
            {
                name_ku: "بەرنامەی داواکاری - APK",
                name_ar: "تطبيق طلبات - APK",
                name_en: "Order App - APK",
                desc_ku: "بەرنامەی داواکاری خواردن بە فۆرماتی APK",
                desc_ar: "تطبيق طلبات طعام بصيغة APK",
                desc_en: "Food order app in APK format",
                price: "١٨٠,٠٠٠ دینار",
                price_en: "180,000 IQD",
                img: "https://picsum.photos/seed/and-order/400/300.jpg",
                badge_ku: "APK", badge_ar: "APK", badge_en: "APK",
                link: "https://example.com/download/android-order.apk"
            },
            {
                name_ku: "بەرنامەی فێرکردن - APK",
                name_ar: "تطبيق تعليمي - APK",
                name_en: "Education App - APK",
                desc_ku: "بەرنامەی خوێندن و فێرکردن بۆ ئەندرۆید",
                desc_ar: "تطبيق تعلم وتعليم لأندرويد",
                desc_en: "Learning app for Android",
                price: "٢٠٠,٠٠٠ دینار",
                price_en: "200,000 IQD",
                img: "https://picsum.photos/seed/and-edu/400/300.jpg",
                badge_ku: "APK", badge_ar: "APK", badge_en: "APK",
                link: "https://example.com/download/android-edu.apk"
            },
            {
                name_ku: "بەرنامەی گشتی - APK",
                name_ar: "تطبيق عام - APK",
                name_en: "General App - APK",
                desc_ku: "بەرنامەی گشتی بەپێی داواکاری خۆت",
                desc_ar: "تطبيق عام حسب طلبك",
                desc_en: "Custom general app",
                price: "١٥٠,٠٠٠ دینار",
                price_en: "150,000 IQD",
                img: "https://picsum.photos/seed/and-general/400/300.jpg",
                badge_ku: "APK", badge_ar: "APK", badge_en: "APK",
                link: "https://example.com/download/android-general.apk"
            }
        ],
        appstore: [
            {
                name_ku: "بەرنامەی فرۆشگا - App Store",
                name_ar: "تطبيق متجر - App Store",
                name_en: "Store App - App Store",
                desc_ku: "بەرنامەی فرۆشگا لە App Store بڵاو دەکرێتەوە",
                desc_ar: "تطبيق متجر ينشر على App Store",
                desc_en: "Store app published on App Store",
                price: "٥٠٠,٠٠٠ دینار",
                price_en: "500,000 IQD",
                img: "https://picsum.photos/seed/as-store/400/300.jpg",
                badge_ku: "App Store", badge_ar: "App Store", badge_en: "App Store",
                link: "https://apps.apple.com/app/id0000000000"
            },
            {
                name_ku: "بەرنامەی داواکاری - App Store",
                name_ar: "تطبيق طلبات - App Store",
                name_en: "Order App - App Store",
                desc_ku: "بەرنامەی داواکاری لە App Store بڵاو دەکرێتەوە",
                desc_ar: "تطبيق طلبات ينشر على App Store",
                desc_en: "Order app published on App Store",
                price: "٤٥٠,٠٠٠ دینار",
                price_en: "450,000 IQD",
                img: "https://picsum.photos/seed/as-order/400/300.jpg",
                badge_ku: "App Store", badge_ar: "App Store", badge_en: "App Store",
                link: "https://apps.apple.com/app/id0000000001"
            },
            {
                name_ku: "بەرنامەی فێرکردن - App Store",
                name_ar: "تطبيق تعليمي - App Store",
                name_en: "Education App - App Store",
                desc_ku: "بەرنامەی فێرکردن لە App Store بڵاو دەکرێتەوە",
                desc_ar: "تطبيق تعليمي ينشر على App Store",
                desc_en: "Education app published on App Store",
                price: "٤٨٠,٠٠٠ دینار",
                price_en: "480,000 IQD",
                img: "https://picsum.photos/seed/as-edu/400/300.jpg",
                badge_ku: "App Store", badge_ar: "App Store", badge_en: "App Store",
                link: "https://apps.apple.com/app/id0000000002"
            },
            {
                name_ku: "بەرنامەی تایبەت - App Store",
                name_ar: "تطبيق مخصص - App Store",
                name_en: "Custom App - App Store",
                desc_ku: "هەر بەرنامەیەک لە App Store بڵاو بکرێتەوە",
                desc_ar: "أي تطبيق ينشر على App Store",
                desc_en: "Any app published on App Store",
                price: "٤٠٠,٠٠٠ دینار",
                price_en: "400,000 IQD",
                img: "https://picsum.photos/seed/as-custom/400/300.jpg",
                badge_ku: "تایبەت", badge_ar: "مخصص", badge_en: "Custom",
                link: "https://apps.apple.com/app/id0000000003"
            }
        ],
        snap: [
            {
                name_ku: "سناپ پڵەس - ١ مانگ",
                name_ar: "سناب شات بلس - ١ شهر",
                name_en: "Snapchat Plus - 1 Month",
                desc_ku: "ئابۆنەمانی سناپ پڵەس بۆ ماوەی ١ مانگ",
                desc_ar: "اشتراك سناب شات بلس لمدة شهر واحد",
                desc_en: "Snapchat Plus subscription for 1 month",
                price: ",٥٠٠٠ دینار",
                price_en: "5,000 IQD",
                img: "https://picsum.photos/seed/snap1/400/300.jpg",
                badge_ku: "هەرزان", badge_ar: "رخيص", badge_en: "Cheap"
            },
            {
                name_ku: "سناپ پڵەس - ٣ مانگ",
                name_ar: "سناب شات بلس - ٣ أشهر",
                name_en: "Snapchat Plus - 3 Months",
                desc_ku: "ئابۆنەمانی سناپ پڵەس بۆ ماوەی ٣ مانگ",
                desc_ar: "اشتراك سناب شات بلس لمدة ٣ أشهر",
                desc_en: "Snapchat Plus subscription for 3 months",
                price: "١٠,٠٠٠ دینار",
                price_en: "10,000 IQD",
                img: "https://picsum.photos/seed/snap3/400/300.jpg",
                badge_ku: "پێشنیارکراو", badge_ar: "موصى به", badge_en: "Recommended"
            },
            {
                name_ku: "سناپ پڵەس - ٦ مانگ",
                name_ar: "سناب شات بلس - ٦ أشهر",
                name_en: "Snapchat Plus - 6 Months",
                desc_ku: "ئابۆنەمانی سناپ پڵەس بۆ ماوەی ٦ مانگ",
                desc_ar: "اشتراك سناب شات بلس لمدة ٦ أشهر",
                desc_en: "Snapchat Plus subscription for 6 months",
                price: "١٥,٠٠٠ دینار",
                price_en: "15,000 IQD",
                img: "https://picsum.photos/seed/snap6/400/300.jpg",
                badge_ku: "باشترین نرخ", badge_ar: "أفضل سعر", badge_en: "Best Price"
            },
            {
                name_ku: "سناپ پڵەس - ١٢ مانگ",
                name_ar: "سناب شات بلس - ١٢ شهر",
                name_en: "Snapchat Plus - 12 Months",
                desc_ku: "ئابۆنەمانی سناپ پڵەس بۆ ماوەی ١ ساڵ",
                desc_ar: "اشتراك سناب شات بلس لمدة سنة",
                desc_en: "Snapchat Plus subscription for 1 year",
                price: "٢٠,٠٠٠ دینار",
                price_en: "20,000 IQD",
                img: "https://picsum.photos/seed/snap12/400/300.jpg",
                badge_ku: "یەک ساڵ", badge_ar: "سنة كاملة", badge_en: "1 Year"
            }
        ]
    };

    let currentLang = 'ku';
    let isDark = false;
    let selectedProduct = null;
    let currentAppSub = 'ios';

    // Download text per language
    const downloadText = {
        ku: 'داونلۆد',
        ar: 'تحميل',
        en: 'Download'
    };
    const downloadingText = {
        ku: 'دەستگیریکردن...',
        ar: 'جاري التحميل...',
        en: 'Preparing...'
    };
    const downloadDoneText = {
        ku: 'دەستگیریکرا!',
        ar: 'تم التحميل!',
        en: 'Downloaded!'
    };

    // Render a grid — type: 'whatsapp' or 'download', platform: 'ios'/'android'/'appstore'
    function renderGrid(gridId, category, type, platform) {
        const grid = document.getElementById(gridId);
        if (!grid) return;
        grid.innerHTML = '';

        const items = products[category];
        if (!items || items.length === 0) {
            grid.innerHTML = `<div class="empty-state" style="grid-column:1/-1;"><i class="fas fa-box-open"></i><p data-ku="هیچ ئەپێک نییە" data-ar="لا يوجد تطبيقات" data-en="No apps available">هیچ ئەپێک نییە</p></div>`;
            return;
        }

        items.forEach((product, idx) => {
            const name = product[`name_${currentLang}`];
            const desc = product[`desc_${currentLang}`];
            const price = currentLang === 'en' ? product.price_en : product.price;
            const badge = product[`badge_${currentLang}`];
            const barId = `${category}-bar-${idx}`;
            const btnId = `${category}-btn-${idx}`;

            let buttonHTML = '';
            let badgeClass = '';

            if (type === 'download' && product.link) {
                badgeClass = `badge-${platform}`;
                buttonHTML = `
                    <button class="product-btn btn-download-${platform}" id="${btnId}" onclick="startDownload('${product.link}', '${btnId}', '${barId}', '${platform}')">
                        <i class="fas fa-download"></i>
                        <span>${downloadText[currentLang]}</span>
                    </button>
                    <div class="download-bar" id="${barId}">
                        <div class="download-bar-inner bar-${platform}"></div>
                    </div>
                `;
            } else {
                buttonHTML = `
                    <button class="product-btn" onclick='openModal(${JSON.stringify({
                        name: product.name_ku,
                        price: product.price
                    }).replace(/'/g, "&#39;")})'>
                        <i class="fab fa-whatsapp"></i>
                        <span data-ku="کڕین" data-ar="شراء" data-en="Buy">کڕین</span>
                    </button>
                `;
            }

            const card = document.createElement('div');
            card.className = 'product-card';
            card.innerHTML = `
                <img src="${product.img}" alt="${name}" class="product-img" loading="lazy">
                <div class="product-info">
                    ${badge ? `<div class="badge ${badgeClass}">${badge}</div>` : ''}
                    <div class="product-name">${name}</div>
                    <div class="product-desc">${desc}</div>
                    <div class="product-price">${price}</div>
                    ${buttonHTML}
                </div>
            `;
            grid.appendChild(card);
        });
    }

    // Animated download function
    function startDownload(link, btnId, barId, platform) {
        const btn = document.getElementById(btnId);
        const bar = document.getElementById(barId);
        const barInner = bar.querySelector('.download-bar-inner');
        const btnSpan = btn.querySelector('span');
        const btnIcon = btn.querySelector('i');

        // Disable button
        btn.disabled = true;
        btn.style.opacity = '0.7';
        btnIcon.className = 'fas fa-circle-notch fa-spin';
        btnSpan.textContent = downloadingText[currentLang];
        bar.classList.add('active');

        // Animate progress bar
        let progress = 0;
        const interval = setInterval(() => {
            progress += Math.random() * 15 + 5;
            if (progress >= 100) {
                progress = 100;
                clearInterval(interval);

                barInner.style.width = '100%';

                setTimeout(() => {
                    // Show done toast
                    showDownloadToast(platform);

                    // Reset button
                    btnIcon.className = 'fas fa-check-circle';
                    btnSpan.textContent = downloadDoneText[currentLang];
                    btn.style.opacity = '1';

                    // Actually open/download the link
                    window.open(link, '_blank');

                    // Reset after 2 seconds
                    setTimeout(() => {
                        btn.disabled = false;
                        btnIcon.className = 'fas fa-download';
                        btnSpan.textContent = downloadText[currentLang];
                        bar.classList.remove('active');
                        barInner.style.width = '0%';
                    }, 2000);
                }, 300);
            } else {
                barInner.style.width = progress + '%';
            }
        }, 120);
    }

    // Download toast
    function showDownloadToast(platform) {
        const toast = document.getElementById('downloadToast');
        const icon = toast.querySelector('i');
        const msg = document.getElementById('downloadToastMsg');

        icon.className = 'fas fa-check-circle dt-' + platform;

        const msgs = {
            ios: { ku: 'فایلی IPA دەستگیریکرا!', ar: 'تم تحميل ملف IPA!', en: 'IPA file downloaded!' },
            android: { ku: 'فایلی APK دەستگیریکرا!', ar: 'تم تحميل ملف APK!', en: 'APK file downloaded!' },
            appstore: { ku: 'ڕێنماییکرا بۆ App Store!', ar: 'تم توجيهك إلى App Store!', en: 'Redirected to App Store!' }
        };
        msg.textContent = msgs[platform][currentLang];

        toast.classList.add('show');
        setTimeout(() => toast.classList.remove('show'), 2500);
    }

    // Render all products
    function renderProducts() {
        renderGrid('websitesGrid', 'websites', 'whatsapp', null);
        renderGrid('iosGrid', 'ios', 'download', 'ios');
        renderGrid('androidGrid', 'android', 'download', 'android');
        renderGrid('appstoreGrid', 'appstore', 'download', 'appstore');
        renderGrid('snapGrid', 'snap', 'whatsapp', null);

        document.getElementById('ios-count').textContent = products.ios.length;
        document.getElementById('android-count').textContent = products.android.length;
        document.getElementById('appstore-count').textContent = products.appstore.length;

        applyTranslations();
    }

    // App sub-tab switching
    function switchAppSub(sub) {
        currentAppSub = sub;
        document.querySelectorAll('.app-subtab').forEach(btn => btn.classList.remove('active'));
        document.getElementById(`subtab-${sub}`).classList.add('active');
        document.querySelectorAll('.app-subcontent').forEach(c => c.classList.remove('active'));
        document.getElementById(`subcontent-${sub}`).classList.add('active');
    }

    // Tab switching
    function switchTab(tabId) {
        document.querySelectorAll('.tab-content').forEach(t => t.classList.remove('active'));
        document.querySelectorAll('.nav-item').forEach(n => n.classList.remove('active'));
        document.getElementById(tabId).classList.add('active');
        document.querySelector(`.nav-item[data-tab="${tabId}"]`).classList.add('active');
        window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    // Theme toggle
    function toggleTheme() {
        isDark = !isDark;
        document.body.classList.toggle('dark-mode', isDark);
        const btn = document.getElementById('themeBtn');
        btn.innerHTML = isDark ? '<i class="fas fa-sun"></i>' : '<i class="fas fa-moon"></i>';
        btn.classList.toggle('active-ctrl', isDark);
    }

    // Language change
    function changeLang(lang) {
        currentLang = lang;
        if (lang === 'ar') {
            document.documentElement.lang = 'ar';
            document.documentElement.dir = 'rtl';
            document.body.classList.remove('english-mode');
            document.body.classList.remove('arabic-mode');
            document.body.classList.add('arabic-mode');
        } else if (lang === 'en') {
            document.documentElement.lang = 'en';
            document.documentElement.dir = 'ltr';
            document.body.classList.remove('arabic-mode');
            document.body.classList.add('english-mode');
        } else {
            document.documentElement.lang = 'ku';
            document.documentElement.dir = 'rtl';
            document.body.classList.remove('english-mode');
            document.body.classList.remove('arabic-mode');
        }
        applyTranslations();
        renderProducts();
        updatePlaceholders();
    }

    function applyTranslations() {
        document.querySelectorAll('[data-ku]').forEach(el => {
            const text = el.getAttribute(`data-${currentLang}`);
            if (text) el.textContent = text;
        });
    }

    function updatePlaceholders() {
        document.querySelectorAll('[data-ph-ku]').forEach(el => {
            el.placeholder = el.getAttribute(`data-ph-${currentLang}`);
        });
    }

    // WhatsApp Modal (only for websites & snap)
    function openModal(product) {
        selectedProduct = product;
        document.getElementById('modalProductName').value = product.name;
        document.getElementById('modalProductPrice').value = product.price;
        document.getElementById('whatsappModal').classList.add('show');
        document.body.style.overflow = 'hidden';
    }

    function closeModal() {
        document.getElementById('whatsappModal').classList.remove('show');
        document.body.style.overflow = '';
        document.getElementById('customerName').value = '';
        document.getElementById('customerPhone').value = '';
        selectedProduct = null;
    }

    function sendWhatsApp() {
        const name = document.getElementById('customerName').value.trim();
        const phone = document.getElementById('customerPhone').value.trim();

        if (!name) {
            showToast(currentLang === 'ku' ? 'تکایە ناوەکەت بنووسە' : currentLang === 'ar' ? 'الرجاء كتابة اسمك' : 'Please enter your name');
            return;
        }
        if (!phone) {
            showToast(currentLang === 'ku' ? 'تکایە ژمارەی مۆبایل بنووسە' : currentLang === 'ar' ? 'الرجاء كتابة رقم هاتفك' : 'Please enter your phone number');
            return;
        }

        const messages = {
            ku: `*سەید ٤ دیجیتاڵ*\n\n🔸 *ناوی کڕیار:* ${name}\n🔸 *ژمارەی مۆبایل:* ${phone}\n🔸 *ناوی کاڵا:* ${selectedProduct.name}\n🔸 *نرخی کاڵا:* ${selectedProduct.price}\n\n_تکایە ئەم وەسڵە لایخۆت بهێڵەوە `,
            ar: `*سيد ٤ الرقمي*\n\n🔸 *اسم العميل:* ${name}\n🔸 *رقم الهاتف:* ${phone}\n🔸 *اسم المنتج:* ${selectedProduct.name}\n🔸 *سعر المنتج:* ${selectedProduct.price}\n\n_الرجاء الرد على هذا الطلب_`,
            en: `*SAYD 4 DIGITAL*\n\n🔸 *Customer Name:* ${name}\n🔸 *Phone:* ${phone}\n🔸 *Product:* ${selectedProduct.name}\n🔸 *Price:* ${selectedProduct.price}\n\n_Please respond to this order_`
        };

        const message = encodeURIComponent(messages[currentLang]);
        const whatsappNumber = '9647505850338';
        window.open(`https://wa.me/${whatsappNumber}?text=${message}`, '_blank');

        closeModal();
        showToast(currentLang === 'ku' ? 'ڕاستەوخۆ بۆ واتساپ نێردرا' : currentLang === 'ar' ? 'تم الإرسال لواتساب' : 'Sent to WhatsApp');
    }

    // Toast
    function showToast(msg) {
        const toast = document.getElementById('toast');
        document.getElementById('toastMsg').textContent = msg;
        toast.classList.add('show');
        setTimeout(() => toast.classList.remove('show'), 3000);
    }

    // Close modal on overlay click
    document.getElementById('whatsappModal').addEventListener('click', function(e) {
        if (e.target === this) closeModal();
    });

    // Keyboard escape
    document.addEventListener('keydown', function(e) {
        if (e.key === 'Escape') closeModal();
    });

    // Init
    renderProducts();
    updatePlaceholders();
</script>

</body>
</html>
