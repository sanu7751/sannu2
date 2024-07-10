# sannu2
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gym Landing Page</title>
    <link rel="stylesheet" href="style.css">
    <style>
        .section{
            background-image: -moz-element(6);
        }
    </style>
          
</head>
<body>
    <header>
        <nav>
            <div class="logo">FitLife Gym</div>
            <ul class="nav-links">
                <li><a href="#services">Services</a></li>
                <li><a href="#testimonials">Testimonials</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>
    
    
    <section class="hero">
        <div class="hero-content">
            <h1>Welcome to FitLife Gym</h1>
            <p>Transform your body, mind, and life.</p>
            <a href="#services" class="cta-button">Join Now</a>
            
        </div>
    </section>
    
    <section id="services" class="services">
        <h2>Our Services</h2>
        <div class="service">
            <h3>Personal Training</h3>
            <p>Get one-on-one training with our certified trainers.</p>
        </div>
        <div class="service">
            <h3>Group Classes</h3>
            <p>Join our diverse group classes for all fitness levels.</p>
        </div>
        <div class="service">
            <h3>Nutrition Plans</h3>
            <p>Receive customized nutrition plans to meet your goals.</p>
        </div>
    </section>
    
    <section id="testimonials" class="testimonials">
        <h2>What Our Members Say</h2>
        <div class="testimonial">
            <p>"FitLife Gym has changed my life. The trainers are amazing!" - Alex P.</p>
        </div>
        <div class="testimonial">
            <p>"Great atmosphere and supportive community. Highly recommend!" - Jamie L.</p>
        </div>
        <div class="testimonial">
            <p>"The group classes are fun and effective. Love this place!" - Casey M.</p>
        </div>
    </section>
    
    <section id="contact" class="contact">
        <h2>Contact Us</h2>
        <form id="contact-form">
            <label for="name">Name:</label>
            <input type="text" id="name" name="name" required>
            
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>
            
            <label for="message">Message:</label>
            <textarea id="message" name="message" required></textarea>
            
            <button type="submit">Send</button>
        </form>
    </section>
    
    <footer>
        <p>&copy; 2024 FitLife Gym. All rights reserved.</p>
    </footer>

    <script src="scripts.js"></script>
</body>
</html>

css
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

header {
    background: #222;
    color: white;
    padding: 10px 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.logo {
    font-size: 1.5em;
    font-weight: bold;
}

.nav-links {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
}

.nav-links li {
    margin-left: 20px;
}

.nav-links a {
    color: white;
    text-decoration: none;
    font-size: 1em;
}

.hero {
    background: url('gym-hero.jpg') no-repeat center center/cover;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    color: white;
    text-align: center;
}

.hero-content {
    max-width: 600px;
}

.cta-button {
    background: #ff7f50;
    color: white;
    padding: 10px 20px;
    text-decoration: none;
    border-radius: 5px;
    font-size: 1.2em;
    margin-top: 20px;
    display: inline-block;
}

.services, .testimonials, .contact {
    padding: 50px 20px;
    text-align: center;
}

.services h2, .testimonials h2, .contact h2 {
    font-size: 2em;
    margin-bottom: 20px;
}

.service, .testimonial {
    margin-bottom: 20px;
}

form {
    display: flex;
    flex-direction: column;
    max-width: 400px;
    margin: 0 auto;
}

label {
    margin-bottom: 5px;
}

input, textarea {
    margin-bottom: 10px;
    padding: 10px;
    font-size: 1em;
}

button {
    background: #222;
    color: white;
    padding: 10px;
    border: none;
    font-size: 1em;
    cursor: pointer;
}

footer {
    background: #222;
    color: white;
    text-align: center;
    padding: 20px;
}


javascript
document.addEventListener('DOMContentLoaded', function() {
    
    const links = document.querySelectorAll('.nav-links a, .cta-button');
    for (const link of links) {
        link.addEventListener('click', smoothScroll);
    }

    function smoothScroll(event) {
        event.preventDefault();
        const targetId = event.currentTarget.getAttribute('href').substring(1);
        const targetPosition = document.getElementById(targetId).offsetTop;
        window.scrollTo({
            top: targetPosition - 50,
            behavior: 'smooth'
        });
    }

    
    const form = document.getElementById('contact-form');
    form.addEventListener('submit', function(event) {
        event.preventDefault();
        alert('Thank you for contacting us!');
        form.reset();
    });
});
