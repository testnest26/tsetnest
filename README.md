[index_Version3_Version3.html](https://github.com/user-attachments/files/25358535/index_Version3_Version3.html)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TESTNEST - Student Portal</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            background: linear-gradient(135deg, #f5f5f5 0%, #e8e8e8 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .container {
            width: 100%;
            max-width: 450px;
        }

        /* LOGIN SCREEN */
        #loginScreen {
            background: white;
            border-radius: 24px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
            padding: 40px 24px;
            transition: all 0.3s ease;
        }

        #loginScreen.hidden {
            display: none;
        }

        /* LOGO SECTION */
        .logo-section {
            text-align: center;
            margin-bottom: 40px;
            margin-top: 20px;
        }

        .logo-section h1 {
            font-size: 42px;
            font-weight: 900;
            color: #0052cc;
            letter-spacing: -1px;
            font-family: 'Trebuchet MS', sans-serif;
        }

        /* ROLE SELECTOR TABS */
        .role-selector {
            display: flex;
            gap: 12px;
            margin-bottom: 32px;
            background: #f0f0f0;
            padding: 6px;
            border-radius: 50px;
            width: 100%;
        }

        .role-tab {
            flex: 1;
            padding: 12px 20px;
            border: none;
            border-radius: 50px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            background: transparent;
            color: #666;
            transition: all 0.3s ease;
        }

        .role-tab.active {
            background: white;
            color: #333;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
        }

        /* FORM */
        .form-group {
            margin-bottom: 24px;
        }

        .form-group label {
            display: block;
            margin-bottom: 10px;
            color: #333;
            font-weight: 600;
            font-size: 16px;
        }

        .form-group input {
            width: 100%;
            padding: 14px 18px;
            border: 2px solid #ddd;
            border-radius: 12px;
            font-size: 16px;
            transition: all 0.3s ease;
            background: #fafafa;
        }

        .form-group input:focus {
            outline: none;
            border-color: #0052cc;
            background: #fff;
            box-shadow: 0 0 0 3px rgba(0, 82, 204, 0.1);
        }

        .form-group input::placeholder {
            color: #999;
        }

        /* LOGIN BUTTON */
        .login-button {
            width: 100%;
            padding: 16px;
            background: linear-gradient(135deg, #ff5722 0%, #ff7043 100%);
            color: white;
            border: none;
            border-radius: 50px;
            font-size: 16px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 10px;
            box-shadow: 0 4px 15px rgba(255, 87, 34, 0.3);
            letter-spacing: 0.5px;
        }

        .login-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(255, 87, 34, 0.4);
        }

        .login-button:active {
            transform: translateY(0);
        }

        .login-button:disabled {
            opacity: 0.7;
            cursor: not-allowed;
            transform: none;
        }

        /* DEMO CREDENTIALS */
        .demo-credentials {
            margin-top: 20px;
            padding: 14px 16px;
            background: #f5f5f5;
            border-radius: 12px;
            font-size: 13px;
            color: #666;
            text-align: center;
            line-height: 1.5;
        }

        .demo-credentials strong {
            display: block;
            color: #333;
            margin-bottom: 6px;
            font-size: 12px;
        }

        .demo-credentials code {
            background: white;
            padding: 2px 6px;
            border-radius: 4px;
            font-family: 'Courier New', monospace;
            font-weight: 600;
        }

        /* NOTIFICATION */
        .notification {
            position: fixed;
            top: 20px;
            right: 20px;
            left: 20px;
            max-width: 400px;
            padding: 14px 16px;
            background: #4caf50;
            color: white;
            border-radius: 12px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
            font-size: 14px;
            font-weight: 500;
            animation: slideIn 0.3s ease;
            z-index: 1000;
        }

        .notification.error {
            background: #f44336;
        }

        .notification.hidden {
            display: none;
        }

        @keyframes slideIn {
            from {
                transform: translateY(-100%);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        /* DASHBOARD */
        #studentDashboard {
            background: white;
            border-radius: 24px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
            padding: 40px 24px;
            animation: fadeIn 0.3s ease;
        }

        #studentDashboard.hidden {
            display: none;
        }

        .dashboard-header {
            text-align: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 2px solid #f0f0f0;
        }

        #studentName {
            font-size: 28px;
            color: #333;
            font-weight: 700;
            margin-bottom: 8px;
        }

        .dashboard-status {
            color: #0052cc;
            font-size: 14px;
            font-weight: 600;
        }

        .dashboard-content {
            margin: 24px 0;
        }

        .dashboard-content p {
            color: #666;
            margin-bottom: 14px;
            line-height: 1.6;
            font-size: 15px;
        }

        .logout-button {
            width: 100%;
            padding: 14px;
            background: #f44336;
            color: white;
            border: none;
            border-radius: 50px;
            font-size: 16px;
            font-weight: 700;
            cursor: pointer;
            margin-top: 24px;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(244, 67, 54, 0.3);
        }

        .logout-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(244, 67, 54, 0.4);
        }

        .logout-button:active {
            transform: translateY(0);
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* MOBILE RESPONSIVE */
        @media (max-width: 480px) {
            body {
                padding: 15px;
                background: linear-gradient(135deg, #f8f8f8 0%, #efefef 100%);
            }

            #loginScreen,
            #studentDashboard {
                padding: 32px 20px;
                border-radius: 20px;
            }

            .logo-section {
                margin-bottom: 32px;
                margin-top: 16px;
            }

            .logo-section h1 {
                font-size: 36px;
            }

            .role-selector {
                margin-bottom: 28px;
            }

            .role-tab {
                padding: 10px 16px;
                font-size: 15px;
            }

            .form-group {
                margin-bottom: 20px;
            }

            .form-group label {
                font-size: 15px;
                margin-bottom: 8px;
            }

            .form-group input {
                padding: 13px 16px;
                font-size: 16px;
            }

            .login-button,
            .logout-button {
                padding: 14px;
                font-size: 16px;
            }

            #studentName {
                font-size: 24px;
            }

            .notification {
                left: 15px;
                right: 15px;
                top: 15px;
                border-radius: 10px;
            }

            .demo-credentials {
                font-size: 12px;
                padding: 12px 14px;
            }
        }

        @media (max-width: 360px) {
            #loginScreen,
            #studentDashboard {
                padding: 24px 16px;
            }

            .logo-section h1 {
                font-size: 32px;
            }

            .role-tab {
                padding: 9px 14px;
                font-size: 14px;
            }

            .form-group input {
                padding: 12px 14px;
            }

            .demo-credentials {
                font-size: 11px;
            }
        }

        /* ACCESSIBILITY */
        @media (prefers-reduced-motion: reduce) {
            * {
                animation: none !important;
                transition: none !important;
            }
        }

        /* DARK MODE SUPPORT */
        @media (prefers-color-scheme: dark) {
            body {
                background: linear-gradient(135deg, #1a1a1a 0%, #2d2d2d 100%);
            }

            #loginScreen,
            #studentDashboard {
                background: #2a2a2a;
                color: #e0e0e0;
            }

            .logo-section h1 {
                color: #4fa3ff;
            }

            .role-selector {
                background: #1a1a1a;
            }

            .role-tab {
                color: #999;
            }

            .role-tab.active {
                background: #3a3a3a;
                color: #e0e0e0;
                box-shadow: 0 2px 8px rgba(0, 0, 0, 0.4);
            }

            .form-group label {
                color: #e0e0e0;
            }

            .form-group input {
                background: #1a1a1a;
                border-color: #444;
                color: #e0e0e0;
            }

            .form-group input:focus {
                border-color: #4fa3ff;
                background: #222;
            }

            .form-group input::placeholder {
                color: #666;
            }

            .demo-credentials {
                background: #1a1a1a;
                color: #999;
            }

            .demo-credentials strong {
                color: #e0e0e0;
            }

            .demo-credentials code {
                background: #3a3a3a;
            }

            .dashboard-header {
                border-bottom-color: #3a3a3a;
            }

            #studentName {
                color: #e0e0e0;
            }

            .dashboard-status {
                color: #4fa3ff;
            }

            .dashboard-content p {
                color: #bbb;
            }
        }
    </style>
