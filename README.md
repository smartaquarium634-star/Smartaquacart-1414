<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SMART AQUA CART - Premium Fishes & Accessories</title>
    <meta name="description" content="Premium Quality Fishes and Their Accessories in Karad, Satara, Maharashtra.">
    <meta property="og:title" content="SMART AQUA CART">
    <meta property="og:description" content="Premium Quality Fishes and Their Accessories.">
    <meta property="og:type" content="website">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --primary-bg: #030a16;
            --surface-glass: rgba(10, 25, 47, 0.7);
            --surface-glass-accent: rgba(0, 242, 254, 0.05);
            --border-glass: rgba(0, 242, 254, 0.15);
            --accent-aqua: #00f2fe;
            --accent-emerald: #4facfe;
            --text-main: #f8fafc;
            --text-muted: #94a3b8;
            --card-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
            --font-main: 'Plus Jakarta Sans', sans-serif;
            --transition-speed: 0.3s;
        }

        [data-theme="light"] {
            --primary-bg: #f0f4f8;
            --surface-glass: rgba(255, 255, 255, 0.75);
            --surface-glass-accent: rgba(0, 114, 255, 0.05);
            --border-glass: rgba(0, 114, 255, 0.15);
            --accent-aqua: #0052d4;
            --accent-emerald: #4364f7;
            --text-main: #0f172a;
            --text-muted: #475569;
            --card-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.08);
        }

        [data-theme="premium-black"] {
            --primary-bg: #050505;
            --surface-glass: rgba(18, 18, 18, 0.8);
            --surface-glass-accent: rgba(212, 175, 55, 0.05);
            --border-glass: rgba(212, 175, 55, 0.2);
            --accent-aqua: #d4af37;
            --accent-emerald: #aa7c11;
            --text-main: #f5f5f7;
            --text-muted: #86868b;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: var(--font-main);
            -webkit-font-smoothing: antialiased;
        }

        body {
            background-color: var(--primary-bg);
            color: var(--text-main);
            overflow-x: hidden;
            transition: background-color var(--transition-speed) ease, color var(--transition-speed) ease;
        }

        /* 3D Simulation Background */
        #aquarium-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: -1;
            pointer-events: none;
        }

        /* App Shell Layout */
        .glass-panel {
            background: var(--surface-glass);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid var(--border-glass);
        }

        /* Header Navigation */
        header {
            position: sticky;
            top: 0;
            z-index: 100;
            width: 100%;
            padding: 1rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
        }

        .logo-container {
            display: flex;
            flex-direction: column;
            cursor: pointer;
            user-select: none;
        }

        .logo-text {
            font-size: 1.5rem;
            font-weight: 800;
            letter-spacing: 1px;
            background: linear-gradient(45deg, var(--accent-aqua), var(--accent-emerald));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .logo-tagline {
            font-size: 0.7rem;
            color: var(--text-muted);
            text-transform: uppercase;
            font-weight: 600;
        }

        .nav-actions {
            display: flex;
            align-items: center;
            gap: 1.5rem;
        }

        .icon-btn {
            background: transparent;
            border: none;
            color: var(--text-main);
            font-size: 1.3rem;
            cursor: pointer;
            position: relative;
            padding: 0.5rem;
            border-radius: 50%;
            transition: transform 0.2s;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .icon-btn:hover {
            transform: scale(1.1);
            background: var(--surface-glass-accent);
        }

        .badge {
            position: absolute;
            top: -2px;
            right: -2px;
            background: linear-gradient(135deg, var(--accent-aqua), var(--accent-emerald));
            color: #fff;
            font-size: 0.7rem;
            font-weight: 700;
            width: 18px;
            height: 18px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        /* Hero Banner */
        .hero {
            padding: 6rem 5% 4rem 5%;
            text-align: center;
            position: relative;
            overflow: hidden;
            background-size: cover;
            background-position: center;
            margin-bottom: 2rem;
            border-bottom: 1px solid var(--border-glass);
        }

        .hero-overlay {
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background: radial-gradient(circle, transparent 20%, var(--primary-bg) 90%);
            z-index: 1;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 800px;
            margin: 0 auto;
        }

        .hero-title {
            font-size: 3rem;
            font-weight: 800;
            margin-bottom: 1rem;
            line-height: 1.2;
        }

        .hero-subtitle {
            font-size: 1.2rem;
            color: var(--text-muted);
            margin-bottom: 2rem;
        }

        .cta-btn {
            padding: 0.8rem 2rem;
            border-radius: 50px;
            border: none;
            background: linear-gradient(45deg, var(--accent-aqua), var(--accent-emerald));
            color: white;
            font-weight: 700;
            cursor: pointer;
            transition: transform var(--transition-speed), box-shadow var(--transition-speed);
            text-decoration: none;
            display: inline-block;
            box-shadow: 0 4px 15px rgba(0, 242, 254, 0.3);
        }

        .cta-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(0, 242, 254, 0.5);
        }

        /* Main Store Front Container */
        .store-container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 2rem 5rem 2rem;
        }

        /* Filter Tabs */
        .filter-section {
            margin-bottom: 2.5rem;
        }

        .search-bar-wrapper {
            max-width: 500px;
            margin: 0 auto 2rem auto;
            position: relative;
        }

        .search-input {
            width: 100%;
            padding: 0.8rem 1.5rem;
            border-radius: 30px;
            border: 1px solid var(--border-glass);
            background: var(--surface-glass);
            color: var(--text-main);
            font-size: 1rem;
            outline: none;
            transition: all var(--transition-speed);
        }

        .search-input:focus {
            border-color: var(--accent-aqua);
            box-shadow: 0 0 15px rgba(0, 242, 254, 0.2);
        }

        .category-scroll {
            display: flex;
            gap: 0.75rem;
            overflow-x: auto;
            padding: 0.5rem 0.25rem;
            scrollbar-width: none;
            justify-content: center;
        }

        .category-scroll::-webkit-scrollbar {
            display: none;
        }

        .cat-chip {
            padding: 0.6rem 1.5rem;
            border-radius: 25px;
            white-space: nowrap;
            cursor: pointer;
            font-weight: 600;
            font-size: 0.9rem;
            transition: all var(--transition-speed);
            border: 1px solid var(--border-glass);
            background: var(--surface-glass);
            color: var(--text-main);
        }

        .cat-chip.active, .cat-chip:hover {
            background: linear-gradient(45deg, var(--accent-aqua), var(--accent-emerald));
            color: #fff;
            border-color: transparent;
            transform: translateY(-2px);
        }

        /* Product Grid */
        .grid-section-title {
            font-size: 1.75rem;
            font-weight: 700;
            margin-bottom: 1.5rem;
            border-left: 4px solid var(--accent-aqua);
            padding-left: 0.75rem;
        }

        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 2rem;
            margin-bottom: 4rem;
        }

        /* Product Cards */
        .product-card {
            border-radius: 20px;
            overflow: hidden;
            transition: transform 0.4s cubic-bezier(0.165, 0.84, 0.44, 1), box-shadow 0.4s;
            display: flex;
            flex-direction: column;
            position: relative;
            height: 100%;
        }

        .product-card:hover {
            transform: translateY(-8px);
            box-shadow: var(--card-shadow);
        }

        .card-img-wrapper {
            width: 100%;
            height: 240px;
            overflow: hidden;
            position: relative;
            background: rgba(0,0,0,0.05);
        }

        .product-img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .product-card:hover .product-img {
            transform: scale(1.08);
        }

        .badge-container {
            position: absolute;
            top: 10px;
            left: 10px;
            display: flex;
            flex-direction: column;
            gap: 5px;
            z-index: 2;
        }

        .status-badge {
            padding: 0.3rem 0.6rem;
            border-radius: 6px;
            font-size: 0.7rem;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            color: #fff;
        }

        .badge-featured { background: #e11d48; }
        .badge-bestseller { background: #f59e0b; }
        .badge-discount { background: #10b981; }
        .badge-outofstock { background: #64748b; }

        .wishlist-btn {
            position: absolute;
            top: 10px;
            right: 10px;
            z-index: 2;
            background: rgba(255,255,255,0.2);
            backdrop-filter: blur(4px);
            border: none;
            width: 34px;
            height: 34px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            color: #fff;
            transition: all 0.2s;
        }

        .wishlist-btn.active {
            color: #e11d48;
            background: rgba(255,255,255,0.9);
        }

        .card-body {
            padding: 1.25rem;
            display: flex;
            flex-direction: column;
            flex-grow: 1;
        }

        .product-cat {
            font-size: 0.75rem;
            text-transform: uppercase;
            color: var(--text-muted);
            font-weight: 700;
            letter-spacing: 0.5px;
            margin-bottom: 0.25rem;
        }

        .product-title {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            line-height: 1.4;
            cursor: pointer;
        }

        .product-title:hover {
            color: var(--accent-aqua);
        }

        .price-row {
            display: flex;
            align-items: baseline;
            gap: 0.5rem;
            margin-top: auto;
            margin-bottom: 1rem;
        }

        .current-price {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--text-main);
        }

        .original-price {
            font-size: 0.9rem;
            text-decoration: line-through;
            color: var(--text-muted);
        }

        .action-btn-group {
            display: grid;
            grid-template-columns: 1fr;
            gap: 0.5rem;
        }

        .add-cart-btn {
            width: 100%;
            padding: 0.7rem;
            border-radius: 12px;
            border: none;
            background: var(--surface-glass-accent);
            border: 1px solid var(--border-glass);
            color: var(--text-main);
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
        }

        .add-cart-btn:hover:not(:disabled) {
            background: linear-gradient(45deg, var(--accent-aqua), var(--accent-emerald));
            color: white;
            border-color: transparent;
        }

        .add-cart-btn:disabled {
            opacity: 0.5;
            cursor: not-allowed;
        }

        /* Modals and Side Drawers Framework */
        .drawer-overlay {
            position: fixed;
            top: 0; left: 0; width: 100vw; height: 100vh;
            background: rgba(0, 0, 0, 0.6);
            backdrop-filter: blur(4px);
            z-index: 1000;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.3s ease;
        }

        .drawer-overlay.active {
            opacity: 1;
            pointer-events: auto;
        }

        .side-drawer {
            position: fixed;
            top: 0; right: -450px; width: 100%; max-width: 450px; height: 100vh;
            z-index: 1001;
            box-shadow: -10px 0 30px rgba(0,0,0,0.5);
            transition: right 0.3s cubic-bezier(0.165, 0.84, 0.44, 1);
            display: flex;
            flex-direction: column;
        }

        .side-drawer.active {
            right: 0;
        }

        .drawer-header {
            padding: 1.5rem;
            border-bottom: 1px solid var(--border-glass);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .drawer-title {
            font-size: 1.25rem;
            font-weight: 700;
        }

        .drawer-body {
            flex-grow: 1;
            overflow-y: auto;
            padding: 1.5rem;
        }

        .drawer-footer {
            padding: 1.5rem;
            border-top: 1px solid var(--border-glass);
        }

        /* Cart Specific UX Elements */
        .cart-item {
            display: flex;
            gap: 1rem;
            margin-bottom: 1.25rem;
            padding-bottom: 1.25rem;
            border-bottom: 1px solid var(--border-glass);
        }

        .cart-item-img {
            width: 70px; height: 70px; border-radius: 10px; object-fit: cover;
        }

        .cart-item-details {
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .cart-item-title {
            font-size: 0.95rem;
            font-weight: 600;
            margin-bottom: 0.25rem;
        }

        .cart-item-price {
            font-size: 0.9rem;
            font-weight: 700;
            color: var(--accent-aqua);
        }

        .qty-controls {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            margin-top: 0.5rem;
        }

        .qty-btn {
            width: 26px; height: 26px; border-radius: 6px; border: 1px solid var(--border-glass);
            background: transparent; color: var(--text-main); cursor: pointer;
            display: flex; align-items: center; justify-content: center; font-weight: bold;
        }

        .qty-val { font-size: 0.9rem; font-weight: 600; min-width: 20px; text-align: center; }

        .remove-item-btn {
            background: transparent; border: none; color: #ef4444; font-size: 0.8rem;
            cursor: pointer; margin-left: auto; margin-top: 0.5rem; font-weight: 500;
        }

        .cart-summary-row {
            display: flex; justify-content: space-between; margin-bottom: 0.75rem; font-weight: 500;
        }

        .cart-total-row {
            display: flex; justify-content: space-between; font-size: 1.2rem; font-weight: 800;
            margin-top: 0.5rem; margin-bottom: 1.5rem; border-top: 1px dashed var(--border-glass);
            padding-top: 0.75rem;
        }

        /* Input Elements */
        .form-group {
            margin-bottom: 1rem;
        }

        .form-group label {
            display: block; font-size: 0.85rem; font-weight: 600; margin-bottom: 0.4rem; color: var(--text-muted);
        }

        .form-control {
            width: 100%; padding: 0.75rem 1rem; border-radius: 10px; border: 1px solid var(--border-glass);
            background: rgba(0,0,0,0.1); color: var(--text-main); font-size: 0.95rem; outline: none;
        }

        .form-control:focus { border-color: var(--accent-aqua); }

        /* Quick View Modal & Admin Dashboard Modal Overrides */
        .center-modal {
            position: fixed;
            top: 50%; left: 50%; transform: translate(-50%, -50%) scale(0.9);
            width: 90%; max-width: 800px; max-height: 85vh;
            z-index: 1050; border-radius: 24px;
            display: flex; flex-direction: column;
            opacity: 0; pointer-events: none;
            transition: all 0.3s cubic-bezier(0.165, 0.84, 0.44, 1);
            overflow: hidden;
        }

        .center-modal.active {
            opacity: 1; pointer-events: auto; transform: translate(-50%, -50%) scale(1);
        }

        .modal-body {
            overflow-y: auto; padding: 2rem; flex-grow: 1;
        }

        /* Admin UI System Configuration */
        .admin-grid {
            display: grid; grid-template-columns: 240px 1fr; gap: 1.5rem; height: 100%; min-height: 500px;
        }

        .admin-sidebar {
            border-right: 1px solid var(--border-glass); padding-right: 1rem;
            display: flex; flex-direction: column; gap: 0.5rem;
        }

        .admin-tab-btn {
            width: 100%; padding: 0.75rem 1rem; text-align: left; border-radius: 10px;
            background: transparent; border: none; color: var(--text-muted); font-weight: 600;
            cursor: pointer; transition: all 0.2s;
        }

        .admin-tab-btn.active, .admin-tab-btn:hover {
            background: var(--surface-glass-accent); color: var(--accent-aqua);
        }

        .admin-panel-content {
            display: none; height: 100%; overflow-y: auto;
        }

        .admin-panel-content.active { display: block; }

        .table-wrapper {
            width: 100%; overflow-x: auto; margin-top: 1rem; border-radius: 12px; border: 1px solid var(--border-glass);
        }

        table {
            width: 100%; border-collapse: collapse; text-align: left; font-size: 0.9rem;
        }

        th, td { padding: 0.75rem 1rem; border-bottom: 1px solid var(--border-glass); }
        th { background: rgba(0,0,0,0.2); font-weight: 600; color: var(--text-muted); }

        .admin-action-inline {
            display: flex; gap: 0.5rem;
        }

        .btn-sm { padding: 0.3rem 0.6rem; font-size: 0.75rem; border-radius: 6px; cursor: pointer; font-weight: 600;}
        .btn-danger { background: #ef4444; color: white; border: none;}
        .btn-primary { background: var(--accent-aqua); color: #000; border: none;}

        /* Floatation Control Utilities */
        .floating-actions {
            position: fixed; bottom: 25px; right: 25px; display: flex; flex-direction: column; gap: 12px; z-index: 99;
        }

        .float-btn {
            width: 52px; height: 52px; border-radius: 50%; display: flex; align-items: center; justify-content: center;
            color: #fff; font-size: 1.5rem; box-shadow: 0 4px 15px rgba(0,0,0,0.3); cursor: pointer; transition: transform 0.2s;
            text-decoration: none; border: none;
        }

        .float-btn:hover { transform: scale(1.1) translateY(-3px); }
        .float-wa { background: #25d366; }
        .float-call { background: #3b82f6; }
        .float-top { background: var(--surface-glass); color: var(--text-main); border: 1px solid var(--border-glass); display: none; }

        /* Toast Engine */
        .toast-container {
            position: fixed; bottom: 30px; left: 30px; display: flex; flex-direction: column; gap: 10px; z-index: 2000;
        }

        .toast-msg {
            padding: 0.8rem 1.5rem; border-radius: 10px; background: #0f172a; color: #fff; font-weight: 600; font-size: 0.9rem;
            box-shadow: 0 4px 12px rgba(0,0,0,0.3); border-left: 4px solid var(--accent-aqua);
            transform: translateX(-120%); animation: slideIn 0.3s forwards;
        }

        /* Structural Informational Sections */
        .info-section { margin-bottom: 5rem; }
        .section-grid-3 { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 2rem; }
        .info-card { padding: 2rem; border-radius: 20px; text-align: center; }
        .info-card-icon { font-size: 2.5rem; margin-bottom: 1rem; color: var(--accent-aqua); }

        /* Accordion UX Pattern */
        .faq-item { border-radius: 12px; border: 1px solid var(--border-glass); margin-bottom: 0.75rem; overflow: hidden; }
        .faq-trigger { width: 100%; padding: 1.2rem; text-align: left; background: transparent; border: none; color: var(--text-main); font-weight: 600; font-size: 1rem; cursor: pointer; display: flex; justify-content: space-between; align-items: center; }
        .faq-content { padding: 0 1.2rem; max-height: 0; overflow: hidden; transition: max-height var(--transition-speed), padding var(--transition-speed); color: var(--text-muted); font-size: 0.95rem; }
        .faq-item.active .faq-content { padding-bottom: 1.2rem; max-height: 200px; }

        /* Quick View Structure */
        .qv-layout { display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; }
        .qv-img-frame { width: 100%; height: 350px; border-radius: 16px; overflow: hidden; }
        .qv-img-frame img { width: 100%; height: 100%; object-fit: cover; }

        footer {
            border-top: 1px solid var(--border-glass); padding: 4rem 5% 2rem 5%; font-size: 0.9rem; color: var(--text-muted);
        }
        .footer-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 2.5rem; margin-bottom: 3rem; }
        .footer-col h4 { color: var(--text-main); font-weight: 700; margin-bottom: 1.2rem; text-transform: uppercase; font-size: 0.85rem; letter-spacing: 0.5px; }
        .footer-col p, .footer-col a { color: var(--text-muted); text-decoration: none; line-height: 1.8; display: block; margin-bottom: 0.5rem; }

        /* Skeleton States */
        .skeleton { background: linear-gradient(90deg, rgba(255,255,255,0.05) 25%, rgba(255,255,255,0.1) 37%, rgba(255,255,255,0.05) 63%); background-size: 400% 100%; animation: skeleton-loading 1.4s ease infinite; }
        @keyframes skeleton-loading { 0% { background-position: 100% 50%; } 100% { background-position: 0% 50%; } }

        @keyframes slideIn { to { transform: translateX(0); } }

        @media(max-width: 768px) {
            .admin-grid { grid-template-columns: 1fr; }
            .admin-sidebar { border-right: none; border-bottom: 1px solid var(--border-glass); padding-bottom: 1rem; flex-direction: row; overflow-x: auto; }
            .qv-layout { grid-template-columns: 1fr; }
            .qv-img-frame { height: 250px; }
            .hero-title { font-size: 2.2rem; }
            .store-container { padding: 0 1rem 4rem 1rem; }
        }
    </style>
</head>
<body>

    <canvas id="aquarium-canvas"></canvas>

    <header class="glass-panel">
        <div class="logo-container" id="app-logo-trigger">
            <span class="logo-text" id="runtime-shop-name">SMART AQUA CART</span>
            <span class="logo-tagline" id="runtime-shop-tagline">PREMIUM QUALITY FISHES AND THEIR ACCESSORIES</span>
        </div>
        <div class="nav-actions">
            <button class="icon-btn" id="theme-switcher" title="Toggle Theme">🌓</button>
            <button class="icon-btn" id="admin-launcher" title="Admin Configuration">⚙</button>
            <button class="icon-btn" id="wishlist-launcher" title="Wishlist View">❤️<span class="badge" id="wishlist-counter">0</span></button>
            <button class="icon-btn" id="cart-launcher" title="Open Shopping Cart">🛒<span class="badge" id="cart-counter">0</span></button>
        </div>
    </header>

    <section class="hero" id="hero-banner-context">
        <div class="hero-overlay"></div>
        <div class="hero-content">
            <h1 class="hero-title">Experience the Deep, Premium Luxury</h1>
            <p class="hero-subtitle">Transform your physical spaces with beautiful aquatic life environments and high-performance structural systems.</p>
            <button class="cta-btn" onclick="document.getElementById('storefront-anchor').scrollIntoView({behavior: 'smooth'});">Browse Inventory</button>
        </div>
    </section>

    <main class="store-container" id="storefront-anchor">
        
        <div class="filter-section">
            <div class="search-bar-wrapper">
                <input type="text" class="search-input" id="global-search" placeholder="Search premium items...">
            </div>
            <div class="category-scroll" id="dynamic-category-chips">
                </div>
        </div>

        <div id="featured-showcase-wrapper" style="display:none;">
            <h3 class="grid-section-title">⭐ Curated Highlights</h3>
            <div class="product-grid" id="featured-products-grid"></div>
        </div>

        <h3 class="grid-section-title">📦 Master Catalog</h3>
        <div class="product-grid" id="master-catalog-grid">
            </div>

        <section class="info-section">
            <h3 class="grid-section-title">⚓ Core Value Propositions</h3>
            <div class="section-grid-3">
                <div class="info-card glass-panel">
                    <div class="info-card-icon">💎</div>
                    <h4>Premium Pedigree</h4>
                    <p style="color: var(--text-muted); margin-top:0.5rem; font-size:0.9rem;">Strict quarantine regimes and premium global accessory tracking ensure optimal biological integrity.</p>
                </div>
                <div class="info-card glass-panel">
                    <div class="info-card-icon">⚡</div>
                    <h4>Zero Cost Logistics</h4>
                    <p style="color: var(--text-muted); margin-top:0.5rem; font-size:0.9rem;">Direct peer-to-peer secure matching ensures premium verification cycles without structural middle-layer markups.</p>
                </div>
                <div class="info-card glass-panel">
                    <div class="info-card-icon">🛡️</div>
                    <h4>Expert Support</h4>
                    <p style="color: var(--text-muted); margin-top:0.5rem; font-size:0.9rem;">Complete technical support for complex high-volume filtration architectures and structural aquascaping layouts.</p>
                </div>
            </div>
        </section>

        <section class="info-section">
            <h3 class="grid-section-title">❓ Operational Protocols FAQ</h3>
            <div id="faq-injection-container">
                <div class="faq-item glass-panel">
                    <button class="faq-trigger"><span>How do I process fulfillment confirmations?</span><span>➕</span></button>
                    <div class="faq-content"><p>Orders compiled on this client interface compile structurally via automated webhook matrices directly to administrative triage channels. Payment tracking runs safe processing variables at delivery execution intervals.</p></div>
                </div>
                <div class="faq-item glass-panel">
                    <button class="faq-trigger"><span>What delivery architectures are mapped within Maharashtra?</span><span>➕</span></button>
                    <div class="faq-content"><p>Localized optimization matrices service Satara regional distributions via rapid transport configurations, safeguarding fragile live ecological items from structural environment changes.</p></div>
                </div>
            </div>
        </section>

    </main>

    <div class="drawer-overlay" id="global-overlay-curtain"></div>

    <div class="side-drawer glass-panel" id="cart-drawer-shell">
        <div class="drawer-header">
            <h3 class="drawer-title">Shopping Manifest</h3>
            <button class="icon-btn" onclick="ui.toggleCart(false)">❌</button>
        </div>
        <div class="drawer-body" id="cart-items-box-target">
            </div>
        <div class="drawer-footer">
            <div class="cart-summary-row"><span>Line items</span><span id="cart-summary-subtotal">₹0</span></div>
            <div class="cart-total-row"><span>Aggregate Total</span><span id="cart-summary-total">₹0</span></div>
            <button class="cta-btn" style="width:100%; text-align:center;" onclick="ui.showCheckout()">Proceed to Checkout Securely</button>
        </div>
    </div>

    <div class="center-modal glass-panel" id="checkout-modal-shell">
        <div class="drawer-header">
            <h3 class="drawer-title">Fulfillment Architecture Verification</h3>
            <button class="icon-btn" onclick="ui.closeCheckout()">❌</button>
        </div>
        <div class="modal-body">
            <form id="checkout-form-engine">
                <div class="form-group">
                    <label>Client Identification / Name</label>
                    <input type="text" class="form-control" id="cust-name" required placeholder="John Doe">
                </div>
                <div class="form-group">
                    <label>Secure Contact Line / Mobile Number</label>
                    <input type="tel" class="form-control" id="cust-phone" required placeholder="+91 XXXXX XXXXX">
                </div>
                <div class="form-group">
                    <label>Physical Address Destination</label>
                    <textarea class="form-control" id="cust-address" rows="3" required placeholder="Full shipping coordinates..."></textarea>
                </div>
                <div class="form-group">
                    <label>Fulfillment Notes / Custom Constraints</label>
                    <textarea class="form-control" id="cust-notes" rows="2" placeholder="Specific handling instructions..."></textarea>
                </div>
                
                <input type="hidden" name="_subject" value="New Secure Order Matrix Received - SMART AQUA CART">
                <input type="hidden" name="Order_Summary_Data" id="formspree-payload-buffer">
                
                <button type="submit" class="cta-btn" style="width:100%; margin-top:1rem;">Broadcast Manifest Verification</button>
            </form>
        </div>
    </div>

    <div class="center-modal glass-panel" id="quickview-modal-shell">
        <div class="drawer-header">
            <h3 class="drawer-title" id="qv-title">Product Focus View</h3>
            <button class="icon-btn" onclick="ui.closeQuickView()">❌</button>
        </div>
        <div class="modal-body" id="qv-body-target">
            </div>
    </div>

    <div class="center-modal glass-panel" id="admin-panel-shell" style="max-width:1100px; width:95%;">
        <div class="drawer-header">
            <h3 class="drawer-title">🛠️ Structural Control Matrix</h3>
            <button class="icon-btn" onclick="ui.closeAdmin()">❌</button>
        </div>
        <div class="modal-body" style="padding:1rem;">
            <div class="admin-grid">
                <aside class="admin-sidebar">
                    <button class="admin-tab-btn active" onclick="ui.switchAdminTab(event, 'adm-inventory')">Products Matrix</button>
                    <button class="admin-tab-btn" onclick="ui.switchAdminTab(event, 'adm-categories')">Category Matrix</button>
                    <button class="admin-tab-btn" onclick="ui.switchAdminTab(event, 'adm-settings')">System Variables</button>
                    <button class="admin-tab-btn" onclick="ui.switchAdminTab(event, 'adm-data')">Migration Engine</button>
                </aside>
                <div class="admin-main">
                    
                    <div class="admin-panel-content active" id="adm-inventory">
                        <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:1rem;">
                            <h4>Inventory Allocations</h4>
                            <button class="cta-btn btn-sm" onclick="ui.openProductForm()">Instate New Inventory Item</button>
                        </div>
                        <div class="table-wrapper">
                            <table>
                                <thead>
                                    <tr>
                                        <th>Allocation Title</th>
                                        <th>Category Mapping</th>
                                        <th>Value Metrics</th>
                                        <th>System Attributes</th>
                                        <th>Operations</th>
                                    </tr>
                                </thead>
                                <tbody id="adm-table-products-target"></tbody>
                            </table>
                        </div>
                        
                        <div id="product-form-sub-drawer" style="display:none; margin-top:2rem; padding:1.5rem; border-radius:12px; background:rgba(0,0,0,0.2); border:1px solid var(--border-glass);">
                            <h5 id="form-action-mode-indicator" style="margin-bottom:1rem; font-size:1rem;">System Record Operations</h5>
                            <input type="hidden" id="form-p-id">
                            <div style="display:grid; grid-template-columns:1fr 1fr; gap:1rem;">
                                <div class="form-group"><label>Product Identifier Title</label><input type="text" id="form-p-name" class="form-control"></div>
                                <div class="form-group"><label>Category Cluster Matrix</label><select id="form-p-cat" class="form-control"></select></div>
                                <div class="form-group"><label>Baseline Financial Valuation (₹)</label><input type="number" id="form-p-price" class="form-control"></div>
                                <div class="form-group"><label>Target Discount Promotional Pricing (₹)</label><input type="number" id="form-p-offer" class="form-control"></div>
                                <div class="form-group" style="grid-column: span 2;"><label>Source Content Image Matrix Location Link (Hosted URL)</label><input type="text" id="form-p-img" class="form-control"></div>
                                <div class="form-group" style="grid-column: span 2;"><label>Structural Description / Variables Spec Sheet Matrix</label><textarea id="form-p-desc" class="form-control" rows="2"></textarea></div>
                            </div>
                            <div style="margin-top:1rem; display:flex; gap:0.5rem; justify-content:flex-end;">
                                <button class="form-control" style="width:auto; cursor:pointer;" onclick="document.getElementById('product-form-sub-drawer').style.display='none'">Abort</button>
                                <button class="cta-btn" onclick="store.saveProductFromForm()">Commit Record</button>
                            </div>
                        </div>
                    </div>

                    <div class="admin-panel-content" id="adm-categories">
                        <h4>Runtime Category Injection Engine</h4>
                        <div style="display:grid; grid-template-columns: 1fr 200px; gap: 1rem; margin-top: 1rem; margin-bottom: 2rem;">
                            <input type="text" id="new-category-input-field" class="form-control" placeholder="Unique category cluster moniker...">
                            <button class="cta-btn" onclick="store.addNewCategoryRuntime()">Inject Category</button>
                        </div>
                        <div class="table-wrapper">
                            <table>
                                <thead>
                                    <tr>
                                        <th>Dynamic Allocation Registry Cluster Key</th>
                                        <th>Operations Tracking</th>
                                    </tr>
                                </thead>
                                <tbody id="adm-table-categories-target"></tbody>
                            </table>
                        </div>
                    </div>

                    <div class="admin-panel-content" id="adm-settings">
                        <h4>System Core Environment Constants</h4>
                        <div style="display:grid; grid-template-columns:1fr 1fr; gap:1rem; margin-top:1rem;">
                            <div class="form-group"><label>Corporate Entity Title</label><input type="text" id="cfg-shop-name" class="form-control"></div>
                            <div class="form-group"><label>Entity Positioning Signature Line</label><input type="text" id="cfg-shop-tagline" class="form-control"></div>
                            <div class="form-group"><label>Communication Routing Primary Mobile Line</label><input type="text" id="cfg-shop-phone" class="form-control"></div>
                            <div class="form-group"><label>Administrative Interface Forwarding Target Mail</label><input type="email" id="cfg-shop-email" class="form-control"></div>
                            <div class="form-group" style="grid-column:span 2;"><label>Operational Base Coordinates (Address)</label><input type="text" id="cfg-shop-addr" class="form-control"></div>
                            <div class="form-group" style="grid-column:span 2;"><label>Formspree Production Webhook Endpoint Token Routing ID</label><input type="text" id="cfg-formspree-id" class="form-control" placeholder="e.g. xv9vjode"></div>
                        </div>
                        <button class="cta-btn" style="margin-top:1rem;" onclick="store.saveGlobalSettings()">Commit Environment Variables</button>
                    </div>

                    <div class="admin-panel-content" id="adm-data">
                        <h4>System Local Migration Control Parameters</h4>
                        <p style="font-size:0.85rem; color:var(--text-muted); margin-bottom:1.5rem;">Perform bare-metal extraction or restoration sequences on local browser environments.</p>
                        <div style="display:flex; gap:1rem; margin-bottom:2rem;">
                            <button class="cta-btn" onclick="store.exportDataPackage()">Download Local Records Snapshot (.json)</button>
                            <button class="cta-btn" style="background:#0284c7;" onclick="document.getElementById('import-file-broker').click()">Restore Structural Package</button>
                            <input type="file" id="import-file-broker" style="display:none;" onchange="store.importDataPackage(event)">
                        </div>
                        <div style="border-top:1px solid var(--border-glass); padding-top:1.5rem;">
                            <button class="btn-danger" style="padding:0.75rem 1.5rem; border-radius:8px; cursor:pointer; font-weight:700;" onclick="store.hardResetSequence()">Execute Factory Initialization Restructure</button>
                        </div>
                    </div>

                </div>
            </div>
        </div>
    </div>

    <div class="floating-actions">
        <button class="float-btn float-top" id="scroll-top-trigger" onclick="window.scrollTo({top:0, behavior:'smooth'});">▲</button>
        <a href="#" class="float-btn float-call" id="float-call-link">📞</a>
        <a href="#" class="float-btn float-wa" id="float-wa-link" target="_blank">💬</a>
    </div>

    <div class="toast-container" id="toast-dock-target"></div>

    <script>
        /*******************************************************************************
         * CORE STATE / DATABASE MANAGEMENT SCHEMAS
         ******************************************************************************/
        const INITIAL_PRODUCTS = [
            { id: "p1", name: "Bluepet Aquarium Powerfilter 6000F", price: 320, offerPrice: null, category: "Filters", img: "https://i.ibb.co/4ZxR9JpS/1782745859148.webp", desc: "High efficiency aquarium sub-surface filtering system designed for optimal aerobic balancing.", status: "In Stock", isFeatured: true, isBestseller: true, order: 1 },
            { id: "p2", name: "Bluepet Aquarium Powerfilter 1000F", price: 350, offerPrice: 320, category: "Filters", img: "https://i.ibb.co/Z6D6DWRM/product-jpeg.jpg", desc: "Robust silent filter stack handling high throughput recirculation cycles gracefully.", status: "In Stock", isFeatured: false, isBestseller: false, order: 2 },
            { id: "p3", name: "Premium sponge filter XF-380", price: 250, offerPrice: null, category: "Filters", img: "https://i.ibb.co/Jjdm4N7b/g-Iz-Ozi-HU.webp", desc: "Maximum surface colonization matrix optimized for fragile specialized biological setups.", status: "In Stock", isFeatured: true, isBestseller: false, order: 3 },
            { id: "p4", name: "Premium Sponge Filter XF-280", price: 200, offerPrice: null, category: "Filters", img: "https://i.ibb.co/dJHDzpLN/71p4-Sso-Vvj-L.jpg", desc: "Mechanical particulate screening mechanism with simple biological extraction attributes.", status: "In Stock", isFeatured: false, isBestseller: false, order: 4 },
            { id: "p5", name: "Aquarium Airpump For fishes", price: 200, offerPrice: null, category: "Filters", img: "https://i.ibb.co/rRgyjSwj/portable-aquarium-air-pump.jpg", desc: "Ultra silent high static displacement air injection apparatus tracking optimal oxygenation metrics.", status: "In Stock", isFeatured: false, isBestseller: false, order: 5 },
            { id: "p6", name: "6 in 1 Biological Sponge", price: 280, offerPrice: 250, category: "Filters", img: "https://i.ibb.co/tPM0vQdL/1683465900149-SKU-0046-0.webp", desc: "Multilayer component structure utilizing micro-porous retention nodes to break down waste parameters.", status: "In Stock", isFeatured: false, isBestseller: true, order: 6 },
            { id: "p7", name: "Best Quality Siphon Pipe", price: 180, offerPrice: null, category: "Filters", img: "https://i.ibb.co/DHPpFDLN/51j0-X8-B5-KQL.jpg", desc: "Heavy-duty manual hydraulic priming component facilitating rapid system cleaning.", status: "In Stock", isFeatured: false, isBestseller: false, order: 7 },
            { id: "p8", name: "Premium Colour Enhancing Royal arowana Food (100gm)", price: 250, offerPrice: null, category: "Fish Food", img: "https://i.ibb.co/HTmSKwCB/71c-OFRBmi-PL.jpg", desc: "High density macro-nutrient dietary complex specifically formulated for high target pigmentation.", status: "In Stock", isFeatured: true, isBestseller: true, order: 8 },
            { id: "p9", name: "Taiyo Turtle Food 250gm", price: 250, offerPrice: null, category: "Turtle Food", img: "https://i.ibb.co/ccnMLzTW/51yv-UMAh-P6-L-AC-UF1000-1000-QL80.jpg", desc: "Perfectly balanced calcium-enriched profile securing shell density and clear optical focus variables.", status: "In Stock", isFeatured: false, isBestseller: false, order: 9 },
            { id: "p10", name: "Tokyo Gold turtle food 500gm", price: 350, offerPrice: 310, category: "Turtle Food", img: "https://i.ibb.co/5Xc9t7DZ/7183b1-K6ah-L.jpg", desc: "Premium high capacity bulk packaging sustaining clean conversion tracking with zero fouling matrices.", status: "In Stock", isFeatured: false, isBestseller: false, order: 10 },
            { id: "p11", name: "Taiyo Pink Fish Food 1kg", price: 550, offerPrice: null, category: "Fish Food", img: "https://i.ibb.co/gbCY2zb9/61-Sf-T-xt-Uo-L.jpg", desc: "Standard community nutritional floating pellet architecture designed for high volume multi-species configurations.", status: "In Stock", isFeatured: false, isBestseller: false, order: 11 },
            { id: "p12", name: "Taiyo Pink Fish Food 500gm", price: 350, offerPrice: null, category: "Fish Food", img: "https://i.ibb.co/ymJx94d5/Taiyo-Pink.png", desc: "Optimized packaging volume sustaining long-term freshness and active nutrient preservation profiles.", status: "In Stock", isFeatured: false, isBestseller: false, order: 12 },
            { id: "p13", name: "Opalfin Premium Quality Ultrafine Fish food (100gm)", price: 120, offerPrice: null, category: "Fish Food", img: "https://i.ibb.co/M53dPDy9/IMG-20260629-214330.jpg", desc: "Micro-milled clean dispersion dust ideal for fry development cycles and surface feeders.", status: "In Stock", isFeatured: false, isBestseller: false, order: 13 },
            { id: "p14", name: "Opalfin Nutrimax Fish Food", price: 100, offerPrice: null, category: "Fish Food", img: "https://i.ibb.co/6Rbdg0JV/IMG-20260629-202101.jpg", desc: "High conversion efficiency dietary component aimed at reducing structural ecological mass accumulation.", status: "In Stock", isFeatured: false, isBestseller: false, order: 14 },
            { id: "p15", name: "Opalfin Xtrabite Fish Food Pellets 100gm (Container)", price: 120, offerPrice: null, category: "Fish Food", img: "https://i.ibb.co/M53dPDy9/IMG-20260629-214330.jpg", desc: "Proteolytic nutrient vector optimizing internal systems structural absorption efficiency tracking indexes.", status: "In Stock", isFeatured: false, isBestseller: false, order: 15 },
            { id: "p16", name: "Opalfin Guppy Plus", price: 150, offerPrice: null, category: "Fish Food", img: "https://i.ibb.co/LDTmp86h/IMG-20260629-202123.jpg", desc: "Tailored micro-granule architecture supplying concentrated multivitamin arrays targeting delicate show grade genetics.", status: "In Stock", isFeatured: false, isBestseller: false, order: 16 },
            { id: "p17", name: "Optimum Premium Fish Food 100gm", price: 80, offerPrice: null, category: "Fish Food", img: "https://i.ibb.co/HDtWZtK8/Untitleddesign-64-fb49fadc-f93d-47f9-ae9c-ccdd929f4e3c.png", desc: "Highly palatable structural daily maintenance option covering major tracking health parameters.", status: "In Stock", isFeatured: false, isBestseller: false, order: 17 }
        ];

        const INITIAL_CATEGORIES = ["All", "Live Fishes", "Fish Food", "Filters", "Air Pumps", "Sponge Filters", "Aquarium Accessories", "Turtle Food", "Aquascaping"];

        const INITIAL_SETTINGS = {
            shopName: "SMART AQUA CART",
            tagline: "PREMIUM QUALITY FISHES AND THEIR ACCESSORIES",
            phone: "7350039389",
            email: "smartaquariumkarad634@gmail.com",
            address: "KARAD, DIST- SATARA, MAHARASHTRA",
            formspreeId: "", // Target webhook parameters mapped on production deployment
            theme: "dark"
        };

        class StoreDatabaseEngine {
            constructor() {
                this.initializeLocalStorageContexts();
            }

            initializeLocalStorageContexts() {
                if(!localStorage.getItem("sac_products")) {
                    localStorage.setItem("sac_products", JSON.stringify(INITIAL_PRODUCTS));
                }
                if(!localStorage.getItem("sac_categories")) {
                    localStorage.setItem("sac_categories", JSON.stringify(INITIAL_CATEGORIES));
                }
                if(!localStorage.getItem("sac_settings")) {
                    localStorage.setItem("sac_settings", JSON.stringify(INITIAL_SETTINGS));
                }
                if(!localStorage.getItem("sac_cart")) {
                    localStorage.setItem("sac_cart", JSON.stringify([]));
                }
                if(!localStorage.getItem("sac_wishlist")) {
                    localStorage.setItem("sac_wishlist", JSON.stringify([]));
                }
            }

            getData(key) { return JSON.parse(localStorage.getItem(`sac_${key}`)); }
            setData(key, data) { localStorage.setItem(`sac_${key}`, JSON.stringify(data)); }

            // System Inventory Manipulation Pipelines
            commitProductMutation(product) {
                let products = this.getData("products");
                const index = products.findIndex(p => p.id === product.id);
                if(index > -1) {
                    products[index] = product;
                    ui.notify(`Updated record: ${product.name}`);
                } else {
                    product.id = "p_" + Date.now();
                    product.order = products.length + 1;
                    products.push(product);
                    ui.notify(`Instated new item: ${product.name}`);
                }
                this.setData("products", products);
                ui.refreshStorefrontView();
            }

            deleteProductRecord(id) {
                let products = this.getData("products");
                products = products.filter(p => p.id !== id);
                this.setData("products", products);
                ui.notify("Item record purged from storage arrays.", "danger");
                ui.refreshStorefrontView();
            }

            shiftProductOrdering(id, axis) {
                let products = this.getData("products");
                const index = products.findIndex(p => p.id === id);
                if(index === -1) return;
                const targetIndex = axis === "up" ? index - 1 : index + 1;
                if(targetIndex < 0 || targetIndex >= products.length) return;
                
                // Swap algorithm sequence
                const temp = products[index];
                products[index] = products[targetIndex];
                products[targetIndex] = temp;
                
                this.setData("products", products);
                ui.refreshStorefrontView();
                ui.hydrateAdminTables();
            }

            addNewCategoryRuntime() {
                const element = document.getElementById("new-category-input-field");
                const token = element.value.trim();
                if(!token) return;
                let cats = this.getData("categories");
                if(cats.includes(token)) { ui.notify("Category exists.", "danger"); return; }
                cats.push(token);
                this.setData("categories", cats);
                element.value = "";
                ui.notify(`Injected cluster: ${token}`);
                ui.refreshStorefrontView();
                ui.hydrateAdminTables();
            }

            purgeCategoryRuntime(token) {
                if(token === "All") return;
                let cats = this.getData("categories");
                cats = cats.filter(c => c !== token);
                this.setData("categories", cats);
                ui.notify("Category cluster purged.", "danger");
                ui.refreshStorefrontView();
                ui.hydrateAdminTables();
            }

            saveGlobalSettings() {
                const cfg = {
                    shopName: document.getElementById("cfg-shop-name").value,
                    tagline: document.getElementById("cfg-shop-tagline").value,
                    phone: document.getElementById("cfg-shop-phone").value,
                    email: document.getElementById("cfg-shop-email").value,
                    address: document.getElementById("cfg-shop-addr").value,
                    formspreeId: document.getElementById("cfg-formspree-id").value,
                    theme: this.getData("settings").theme
                };
                this.setData("settings", cfg);
                ui.applyConfigurationEnvironment();
                ui.notify("Core ecosystem settings updated.");
            }

            exportDataPackage() {
                const bundle = {
                    products: this.getData("products"),
                    categories: this.getData("categories"),
                    settings: this.getData("settings")
                };
                const blob = new Blob([JSON.stringify(bundle, null, 2)], {type : 'application/json'});
                const link = document.createElement('a');
                link.href = URL.createObjectURL(blob);
                link.download = `smart_aqua_cart_backup_${Date.now()}.json`;
                link.click();
            }

            importDataPackage(e) {
                const reader = new FileReader();
                reader.onload = (event) => {
                    try {
                        const parsed = JSON.parse(event.target.result);
                        if(parsed.products && parsed.categories && parsed.settings) {
                            this.setData("products", parsed.products);
                            this.setData("categories", parsed.categories);
                            this.setData("settings", parsed.settings);
                            ui.applyConfigurationEnvironment();
                            ui.refreshStorefrontView();
                            ui.notify("System configuration state fully restored.");
                            ui.closeAdmin();
                        } else { ui.notify("Invalid file schema integrity.", "danger"); }
                    } catch(err) { ui.notify("Structural file processing error.", "danger"); }
                };
                reader.readAsText(e.target.files[0]);
            }

            hardResetSequence() {
                if(confirm("Confirm catastrophic erase? This clears all system overrides and local mutations permanently.")) {
                    localStorage.clear();
                    this.initializeLocalStorageContexts();
                    window.location.reload();
                }
            }
        }

        /*******************************************************************************
         * UX RENDERING INTERFACE / DOM MATRIX INTERFACES
         ******************************************************************************/
        class UserInterfaceController {
            constructor() {
                this.activeCategory = "All";
                this.searchToken = "";
            }

            init() {
                this.applyConfigurationEnvironment();
                this.bindInterfaceEvents();
                this.refreshStorefrontView();
            }

            applyConfigurationEnvironment() {
                const settings = store.getData("settings");
                document.getElementById("runtime-shop-name").innerText = settings.shopName;
                document.getElementById("runtime-shop-tagline").innerText = settings.tagline;
                document.getElementById("float-call-link").href = `tel:${settings.phone}`;
                document.getElementById("float-wa-link").href = `https://wa.me/91${settings.phone}`;
                document.body.setAttribute("data-theme", settings.theme || "dark");
            }

            bindInterfaceEvents() {
                // Tracking Administrative Security Triggers
                let logoPressTimer;
                const logo = document.getElementById("app-logo-trigger");
                logo.addEventListener("mousedown", () => { logoPressTimer = setTimeout(() => this.promptSecurityChallenge(), 3000); });
                logo.addEventListener("mouseup", () => clearTimeout(logoPressTimer));
                logo.addEventListener("touchstart", () => { logoPressTimer = setTimeout(() => this.promptSecurityChallenge(), 3000); });
                logo.addEventListener("touchend", () => clearTimeout(logoPressTimer));

                document.getElementById("admin-launcher").addEventListener("click", () => this.promptSecurityChallenge());
                document.getElementById("cart-launcher").addEventListener("click", () => this.toggleCart(true));
                document.getElementById("global-overlay-curtain").addEventListener("click", () => this.dismissAllOverlays());
                
                document.getElementById("global-search").addEventListener("input", (e) => {
                    this.searchToken = e.target.value.toLowerCase();
                    this.renderCatalogGrid();
                });

                document.getElementById("theme-switcher").addEventListener("click", () => {
                    let settings = store.getData("settings");
                    const sequence = ["dark", "light", "premium-black"];
                    let next = sequence[(sequence.indexOf(settings.theme) + 1) % sequence.length];
                    settings.theme = next;
                    store.setData("settings", settings);
                    this.applyConfigurationEnvironment();
                    this.notify(`Ecosystem visual theme switched to [${next.toUpperCase()}]`);
                });

                // Scroll monitoring for floating structures
                window.addEventListener("scroll", () => {
                    const btn = document.getElementById("scroll-top-trigger");
                    if(window.scrollY > 400) btn.style.display = "flex";
                    else btn.style.display = "none";
                });

                // Set up checkout delivery engine interception hook
                document.getElementById("checkout-form-engine").addEventListener("submit", (e) => this.interceptOrderSubmission(e));
                
                // Initialize programmatic setup variables for FAQ triggers
                document.querySelectorAll(".faq-trigger").forEach(trig => {
                    trig.addEventListener("click", () => {
                        const parent = trig.parentElement;
                        parent.classList.toggle("active");
                        trig.querySelector("span:last-child").innerText = parent.classList.contains("active") ? "➖" : "➕";
                    });
                });
            }

            notify(msg, status = "success") {
                const dock = document.getElementById("toast-dock-target");
                const element = document.createElement("div");
                element.className = "toast-msg";
                if(status === "danger") element.style.borderLeftColor = "#ef4444";
                element.innerText = msg;
                dock.appendChild(element);
                setTimeout(() => { element.style.animation = "none"; element.remove(); }, 4000);
            }

            promptSecurityChallenge() {
                const challenge = prompt("Access Key Required for System Controls Override:");
                if(challenge === "smartaquarium123") {
                    this.openAdminPanel();
                } else if(challenge !== null) {
                    this.notify("Authorization Failure Token Match Unsuccessful.", "danger");
                }
            }

            toggleCart(open) {
                const drawer = document.getElementById("cart-drawer-shell");
                const overlay = document.getElementById("global-overlay-curtain");
                if(open) {
                    this.hydrateCartView();
                    drawer.classList.add("active");
                    overlay.classList.add("active");
                } else {
                    drawer.classList.remove("active");
                    overlay.classList.remove("active");
                }
            }

            dismissAllOverlays() {
                this.toggleCart(false);
                document.getElementById("checkout-modal-shell").classList.remove("active");
                document.getElementById("quickview-modal-shell").classList.remove("active");
                this.closeAdmin();
                document.getElementById("global-overlay-curtain").classList.remove("active");
            }

            refreshStorefrontView() {
                this.renderCategoryChips();
                this.renderCatalogGrid();
                this.updateGlobalBadgeMetrics();
            }

            renderCategoryChips() {
                const container = document.getElementById("dynamic-category-chips");
                const categories = store.getData("categories");
                container.innerHTML = categories.map(cat => `
                    <div class="cat-chip ${this.activeCategory === cat ? 'active' : ''}" onclick="ui.setCategoryFilter('${cat}')">${cat}</div>
                `).join('');
            }

            setCategoryFilter(cat) {
                this.activeCategory = cat;
                this.renderCategoryChips();
                this.renderCatalogGrid();
            }

            renderCatalogGrid() {
                const masterGrid = document.getElementById("master-catalog-grid");
                const featuredGrid = document.getElementById("featured-products-grid");
                const featuredWrapper = document.getElementById("featured-showcase-wrapper");
                
                const products = store.getData("products");
                const wishlist = store.getData("wishlist");

                // Execute evaluation filters
                let filtered = products.filter(p => {
                    const matchesCategory = (this.activeCategory === "All" || p.category === this.activeCategory);
                    const matchesSearch = p.name.toLowerCase().includes(this.searchToken);
                    return matchesCategory && matchesSearch;
                });

                // Process standard sorting algorithms mapped via admin control array vectors
                filtered.sort((a,b) => (a.order || 0) - (b.order || 0));

                const compiledCardHtml = (p) => {
                    const displayPrice = p.offerPrice ? p.offerPrice : p.price;
                    const hasDiscount = !!p.offerPrice;
                    const isWished = wishlist.includes(p.id);
                    const isOutOfStock = p.status === "Out of Stock";

                    return `
                        <div class="product-card glass-panel">
                            <div class="card-img-wrapper">
                                <div class="badge-container">
                                    ${p.isFeatured ? '<span class="status-badge badge-featured">Featured</span>' : ''}
                                    ${p.isBestseller ? '<span class="status-badge badge-bestseller">🔥 Best Seller</span>' : ''}
                                    ${hasDiscount ? `<span class="status-badge badge-discount">-${Math.round(((p.price - p.offerPrice)/p.price)*100)}%</span>` : ''}
                                    ${isOutOfStock ? '<span class="status-badge badge-outofstock">Out of Stock</span>' : ''}
                                </div>
                                <button class="wishlist-btn ${isWished ? 'active' : ''}" onclick="ui.toggleWishlist('${p.id}')">❤️</button>
                                <img src="${p.img}" alt="${p.name}" class="product-img" loading="lazy" onclick="ui.openQuickView('${p.id}')">
                            </div>
                            <div class="card-body">
                                <span class="product-cat">${p.category}</span>
                                <h4 class="product-title" onclick="ui.openQuickView('${p.id}')">${p.name}</h4>
                                <div class="price-row">
                                    <span class="current-price">₹${displayPrice}</span>
                                    ${hasDiscount ? `<span class="original-price">₹${p.price}</span>` : ''}
                                </div>
                                <div class="action-btn-group">
                                    <button class="add-cart-btn" ${isOutOfStock ? 'disabled' : ''} onclick="ui.addToCartExecute('${p.id}')">
                                        ${isOutOfStock ? 'Unavailable' : '⚡ Allocation Package to Cart'}
                                    </button>
                                </div>
                            </div>
                        </div>
                    `;
                };

                masterGrid.innerHTML = filtered.length ? filtered.map(p => compiledCardHtml(p)).join('') : '<p style="padding:2rem; color:var(--text-muted);">No operational inventory tracked inside filter context vectors.</p>';

                // Process Rendering Requirements for structural featured showcases
                let targetFeatured = products.filter(p => p.isFeatured);
                if(targetFeatured.length && this.activeCategory === "All" && !this.searchToken) {
                    featuredWrapper.style.display = "block";
                    featuredGrid.innerHTML = targetFeatured.map(p => compiledCardHtml(p)).join('');
                } else {
                    featuredWrapper.style.display = "none";
                }
            }

            updateGlobalBadgeMetrics() {
                const cart = store.getData("cart");
                const wishlist = store.getData("wishlist");
                
                const cartCount = cart.reduce((acc, item) => acc + item.qty, 0);
                document.getElementById("cart-counter").innerText = cartCount;
                document.getElementById("wishlist-counter").innerText = wishlist.length;
            }

            addToCartExecute(id) {
                let cart = store.getData("cart");
                const index = cart.findIndex(item => item.id === id);
                if(index > -1) {
                    cart[index].qty += 1;
                } else {
                    cart.push({ id: id, qty: 1 });
                }
                store.setData("cart", cart);
                this.updateGlobalBadgeMetrics();
                this.notify("Item allocation units added to cart routing buffer.");
            }

            toggleWishlist(id) {
                let wishlist = store.getData("wishlist");
                if(wishlist.includes(id)) {
                    wishlist = wishlist.filter(item => item !== id);
                    this.notify("Item dropped from active tracking wishlist.", "danger");
                } else {
                    wishlist.push(id);
                    this.notify("Item appended to selective customer monitoring portfolio.");
                }
                store.setData("wishlist", wishlist);
                this.updateGlobalBadgeMetrics();
                this.renderCatalogGrid();
            }

            hydrateCartView() {
                const box = document.getElementById("cart-items-box-target");
                const cart = store.getData("cart");
                const products = store.getData("products");
                
                if(!cart.length) {
                    box.innerHTML = `<p style="color:var(--text-muted); text-align:center; padding:3rem 0;">Shopping queue is empty.</p>`;
                    this.updateCartSummaryMetrics(0);
                    return;
                }

                let operationalTotal = 0;
                box.innerHTML = cart.map(item => {
                    const p = products.find(prod => prod.id === item.id);
                    if(!p) return '';
                    const actualPrice = p.offerPrice ? p.offerPrice : p.price;
                    const lineCost = actualPrice * item.qty;
                    operationalTotal += lineCost;

                    return `
                        <div class="cart-item">
                            <img src="${p.img}" class="cart-item-img" alt="">
                            <div class="cart-item-details">
                                <span class="cart-item-title">${p.name}</span>
                                <span class="cart-item-price">₹${actualPrice}</span>
                                <div class="qty-controls">
                                    <button class="qty-btn" onclick="ui.mutateCartQty('${item.id}', -1)">-</button>
                                    <span class="qty-val">${item.qty}</span>
                                    <button class="qty-btn" onclick="ui.mutateCartQty('${item.id}', 1)">+</button>
                                    <button class="remove-item-btn" onclick="ui.removeCartItem('${item.id}')">Purge</button>
                                </div>
                            </div>
                        </div>
                    `;
                }).join('');

                this.updateCartSummaryMetrics(operationalTotal);
            }

            mutateCartQty(id, delta) {
                let cart = store.getData("cart");
                const index = cart.findIndex(item => item.id === id);
                if(index === -1) return;
                cart[index].qty += delta;
                if(cart[index].qty <= 0) cart = cart.filter(item => item.id !== id);
                store.setData("cart", cart);
                this.hydrateCartView();
                this.updateGlobalBadgeMetrics();
            }

            removeCartItem(id) {
                let cart = store.getData("cart");
                cart = cart.filter(item => item.id !== id);
                store.setData("cart", cart);
                this.hydrateCartView();
                this.updateGlobalBadgeMetrics();
            }

            updateCartSummaryMetrics(total) {
                document.getElementById("cart-summary-subtotal").innerText = `₹${total}`;
                document.getElementById("cart-summary-total").innerText = `₹${total}`;
            }

            showCheckout() {
                const cart = store.getData("cart");
                if(!cart.length) { this.notify("No active elements inside execution stack queue.", "danger"); return; }
                
                // Construct and balance structural hidden form arrays tracking parameters
                const products = store.getData("products");
                let report = "--- SMART AQUA CART ORDER MANIFEST ---\n\n";
                let total = 0;
                
                cart.forEach(item => {
                    const p = products.find(prod => prod.id === item.id);
                    if(p) {
                        const price = p.offerPrice ? p.offerPrice : p.price;
                        report += `Allocation Unit ID: ${p.id}\nItem Moniker: ${p.name}\nQuantity Requested: ${item.qty}\nUnit Base Cost: ₹${price}\nCumulative Pipeline cost: ₹${price * item.qty}\n\n`;
                        total += (price * item.qty);
                    }
                });
                report += `Total Structural Financial Evaluation Assessment: ₹${total}\n`;
                document.getElementById("formspree-payload-buffer").value = report;

                document.getElementById("checkout-modal-shell").classList.add("active");
                document.getElementById("global-overlay-curtain").classList.add("active");
            }

            closeCheckout() {
                document.getElementById("checkout-modal-shell").classList.remove("active");
            }

            interceptOrderSubmission(e) {
                const settings = store.getData("settings");
                if(!settings.formspreeId) {
                    // Fallback to pure client routing if integration endpoints are omitted
                    e.preventDefault();
                    this.executeWhatsAppDirectFallback();
                    return;
                }
                // Construct standard processing hooks
                const form = document.getElementById("checkout-form-engine");
                form.action = `https://formspree.io/f/${settings.formspreeId}`;
                
                // Allow process stream chain to continue execution cleanly
                ui.notify("Formspree payload broadcast executing...");
                setTimeout(() => {
                    store.setData("cart", []);
                    ui.dismissAllOverlays();
                    ui.refreshStorefrontView();
                    alert("Order data structurally broadcast via Formspree. Loading instant confirmation matrix validation via WhatsApp channel.");
                    ui.executeWhatsAppDirectFallback();
                }, 500);
            }

            executeWhatsAppDirectFallback() {
                const settings = store.getData("settings");
                const name = document.getElementById("cust-name").value;
                const phone = document.getElementById("cust-phone").value;
                const addr = document.getElementById("cust-address").value;
                const notes = document.getElementById("cust-notes").value;
                
                let encodedText = encodeURIComponent(`Hello SMART AQUA CART, I am placing an order:\n\nClient: ${name}\nLine: ${phone}\nDestination: ${addr}\nNotes: ${notes}\n\nPayload Summary Configured inside Data Packet Stream Engine.`);
                window.open(`https://wa.me/91${settings.phone}?text=${encodedText}`, '_blank');
            }

            openQuickView(id) {
                const products = store.getData("products");
                const p = products.find(prod => prod.id === id);
                if(!p) return;

                const price = p.offerPrice ? p.offerPrice : p.price;
                const targetModal = document.getElementById("quickview-modal-shell");
                const targetBody = document.getElementById("qv-body-target");

                targetBody.innerHTML = `
                    <div class="qv-layout">
                        <div class="qv-img-frame">
                            <img src="${p.img}" alt="">
                        </div>
                        <div style="display:flex; flex-direction:column; justify-content:center;">
                            <span class="product-cat" style="font-size:0.85rem;">${p.category}</span>
                            <h2 style="margin-bottom:1rem; font-weight:800; font-size:1.6rem;">${p.name}</h2>
                            <p style="color:var(--text-muted); margin-bottom:1.5rem; font-size:0.95rem; line-height:1.6;">${p.desc || 'No further detailed spec sheet variables appended to structural cluster registry.'}</p>
                            <div style="font-size:1.5rem; font-weight:800; margin-bottom:1.5rem; color:var(--accent-aqua)">₹${price}</div>
                            <button class="cta-btn" onclick="ui.addToCartExecute('${p.id}'); ui.closeQuickView();">Inject Allocation Component to Shopping Queue</button>
                        </div>
                    </div>
                `;

                targetModal.classList.add("active");
                document.getElementById("global-overlay-curtain").classList.add("active");
            }

            closeQuickView() { document.getElementById("quickview-modal-shell").classList.remove("active"); }

            /* Administrative Matrix Dashboard Logic Modules */
            openAdminPanel() {
                this.hydrateAdminTables();
                // Hydrate core options systems form contexts
                const settings = store.getData("settings");
                document.getElementById("cfg-shop-name").value = settings.shopName;
                document.getElementById("cfg-shop-tagline").value = settings.tagline;
                document.getElementById("cfg-shop-phone").value = settings.phone;
                document.getElementById("cfg-shop-email").value = settings.email;
                document.getElementById("cfg-shop-addr").value = settings.address;
                document.getElementById("cfg-formspree-id").value = settings.formspreeId || "";

                document.getElementById("admin-panel-shell").classList.add("active");
                document.getElementById("global-overlay-curtain").classList.add("active");
            }

            closeAdmin() { document.getElementById("admin-panel-shell").classList.remove("active"); }

            switchAdminTab(e, targetId) {
                document.querySelectorAll(".admin-tab-btn").forEach(btn => btn.classList.remove("active"));
                document.querySelectorAll(".admin-panel-content").forEach(panel => panel.classList.remove("active"));
                e.target.classList.add("active");
                document.getElementById(targetId).classList.add("active");
            }

            hydrateAdminTables() {
                const products = store.getData("products");
                const categories = store.getData("categories");
                
                // Hydrate table containing programmatic product matrix entities
                const pBody = document.getElementById("adm-table-products-target");
                pBody.innerHTML = products.map(p => `
                    <tr>
                        <td><strong>${p.name}</strong><br><span style="font-size:0.75rem; color:var(--text-muted);">ID: ${p.id}</span></td>
                        <td><span class="cat-chip" style="padding:0.2rem 0.5rem; font-size:0.75rem;">${p.category}</span></td>
                        <td>Base: ₹${p.price}<br><span style="color:var(--accent-aqua)">Promo: ₹${p.offerPrice || '-'}</span></td>
                        <td>
                            <label style="font-size:0.75rem; display:block;"><input type="checkbox" ${p.isFeatured ? 'checked':''} onchange="ui.toggleProductAttribute('${p.id}', 'isFeatured')"> Featured</label>
                            <label style="font-size:0.75rem; display:block;"><input type="checkbox" ${p.isBestseller ? 'checked':''} onchange="ui.toggleProductAttribute('${p.id}', 'isBestseller')"> Bestseller</label>
                            <select style="font-size:0.7rem; background:transparent; color:var(--text-main); margin-top:0.25rem;" onchange="ui.setProductStatus('${p.id}', this.value)">
                                <option value="In Stock" ${p.status === 'In Stock' ? 'selected':''} style="color:#000;">In Stock</option>
                                <option value="Out of Stock" ${p.status === 'Out of Stock' ? 'selected':''} style="color:#000;">Out of Stock</option>
                            </select>
                        </td>
                        <td>
                            <div class="admin-action-inline">
                                <button class="btn-primary btn-sm" onclick="ui.openProductForm('${p.id}')">✏️</button>
                                <button class="btn-danger btn-sm" onclick="store.deleteProductRecord('${p.id}'); ui.hydrateAdminTables();">🗑️</button>
                                <button class="btn-primary btn-sm" onclick="store.shiftProductOrdering('${p.id}','up')">▲</button>
                                <button class="btn-primary btn-sm" onclick="store.shiftProductOrdering('${p.id}','down')">▼</button>
                            </div>
                        </td>
                    </tr>
                `).join('');

                // Hydrate dynamic runtime categories lists tracking arrays
                const cBody = document.getElementById("adm-table-categories-target");
                cBody.innerHTML = categories.map(c => `
                    <tr>
                        <td><strong>${c}</strong></td>
                        <td>
                            ${c !== 'All' ? `<button class="btn-danger btn-sm" onclick="store.purgeCategoryRuntime('${c}')">Purge Segment</button>` : '<span style="font-size:0.75rem; color:var(--text-muted)">Immutable System Core</span>'}
                        </td>
                    </tr>
                `).join('');
            }

            toggleProductAttribute(id, attribute) {
                let products = store.getData("products");
                const index = products.findIndex(p => p.id === id);
                if(index > -1) {
                    products[index][attribute] = !products[index][attribute];
                    store.setData("products", products);
                    this.renderCatalogGrid();
                }
            }

            setProductStatus(id, value) {
                let products = store.getData("products");
                const index = products.findIndex(p => p.id === id);
                if(index > -1) {
                    products[index].status = value;
                    store.setData("products", products);
                    this.renderCatalogGrid();
                    this.notify(`Status set: ${value}`);
                }
            }

            openProductForm(id = null) {
                const pane = document.getElementById("product-form-sub-drawer");
                const select = document.getElementById("form-p-cat");
                const categories = store.getData("categories");
                
                select.innerHTML = categories.filter(c => c !== 'All').map(c => `<option value="${c}">${c}</option>`).join('');
                pane.style.display = "block";

                if(id) {
                    document.getElementById("form-action-mode-indicator").innerText = "Modify Active Structural Record Asset";
                    const p = store.getData("products").find(prod => prod.id === id);
                    document.getElementById("form-p-id").value = p.id;
                    document.getElementById("form-p-name").value = p.name;
                    document.getElementById("form-p-cat").value = p.category;
                    document.getElementById("form-p-price").value = p.price;
                    document.getElementById("form-p-offer").value = p.offerPrice || "";
                    document.getElementById("form-p-img").value = p.img;
                    document.getElementById("form-p-desc").value = p.desc || "";
                } else {
                    document.getElementById("form-action-mode-indicator").innerText = "Instate Fresh Structural Records Asset";
                    document.getElementById("form-p-id").value = "";
                    document.getElementById("form-p-name").value = "";
                    document.getElementById("form-p-price").value = "";
                    document.getElementById("form-p-offer").value = "";
                    document.getElementById("form-p-img").value = "";
                    document.getElementById("form-p-desc").value = "";
                }
            }

            saveProductFromForm() {
                const id = document.getElementById("form-p-id").value;
                const payload = {
                    id: id || null,
                    name: document.getElementById("form-p-name").value,
                    category: document.getElementById("form-p-cat").value,
                    price: parseFloat(document.getElementById("form-p-price").value),
                    offerPrice: parseFloat(document.getElementById("form-p-offer").value) || null,
                    img: document.getElementById("form-p-img").value,
                    desc: document.getElementById("form-p-desc").value,
                    status: "In Stock",
                    isFeatured: false,
                    isBestseller: false
                };

                if(!payload.name || !payload.price || !payload.img) { this.notify("Please fill critical baseline metrics fields.", "danger"); return; }
                
                store.commitProductMutation(payload);
                document.getElementById("product-form-sub-drawer").style.display = "none";
                this.hydrateAdminTables();
            }
        }

        /*******************************************************************************
         * DYNAMIC BACKGROUND KINETIC AQUARIUM FLOW SIMULATION ENGINE
         ******************************************************************************/
        class FluidAquariumSimulationEngine {
            constructor() {
                this.canvas = document.getElementById("aquarium-canvas");
                this.ctx = this.canvas.getContext("2d");
                this.fishCollection = [];
                this.bubbleCollection = [];
                this.resizeCanvasToWindowContext();
                window.addEventListener("resize", () => this.resizeCanvasToWindowContext());
            }

            resizeCanvasToWindowContext() {
                this.canvas.width = window.innerWidth;
                this.canvas.height = window.innerHeight;
            }

            instantiateSimulationMatrices() {
                // Populate distinct animated vector matrices across deep virtual display plane nodes
                for (let i = 0; i < 8; i++) {
                    this.fishCollection.push({
                        x: Math.random() * this.canvas.width,
                        y: Math.random() * this.canvas.height,
                        length: 35 + Math.random() * 45,
                        speed: 0.6 + Math.random() * 1.2,
                        direction: Math.random() > 0.5 ? 1 : -1,
                        verticalPhase: Math.random() * Math.PI * 2,
                        colorBias: `hsl(${180 + Math.random() * 50}, 85%, ${40 + Math.random() * 20}%)`
                    });
                }
                for (let j = 0; j < 40; j++) {
                    this.bubbleCollection.push({
                        x: Math.random() * this.canvas.width,
                        y: this.canvas.height + Math.random() * 300,
                        radius: 1 + Math.random() * 3,
                        ascentRate: 0.4 + Math.random() * 0.9,
                        driftPhase: Math.random() * Math.PI
                    });
                }
            }

            executeFrameStepLoop() {
                // Determine layout configuration context parameters dynamically before clearing mapping space
                const currentTheme = document.body.getAttribute("data-theme") || "dark";
                this.ctx.clearRect(0, 0, this.canvas.width, this.canvas.height);

                // Render Background Depth Gradients based on Active Design Architecture Context
                let depthGrad = this.ctx.createLinearGradient(0, 0, 0, this.canvas.height);
                if (currentTheme === "light") {
                    depthGrad.addColorStop(0, '#e0f2fe');
                    depthGrad.addColorStop(1, '#bae6fd');
                } else if (currentTheme === "premium-black") {
                    depthGrad.addColorStop(0, '#050505');
                    depthGrad.addColorStop(1, '#0c1a24');
                } else {
                    depthGrad.addColorStop(0, '#020617');
                    depthGrad.addColorStop(1, '#072b4a');
                }
                this.ctx.fillStyle = depthGrad;
                this.ctx.fillRect(0, 0, this.canvas.width, this.canvas.height);

                // Dynamic simulation update loop sequence execution
                this.renderBackgroundBubbles();
                this.renderKineticFishEntities();

                requestAnimationFrame(() => this.executeFrameStepLoop());
            }

            renderBackgroundBubbles() {
                this.ctx.fillStyle = "rgba(0, 242, 254, 0.25)";
                this.bubbleCollection.forEach(b => {
                    b.y -= b.ascentRate;
                    b.x += Math.sin(b.driftPhase) * 0.2;
                    b.driftPhase += 0.01;

                    if (b.y < -10) {
                        b.y = this.canvas.height + 20;
                        b.x = Math.random() * this.canvas.width;
                    }

                    this.ctx.beginPath();
                    this.ctx.arc(b.x, b.y, b.radius, 0, Math.PI * 2);
                    this.ctx.fill();
                });
            }

            renderKineticFishEntities() {
                this.fishCollection.forEach(f => {
                    // Kinematics updates mapped directly to absolute pixel structures
                    f.x += f.speed * f.direction;
                    f.verticalPhase += 0.015;
                    f.y += Math.sin(f.verticalPhase) * 0.3;

                    // Bounds handling tracking matrices layout coordinate wraps
                    if (f.direction === 1 && f.x > this.canvas.width + f.length * 2) {
                        f.x = -f.length * 2; f.y = Math.random() * this.canvas.height;
                    } else if (f.direction === -1 && f.x < -f.length * 2) {
                        f.x = this.canvas.width + f.length * 2; f.y = Math.random() * this.canvas.height;
                    }

                    // Render geometry calculations smoothly leveraging native transform pipelines
                    this.ctx.save();
                    this.ctx.translate(f.x, f.y);
                    if (f.direction === -1) { this.ctx.scale(-1, 1); }

                    // Generate smooth fish torso silhouette curves
                    this.ctx.fillStyle = f.colorBias;
                    this.ctx.beginPath();
                    this.ctx.ellipse(0, 0, f.length / 2, f.length / 5, 0, 0, Math.PI * 2);
                    this.ctx.fill();

                    // Generate animated tail component oscillations
                    this.ctx.beginPath();
                    let tailWag = Math.sin(f.verticalPhase * 3) * 6;
                    this.ctx.moveTo(-f.length / 2, 0);
                    this.ctx.lineTo(-f.length * 0.8, -f.length / 4 + tailWag);
                    this.ctx.lineTo(-f.length * 0.8, f.length / 4 + tailWag);
                    this.ctx.closePath();
                    this.ctx.fill();

                    // Render micro glow highlights around focal components
                    this.ctx.fillStyle = "rgba(255,255,255,0.6)";
                    this.ctx.beginPath();
                    this.ctx.arc(f.length / 4, -f.length / 15, 2, 0, Math.PI * 2);
                    this.ctx.fill();

                    this.ctx.restore();
                });
            }
        }

        /*******************************************************************************
         * INSTANTIATION ENGINE LIFECYCLE INITIALIZER ENTRYPOINTS
         ******************************************************************************/
        const store = new StoreDatabaseEngine();
        const ui = new UserInterfaceController();
        const sim = new FluidAquariumSimulationEngine();

        window.addEventListener("DOMContentLoaded", () => {
            ui.init();
            sim.instantiateSimulationMatrices();
            sim.executeFrameStepLoop();
        });
    </script>
</body>
</html> 
