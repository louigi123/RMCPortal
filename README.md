<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RMC Tagum Student Portal</title>
    <link rel="stylesheet" href="louigi.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;700;800&display=swap" rel="stylesheet">
    <link href="https://cdn.jsdelivr.net/npm/boxicons@2.1.4/css/boxicons.min.css" rel="stylesheet">
</head>
<body>

    <!-- Header -->
    <header>
        <div class="logo-container">
            <img src="logo.png" alt="RMC Logo"> <!-- Fixed Image Path -->
            <h1>RMC Tagum Student Portal</h1>
        </div>
        <nav class="nav-links">
            <a href="#">About Us</a>
            <a href="#">Home</a>
            <a href="#">Contact</a>     
        </nav>
    </header>

    <div class="overlay"></div> <!-- Background blur -->
    <div class="content"></div>

    <!-- Mission Section -->
    <section class="mission-container">
        <div class="mission">
            <h2>Our Mission</h2>
            <p>The RMC Community is keeping up to produce “cream of the crop” graduates who are research-driven, 
               community service-oriented, globally competitive, and life-long learners.</p>
            <p>Established as a private educational institution, RMC is committed to upholding the laws of the Republic 
               and the goals of the Department of Education, CHED, and TESDA. We aim to educate the Filipino in accordance 
               with total personal development, regardless of sex, race, age, or economic status.</p>
            <h3>Pro Deo Et Patria</h3>
            <p>(God and Country)</p>

            <!-- Login Button -->
            <div class="buttons">
                <button id="student-btn" style="font-size: 20px; font-weight: bold; padding: 15px 30px; background-color: rgb(36, 138, 223); color: white; border: none; border-radius: 5px; cursor: pointer;">
                    Login
                </button>
            </div>
        </div>

        <!-- Sign In Box -->
        <div class="sign-in-box">
            <h2>Sign In</h2>

            <!-- I.D. Number -->
            <div class="input-container">
                <i class='bx bx-id-card'></i>
                <input type="text" id="id" placeholder="Enter I.D. Number">
            </div>

            <!-- Email -->
            <div class="input-container">
                <i class='bx bx-envelope'></i>
                <input type="email" id="email" placeholder="Enter Email">
            </div>

            <!-- Password -->
            <div class="input-container">
                <i class='bx bx-lock'></i>
                <input type="password" id="password" placeholder="Enter Password">
            </div>

            <div class="remember-forgot">
                <label><input type="checkbox"> Remember me</label>
                <a href="#">Forgot Password</a>
            </div>

            <button id="sign-in-btn">Sign In</button>
            <button id="back-btn">Back</button>
        </div>

        <!-- Image Box -->
        <div class="image-box">
            <img src="CAPSTONE.png" alt="Mission Image"> <!-- Fixed Image Path -->
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="contact-info">
            <p>
                <i class="bx bxl-gmail"></i>
                <a href="mailto:admissions.rmctagum@gmail.com" style="text-decoration: none; color: inherit;">
                    admissions.rmctagum@gmail.com
                </a>
            </p>
            <p>
                <i class="bx bxl-facebook-circle"></i>
                <a href="https://www.facebook.com/RMCTagumBranchOfficial" target="_blank" style="text-decoration: none; color: inherit;">
                    Rizal Memorial Colleges, Inc. Tagum
                </a>
            </p>
            <p>
                <i class="bx bxs-map"></i>
                <a href="https://maps.app.goo.gl/svUdVLbUut9TV7DY8" target="_blank" style="text-decoration: none; color: inherit;">
                    Purok Gulayan Boizer Avenue, Brgy. Mankilam, Tagum City
                </a>
            </p>
        </div>
    </footer>

    <!-- JavaScript for Login & Logout -->
    <script>
        document.getElementById("student-btn").addEventListener("click", function() {
            document.querySelector(".sign-in-box").classList.add("active");
            document.querySelector(".image-box").style.display = "none";
        });

        document.getElementById("back-btn").addEventListener("click", function() {
            document.querySelector(".sign-in-box").classList.remove("active");
            document.querySelector(".image-box").style.display = "block";
        });

        document.getElementById("sign-in-btn").addEventListener("click", function() {
            let id = document.getElementById("id").value;
            let email = document.getElementById("email").value;
            let password = document.getElementById("password").value;

            if (id && email && password) {
                localStorage.setItem("isLoggedIn", "true"); // Store login status
                window.location.href = "dashboard-page.html"; // Redirect to dashboard
            } else {
                alert("Please fill in all fields!");
            }
        });

        // Auto Redirect to Dashboard if Already Logged In
        if (localStorage.getItem("isLoggedIn") === "true") {
            window.location.href = "dashboard-page.html";
        }
    </script>

