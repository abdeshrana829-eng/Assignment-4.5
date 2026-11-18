Below is a complete, multi-page college club website (NovaTech Robotics & Coding Club) fulfilling every requirement of Assignment 4.5, including shared navigation, metadata with an inline SVG favicon, semantic HTML5 structure, an events schedule table, and a validated registration form.

Project Structure
Save all five files in the exact same folder so the relative links and shared stylesheet work seamlessly across every page:

style.css: Shared responsive layout, navigation bar, cards, table styling, and form controls.

index.html: Home page with club overview, core activities, and an upcoming events schedule table.

about.html: Club mission, founding history, and executive member directory.

registration.html: Student membership sign-up form with validation attributes.

contact.html: Official email, campus lab location, office hours, and quick inquiry box.

1. Shared Stylesheet (style.css)
CSS
/* style.css — Shared styles for all 4 pages */
:root {
  --primary: #1e3a8a;
  --accent: #2563eb;
  --bg: #f8fafc;
  --surface: #ffffff;
  --text: #1e293b;
  --muted: #64748b;
  --border: #e2e8f0;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: system-ui, -apple-system, Segoe UI, Roboto, sans-serif;
  background-color: var(--bg);
  color: var(--text);
  line-height: 1.6;
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

header {
  background-color: var(--primary);
  color: #ffffff;
  padding: 1rem 2rem;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
}

.nav-container {
  max-width: 1000px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
}

.brand {
  font-size: 1.25rem;
  font-weight: 700;
  color: #ffffff;
  text-decoration: none;
}

nav ul {
  list-style: none;
  display: flex;
  gap: 1.25rem;
}

nav a {
  color: #dbeafe;
  text-decoration: none;
  font-weight: 500;
  padding: 0.35rem 0.65rem;
  border-radius: 6px;
  transition: background 0.2s, color 0.2s;
}

nav a:hover,
nav a.active {
  background-color: var(--accent);
  color: #ffffff;
}

main {
  max-width: 1000px;
  width: 100%;
  margin: 2rem auto;
  padding: 0 1.5rem;
  flex: 1;
}

.hero {
  background: var(--surface);
  border: 1px solid var(--border);
  border-left: 5px solid var(--accent);
  border-radius: 8px;
  padding: 2rem;
  margin-bottom: 2rem;
}

h1 {
  color: var(--primary);
  margin-bottom: 0.5rem;
}

h2 {
  color: var(--primary);
  margin: 1.5rem 0 0.75rem;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 1.25rem;
  margin-top: 1rem;
}

.card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: 1.25rem;
}

.card h3 {
  margin-bottom: 0.4rem;
  color: var(--accent);
}

table {
  width: 100%;
  border-collapse: collapse;
  background: var(--surface);
  margin-top: 1rem;
  border-radius: 8px;
  overflow: hidden;
  border: 1px solid var(--border);
}

th, td {
  padding: 0.85rem 1rem;
  text-align: left;
  border-bottom: 1px solid var(--border);
}

th {
  background-color: var(--primary);
  color: #ffffff;
}

tr:nth-child(even) {
  background-color: #f1f5f9;
}

form {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 8px;
  padding: 1.75rem;
  max-width: 600px;
}

.form-group {
  margin-bottom: 1.1rem;
}

label {
  display: block;
  font-weight: 600;
  margin-bottom: 0.35rem;
}

input, select, textarea {
  width: 100%;
  padding: 0.65rem;
  border: 1px solid #cbd5e1;
  border-radius: 6px;
  font: inherit;
}

button, .btn {
  display: inline-block;
  background-color: var(--accent);
  color: #ffffff;
  border: none;
  padding: 0.7rem 1.3rem;
  border-radius: 6px;
  font-weight: 600;
  text-decoration: none;
  cursor: pointer;
  margin-top: 0.5rem;
}

button:hover, .btn:hover {
  background-color: var(--primary);
}

