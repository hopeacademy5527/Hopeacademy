
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hope Academy Registration</title>
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background: var(--tg-theme-bg-color, #ffffff);
            color: var(--tg-theme-text-color, #000000);
            line-height: 1.6;
            padding: 20px;
            padding-bottom: 80px;
        }

        .header {
            text-align: center;
            padding: 30px 20px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border-radius: 15px;
            margin-bottom: 30px;
        }

        .logo {
            font-size: 28px;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
        }

        input, select, textarea {
            width: 100%;
            padding: 15px;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            font-size: 16px;
        }

        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: #667eea;
        }

        .btn {
            background: #667eea;
            color: white;
            border: none;
            padding: 15px 20px;
            border-radius: 10px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            width: 100%;
            margin: 10px 0;
        }

        /* Bottom Navigation Menu */
        .bottom-nav {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            background: white;
            border-top: 2px solid #f0f0f0;
            display: flex;
            padding: 10px 0;
        }

        .nav-item {
            flex: 1;
            text-align: center;
            padding: 10px 5px;
            cursor: pointer;
        }

        .nav-item.active {
            color: #667eea;
        }

        .nav-icon {
            font-size: 20px;
            margin-bottom: 4px;
        }

        .nav-label {
            font-size: 12px;
        }

        .page {
            display: none;
        }

        .page.active {
            display: block;
        }

        .course-card {
            background: #f8f9fa;
            border-radius: 12px;
            padding: 15px;
            margin: 10px 0;
            border-left: 4px solid #667eea;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <div class="header">
        <div class="logo">🏫 Hope Academy</div>
        <div>Quality Education for Everyone</div>
    </div>

    <!-- Registration Page -->
    <div id="registerPage" class="page active">
        <h2>Student Registration 📝</h2>
        
        <div class="form-group">
            <label for="fullName">Full Name</label>
            <input type="text" id="fullName" placeholder="Enter your full name">
        </div>

        <div class="form-group">
            <label for="email">Email</label>
            <input type="email" id="email" placeholder="Enter your email">
        </div>

        <div class="form-group">
            <label for="course">Select Course</label>
            <select id="course">
                <option value="">Choose a course...</option>
                <option value="programming">Programming</option>
                <option value="design">Graphic Design</option>
                <option value="english">English Language</option>
            </select>
        </div>

        <button class="btn" onclick="submitRegistration()">Submit Registration</button>
    </div>

    <!-- Courses Page -->
    <div id="coursesPage" class="page">
        <h2>Available Courses 📚</h2>
        
        <div class="course-card">
            <h3>Programming Fundamentals</h3>
            <p>Learn programming with Python - $99</p>
            <button class="btn" onclick="selectCourse('programming')">Select</button>
        </div>

        <div class="course-card">
            <h3>Graphic Design</h3>
            <p>Master design principles - $79</p>
            <button class="btn" onclick="selectCourse('design')">Select</button>
        </div>
    </div>

    <!-- Profile Page -->
    <div id="profilePage" class="page">
        <h2>Student Profile 👤</h2>
        <div id="userInfo">
            <p>Your profile information will appear here.</p>
        </div>
    </div>

    <!-- About Page -->
    <div id="aboutPage" class="page">
        <h2>About Hope Academy ℹ️</h2>
        <p>We provide quality education to everyone.</p>
        <p>Contact: info@hopeacademy.edu</p>
    </div>

    <!-- Bottom Navigation Menu -->
    <div class="bottom-nav">
        <div class="nav-item active" onclick="showPage('registerPage')">
            <div class="nav-icon">📝</div>
            <div class="nav-label">Register</div>
        </div>
        
        <div class="nav-item" onclick="showPage('coursesPage')">
            <div class="nav-icon">📚</div>
            <div class="nav-label">Courses</div>
        </div>
        
        <div class="nav-item" onclick="showPage('profilePage')">
            <div class="nav-icon">👤</div>
            <div class="nav-label">Profile</div>
        </div>
        
        <div class="nav-item" onclick="showPage('aboutPage')">
            <div class="nav-icon">ℹ️</div>
            <div class="nav-label">About</div>
        </div>
    </div>

    <script>
        // Simple navigation function
        function showPage(pageId) {
            // Hide all pages
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            
            // Remove active class from all nav items
            document.querySelectorAll('.nav-item').forEach(item => {
                item.classList.remove('active');
            });
            
            // Show selected page
            document.getElementById(pageId).classList.add('active');
            
            // Add active class to clicked nav item
            event.currentTarget.classList.add('active');
        }

        function submitRegistration() {
            const name = document.getElementById('fullName').value;
            const email = document.getElementById('email').value;
            const course = document.getElementById('course').value;
            
            if (name && email && course) {
                alert('Registration Successful! We will contact you soon.');
                document.getElementById('fullName').value = '';
                document.getElementById('email').value = '';
                document.getElementById('course').value = '';
            } else {
                alert('Please fill in all fields!');
            }
        }

        function selectCourse(course) {
            document.getElementById('course').value = course;
            showPage('registerPage');
        }

        // Initialize Telegram Web App if in Telegram
        if (typeof window.Telegram !== 'undefined') {
            let tg = window.Telegram.WebApp;
            tg.expand();
            tg.ready();
            
            // Show user info if available
            let user = tg.initDataUnsafe.user;
            if (user) {
                document.getElementById('userInfo').innerHTML = `
                    <p><strong>Name:</strong> ${user.first_name} ${user.last_name || ''}</p>
                    <p><strong>Username:</strong> @${user.username || 'Not set'}</p>
                `;
            }
        }
    </script>
</body>
</html>
