# Edu-Platform
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EduPlatform - المنصة التعليمية المتكاملة</title>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* CSS Variables - Design System */
        :root {
            /* Colors */
            --primary-50: #eff6ff;
            --primary-100: #dbeafe;
            --primary-500: #3b82f6;
            --primary-600: #2563eb;
            --primary-700: #1d4ed8;
            
            --secondary-50: #f0fdf4;
            --secondary-500: #22c55e;
            --secondary-600: #16a34a;
            
            --danger-50: #fef2f2;
            --danger-500: #ef4444;
            --danger-600: #dc2626;
            
            --warning-50: #fffbeb;
            --warning-500: #f59e0b;
            --warning-600: #d97706;
            
            --gray-50: #f9fafb;
            --gray-100: #f3f4f6;
            --gray-200: #e5e7eb;
            --gray-300: #d1d5db;
            --gray-400: #9ca3af;
            --gray-500: #6b7280;
            --gray-600: #4b5563;
            --gray-700: #374151;
            --gray-800: #1f2937;
            --gray-900: #111827;
            
            /* Semantic Colors */
            --bg-primary: white;
            --bg-secondary: var(--gray-50);
            --bg-tertiary: var(--gray-100);
            --text-primary: var(--gray-900);
            --text-secondary: var(--gray-600);
            --text-tertiary: var(--gray-400);
            --border-light: var(--gray-200);
            --border-medium: var(--gray-300);
            
            /* Spacing */
            --space-1: 0.25rem;
            --space-2: 0.5rem;
            --space-3: 0.75rem;
            --space-4: 1rem;
            --space-5: 1.25rem;
            --space-6: 1.5rem;
            --space-8: 2rem;
            --space-10: 2.5rem;
            --space-12: 3rem;
            --space-16: 4rem;
            
            /* Typography */
            --text-xs: 0.75rem;
            --text-sm: 0.875rem;
            --text-base: 1rem;
            --text-lg: 1.125rem;
            --text-xl: 1.25rem;
            --text-2xl: 1.5rem;
            --text-3xl: 1.875rem;
            
            /* Borders */
            --radius-sm: 0.375rem;
            --radius: 0.5rem;
            --radius-md: 0.75rem;
            --radius-lg: 1rem;
            --radius-xl: 1.5rem;
            
            /* Shadows */
            --shadow-sm: 0 1px 2px 0 rgb(0 0 0 / 0.05);
            --shadow: 0 1px 3px 0 rgb(0 0 0 / 0.1), 0 1px 2px -1px rgb(0 0 0 / 0.1);
            --shadow-md: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
            --shadow-lg: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1);
            
            /* Transitions */
            --transition-fast: 150ms ease-in-out;
            --transition-normal: 300ms ease-in-out;
            --transition-slow: 500ms ease-in-out;
            
            /* Z-index */
            --z-dropdown: 1000;
            --z-sticky: 1020;
            --z-fixed: 1030;
            --z-modal: 1040;
            --z-popover: 1050;
            --z-tooltip: 1060;
        }

        /* Dark Theme */
        [data-theme="dark"] {
            --bg-primary: var(--gray-900);
            --bg-secondary: var(--gray-800);
            --bg-tertiary: var(--gray-700);
            --text-primary: white;
            --text-secondary: var(--gray-300);
            --text-tertiary: var(--gray-400);
            --border-light: var(--gray-700);
            --border-medium: var(--gray-600);
        }

        /* High Contrast Theme */
        [data-theme="high-contrast"] {
            --primary-500: #0044cc;
            --secondary-500: #006600;
            --danger-500: #cc0000;
            --bg-primary: white;
            --text-primary: black;
            --border-light: black;
        }

        /* Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Cairo', -apple-system, BlinkMacSystemFont, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            color: var(--text-primary);
            line-height: 1.6;
            transition: background-color var(--transition-normal);
        }

        [data-theme="dark"] body {
            background: linear-gradient(135deg, var(--gray-800) 0%, var(--gray-900) 100%);
        }

        /* Reduced Motion */
        @media (prefers-reduced-motion: reduce) {
            * {
                animation-duration: 0.01ms !important;
                animation-iteration-count: 1 !important;
                transition-duration: 0.01ms !important;
                scroll-behavior: auto !important;
            }
        }

        /* Utility Classes */
        .sr-only {
            position: absolute;
            width: 1px;
            height: 1px;
            padding: 0;
            margin: -1px;
            overflow: hidden;
            clip: rect(0, 0, 0, 0);
            white-space: nowrap;
            border: 0;
        }

        .loading {
            opacity: 0.6;
            pointer-events: none;
        }

        .error-message {
            color: var(--danger-600);
            background: var(--danger-50);
            padding: var(--space-3);
            border-radius: var(--radius);
            border: 1px solid var(--danger-500);
            font-size: var(--text-sm);
            margin-bottom: var(--space-4);
        }

        .success-message {
            color: var(--secondary-600);
            background: var(--secondary-50);
            padding: var(--space-3);
            border-radius: var(--radius);
            border: 1px solid var(--secondary-500);
            font-size: var(--text-sm);
            margin-bottom: var(--space-4);
        }

        .warning-message {
            color: var(--warning-600);
            background: var(--warning-50);
            padding: var(--space-3);
            border-radius: var(--radius);
            border: 1px solid var(--warning-500);
            font-size: var(--text-sm);
            margin-bottom: var(--space-4);
        }

        /* Layout Components */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 var(--space-4);
        }

        .grid {
            display: grid;
            gap: var(--space-6);
        }

        .grid-cols-1 { grid-template-columns: 1fr; }
        .grid-cols-2 { grid-template-columns: repeat(2, 1fr); }
        .grid-cols-3 { grid-template-columns: repeat(3, 1fr); }
        .grid-cols-4 { grid-template-columns: repeat(4, 1fr); }

        @media (max-width: 768px) {
            .grid-cols-2,
            .grid-cols-3,
            .grid-cols-4 {
                grid-template-columns: 1fr;
            }
        }

        .flex {
            display: flex;
        }

        .flex-col {
            flex-direction: column;
        }

        .items-center {
            align-items: center;
        }

        .justify-between {
            justify-content: space-between;
        }

        .gap-2 { gap: var(--space-2); }
        .gap-3 { gap: var(--space-3); }
        .gap-4 { gap: var(--space-4); }
        .gap-6 { gap: var(--space-6); }

        /* Header */
        .header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: var(--radius-lg);
            padding: var(--space-4);
            margin-bottom: var(--space-6);
            box-shadow: var(--shadow-md);
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: var(--space-4);
        }

        [data-theme="dark"] .header {
            background: rgba(31, 41, 55, 0.95);
        }

        .logo {
            display: flex;
            align-items: center;
            gap: var(--space-3);
        }

        .logo h1 {
            font-size: var(--text-2xl);
            color: var(--primary-600);
            font-weight: 700;
        }

        .user-actions {
            display: flex;
            gap: var(--space-3);
            align-items: center;
            flex-wrap: wrap;
        }

        /* Buttons */
        .btn {
            display: inline-flex;
            align-items: center;
            gap: var(--space-2);
            padding: var(--space-3) var(--space-4);
            border: none;
            border-radius: var(--radius);
            font-family: inherit;
            font-size: var(--text-sm);
            font-weight: 600;
            text-decoration: none;
            cursor: pointer;
            transition: all var(--transition-fast);
            position: relative;
            overflow: hidden;
        }

        .btn:disabled {
            opacity: 0.6;
            cursor: not-allowed;
            transform: none !important;
        }

        .btn:focus {
            outline: 2px solid var(--primary-500);
            outline-offset: 2px;
        }

        .btn-primary {
            background: var(--primary-600);
            color: white;
        }

        .btn-primary:hover:not(:disabled) {
            background: var(--primary-700);
            transform: translateY(-1px);
            box-shadow: var(--shadow-md);
        }

        .btn-secondary {
            background: var(--secondary-600);
            color: white;
        }

        .btn-outline {
            background: transparent;
            border: 2px solid var(--primary-600);
            color: var(--primary-600);
        }

        .btn-outline:hover:not(:disabled) {
            background: var(--primary-600);
            color: white;
        }

        .btn-ghost {
            background: transparent;
            color: var(--text-secondary);
        }

        .btn-ghost:hover:not(:disabled) {
            background: var(--bg-tertiary);
            color: var(--text-primary);
        }

        /* Cards */
        .card {
            background: var(--bg-primary);
            border-radius: var(--radius-lg);
            padding: var(--space-6);
            box-shadow: var(--shadow-sm);
            border: 1px solid var(--border-light);
            transition: all var(--transition-normal);
        }

        .card:hover {
            box-shadow: var(--shadow-md);
            transform: translateY(-2px);
        }

        .card-header {
            margin-bottom: var(--space-4);
        }

        .card-title {
            font-size: var(--text-xl);
            font-weight: 700;
            color: var(--text-primary);
            margin-bottom: var(--space-2);
        }

        /* Navigation */
        .nav {
            background: var(--bg-primary);
            border-radius: var(--radius);
            padding: var(--space-3);
            margin-bottom: var(--space-6);
            box-shadow: var(--shadow-sm);
        }

        .nav-links {
            display: flex;
            justify-content: center;
            list-style: none;
            gap: var(--space-2);
            flex-wrap: wrap;
        }

        .nav-link {
            display: flex;
            align-items: center;
            gap: var(--space-2);
            padding: var(--space-3) var(--space-4);
            border-radius: var(--radius);
            text-decoration: none;
            color: var(--text-secondary);
            font-weight: 600;
            transition: all var(--transition-fast);
        }

        .nav-link:hover,
        .nav-link.active {
            background: var(--primary-600);
            color: white;
        }

        /* Forms */
        .form-group {
            margin-bottom: var(--space-4);
        }

        .form-label {
            display: block;
            margin-bottom: var(--space-2);
            font-weight: 600;
            color: var(--text-primary);
        }

        .form-control {
            width: 100%;
            padding: var(--space-3);
            border: 1px solid var(--border-medium);
            border-radius: var(--radius);
            font-family: inherit;
            font-size: var(--text-base);
            transition: all var(--transition-fast);
            background: var(--bg-primary);
            color: var(--text-primary);
        }

        .form-control:focus {
            outline: none;
            border-color: var(--primary-500);
            box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.1);
        }

        .form-control.error {
            border-color: var(--danger-500);
            box-shadow: 0 0 0 3px rgba(239, 68, 68, 0.1);
        }

        .form-hint {
            font-size: var(--text-sm);
            color: var(--text-tertiary);
            margin-top: var(--space-1);
        }

        .form-error {
            font-size: var(--text-sm);
            color: var(--danger-600);
            margin-top: var(--space-1);
        }

        /* Modals */
        .modal {
            position: fixed;
            inset: 0;
            background: rgba(0, 0, 0, 0.5);
            display: flex;
            align-items: center;
            justify-content: center;
            padding: var(--space-4);
            z-index: var(--z-modal);
            opacity: 0;
            visibility: hidden;
            transition: all var(--transition-normal);
        }

        .modal.active {
            opacity: 1;
            visibility: visible;
        }

        .modal-content {
            background: var(--bg-primary);
            border-radius: var(--radius-xl);
            padding: var(--space-6);
            width: 100%;
            max-width: 500px;
            max-height: 90vh;
            overflow-y: auto;
            box-shadow: var(--shadow-lg);
            transform: scale(0.9);
            transition: transform var(--transition-normal);
        }

        .modal.active .modal-content {
            transform: scale(1);
        }

        .modal-header {
            display: flex;
            justify-content: between;
            align-items: center;
            margin-bottom: var(--space-4);
        }

        .modal-title {
            font-size: var(--text-xl);
            font-weight: 700;
        }

        /* Progress */
        .progress-bar {
            width: 100%;
            height: 8px;
            background: var(--border-light);
            border-radius: var(--radius-xl);
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            background: var(--primary-600);
            transition: width var(--transition-slow);
        }

        /* Loading States */
        .skeleton {
            background: linear-gradient(90deg, var(--border-light) 25%, var(--bg-secondary) 50%, var(--border-light) 75%);
            background-size: 200% 100%;
            animation: loading 1.5s infinite;
            border-radius: var(--radius);
        }

        @keyframes loading {
            0% { background-position: 200% 0; }
            100% { background-position: -200% 0; }
        }

        .spinner {
            width: 20px;
            height: 20px;
            border: 2px solid transparent;
            border-top: 2px solid var(--primary-600);
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Notifications */
        .notification {
            position: fixed;
            top: var(--space-4);
            left: var(--space-4);
            right: var(--space-4);
            background: var(--bg-primary);
            border-radius: var(--radius);
            padding: var(--space-4);
            box-shadow: var(--shadow-lg);
            border-left: 4px solid var(--primary-600);
            z-index: var(--z-tooltip);
            transform: translateY(-100px);
            transition: transform var(--transition-normal);
        }

        .notification.show {
            transform: translateY(0);
        }

        .notification.success {
            border-left-color: var(--secondary-600);
        }

        .notification.error {
            border-left-color: var(--danger-600);
        }

        .notification.warning {
            border-left-color: var(--warning-600);
        }

        /* Responsive */
        @media (max-width: 640px) {
            .container {
                padding: 0 var(--space-3);
            }
            
            .header {
                flex-direction: column;
                text-align: center;
            }
            
            .user-actions {
                justify-content: center;
            }
            
            .nav-links {
                flex-direction: column;
            }
        }

        /* Print Styles */
        @media print {
            .header,
            .nav,
            .btn {
                display: none !important;
            }
            
            .card {
                box-shadow: none !important;
                border: 1px solid #000 !important;
            }
        }
    </style>
</head>
<body>
    <!-- Skip Link for Accessibility -->
    <a href="#main-content" class="sr-only">انتقل إلى المحتوى الرئيسي</a>

    <div class="container">
        <!-- Header -->
        <header class="header" role="banner">
            <div class="logo">
                <i class="fas fa-graduation-cap" aria-hidden="true"></i>
                <div>
                    <h1>EduPlatform</h1>
                    <p class="text-secondary">المنصة التعليمية المتكاملة</p>
                </div>
            </div>
            
            <div class="user-actions">
                <button class="btn btn-ghost" onclick="ThemeManager.toggle()" aria-label="تبديل السمة">
                    <i class="fas fa-moon"></i>
                </button>
                <button class="btn btn-ghost" onclick="NotificationManager.showPanel()" aria-label="الإشعارات">
                    <i class="fas fa-bell"></i>
                    <span class="notification-badge" id="notificationCount" aria-live="polite">0</span>
                </button>
                <button class="btn btn-primary" id="loginBtn" onclick="AuthManager.showLogin()">
                    <i class="fas fa-sign-in-alt"></i> تسجيل الدخول
                </button>
                <div class="user-menu" id="userMenu" style="display: none;">
                    <button class="btn btn-ghost" onclick="UserManager.showProfile()">
                        <i class="fas fa-user"></i>
                        <span id="userName"></span>
                    </button>
                    <button class="btn btn-outline" onclick="AuthManager.logout()">
                        <i class="fas fa-sign-out-alt"></i> تسجيل الخروج
                    </button>
                </div>
            </div>
        </header>

        <!-- Navigation -->
        <nav class="nav" role="navigation" aria-label="القائمة الرئيسية">
            <ul class="nav-links">
                <li><a href="#" class="nav-link active" onclick="Router.navigate('home')" aria-current="page">
                    <i class="fas fa-home"></i> الرئيسية
                </a></li>
                <li><a href="#" class="nav-link" onclick="Router.navigate('subjects')">
                    <i class="fas fa-book"></i> المواد الدراسية
                </a></li>
                <li><a href="#" class="nav-link" onclick="Router.navigate('exams')">
                    <i class="fas fa-tasks"></i> الاختبارات
                </a></li>
                <li><a href="#" class="nav-link" onclick="Router.navigate('progress')">
                    <i class="fas fa-chart-line"></i> التقدم
                </a></li>
                <li><a href="#" class="nav-link" onclick="Router.navigate('discussions')">
                    <i class="fas fa-comments"></i> المناقشات
                </a></li>
            </ul>
        </nav>

        <!-- Main Content -->
        <main id="main-content" role="main">
            <div id="app-content">
                <!-- سيتم تحميل المحتوى ديناميكياً هنا -->
            </div>
        </main>
    </div>

    <!-- Modals -->
    <div id="authModal" class="modal" role="dialog" aria-labelledby="authModalTitle" aria-hidden="true">
        <div class="modal-content">
            <div class="modal-header">
                <h2 id="authModalTitle">تسجيل الدخول</h2>
                <button class="btn btn-ghost" onclick="ModalManager.close('authModal')" aria-label="إغلاق">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            <div id="authModalBody">
                <!-- سيتم تحميل نموذج المصادقة هنا -->
            </div>
        </div>
    </div>

    <!-- Notification Container -->
    <div id="notificationContainer"></div>

    <!-- Loading Overlay -->
    <div id="loadingOverlay" class="modal" style="background: rgba(0,0,0,0.8);">
        <div class="modal-content" style="background: transparent; box-shadow: none;">
            <div class="flex flex-col items-center gap-4">
                <div class="spinner" style="width: 40px; height: 40px;"></div>
                <p class="text-primary">جاري التحميل...</p>
            </div>
        </div>
    </div>

    <script>
        // ==================== نظام إدارة التطبيق ====================
        class EduPlatform {
            constructor() {
                this.modules = new Map();
                this.isInitialized = false;
            }

            async initialize() {
                try {
                    await this.loadCoreModules();
                    await this.initializeModules();
                    this.setupErrorHandling();
                    this.isInitialized = true;
                    
                    console.log('✅ تم تهيئة المنصة بنجاح');
                } catch (error) {
                    console.error('❌ فشل تهيئة المنصة:', error);
                    this.handleCriticalError(error);
                }
            }

            async loadCoreModules() {
                const coreModules = [
                    Router,
                    AuthManager,
                    StorageManager,
                    ThemeManager,
                    NotificationManager,
                    ModalManager,
                    ErrorHandler
                ];

                for (const Module of coreModules) {
                    const instance = new Module();
                    this.modules.set(Module.name, instance);
                    await instance.initialize?.();
                }
            }

            async initializeModules() {
                for (const [name, module] of this.modules) {
                    await module.initialize?.();
                }
            }

            setupErrorHandling() {
                window.addEventListener('error', (event) => {
                    this.modules.get('ErrorHandler').handleError(event.error);
                });

                window.addEventListener('unhandledrejection', (event) => {
                    this.modules.get('ErrorHandler').handleError(event.reason);
                });
            }

            handleCriticalError(error) {
                document.getElementById('app-content').innerHTML = `
                    <div class="card">
                        <div class="error-message">
                            <h3>حدث خطأ في التطبيق</h3>
                            <p>نعتذر عن هذا الخطأ. يرجى تحديث الصفحة.</p>
                            <button class="btn btn-primary" onclick="location.reload()">
                                تحديث الصفحة
                            </button>
                        </div>
                    </div>
                `;
            }

            getModule(name) {
                return this.modules.get(name);
            }
        }

        // ==================== نظام التوجيه ====================
        class Router {
            constructor() {
                this.routes = new Map();
                this.currentRoute = null;
                this.middlewares = [];
            }

            initialize() {
                this.defineRoutes();
                this.setupNavigation();
                this.handleInitialRoute();
            }

            defineRoutes() {
                this.routes.set('home', {
                    component: HomePage,
                    title: 'الرئيسية - EduPlatform',
                    requiresAuth: false
                });

                this.routes.set('subjects', {
                    component: SubjectsPage,
                    title: 'المواد الدراسية - EduPlatform',
                    requiresAuth: true
                });

                this.routes.set('exams', {
                    component: ExamsPage,
                    title: 'الاختبارات - EduPlatform',
                    requiresAuth: true
                });

                this.routes.set('progress', {
                    component: ProgressPage,
                    title: 'التقدم - EduPlatform',
                    requiresAuth: true
                });

                this.routes.set('discussions', {
                    component: DiscussionsPage,
                    title: 'المناقشات - EduPlatform',
                    requiresAuth: true
                });
            }

            async navigate(routeName, params = {}) {
                try {
                    const route = this.routes.get(routeName);
                    if (!route) {
                        throw new Error(`الصفحة "${routeName}" غير موجودة`);
                    }

                    // التحقق من المصادقة
                    if (route.requiresAuth && !AuthManager.isAuthenticated()) {
                        AuthManager.showLogin();
                        return;
                    }

                    // تطبيق الوسائط
                    for (const middleware of this.middlewares) {
                        const result = await middleware.beforeNavigate(route, params);
                        if (result === false) return;
                    }

                    // تغيير العنوان
                    document.title = route.title;

                    // تحميل المكون
                    await this.renderRoute(route, params);

                    this.currentRoute = { name: routeName, params };
                    
                    // تحديث التنقل
                    this.updateNavigation(routeName);

                } catch (error) {
                    ErrorHandler.handleError(error, 'Router.navigate');
                }
            }

            async renderRoute(route, params) {
                const appContent = document.getElementById('app-content');
                
                // عرض حالة التحميل
                appContent.innerHTML = this.getLoadingTemplate();

                try {
                    const component = new route.component();
                    const html = await component.render(params);
                    
                    appContent.innerHTML = html;
                    await component.afterRender?.();

                } catch (error) {
                    appContent.innerHTML = this.getErrorTemplate(error);
                }
            }

            getLoadingTemplate() {
                return `
                    <div class="card">
                        <div class="flex flex-col items-center gap-4">
                            <div class="skeleton" style="width: 100px; height: 100px; border-radius: 50%;"></div>
                            <div class="skeleton" style="width: 200px; height: 20px;"></div>
                            <div class="skeleton" style="width: 150px; height: 16px;"></div>
                        </div>
                    </div>
                `;
            }

            getErrorTemplate(error) {
                return `
                    <div class="card">
                        <div class="error-message">
                            <h3>فشل تحميل الصفحة</h3>
                            <p>${error.message}</p>
                            <button class="btn btn-primary" onclick="Router.navigate('home')">
                                العودة للرئيسية
                            </button>
                        </div>
                    </div>
                `;
            }

            updateNavigation(activeRoute) {
                document.querySelectorAll('.nav-link').forEach(link => {
                    link.classList.remove('active');
                    link.setAttribute('aria-current', 'false');
                });

                const activeLink = document.querySelector(`[onclick="Router.navigate('${activeRoute}')"]`);
                if (activeLink) {
                    activeLink.classList.add('active');
                    activeLink.setAttribute('aria-current', 'page');
                }
            }

            setupNavigation() {
                // التعامل مع زر الرجوع في المتصفح
                window.addEventListener('popstate', (event) => {
                    if (event.state && event.state.route) {
                        this.navigate(event.state.route, event.state.params);
                    }
                });
            }

            handleInitialRoute() {
                const urlParams = new URLSearchParams(window.location.search);
                const route = urlParams.get('route') || 'home';
                this.navigate(route);
            }

            addMiddleware(middleware) {
                this.middlewares.push(middleware);
            }
        }

        // ==================== نظام المصادقة المتكامل ====================
        class AuthManager {
            constructor() {
                this.sessionDuration = 24 * 60 * 60 * 1000; // 24 ساعة
                this.refreshThreshold = 5 * 60 * 1000; // 5 دقائق
                this.currentUser = null;
                this.sessionTimer = null;
            }

            initialize() {
                this.loadSession();
                this.setupAutoRefresh();
            }

            async login(credentials) {
                try {
                    // التحقق من البيانات
                    const validation = this.validateCredentials(credentials);
                    if (!validation.isValid) {
                        throw new Error(validation.errors.join('\n'));
                    }

                    // محاكاة طلب المصادقة
                    const user = await this.authenticate(credentials);
                    
                    // إنشاء الجلسة
                    await this.createSession(user);
                    
                    // تحديث الواجهة
                    this.updateUI();
                    
                    NotificationManager.show('تم تسجيل الدخول بنجاح', 'success');
                    
                    return user;

                } catch (error) {
                    ErrorHandler.handleError(error, 'AuthManager.login');
                    throw error;
                }
            }

            async authenticate(credentials) {
                // محاكاة تأخير الشبكة
                await new Promise(resolve => setTimeout(resolve, 1000));

                // حساب المدير
                if (credentials.email === 'ahah00em@gmail.com' && credentials.password === 'A010909090') {
                    return {
                        id: 1,
                        name: 'مدير النظام',
                        email: credentials.email,
                        role: 'admin',
                        permissions: ['*']
                    };
                }

                // محاكاة قاعدة بيانات المستخدمين
                const users = await StorageManager.get('users') || [];
                const user = users.find(u => u.email === credentials.email);
                
                if (!user) {
                    throw new Error('البريد الإلكتروني أو كلمة المرور غير صحيحة');
                }

                const isValid = await SecurityManager.verifyPassword(
                    credentials.password, 
                    user.passwordHash
                );

                if (!isValid) {
                    throw new Error('البريد الإلكتروني أو كلمة المرور غير صحيحة');
                }

                return user;
            }

            validateCredentials(credentials) {
                const errors = [];
                
                if (!SecurityManager.validateEmail(credentials.email)) {
                    errors.push('البريد الإلكتروني غير صالح');
                }
                
                const passwordValidation = SecurityManager.validatePassword(credentials.password);
                if (!passwordValidation.isValid) {
                    errors.push(...passwordValidation.issues);
                }

                return {
                    isValid: errors.length === 0,
                    errors
                };
            }

            async createSession(user) {
                this.currentUser = user;
                
                const session = {
                    user: user,
                    createdAt: new Date().toISOString(),
                    expiresAt: new Date(Date.now() + this.sessionDuration).toISOString(),
                    token: SecurityManager.generateToken()
                };

                await StorageManager.set('session', session);
                this.startSessionTimer();
                
                // إرسال حدث المصادقة
                window.dispatchEvent(new CustomEvent('authChange', { 
                    detail: { user, type: 'login' } 
                }));
            }

            async logout() {
                try {
                    // إرسال حدث تسجيل الخروج
                    window.dispatchEvent(new CustomEvent('authChange', { 
                        detail: { user: this.currentUser, type: 'logout' } 
                    }));

                    this.currentUser = null;
                    this.clearSessionTimer();
                    
                    await StorageManager.remove('session');
                    this.updateUI();
                    
                    NotificationManager.show('تم تسجيل الخروج بنجاح', 'success');
                    
                    // إعادة التوجيه للرئيسية
                    Router.navigate('home');

                } catch (error) {
                    ErrorHandler.handleError(error, 'AuthManager.logout');
                }
            }

            loadSession() {
                try {
                    const session = StorageManager.get('session');
                    if (session && new Date(session.expiresAt) > new Date()) {
                        this.currentUser = session.user;
                        this.startSessionTimer();
                        this.updateUI();
                    } else {
                        this.clearExpiredSession();
                    }
                } catch (error) {
                    this.clearExpiredSession();
                }
            }

            clearExpiredSession() {
                StorageManager.remove('session');
                this.currentUser = null;
                this.updateUI();
            }

            startSessionTimer() {
                this.clearSessionTimer();
                
                this.sessionTimer = setTimeout(() => {
                    this.logout();
                }, this.sessionDuration);
            }

            clearSessionTimer() {
                if (this.sessionTimer) {
                    clearTimeout(this.sessionTimer);
                    this.sessionTimer = null;
                }
            }

            setupAutoRefresh() {
                // تجديد الجلسة تلقائياً قبل انتهائها
                setInterval(() => {
                    if (this.isAuthenticated()) {
                        this.refreshSession();
                    }
                }, this.refreshThreshold);
            }

            async refreshSession() {
                if (this.currentUser) {
                    await this.createSession(this.currentUser);
                }
            }

            isAuthenticated() {
                return this.currentUser !== null;
            }

            hasPermission(permission) {
                if (!this.currentUser) return false;
                if (this.currentUser.permissions?.includes('*')) return true;
                return this.currentUser.permissions?.includes(permission);
            }

            updateUI() {
                const loginBtn = document.getElementById('loginBtn');
                const userMenu = document.getElementById('userMenu');
                const userName = document.getElementById('userName');

                if (this.isAuthenticated()) {
                    loginBtn.style.display = 'none';
                    userMenu.style.display = 'flex';
                    userName.textContent = this.currentUser.name;
                } else {
                    loginBtn.style.display = 'block';
                    userMenu.style.display = 'none';
                }
            }

            async showLogin() {
                const modalBody = document.getElementById('authModalBody');
                modalBody.innerHTML = `
                    <form onsubmit="return AuthManager.handleLoginSubmit(event)">
                        <div class="form-group">
                            <label for="loginEmail" class="form-label">البريد الإلكتروني</label>
                            <input type="email" id="loginEmail" class="form-control" required
                                   placeholder="أدخل بريدك الإلكتروني">
                        </div>
                        
                        <div class="form-group">
                            <label for="loginPassword" class="form-label">كلمة المرور</label>
                            <input type="password" id="loginPassword" class="form-control" required
                                   placeholder="أدخل كلمة المرور">
                        </div>

                        <div class="form-group">
                            <label class="flex items-center gap-2">
                                <input type="checkbox" id="rememberMe">
                                <span>تذكرني</span>
                            </label>
                        </div>

                        <button type="submit" class="btn btn-primary" style="width: 100%;">
                            <span class="btn-text">تسجيل الدخول</span>
                            <div class="spinner" style="display: none;"></div>
                        </button>

                        <div class="text-center mt-4">
                            <a href="#" onclick="AuthManager.showPasswordReset()" class="text-primary">
                                نسيت كلمة المرور؟
                            </a>
                        </div>
                    </form>
                `;

                ModalManager.open('authModal');
            }

            async handleLoginSubmit(event) {
                event.preventDefault();
                
                const form = event.target;
                const submitBtn = form.querySelector('button[type="submit"]');
                const btnText = submitBtn.querySelector('.btn-text');
                const spinner = submitBtn.querySelector('.spinner');

                try {
                    // عرض حالة التحميل
                    btnText.style.display = 'none';
                    spinner.style.display = 'block';
                    submitBtn.disabled = true;

                    const credentials = {
                        email: document.getElementById('loginEmail').value,
                        password: document.getElementById('loginPassword').value,
                        rememberMe: document.getElementById('rememberMe').checked
                    };

                    await this.login(credentials);
                    ModalManager.close('authModal');

                } catch (error) {
                    NotificationManager.show(error.message, 'error');
                } finally {
                    // إعادة تعيين حالة الزر
                    btnText.style.display = 'block';
                    spinner.style.display = 'none';
                    submitBtn.disabled = false;
                }
            }

            async showPasswordReset() {
                const modalBody = document.getElementById('authModalBody');
                modalBody.innerHTML = `
                    <div class="form-group">
                        <label for="resetEmail" class="form-label">البريد الإلكتروني</label>
                        <input type="email" id="resetEmail" class="form-control" 
                               placeholder="أدخل بريدك الإلكتروني">
                        <p class="form-hint">سيتم إرسال رابط إعادة تعيين كلمة المرور إلى بريدك الإلكتروني</p>
                    </div>
                    
                    <button onclick="AuthManager.handlePasswordReset()" class="btn btn-primary" style="width: 100%;">
                        إرسال رابط التعيين
                    </button>
                    
                    <div class="text-center mt-4">
                        <a href="#" onclick="AuthManager.showLogin()" class="text-primary">
                            العودة لتسجيل الدخول
                        </a>
                    </div>
                `;

                document.getElementById('authModalTitle').textContent = 'استعادة كلمة المرور';
            }

            async handlePasswordReset() {
                // تنفيذ استعادة كلمة المرور
                NotificationManager.show('تم إرسال رابط استعادة كلمة المرور إلى بريدك الإلكتروني', 'success');
                this.showLogin();
            }
        }

        // ==================== نظام إدارة التخزين ====================
        class StorageManager {
            static async get(key) {
                try {
                    const item = localStorage.getItem(`eduplatform_${key}`);
                    return item ? JSON.parse(item) : null;
                } catch (error) {
                    console.error('Error reading from storage:', error);
                    return null;
                }
            }

            static async set(key, value) {
                try {
                    localStorage.setItem(`eduplatform_${key}`, JSON.stringify(value));
                    return true;
                } catch (error) {
                    console.error('Error writing to storage:', error);
                    return false;
                }
            }

            static async remove(key) {
                try {
                    localStorage.removeItem(`eduplatform_${key}`);
                    return true;
                } catch (error) {
                    console.error('Error removing from storage:', error);
                    return false;
                }
            }

            static async clear() {
                try {
                    const keys = Object.keys(localStorage).filter(key => 
                        key.startsWith('eduplatform_')
                    );
                    keys.forEach(key => localStorage.removeItem(key));
                    return true;
                } catch (error) {
                    console.error('Error clearing storage:', error);
                    return false;
                }
            }
        }

        // ==================== نظام الأمان ====================
        class SecurityManager {
            static validateEmail(email) {
                const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
                return re.test(email);
            }

            static validatePassword(password) {
                const minLength = 8;
                const hasUpperCase = /[A-Z]/.test(password);
                const hasLowerCase = /[a-z]/.test(password);
                const hasNumbers = /\d/.test(password);
                const hasSpecialChar = /[!@#$%^&*(),.?":{}|<>]/.test(password);
                
                return {
                    isValid: password.length >= minLength && hasUpperCase && hasLowerCase && hasNumbers && hasSpecialChar,
                    issues: [
                        password.length < minLength && `كلمة المرور يجب أن تكون ${minLength} أحرف على الأقل`,
                        !hasUpperCase && 'يجب أن تحتوي على حرف كبير واحد على الأقل',
                        !hasLowerCase && 'يجب أن تحتوي على حرف صغير واحد على الأقل',
                        !hasNumbers && 'يجب أن تحتوي على رقم واحد على الأقل',
                        !hasSpecialChar && 'يجب أن تحتوي على رمز خاص واحد على الأقل'
                    ].filter(Boolean)
                };
            }

            static async hashPassword(password) {
                // في تطبيق حقيقي، نستخدم مكتبة مثل bcrypt
                const encoder = new TextEncoder();
                const data = encoder.encode(password);
                const hash = await crypto.subtle.digest('SHA-256', data);
                return Array.from(new Uint8Array(hash)).map(b => b.toString(16).padStart(2, '0')).join('');
            }

            static async verifyPassword(password, hash) {
                const newHash = await this.hashPassword(password);
                return newHash === hash;
            }

            static generateToken() {
                return 'token_' + Math.random().toString(36).substr(2) + Date.now().toString(36);
            }

            static sanitizeInput(input) {
                const div = document.createElement('div');
                div.textContent = input;
                return div.innerHTML;
            }
        }

        // ==================== نظام الإشعارات ====================
        class NotificationManager {
            constructor() {
                this.notifications = new Map();
                this.maxNotifications = 100;
            }

            initialize() {
                this.cleanupExpired();
                setInterval(() => this.cleanupExpired(), 60 * 1000); // تنظيف كل دقيقة
            }

            static show(message, type = 'info', duration = 5000) {
                const container = document.getElementById('notificationContainer');
                const id = 'notification_' + Date.now();
                
                const notification = document.createElement('div');
                notification.id = id;
                notification.className = `notification ${type}`;
                notification.innerHTML = `
                    <div class="flex justify-between items-start">
                        <div>
                            <strong>${this.getTypeTitle(type)}</strong>
                            <p>${message}</p>
                        </div>
                        <button onclick="NotificationManager.close('${id}')" class="btn btn-ghost" style="padding: 0;">
                            <i class="fas fa-times"></i>
                        </button>
                    </div>
                `;
                
                container.appendChild(notification);
                
                // إظهار الإشعار
                setTimeout(() => notification.classList.add('show'), 100);
                
                // إخفاء تلقائي
                if (duration > 0) {
                    setTimeout(() => this.close(id), duration);
                }
                
                return id;
            }

            static getTypeTitle(type) {
                const titles = {
                    info: 'معلومة',
                    success: 'نجاح',
                    error: 'خطأ',
                    warning: 'تحذير'
                };
                return titles[type] || 'إشعار';
            }

            static close(id) {
                const notification = document.getElementById(id);
                if (notification) {
                    notification.classList.remove('show');
                    setTimeout(() => {
                        if (notification.parentNode) {
                            notification.parentNode.removeChild(notification);
                        }
                    }, 300);
                }
            }

            cleanupExpired() {
                const now = Date.now();
                for (const [id, notification] of this.notifications) {
                    if (notification.expiresAt < now) {
                        this.notifications.delete(id);
                    }
                }
            }

            showPanel() {
                // تنفيذ لوحة الإشعارات
                NotificationManager.show('لوحة الإشعارات قيد التطوير', 'info');
            }
        }

        // ==================== نظام السمات ====================
        class ThemeManager {
            static themes = ['light', 'dark', 'high-contrast'];
            
            static initialize() {
                this.loadTheme();
            }

            static loadTheme() {
                const savedTheme = localStorage.getItem('eduplatform_theme') || 'light';
                this.setTheme(savedTheme);
            }

            static setTheme(themeName) {
                if (!this.themes.includes(themeName)) {
                    themeName = 'light';
                }
                
                document.documentElement.setAttribute('data-theme', themeName);
                localStorage.setItem('eduplatform_theme', themeName);
                
                // إرسال حدث تغيير السمة
                window.dispatchEvent(new CustomEvent('themeChange', { detail: { theme: themeName } }));
            }

            static toggle() {
                const currentTheme = document.documentElement.getAttribute('data-theme') || 'light';
                const currentIndex = this.themes.indexOf(currentTheme);
                const nextIndex = (currentIndex + 1) % this.themes.length;
                this.setTheme(this.themes[nextIndex]);
            }

            static getCurrentTheme() {
                return document.documentElement.getAttribute('data-theme') || 'light';
            }
        }

        // ==================== نظام النوافذ ====================
        class ModalManager {
            static open(modalId) {
                const modal = document.getElementById(modalId);
                if (modal) {
                    modal.classList.add('active');
                    modal.setAttribute('aria-hidden', 'false');
                    
                    // حبس التركيز داخل النافذة
                    this.trapFocus(modal);
                }
            }

            static close(modalId) {
                const modal = document.getElementById(modalId);
                if (modal) {
                    modal.classList.remove('active');
                    modal.setAttribute('aria-hidden', 'true');
                }
            }

            static trapFocus(modal) {
                const focusableElements = modal.querySelectorAll(
                    'button, [href], input, select, textarea, [tabindex]:not([tabindex="-1"])'
                );
                
                if (focusableElements.length === 0) return;

                const firstElement = focusableElements[0];
                const lastElement = focusableElements[focusableElements.length - 1];

                modal.addEventListener('keydown', function handleTab(e) {
                    if (e.key === 'Tab') {
                        if (e.shiftKey) {
                            if (document.activeElement === firstElement) {
                                lastElement.focus();
                                e.preventDefault();
                            }
                        } else {
                            if (document.activeElement === lastElement) {
                                firstElement.focus();
                                e.preventDefault();
                            }
                        }
                    }

                    if (e.key === 'Escape') {
                        ModalManager.close(modal.id);
                    }
                });
            }
        }

        // ==================== نظام معالجة الأخطاء ====================
        class ErrorHandler {
            static handleError(error, context = 'Unknown') {
                console.error(`[${context}]`, error);
                
                // في تطبيق حقيقي، نرسل الخطأ للخادم
                this.reportError(error, context);
                
                // عرض رسالة خطأ مناسبة للمستخدم
                this.showUserFriendlyError(error);
            }

            static reportError(error, context) {
                const errorData = {
                    message: error.message,
                    stack: error.stack,
                    context: context,
                    timestamp: new Date().toISOString(),
                    userAgent: navigator.userAgent,
                    url: window.location.href
                };

                // إرسال الخطأ للخادم (محاكاة)
                console.log('Reporting error:', errorData);
            }

            static showUserFriendlyError(error) {
                let userMessage = 'حدث خطأ غير متوقع. يرجى المحاولة مرة أخرى.';
                
                if (error.message.includes('network') || error.message.includes('Network')) {
                    userMessage = 'حدث خطأ في الاتصال بالشبكة. يرجى التحقق من اتصال الإنترنت.';
                } else if (error.message.includes('auth') || error.message.includes('Auth')) {
                    userMessage = 'حدث خطأ في المصادقة. يرجى تسجيل الدخول مرة أخرى.';
                }

                NotificationManager.show(userMessage, 'error');
            }
        }

        // ==================== المكونات ====================
        class HomePage {
            async render() {
                return `
                    <div class="grid grid-cols-1 gap-6">
                        <div class="card">
                            <div class="card-header">
                                <h2 class="card-title">مرحباً بك في EduPlatform</h2>
                                <p class="text-secondary">منصة تعليمية متكاملة لتجربة تعلم استثنائية</p>
                            </div>
                            
                            <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                                <div class="card">
                                    <i class="fas fa-book fa-2x text-primary mb-3"></i>
                                    <h3 class="text-lg font-semibold mb-2">مواد شاملة</h3>
                                    <p class="text-secondary">محتوى تعليمي متكامل لجميع المواد</p>
                                </div>
                                
                                <div class="card">
                                    <i class="fas fa-tasks fa-2x text-primary mb-3"></i>
                                    <h3 class="text-lg font-semibold mb-2">اختبارات تفاعلية</h3>
                                    <p class="text-secondary">تقييم فوري مع تحليل النتائج</p>
                                </div>
                                
                                <div class="card">
                                    <i class="fas fa-chart-line fa-2x text-primary mb-3"></i>
                                    <h3 class="text-lg font-semibold mb-2">تتبع التقدم</h3>
                                    <p class="text-secondary">مراقبة تطورك الدراسي بشكل مستمر</p>
                                </div>
                            </div>
                        </div>
                    </div>
                `;
            }
        }

        class SubjectsPage {
            async render() {
                return `
                    <div class="card">
                        <div class="card-header">
                            <h2 class="card-title">المواد الدراسية</h2>
                            <p class="text-secondary">اختر المادة التي تريد دراستها</p>
                        </div>
                        
                        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
                            <div class="card">
                                <h3 class="text-lg font-semibold mb-2">الكيمياء</h3>
                                <p class="text-secondary mb-4">علم المواد والتفاعلات الكيميائية</p>
                                <div class="progress-bar">
                                    <div class="progress-fill" style="width: 65%"></div>
                                </div>
                                <p class="text-sm text-secondary mt-2">65% مكتمل</p>
                                <button class="btn btn-primary w-full mt-4">بدء الدراسة</button>
                            </div>
                            
                            <div class="card">
                                <h3 class="text-lg font-semibold mb-2">الفيزياء</h3>
                                <p class="text-secondary mb-4">علم المادة والطاقة والحركة</p>
                                <div class="progress-bar">
                                    <div class="progress-fill" style="width: 30%"></div>
                                </div>
                                <p class="text-sm text-secondary mt-2">30% مكتمل</p>
                                <button class="btn btn-primary w-full mt-4">بدء الدراسة</button>
                            </div>
                            
                            <div class="card">
                                <h3 class="text-lg font-semibold mb-2">الرياضيات</h3>
                                <p class="text-secondary mb-4">علم الأعداد والكميات والأشكال</p>
                                <div class="progress-bar">
                                    <div class="progress-fill" style="width: 80%"></div>
                                </div>
                                <p class="text-sm text-secondary mt-2">80% مكتمل</p>
                                <button class="btn btn-primary w-full mt-4">بدء الدراسة</button>
                            </div>
                        </div>
                    </div>
                `;
            }
        }

        class ExamsPage {
            async render() {
                return `
                    <div class="card">
                        <div class="card-header">
                            <h2 class="card-title">الاختبارات</h2>
                            <p class="text-secondary">اختبر معرفتك وتابع تقدمك</p>
                        </div>
                        
                        <div class="grid grid-cols-1 gap-4">
                            <div class="card">
                                <h3 class="text-lg font-semibold mb-2">اختبار الكيمياء الشامل</h3>
                                <p class="text-secondary mb-2">25 سؤال - 60 دقيقة</p>
                                <p class="text-sm text-secondary">أفضل نتيجة: 85%</p>
                                <button class="btn btn-primary mt-4">بدء الاختبار</button>
                            </div>
                            
                            <div class="card">
                                <h3 class="text-lg font-semibold mb-2">اختبار الفيزياء النهائي</h3>
                                <p class="text-secondary mb-2">30 سؤال - 75 دقيقة</p>
                                <p class="text-sm text-secondary">أفضل نتيجة: 72%</p>
                                <button class="btn btn-primary mt-4">بدء الاختبار</button>
                            </div>
                        </div>
                    </div>
                `;
            }
        }

        class ProgressPage {
            async render() {
                return `
                    <div class="card">
                        <div class="card-header">
                            <h2 class="card-title">التقدم الدراسي</h2>
                            <p class="text-secondary">تابع تطورك في جميع المواد</p>
                        </div>
                        
                        <div class="grid grid-cols-2 md:grid-cols-4 gap-4 mb-6">
                            <div class="card text-center">
                                <div class="text-2xl font-bold text-primary">3</div>
                                <div class="text-sm text-secondary">المواد المكتملة</div>
                            </div>
                            
                            <div class="card text-center">
                                <div class="text-2xl font-bold text-primary">78%</div>
                                <div class="text-sm text-secondary">متوسط النتائج</div>
                            </div>
                            
                            <div class="card text-center">
                                <div class="text-2xl font-bold text-primary">15</div>
                                <div class="text-sm text-secondary">ساعة دراسة</div>
                            </div>
                            
                            <div class="card text-center">
                                <div class="text-2xl font-bold text-primary">2</div>
                                <div class="text-sm text-secondary">الإنجازات</div>
                            </div>
                        </div>
                        
                        <div class="space-y-4">
                            <div>
                                <div class="flex justify-between mb-2">
                                    <span class="font-semibold">الكيمياء</span>
                                    <span class="text-secondary">65%</span>
                                </div>
                                <div class="progress-bar">
                                    <div class="progress-fill" style="width: 65%"></div>
                                </div>
                            </div>
                            
                            <div>
                                <div class="flex justify-between mb-2">
                                    <span class="font-semibold">الفيزياء</span>
                                    <span class="text-secondary">30%</span>
                                </div>
                                <div class="progress-bar">
                                    <div class="progress-fill" style="width: 30%"></div>
                                </div>
                            </div>
                            
                            <div>
                                <div class="flex justify-between mb-2">
                                    <span class="font-semibold">الرياضيات</span>
                                    <span class="text-secondary">80%</span>
                                </div>
                                <div class="progress-bar">
                                    <div class="progress-fill" style="width: 80%"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                `;
            }
        }

        class DiscussionsPage {
            async render() {
                return `
                    <div class="card">
                        <div class="card-header">
                            <h2 class="card-title">المناقشات</h2>
                            <p class="text-secondary">شارك في النقاشات مع الزملاء</p>
                        </div>
                        
                        <div class="space-y-4">
                            <div class="card">
                                <h3 class="text-lg font-semibold mb-2">كيفية موازنة المعادلات الكيميائية</h3>
                                <p class="text-secondary mb-3">مناقشة حول طرق موازنة المعادلات الكيميائية المعقدة</p>
                                <div class="flex justify-between items-center">
                                    <span class="text-sm text-secondary">12 مشاركة</span>
                                    <button class="btn btn-outline">المشاركة</button>
                                </div>
                            </div>
                            
                            <div class="card">
                                <h3 class="text-lg font-semibold mb-2">تطبيقات قوانين نيوتن في الحياة اليومية</h3>
                                <p class="text-secondary mb-3">أمثلة عملية على قوانين الحركة</p>
                                <div class="flex justify-between items-center">
                                    <span class="text-sm text-secondary">8 مشاركات</span>
                                    <button class="btn btn-outline">المشاركة</button>
                                </div>
                            </div>
                        </div>
                    </div>
                `;
            }
        }

        // ==================== تهيئة التطبيق ====================
        const platform = new EduPlatform();

        // جعل المديرات متاحة عالمياً
        window.Router = new Router();
        window.AuthManager = new AuthManager();
        window.ThemeManager = ThemeManager;
        window.NotificationManager = NotificationManager;
        window.ModalManager = ModalManager;

        // بدء التطبيق
        document.addEventListener('DOMContentLoaded', () => {
            platform.initialize();
        });

        // التعامل مع أخطاء التحميل
        window.addEventListener('load', () => {
            if (!platform.isInitialized) {
                platform.initialize();
            }
        });
    </script>
</body>
</html>
project-root/
├─ docker-compose.yml
├─ README.md
├─ server/
│ ├─ package.json
│ ├─ prisma/schema.prisma
│ ├─ .env.example
│ └─ src/
│ ├─ index.js
│ ├─ app.js
│ ├─ routes/
│ │ ├─ auth.js
│ │ ├─ admin.js
│ │ └─ courses.js
│ ├─ middleware/auth.js
│ ├─ services/storage.js # يمكنك تركه فارغ أو إضافة خدمات التخزين
│ ├─ services/notifications.js # يمكنك تركه فارغ أو إضافة وظائف الإشعارات
│ └─ seed/adminSeed.js
└─ client/
├─ package.json
├─ vite.config.ts
├─ tsconfig.json
├─ index.html
└─ src/
├─ index.tsx
├─ main.tsx
├─ App.tsx
├─ components/Hello.tsx
├─ styles.css
└─ __tests__/
├─ App.test.tsx
└─ Hello.test.tsx