footer {
  background-color: #0f172a;
  color: #94a3b8;
  text-align: center;
  padding: 1.25rem;
  margin-top: 3rem;
  font-size: 0.9rem;
}
2. Home Page (index.html)
HTML
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Official website of NovaTech Club — student robotics, coding workshops, and campus hackathons.">
  <meta name="author" content="NovaTech Student Committee">
  <title>Home | NovaTech College Club</title>
  <link rel="icon" type="image/svg+xml" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><rect width='100' height='100' rx='20' fill='%232563eb'/><text x='50' y='68' font-size='55' text-anchor='middle' fill='white' font-family='sans-serif'>N</text></svg>">
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <div class="nav-container">
      <a href="index.html" class="brand">NovaTech Club</a>
      <nav aria-label="Primary Navigation">
        <ul>
          <li><a href="index.html" class="active">Home</a></li>
          <li><a href="about.html">About</a></li>
          <li><a href="registration.html">Registration</a></li>
          <li><a href="contact.html">Contact</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <main>
    <section class="hero">
      <h1>Welcome to NovaTech College Club</h1>
      <p>We are a student-driven engineering and software community dedicated to hands-on building, peer mentorship, and inter-college innovation.</p>
      <a href="registration.html" class="btn">Join the Club</a>
    </section>

    <section>
      <h2>Core Club Activities</h2>
      <div class="grid">
        <article class="card">
          <h3>Weekly Coding Labs</h3>
          <p>Collaborative sessions covering full-stack web development, open-source contributions, and competitive algorithms.</p>
        </article>
        <article class="card">
          <h3>Robotics & IoT Builds</h3>
          <p>Hardware prototyping with microcontrollers, sensors, and autonomous navigation kits in the campus makerspace.</p>
        </article>
        <article class="card">
          <h3>Annual TechFest & Hackathons</h3>
          <p>24-hour product sprints, alumni industry panels, and live project showcases open to all undergraduate majors.</p>
        </article>
      </div>
    </section>

    <section>
      <h2>Fall Semester Events Schedule</h2>
      <table>
        <thead>
          <tr>
            <th>Date</th>
            <th>Event Title</th>
            <th>Venue</th>
            <th>Lead Coordinator</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Nov 24, 2026</td>
            <td>Intro to Git & Web Deployment</td>
            <td>CS Block, Lab 204</td>
            <td>Aarav Sharma</td>
          </tr>
          <tr>
            <td>Dec 05, 2026</td>
            <td>Line-Follower Bot Challenge</td>
            <td>Innovation Makerspace</td>
            <td>Meera Nair</td>
          </tr>
          <tr>
            <td>Dec 14, 2026</td>
            <td>Winter Mini-Hackathon</td>
            <td>Main Auditorium</td>
            <td>Rohan Verma</td>
          </tr>
        </tbody>
      </table>
    </section>
  </main>

  <footer>
    <p>&copy; 2026 NovaTech College Club. All rights reserved.</p>
  </footer>
</body>
</html>
3. About Page (about.html)
HTML
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Learn about NovaTech College Club's mission, history, and student leadership team.">
  <title>About Us | NovaTech College Club</title>
  <link rel="icon" type="image/svg+xml" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><rect width='100' height='100' rx='20' fill='%232563eb'/><text x='50' y='68' font-size='55' text-anchor='middle' fill='white' font-family='sans-serif'>N</text></svg>">
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <div class="nav-container">
      <a href="index.html" class="brand">NovaTech Club</a>
      <nav aria-label="Primary Navigation">
        <ul>
          <li><a href="index.html">Home</a></li>
          <li><a href="about.html" class="active">About</a></li>
          <li><a href="registration.html">Registration</a></li>
          <li><a href="contact.html">Contact</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <main>
    <section class="hero">
      <h1>About NovaTech Club</h1>
      <p>Founded in 2019 by twelve computer science and electronics undergraduates, NovaTech bridges classroom theory and practical engineering. Today, over 140 active members collaborate on open-source software, embedded systems, and national design competitions.</p>
    </section>

    <section>
      <h2>Club Details & Tracks</h2>
      <div class="card">
        <p><strong>Faculty Advisor:</strong> Dr. Kavita Deshmukh (Department of Computer Science)</p>
        <p><strong>Meeting Schedule:</strong> Every Wednesday & Friday, 4:30 PM – 6:30 PM</p>
        <p><strong>Eligibility:</strong> Open to all enrolled students across all departments; no prior coding experience required.</p>
      </div>
    </section>

    <section>
      <h2>2026–2027 Executive Board</h2>
      <div class="grid">
        <article class="card">
          <h3>Aarav Sharma</h3>
          <p><strong>President</strong> — B.Tech CSE (4th Year)</p>
          <p>Oversees club operations, industry partnerships, and web architecture workshops.</p>
        </article>
        <article class="card">
          <h3>Meera Nair</h3>
          <p><strong>Vice President & Robotics Lead</strong> — B.Tech ECE (3rd Year)</p>
          <p>Manages hardware inventory, embedded systems labs, and inter-college bot competitions.</p>
        </article>
        <article class="card">
          <h3>Rohan Verma</h3>
          <p><strong>Events & Community Secretary</strong> — B.Sc IT (3rd Year)</p>
          <p>Coordinates hackathons, member onboarding, and campus outreach.</p>
        </article>
      </div>
    </section>
  </main>

  <footer>
    <p>&copy; 2026 NovaTech College Club. All rights reserved.</p>
  </footer>