</body>
</html>
/* General Styles */
body {
    background: url('RMC FRont.png') no-repeat center center fixed;
    background-size: cover;  /* Ensures it covers the entire screen */

    color: #2d27da;
}


.overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(10, 6, 69, 0.888); /* Light transparent layer */
    backdrop-filter: blur(5px); /* Blur only this layer */
    z-index: -1; /* Puts it behind everything */
}
.logo-container {
    display: flex;
    align-items: center;  /* Aligns logo and text */
    gap: 10px;  /* Adds spacing between logo and title */
}

.logo-container img {
    width: 50px;  /* Adjust the size as needed */
    height: auto;  /* Maintains aspect ratio */ 
        width: 100px;  /* Logo size */
        height: auto;  /* Keeps aspect ratio */
    
}

/* Header Styling */
header {
    background-color: #15a8fd9a; /*header background */
    color: white;
    padding: 7px;
    text-align: left;
    display: flex;
    align-items: center;
    justify-content: space-between;
}

header img {
    width: 50px;
    height: auto;
    margin-right: 10px;



}

header h1 {
    font-size: 30px;
    font-weight: bold;
    margin-right: 600px;
        font-family: 'Poppins', sans-serif;  /* Apply Poppins font */
        font-weight: 800;  /* Extra Bold */
        font-style: italic;  /* Italic */
        font-size: 1.8rem;  /* RMC Tagum Student Portal */
        color: white;  
        text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);  /* Optional shadow */
    
}

.nav-links a {
    color: white !important; 
    text-decoration: none; 
    margin:  -100px;
    font-weight: bold;
    font-size: 10spx;
    
}

.nav-links a:hover {
    text-decoration:underline;
    color: #ddd; 
}
nav ul {
    list-style: none;
    display: flex;
}

nav ul li {
    margin: 15px;
}

nav ul li a {
    color: rgb(255, 255, 255);
    text-decoration: none;
    font-weight: bolder;
}

/* Mission Section */
.mission-container {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    padding: 50px;
    background:none
     auto;
}



.mission {
    background: none
    padding 20px;
    max-width: 50%;
    border-radius: 10px;
    color: white;
    text-align: justify;

}

.mission h2, .mission h3 {
    color: white;
    font-weight: bold; 
        font-size: 30px; /* Adjust as needed */
        font-weight: bold;
        color: white;
}

.motto-container {
    text-align: center; /* Centers the text */
    margin-top: 20px; /* Adjust top spacing */
}

.pro-deo {
    font-size: 26px;
    font-weight: bold;
    text-transform: uppercase;
    color: white;
    text-align: center;
    font-family: "Arial", sans-serif;
    letter-spacing: 1px;
    margin-bottom: 5px; /* Reduces space between text */
}

.pro-deo-sub {
    font-size: 16px;
    font-style: italic;
    color: white;
    text-align: center;
    margin-top: -10px; /* Moves it closer to the heading */
}

.motto {
    font-size: 28px; 
    font-weight: bold;
    margin-top: 10px;
}



.button-container {
    text-align: center; /* Center aligns the buttons */
    margin-top: 10px; /* Controls space between the text and buttons */
}



.mission-container {
    display: flex;  /* Align text and image side by side */
    justify-content: space-between; /* Creates space between text & image */
    align-items: center; /* Align vertically */
    color: white;
    padding: 20px;
}

.mission-text {
    flex: 1; /* Takes up available space */
}


.image-box {
    width: 560px; /* Adjust size as needed */
    height: 400px;
    background-color: rgba(255, 255, 255, 0.2); /* Light transparent background */
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10px; /* Optional: Rounded corners */
    overflow: hidden; /* Ensures image stays inside box */
}