</head>
<body>
    <!-- LOGIN SCREEN -->
    <div id="loginScreen" class="container">
        <div class="logo-section">
            <h1>TESTNEST</h1>
        </div>

        <!-- ROLE SELECTOR -->
        <div class="role-selector">
            <button class="role-tab active" data-role="student" onclick="switchRole('student')">
                Student
            </button>
            <button class="role-tab" data-role="admin" onclick="switchRole('admin')">
                Admin
            </button>
        </div>

        <form id="loginForm" onsubmit="handleLoginSubmit(event)">
            <div class="form-group">
                <label for="studentUsername">Username</label>
                <input
                    type="text"
                    id="studentUsername"
                    placeholder="Enter your username"
                    autocomplete="username"
                    required
                />
            </div>

            <div class="form-group">
                <label for="studentPassword">Password</label>
                <input
                    type="password"
                    id="studentPassword"
                    placeholder="Enter your password"
                    autocomplete="current-password"
                    required
                />
            </div>

            <button type="submit" class="login-button" id="loginBtn">
                LOGIN AS <span id="roleText">STUDENT</span>
            </button>
        </form>

        <div class="demo-credentials">
            <strong>Demo: student/student123 or admin/admin123</strong>
        </div>
    </div>

    <!-- STUDENT DASHBOARD -->
    <div id="studentDashboard" class="container hidden">
        <div class="dashboard-header">
            <div id="studentName"></div>
            <div class="dashboard-status">✓ Successfully logged in</div>
        </div>

        <div class="dashboard-content">
            <p>Welcome to your dashboard! You can now access your courses, assignments, and grades.</p>
            <p id="loginTime"></p>
        </div>

        <button class="logout-button" onclick="handleLogout()">
            SIGN OUT
        </button>
    </div>

    <!-- NOTIFICATION -->
    <div id="notification" class="notification hidden"></div>

    <script>
        let currentUser = null;
        let selectedRole = 'student';

        const credentials = {
            student: { username: 'student', password: 'student123' },
            admin: { username: 'admin', password: 'admin123' }
        };

        // Load user from localStorage on page load
        window.addEventListener('DOMContentLoaded', () => {
            const savedUser = localStorage.getItem('currentUser');
            if (savedUser) {
                try {
                    currentUser = JSON.parse(savedUser);
                    showStudentDashboard();
                } catch (e) {
                    console.error('Error loading user:', e);
                    localStorage.removeItem('currentUser');
                }
            }
        });

        /**
         * Switch between Student and Admin roles
         */
        function switchRole(role) {
            selectedRole = role;
            
            // Update active tab
            document.querySelectorAll('.role-tab').forEach(tab => {
                tab.classList.remove('active');
            });
            document.querySelector(`[data-role="${role}"]`).classList.add('active');
            
            // Update button text
            document.getElementById('roleText').textContent = role.toUpperCase();
            
            // Clear form
            document.getElementById('loginForm').reset();
            document.getElementById('studentUsername').focus();
        }

        /**
         * Handle login form submission
         */
        function handleLoginSubmit(event) {
            event.preventDefault();
            loginStudent();
        }

        /**
         * Authenticate student/admin and show dashboard
         */
        function loginStudent() {
            const username = document.getElementById('studentUsername').value.trim();
            const password = document.getElementById('studentPassword').value;
            const loginBtn = document.getElementById('loginBtn');
            const creds = credentials[selectedRole];

            // Input validation
            if (!username || !password) {
                showNotification('Please enter both username and password', 'error');
                return;
            }

            // Disable button during login
            loginBtn.disabled = true;
            loginBtn.textContent = `SIGNING IN...`;

            // Simulate network delay
            setTimeout(() => {
                if (username === creds.username && password === creds.password) {
                    currentUser = { 
                        name: username, 
                        type: selectedRole, 
                        loginTime: new Date().toISOString() 
                    };
                    localStorage.setItem('currentUser', JSON.stringify(currentUser));
                    
                    showNotification('Login successful! 🎉');
                    document.getElementById('loginForm').reset();
                    
                    setTimeout(() => {
                        showStudentDashboard();
                    }, 500);
                } else {
                    showNotification(
                        `Invalid credentials! Use: ${creds.username} / ${creds.password}`, 
                        'error'
                    );
                    document.getElementById('studentPassword').value = '';
                    loginBtn.disabled = false;
                    loginBtn.textContent = `LOGIN AS ${selectedRole.toUpperCase()}`;
                    document.getElementById('studentPassword').focus();
                }
            }, 500);
        }

        /**
         * Display student dashboard
         */
        function showStudentDashboard() {
            document.getElementById('loginScreen').classList.add('hidden');
            document.getElementById('studentDashboard').classList.remove('hidden');
            
            const welcomeName = currentUser.name.charAt(0).toUpperCase() + currentUser.name.slice(1);
            const roleLabel = currentUser.type.charAt(0).toUpperCase() + currentUser.type.slice(1);
            document.getElementById('studentName').textContent = `Welcome, ${welcomeName}!`;
            
            if (currentUser.loginTime) {
                const loginDate = new Date(currentUser.loginTime);
                document.getElementById('loginTime').textContent = 
                    `Logged in as: ${roleLabel} • ${loginDate.toLocaleString()}`;
            }

            const loginBtn = document.getElementById('loginBtn');
            loginBtn.disabled = false;
            loginBtn.textContent = `LOGIN AS ${selectedRole.toUpperCase()}`;
        }

        /**
         * Handle logout
         */
        function handleLogout() {
            if (confirm('Are you sure you want to sign out?')) {
                currentUser = null;
                localStorage.removeItem('currentUser');
                
                document.getElementById('studentDashboard').classList.add('hidden');
                document.getElementById('loginScreen').classList.remove('hidden');
                document.getElementById('loginForm').reset();
                
                // Reset to Student role
                switchRole('student');
                
                showNotification('You have been signed out');
                document.getElementById('studentUsername').focus();
            }
        }

        /**
         * Show notification with auto-dismiss
         */
        function showNotification(message, type = 'success') {
            const notification = document.getElementById('notification');
            notification.textContent = message;
            notification.className = `notification ${type === 'error' ? 'error' : ''}`;
            
            setTimeout(() => {
                notification.classList.add('hidden');
            }, 4000);
        }

        // Allow Enter key to submit form
        document.addEventListener('DOMContentLoaded', () => {
            document.getElementById('loginForm').addEventListener('keypress', (e) => {
                if (e.key === 'Enter') {
                    handleLoginSubmit(e);
                }
            });
        });
    </script>
</body>
</html>