</body>
</html>
4. Registration Page (registration.html)
HTML
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Register as a student member of NovaTech College Club.">
  <title>Student Registration | NovaTech College Club</title>
  <link rel="icon" type="image/svg+xml" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><rect width='100' height='100' rx='20' fill='%232563eb'/><text x='50' y='68' font-size='55' text-anchor='middle' fill='white' font-family='sans-serif'>N</text></svg>">
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <div class="nav-container">
      <a href="index.html" class="brand">NovaTech Club</a>
      <nav aria-label="Primary Navigation">
        <ul>
          <li><a href="index.html">Home</a></li>
          <li><a href="about.html">About</a></li>
          <li><a href="registration.html" class="active">Registration</a></li>
          <li><a href="contact.html">Contact</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <main>
    <h1>Student Membership Registration</h1>
    <p style="margin-bottom: 1.5rem;">Complete the form below to apply for membership in the 2026–2027 academic session.</p>

    <form action="#" method="post" onsubmit="event.preventDefault(); alert('Thank you! Your NovaTech Club registration has been submitted.'); this.reset();">
      <div class="form-group">
        <label for="fullName">Full Name *</label>
        <input type="text" id="fullName" name="fullName" placeholder="e.g., Priya Patel" required>
      </div>

      <div class="form-group">
        <label for="studentId">Student Roll Number / ID *</label>
        <input type="text" id="studentId" name="studentId" placeholder="e.g., 2026CS1042" required>
      </div>

      <div class="form-group">
        <label for="email">College Email Address *</label>
        <input type="email" id="email" name="email" placeholder="priya.patel@college.edu" required>
      </div>

      <div class="form-group">
        <label for="department">Department & Year *</label>
        <select id="department" name="department" required>
          <option value="">-- Select Your Department --</option>
          <option value="cse">Computer Science & Engineering</option>
          <option value="ece">Electronics & Communication</option>
          <option value="mech">Mechanical Engineering</option>
          <option value="other">Other Department</option>
        </select>
      </div>

      <div class="form-group">
        <label for="track">Primary Interest Track *</label>
        <select id="track" name="track" required>
          <option value="web">Web & App Development</option>
          <option value="robotics">Robotics & Embedded Systems</option>
          <option value="ai">AI & Data Science</option>
          <option value="design">UI/UX & Event Management</option>
        </select>
      </div>

      <div class="form-group">
        <label for="goals">What would you like to build or learn?</label>
        <textarea id="goals" name="goals" rows="3" placeholder="Tell us briefly about your interests or past projects..."></textarea>
      </div>

      <button type="submit">Submit Application</button>
    </form>
  </main>

  <footer>
    <p>&copy; 2026 NovaTech College Club. All rights reserved.</p>
  </footer>
</body>
</html>
5. Contact Page (contact.html)
HTML
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Contact details, campus lab location, and office hours for NovaTech College Club.">
  <title>Contact Us | NovaTech College Club</title>
  <link rel="icon" type="image/svg+xml" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><rect width='100' height='100' rx='20' fill='%232563eb'/><text x='50' y='68' font-size='55' text-anchor='middle' fill='white' font-family='sans-serif'>N</text></svg>">
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <div class="nav-container">
      <a href="index.html" class="brand">NovaTech Club</a>
      <nav aria-label="Primary Navigation">
        <ul>
          <li><a href="index.html">Home</a></li>
          <li><a href="about.html">About</a></li>
          <li><a href="registration.html">Registration</a></li>
          <li><a href="contact.html" class="active">Contact</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <main>
    <h1>Contact NovaTech Club</h1>
    <p>Have questions about upcoming workshops, sponsorship, or project collaborations? Reach out through any channel below.</p>

    <div class="grid">
      <article class="card">
        <h3>Email & Phone</h3>
        <p><strong>General Inquiries:</strong> <a href="mailto:novatech@college.edu">novatech@college.edu</a></p>
        <p><strong>Events Desk:</strong> <a href="mailto:events.novatech@college.edu">events.novatech@college.edu</a></p>
        <p><strong>Student Helpdesk:</strong> +91 98765 43210</p>
      </article>

      <article class="card">
        <h3>Campus Location</h3>
        <p>Room 108, Innovation & Makerspace Wing</p>
        <p>Academic Block B, Central Engineering Campus</p>
        <p><strong>Drop-in Hours:</strong> Mon–Fri, 3:30 PM – 6:00 PM</p>
      </article>
    </div>

    <section>
      <h2>Send a Quick Message</h2>
      <form action="#" method="post" onsubmit="event.preventDefault(); alert('Message sent! Our coordinators will reply within 24 hours.'); this.reset();">
        <div class="form-group">
          <label for="senderName">Your Name *</label>
          <input type="text" id="senderName" name="senderName" required>
        </div>
        <div class="form-group">
          <label for="senderEmail">Your Email *</label>
          <input type="email" id="senderEmail" name="senderEmail" required>
        </div>
        <div class="form-group">
          <label for="message">Message *</label>
          <textarea id="message" name="message" rows="4" required></textarea>
        </div>
        <button type="submit">Send Message</button>
      </form>
    </section>
  </main>

  <footer>
    <p>&copy; 2026 NovaTech College Club. All rights reserved.</p>
  </footer>
</body>
</html>
Step 8: Internal Link & Requirement Verification
Navigation & Active States: Every page links to index.html, about.html, registration.html, and contact.html via identical relative paths, highlighting the current page with class="active".

Call-to-Action & Contact Links: The Join the Club button on index.html routes directly to registration.html, and the email links on contact.html use valid mailto: URIs.

Metadata & Favicon: Every HTML file includes UTF-8 charset, responsive viewport settings, page-specific <meta name="description"> tags, and a self-contained SVG data-URI favicon that works offline without external image dependencies.