.image-box img {
    width: 100%; /* Makes the image fit */
    height: 100%;
    object-fit: cover; /* Keeps image proportional */

}
.sign-in-box {
    position: absolute;
    top: 55%;
    right: -100%; /* Start off-screen */
    transform: translateY(-48%);
    width: 520px;
    height: 399px;
    background: rgba(255, 255, 255, 0.9);
    padding: 20px;
    border-radius: 10px;
    transition: right 0.5s ease-in-out;
    box-shadow: 0px 5px 15px rgba(26, 17, 17, 0.2);
}

#dashboard-page {
    display: none;
}
/* When active, move into view */
.sign-in-box.active {
    right: 2%; /* Adjust as needed */
}

/* Input field container */
.input-container {
    display: flex;
    align-items: center;
    background: white;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    margin: 10px 0;
}
.sign-in-box h2 {
    font-size: 3rem; /* Adjust size as needed */
    font-weight: bold;
    text-align: center;
    margin-bottom: 15px;
}

.sign-in-box.active ~ .image-box {
    display: none;
}

.input-container i {
    font-size: 20px;
    color: #333;
    margin-right: 10px;
}

.input-container input {
    border: none;
    outline: none;
    width: 100%; /*word sa password and gmail etc.*/
    font-size: 16px;
}

#back-btn {
    margin-top: 10px;
    background: #090538;
    color: white;
    border: none;
    padding: 10px 15px;
    border-radius: 5px;
    cursor: pointer;
    width: 100%;
    font-size: 16px;
    transition: background 0.3s ease;
}

#back-btn:hover {
    background: #0a032c;
}

/* Buttons */
.buttons {
    margin-top: 40px;
    margin-inline: 40px;
    display: flex;
    gap: 10px;
}




