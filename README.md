# react-router-dom
This is a simple React application demonstrating how to use React Router DOM for client-side routing. The project features a basic navigation system with multiple pages including Home, About, and Contact.

## Demo
![Screenshot 2025-05-23 160739](https://github.com/user-attachments/assets/cb4142bd-d85a-4656-b1a6-136f0857c73f)
![Screenshot 2025-05-23 160750](https://github.com/user-attachments/assets/b479f74e-6aa5-4073-9111-933fa1f9596e)
![Screenshot 2025-05-23 160803](https://github.com/user-attachments/assets/1d043ceb-827a-4a17-bce1-441cd08c5624)


## Features
Client-side routing with React Router DOM v6

Navigation bar with links to different pages

Home page with welcome message and banner image

About page describing the project and mission

Contact page with contact info and a sample contact form

404 Not Found page for unmatched routes

Responsive and clean UI with simple CSS

Getting Started
## rerequisites
Node.js (v14 or newer recommended)
```
npm (comes with Node.js)
```
## Installation
```
cd my-router-app
```
## Install dependencies:
```
npm install
```
## Start the development server:
```
npm start
```
## Open your browser and navigate to:

http://localhost:3000
# Project Structure

my-router-app/
├── public/
│   ├── index.html
│   └── banner.jpg          # Banner image used in Home page
├── src/
│   ├── components/
│   │   ├── About.js
│   │   ├── Contact.js
│   │   ├── Home.js
│   │   ├── Navbar.js
│   │   └── NotFound.js
│   ├── App.js
│   ├── App.css
│   └── index.js
├── package.json
└── README.md

# Code Overview
## src/App.js
```
import React from 'react';
import { BrowserRouter as Router, Routes, Route } from 'react-router-dom';
import Navbar from './components/Navbar';
import Home from './components/Home';
import About from './components/About';
import Contact from './components/Contact';
import NotFound from './components/NotFound';
import './App.css';

function App() {
  return (
    <Router>
      <Navbar />
      <div className="main-content">
        <Routes>
          <Route path="/" element={<Home />} />
          <Route path="/about" element={<About />} />
          <Route path="/contact" element={<Contact />} />
          <Route path="*" element={<NotFound />} />
        </Routes>
      </div>
    </Router>
  );
}

export default App;
```
## src/components/Navbar.js
```
import React from 'react';
import { Link } from 'react-router-dom';
import './Navbar.css';

function Navbar() {
  return (
    <nav className="navbar">
      <ul>
        <li><Link to="/">Home</Link></li>
        <li><Link to="/about">About</Link></li>
        <li><Link to="/contact">Contact</Link></li>
      </ul>
    </nav>
  );
}

export default Navbar;
```
## src/components/Home.js
```
import React from 'react';

function Home() {
  return (
    <div>
      <h2>Welcome to the Home Page</h2>

      <img
        src="/banner.jpg"
        alt="Banner"
        style={{ width: '100%', maxWidth: '600px', borderRadius: '10px', marginTop: '1rem' }}
      />

      <section style={{ marginTop: '2rem', lineHeight: '1.6', color: '#444' }}>
        <p>
          This is a sample React application demonstrating how to use React Router for client-side routing.
          Navigate through the pages using the menu above.
        </p>

        <h3>Features:</h3>
        <ul>
          <li>Simple and clean navigation with React Router DOM</li>
          <li>Multiple pages with route handling</li>
          <li>Responsive design with basic CSS styling</li>
          <li>Easy to extend and customize</li>
        </ul>

        <p>
          Feel free to explore the About and Contact pages to see how routing works in React applications.
        </p>
      </section>
    </div>
  );
}

export default Home;
```
## src/components/About.js
```
import React from 'react';

function About() {
  return (
    <div style={{ maxWidth: '700px', margin: '0 auto', lineHeight: '1.6', color: '#444' }}>
      <h2>About Us</h2>
      
      <p>
        Welcome to our React Router demo app! This project is designed to showcase how to implement client-side routing using <strong>React Router DOM</strong>.
        It is a simple, clean, and modular React application with multiple pages and easy navigation.
      </p>
      
      <h3>Our Mission</h3>
      <p>
        To help developers learn React routing quickly by providing a practical, hands-on example.
        We believe in building web applications that are user-friendly, fast, and scalable.
      </p>
      
      <h3>What We Offer</h3>
      <ul>
        <li>Clear, maintainable code using React best practices</li>
        <li>Simple navigation with React Router</li>
        <li>Easy customization and extensibility</li>
        <li>Responsive design and good user experience</li>
      </ul>
      
      <p>
        Feel free to explore the app and use it as a starting point for your projects!
      </p>
    </div>
  );
}

export default About;
```
## src/components/Contact.js
```
import React from 'react';

function Contact() {
  return (
    <div style={{ maxWidth: '600px', margin: '0 auto' }}>
      <h2>Contact Us</h2>

      <p>
        We'd love to hear from you! Whether you have questions, feedback, or want to say hello, feel free to reach out.
      </p>

      <h3>Our Contact Details</h3>
      <ul>
        <li>Email: support@example.com</li>
        <li>Phone: +1 (555) 123-4567</li>
        <li>Address: 123 React Street, JavaScript City, Web</li>
      </ul>

      <h3>Send Us a Message</h3>
      <form>
        <div style={{ marginBottom: '1rem' }}>
          <label htmlFor="name" style={{ display: 'block', marginBottom: '0.5rem' }}>Name:</label>
          <input type="text" id="name" name="name" style={{ width: '100%', padding: '0.5rem' }} />
        </div>

        <div style={{ marginBottom: '1rem' }}>
          <label htmlFor="email" style={{ display: 'block', marginBottom: '0.5rem' }}>Email:</label>
          <input type="email" id="email" name="email" style={{ width: '100%', padding: '0.5rem' }} />
        </div>

        <div style={{ marginBottom: '1rem' }}>
          <label htmlFor="message" style={{ display: 'block', marginBottom: '0.5rem' }}>Message:</label>
          <textarea id="message" name="message" rows="5" style={{ width: '100%', padding: '0.5rem' }} />
        </div>

        <button type="submit" style={{ backgroundColor: '#0077cc', color: '#fff', padding: '0.5rem 1rem', border: 'none', borderRadius: '4px', cursor: 'pointer' }}>
          Send
        </button>
      </form>
    </div>
  );
}

export default Contact;
```
## src/components/NotFound.js
```
import React from 'react';

function NotFound() {
  return <h2 style={{ textAlign: 'center', marginTop: '2rem' }}>404 - Page Not Found</h2>;
}

export default NotFound;
src/App.css
css
Copy
Edit
body {
  font-family: Arial, sans-serif;
  margin: 0;
  background-color: #f2f2f2;
}

.main-content {
  padding: 2rem;
}

h2 {
  color: #333;
}
```
## src/components/Navbar.css

```
.navbar {
  background-color: #0077cc;
  padding: 1rem;
}

.navbar ul {
  list-style: none;
  display: flex;
  gap: 1rem;
  margin: 0;
  padding: 0;
}

.navbar a {
  color: white;
  text-decoration: none;
  font-weight: bold;
}

.navbar a:hover {
  text-decoration: underline;
}

```

## Usage
Use the navigation bar at the top to visit different pages

The Home page shows a banner image and information

The About page explains the project goals

The Contact page includes contact details and a simple form

Navigate to an invalid URL to see the 404 Not Found page

## Customization
Replace public/banner.jpg with your own banner image

Modify components inside src/components/ to add your content

Update styles in src/App.css and src/components/Navbar.css for custom look

## Technologies Used
React 18

React Router DOM 6

CSS for styling
