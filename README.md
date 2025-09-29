<!DOCTYPE html>
<html>
<head>
    <title>Hope Academy Registration</title>
    <style>
        body { 
            font-family: Arial, sans-serif; 
            padding: 20px; 
            text-align: center; 
        }
        .menu { 
            display: flex; 
            justify-content: space-around; 
            margin: 30px 0; 
        }
        .menu-item { 
            padding: 15px; 
            background: #007bff; 
            color: white; 
            border-radius: 10px; 
            cursor: pointer;
        }
        .page { 
            display: none; 
            padding: 20px;
        }
        .active { 
            display: block; 
        }
        h1 { color: #007bff; }
    </style>
</head>
<body>
    <h1>🏫 Hope Academy</h1>
    <p>Student Registration System</p>
    
    <div class="menu">
        <div class="menu-item" onclick="showPage('home')">Home</div>
        <div class="menu-item" onclick="showPage('register')">Register</div>
        <div class="menu-item" onclick="showPage('courses')">Courses</div>
    </div>

    <div id="home" class="page active">
        <h2>Welcome to Hope Academy! 🎓</h2>
        <p>Quality education for everyone</p>
    </div>

    <div id="register" class="page">
        <h2>Student Registration</h2>
        <p>Registration form will be here</p>
    </div>

    <div id="courses" class="page">
        <h2>Available Courses</h2>
        <p>• Programming</p>
        <p>• English Language</p>
        <p>• Graphic Design</p>
    </div>

    <script>
        function showPage(pageName) {
            // Hide all pages
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            // Show selected page
            document.getElementById(pageName).classList.add('active');
        }
    </script>
</body>
</html>