.header, .footer {
    background: linear-gradient(to right, #070a8d, #4CCEEB);
    color: white; /* Ensure text is visible */
    padding: 20px; /* Adjust spacing */
    text-align: center; /* Center align text */
}


/* Footer Styling */
footer {
    background:linear-gradient(to right,#4CCEEB,#070a8d);
    padding: 15px;
    margin-top: 30px; /*footer background*/
    color: white;
    text-align: center;
}

/* Align contact info in one line */
.contact-info {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 20px; /* Space between icons */
    flex-wrap: wrap; /* Prevents breaking into multiple lines */
    text-decoration: none;
}

.contact-info p {
    display: flex;
    align-items: center;
    margin: 50;
    font-size: 16px;
}

.contact-info i {
    margin-right: 8px;
    font-size: 20px;
}
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RMC Tagum Student Portal</title>
    <link rel="stylesheet" href="dashboard-page.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/boxicons@2.1.4/css/boxicons.min.css">
</head>
<body>
    
    <!-- Sidebar Navigation -->
    <aside class="sidebar" id="sidebar">
        <div class="sidebar-header">
            <img src="logo.png" alt="School Logo" class="school-logo"> <!-- Fixed Image Path -->
            <h2>RMC Tagum Student Portal</h2>
        </div>
        <nav class="sidebar-menu">
            <a href="#" class="active"><i class='bx bx-home'></i> Dashboard</a>
            <a href="#"><i class='bx bx-user'></i> Profile</a>
            <a href="#"><i class='bx bx-book'></i> Classes</a>
            <a href="#"><i class='bx bx-bell'></i> Announcements</a>
            <a href="#"><i class='bx bx-edit'></i> Enrollment</a>
            <a href="#"><i class='bx bx-info-circle'></i> Mission, Vision, and Values</a>
            <a href="#" id="logout"><i class="bx bx-log-out"></i> Logout</a> <!-- Fixed Logout Button -->
        </nav>
        <button class="toggle-btn" onclick="toggleSidebar()">☰</button>
    </aside>

    <!-- Main Content -->
    <main class="main-content" id="mainContent">
        <!-- Header -->
        <header class="dashboard-header">
            <div class="user-info">
                <i class='bx bx-user-circle'></i>
                <span>JIM ROSS TAN</span>
            </div>
            <i class='bx bx-bell notification'></i>
        </header>

        <!-- Welcome Section -->
        <section class="welcome-container">
            <div class="welcome-text">
                <p id="current-date"></p>
                <h2>Welcome back, Jim!</h2>
                <p>Always stay updated in your student portal.</p>
            </div>
            <img src="c:\Users\Manilyn\OneDrive\Attachments\Sir tan.jpg" alt="Profile Picture" class="profile-picture"> <!-- Fixed Image Path -->
        </section>

        <!-- Dashboard Menu -->
        <section class="dashboard-menu">
            <div class="menu-item">
                <i class='bx bx-wallet'></i>
                <p>Balance</p>
            </div>
            <div class="menu-item">
                <i class='bx bx-check-circle'></i>
                <p>Clearance</p>
            </div>
            <div class="menu-item">
                <i class='bx bx-first-aid'></i>
                <p>Clinic History</p>
            </div>
            <div class="menu-item">
                <i class='bx bx-graduation'></i>
                <p>Scholarship</p>
            </div>
            <div class="menu-item">
                <i class='bx bx-list-check'></i>
                <p>To-Dos</p>
            </div>
            <div class="menu-item">
                <i class='bx bx-news'></i>
                <p>School News</p>
            </div>
        </section>

        <!-- Subject Teachers -->
        <section class="teachers-section">
            <h3>Subject Teachers</h3>
            <div class="teachers-list">
                <img src="teacher1.jpg" alt="Teacher 1">
                <img src="teacher2.jpg" alt="Teacher 2">
                <img src="teacher3.jpg" alt="Teacher 3">
            </div>
        </section>

        <!-- Daily Reminders -->
        <section class="reminders-section">
            <h3>Daily Reminders</h3>
            <ul>
                <li><i class='bx bx-message-square-dots'></i> Ma'am Menche posted an assignment (COR 18)</li>
                <li><i class='bx bx-message-square-dots'></i> Sir Dave posted an assignment (STEM 100)</li>
                <li><i class='bx bx-message-square-dots'></i> Ma'am Dags posted an assignment (Gosur 50)</li>
            </ul>
        </section>
    </main>

    <script>
        function toggleSidebar() {
            document.getElementById("sidebar").classList.toggle("hidden");
            document.getElementById("mainContent").classList.toggle("shift");
        }

        // Auto Redirect to Login Page if Not Logged In
        if (localStorage.getItem("isLoggedIn") !== "true") {
            window.location.href = "louigi.html"; // Redirect to login page
        }

        // Logout Functionality
        document.getElementById("logout").addEventListener("click", function(event) {
            event.preventDefault();  // Prevent default link action
            localStorage.removeItem("isLoggedIn"); // Remove login status
            window.location.href = "louigi.html"; // Redirect to login page
        });

        // Display Current Date
        document.getElementById("current-date").textContent = new Date().toLocaleDateString();

        document.addEventListener("DOMContentLoaded", function () {
    const dateElement = document.getElementById("current-date");

    // Get current date
    const options = { year: "numeric", month: "long", day: "numeric" };
    const today = new Date().toLocaleDateString("en-US", options);

    // Display formatted date
    dateElement.textContent = today;
});
    </script>
</body>
</html>

/* General Styles */
body {
    font-family: 'Poppins', sans-serif;
    margin: 0;
    padding: 0;
    display: flex;
    background-color: #f8f9fa;
}

.welcome-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    text-align: left;
    height: 150px; /* Adjusted to match the image */
    background: linear-gradient(to right, #60d6ff, #004aad); /* Matched the gradient */
    color: white;
    padding: 20px 30px;
    border-radius: 15px;
    max-width: 700px; /* Adjust width as needed */
}

.welcome-text {
    flex: 1;
}

.welcome-text p {
    font-size: 1rem; /* Adjusted for date */
    font-weight: 500;
    margin: 0;
}

.welcome-text h2 {
    font-size: 2rem; /* Matched the size in the image */
    font-weight: 700;
    margin: 5px 0;
}

.profile-img {
    width: 60px; /* Adjusted size */
    height: 60px;
    border-radius: 50%;
    object-fit: cover;
    margin-left: 20px; /* Space between text and image */
}



/* Sidebar */
.sidebar {
    width: 250px;
    background-color: #003366;
    color: white;
    height: 100vh;
    position: fixed;
    padding-top: 20px;
}

.sidebar-header {
    text-align: center;
    padding: 10px;
}

/* Sidebar styling */
.sidebar {
    height: 100vh; /* Full viewport height */
    overflow-y: auto; /* Enable vertical scrolling */
    position: fixed;
    left: 10;
    top: 10;
    width: 250px;
    background-color: #0a3d62; /* Sidebar color */
    transition: transform 0.3s ease-in-out;
}

/* When sidebar is hidden */
.sidebar.hidden {
    transform: translateX(-100%);
}

/* Main content */
.main-content {
    margin-left: 250px; /* Same as sidebar width */
    padding: 20px;
    transition: margin-left 0.3s ease-in-out;
}

/* When sidebar is hidden, shift content */
.main-content.shift {
    margin-left: 0;
}
/* Sidebar */
.sidebar {
    width: 250px;
    background-color: #003366;
    color: white;
    height: 100vh; /* Ensure it takes full viewport height */
    position: fixed;
    padding-top: 20px;
    overflow-y: auto; /* Enable scrolling inside the sidebar */
}

/* Main Content */
.main-content {
    margin-left: 260px;
    padding: 20px;
    min-height: 150vh; /* Extend height to allow scrolling */
    width: calc(100% - 260px);
}

/* Ensuring Sidebar Scrollability */
.sidebar-menu {
    display: flex;
    flex-direction: column;
    height: calc(100vh - 100px); /* Leave space for header/footer */
    overflow-y: auto; /* Scroll inside the sidebar */
    padding-bottom: 20px; /* Ensure spacing */
}

/* Logout Button Position */
.logout {
    margin-top: auto; /* Push logout button to bottom */
    padding: 15px;
    color: red;
    text-align: center;
    cursor: pointer;
}

/* Button to toggle sidebar */
.toggle-btn {
    position: fixed;
    top: 20px;
    left: 20px;
    z-index: 1000;
    background-color: #007bff;
    color: white;
    border: none;
    padding: 10px 15px;
    cursor: pointer;
    border-radius: 5px;
}

.toggle-btn:hover {
    background-color: #0056b3;
}


.school-logo {
    width: 100px;
    display: block;
    margin: 10px auto;
}


.sidebar-menu a {
    display: block;
    color: white;
    padding: 15px;
    text-decoration: none;
    font-size: 16px;
    transition: 0.3s;
}

.sidebar-menu a:hover, .sidebar-menu a.active {
    background-color: #0056b3;
}

.logout {
    margin-top: 20px;
    color: red;
}

/* Main Content */
.main-content {
    margin-left: 260px;
    padding: 20px;
    width: 100%;
}

/* Header */
.dashboard-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: white;
    padding: 15px 20px;
    border-radius: 10px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.user-info {
    font-size: 18px;
    font-weight: bold;
}

.notification {
    font-size: 24px;
    cursor: pointer;
}

/* Welcome Section */
.welcome-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: linear-gradient(to right, #1E5799, #2989D8);
    padding: 20px;
    border-radius: 10px;
    color: white;
    position: relative;
    margin-top: 20px;
}

.welcome-text {
    flex: 1;
}

.profile-picture {
    width: 80px;
    height: 80px;
    border-radius: 50%;
    border: 3px solid white;
    object-fit: cover;
    position: absolute;
    right: 20px;
    top: 50%;
    transform: translateY(-50%);
}

/* Dashboard Menu */
.dashboard-menu {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
    margin-top: 20px;
}

.menu-item {
    background: white;
    padding: 20px;
    border-radius: 10px;
    text-align: center;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    transition: 0.3s;
}

.menu-item:hover {
    background-color: #e0f3ff;
}

/* Subject Teachers */
.teachers-section, .reminders-section {
    margin-top: 20px;
}

.teachers-list img {
    width: 60px;
    height: 60px;
    border-radius: 50%;
    margin-right: 10px;
}
.header, .footer {
    background: linear-gradient(to right, #070a8d, #4CCEEB);
    color: white; /* Ensure text is visible */
    padding: 20px; /* Adjust spacing */
    text-align: center; /* Center align text */
}

/* Daily Reminders */
.reminders-section ul {
    list-style: none;
    padding: 0;
}

.reminders-section li {
    background: white;
    padding: 10px;
    border-radius: 5px;
    margin-top: 5px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}
