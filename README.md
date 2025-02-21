<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Website</title>
    <link rel="stylesheet" href="styles.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" integrity="sha512-9usAa10IRO0HhonpyAIVpjrylPvoDwiPUiKdWk5t3PyolY1cOd4DSE0Ga+ri4AuTroPR5aQvXU9xC6qOPnzFeg==" crossorigin="anonymous" referrerpolicy="no-referrer" />
</head>
<body>
    <header>
        <nav>
            <div class="logo">My Logo</div>  
            <ul class="nav-links">
                <li><a href="#about">About Us</a></li>
                <li><a href="#contact">Contact Us</a></li>
            </ul>
        </nav>
    </header>

    <section id="hero">
        <div class="hero-content">
            <h1>Welcome to My Website</h1>
            <p>This is a brief description of what I do.</p>
            <a href="login.html" class="get-started-btn">Get Started</a>
        </div>
    </section>

    <section id="about" class="section">
        <h2>About Us</h2>
        <div class="about-content">
            <img src="bg.jpg" alt="About Us Image">  
            <p>This is where you'll write about your company or yourself. You can include information about your mission, values, and what makes you unique. This section should be engaging and informative, giving visitors a good understanding of who you are.</p>
        </div>
    </section>

    <section id="contact" class="section">
        <h2>Contact Us</h2>
        <form>
            <input type="text" placeholder="Your Name" required>
            <input type="email" placeholder="Your Email" required>
            <textarea placeholder="Your Message" required></textarea>
            <button type="submit">Send Message</button>
        </form>
    </section>

    <footer>
        <p>&copy; 2023 My Website</p>
        <div class="social-links">
            <a href="#"><i class="fab fa-facebook"></i></a>
            <a href="#"><i class="fab fa-twitter"></i></a>
            <a href="#"><i class="fab fa-instagram"></i></a>
        </div>
    </footer>

    <script src="script.js"></script>
</body>
</html>
