# Hangbiao-Zhao.github.io

<p><a href="/BasicWebDev/Final Assignment: Putting All the Pieces Together.html" target="black">Final Assignment: Putting All the Pieces Together</a></p>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Community Cares - Helping Our Neighborhood Thrive</title>
    <link rel="stylesheet" href="css/styles.css">
</head>
<body>
    <header class="header-grid">
        <img src="images/logo.png" alt="Community Cares logo" class="logo">
        <nav class="nav-flex">
            <a href="index.html">Home</a>
            <a href="about.html">About Us</a>
            <a href="volunteer.html">Volunteer</a>
            <a href="stories.html">Success Stories</a>
            <a href="events.html">Events</a>
            <a href="contact.html">Contact</a>
        </nav>
    </header>

    <main class="hero-grid">
        <section class="hero-content">
            <h1>Building a Stronger Community Together</h1>
            <p>
                Join over 500 volunteers making a difference every week
            </p>
            <a href="volunteer.html" class="cta-button">Become a Volunteer</a>
        </section>
        <img src="images/hero-image.jpg" alt="Volunteers planting trees in community garden" class="hero-image">
    </main>

    <section class="stats-flex">
        <div class="stat-card">
            <h3>1,200+</h3>
            <p>
                People Helped Monthly
            </p>
        </div>
        <div class="stat-card">
            <h3>85</h3>
            <p>
                Community Projects
            </p>
        </div>
        <div class="stat-card">
            <h3>12</h3>
            <p>
                Years of Service
            </p>
        </div>
    </section>

    <footer>
        <!-- Footer content -->
    </footer>
</body>
</html>
<section class="about-grid">
    <article class="mission-statement">
        <h2>Our Mission</h2>
        <p>
            Founded in 2012, Community Cares connects volunteers with meaningful opportunities to address food insecurity, housing needs, and educational support in our city.
        </p>
    </article>

    <div class="team-gallery">
        <figure>
            <img src="images/director.jpg" alt="Executive Director Maria Gonzalez smiling">
            <figcaption>Maria Gonzalez, Executive Director</figcaption>
        </figure>
        <!-- More team members -->
    </div>

    <aside class="timeline">
        <h3>Our Journey</h3>
        <ul class="timeline-list">
            <li><strong>2012</strong> - Founded by local residents</li>
            <li><strong>2015</strong> - Expanded to 3 neighborhoods</li>
            <!-- More timeline items -->
        </ul>
    </aside>
</section>
<section class="volunteer-options">
    <h2>Current Opportunities</h2>

    <table class="opportunity-table">
        <thead>
            <tr>
                <th scope="col">Position</th>
                <th scope="col">Time Commitment</th>
                <th scope="col">Skills Needed</th>
                <th scope="col">Location</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Food Pantry Assistant</td>
                <td>4 hrs/week</td>
                <td>None required</td>
                <td>Main Community Center</td>
            </tr>
            <!-- More rows -->
        </tbody>
    </table>

    <form class="volunteer-form">
        <h3>Apply to Volunteer</h3>
        <label for="name">Full Name:</label>
        <input type="text" id="name" name="name" required>

        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>

        <label for="interest">Area of Interest:</label>
        <select id="interest" name="interest">
            <option value="">Select one...</option>
            <option value="food">Food Pantry</option>
            <!-- More options -->
        </select>

        <fieldset>
            <legend>Availability</legend>
            <input type="checkbox" id="weekday" name="availability" value="weekday">
            <label for="weekday">Weekdays</label>
            <!-- More checkboxes -->
        </fieldset>

        <button type="submit">Submit Application</button>
    </form>
</section>
<section class="stories-grid">
    <article class="featured-story">
        <img src="images/family-story.jpg" alt="The Johnson family receiving groceries">
        <div class="story-content">
            <h3>The Johnson Family's Story</h3>
            <p>
                "When my husband lost his job, Community Cares provided groceries and helped with rent. Now I volunteer to help others."
            </p>
            <p>
                - Tamika Johnson
            </p>
        </div>
    </article>

    <div class="story-gallery">
        <figure>
            <img src="images/garden1.jpg" alt="Community garden before renovation">
            <figcaption>Vacant lot in 2020</figcaption>
        </figure>
        <figure>
            <img src="images/garden2.jpg" alt="Community garden after renovation">
            <figcaption>Thriving garden in 2023</figcaption>
        </figure>
    </div>

    <aside class="impact-stats">
        <h3>By the Numbers</h3>
        <ul>
            <li>500+ families fed monthly</li>
            <li>120 students tutored weekly</li>
            <!-- More stats -->
        </ul>
    </aside>
</section>
<section class="events-container">
    <h2>Upcoming Events</h2>

    <div class="event-flex">
        <article class="event-card">
            <h3>Monthly Food Drive</h3>
            <p class="event-date">
                June 15, 2023 | 9am-2pm
            </p>
            <p>
                Help sort and distribute food donations at our main location.
            </p>
            <a href="#register-food-drive" class="event-button">Sign Up</a>
        </article>
        <!-- More event cards -->
    </div>

    <section class="video-section">
        <h3>See Our Work in Action</h3>
        <video controls poster="images/video-poster.jpg">
            <source src="media/impact-video.mp4" type="video/mp4">
            <track kind="captions" src="media/captions.vtt" srclang="en" label="English">
            <p>
                Your browser doesn't support HTML5 video. <a href="media/impact-video.mp4">Download the video</a> instead.
            </p>
        </video>
        <a href="media/impact-transcript.txt" class="transcript-link">Video Transcript</a>
    </section>
</section>
<section class="contact-grid">
    <div class="contact-info">
        <h2>Get in Touch</h2>
        <address>
            <p>
                <strong>Community Cares</strong><br>
                123 Helping Street<br>
                Your City, ST 12345
            </p>

            <p>
                Phone: <a href="tel:+15551234567">(555) 123-4567</a><br>
                Email: <a href="mailto:info@communitycares.org">info@communitycares.org</a>
            </p>
        </address>

        <div class="social-links">
            <a href="https://facebook.com/communitycares" aria-label="Facebook">
                <img src="images/facebook-icon.png" alt="Facebook icon">
            </a>
            <!-- More social links -->
        </div>
    </div>

    <form class="contact-form">
        <h3>Send Us a Message</h3>
        <label for="contact-name">Name:</label>
        <input type="text" id="contact-name" required>

        <label for="contact-email">Email:</label>
        <input type="email" id="contact-email" required>

        <label for="contact-message">Message:</label>
        <textarea id="contact-message" rows="5" required></textarea>

        <button type="submit">Send Message</button>
    </form>

    <div class="map-container">
        <iframe src="https://maps.google.com/maps?q=123+Helping+Street&output=embed"
            title="Map to Community Cares location"></iframe>
    </div>
</section>

