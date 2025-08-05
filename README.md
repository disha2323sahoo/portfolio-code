<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Disha Sahoo - Portfolio</title>
  <link href="https://fonts.googleapis.com/css2?family=Outfit:wght@300;500;700&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      font-family: 'Outfit', sans-serif;
      background-color: #f5f3ff;
      color: #2d0c57;
      line-height: 1.6;
      transition: background-color 0.3s ease, color 0.3s ease;
    }
    body.dark-mode {
      background-color: #440088;
      color: #000;
    }
    .toggle-button {
      position: fixed;
      top: 10px;
      right: 10px;
      background-color: #c8b6ff;
      color: #2d0c57;
      border: none;
      padding: 10px 20px;
      border-radius: 5px;
      cursor: pointer;
      z-index: 1000;
    }
    .toggle-button::before {
      content: '\2600';
      margin-right: 10px;
      display: inline-block;
      transition: transform 0.3s;
    }
    body.dark-mode .toggle-button::before {
      content: '\1F319';
      transform: rotate(360deg);
    }

    nav.taskbar {
      position: fixed;
      top: 0;
      width: 100%;
      background: linear-gradient(90deg, #2e0a64, #074682);
      padding: 1rem;
      display: flex;
      justify-content: center;
      gap: 2rem;
      z-index: 999;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    nav.taskbar a {
      color: #fff;
      text-decoration: none;
      font-weight: 600;
      transition: color 0.3s;
    }
    nav.taskbar a:hover {
      color: #cba7ff;
    }
    body.dark-mode nav.taskbar {
      background: linear-gradient(90deg, #301755, #4d2a7d);
    }
    body.dark-mode nav.taskbar a {
      color: #fff;
    }
    body.dark-mode nav.taskbar a:hover {
      color: #d0bdf4;
    }

    header {
      background: linear-gradient(90deg, #8a2fd4, #8c76cd);
      padding: 3rem 1rem;
      text-align: center;
    }
    .header-profile img {
      width: 150px;
      height: 150px;
      border-radius: 50%;
      object-fit: cover;
      border: 4px solid #a770ff;
    }
    .header-profile h1 {
      margin-top: 1rem;
      font-size: 2.5rem;
      color: #2d0c57;
    }
    body.dark-mode .header-profile h1 {
      color: #fff;
    }
    section {
      padding: 3rem 2rem;
      max-width: 900px;
      margin: auto;
    }
    h2 {
      font-size: 2rem;
      color: #2d0c57;
      margin-bottom: 1rem;
      position: relative;
    }
    body.dark-mode h2 {
      color: #fff;
    }
    h2::before {
      content: '';
      position: absolute;
      left: 0;
      bottom: -5px;
      width: 100%;
      height: 3px;
      background-color: #c19bf5;
    }
    body.dark-mode .tag, body.dark-mode .skill-category, body.dark-mode .about-animate, body.dark-mode .project {
      color: #000;
      background-color: #f3e9ff;
    }
    .project, .skill-category, .about-animate {
      background-color: #ede7f6;
      padding: 1.5rem;
      border-radius: 8px;
      margin-bottom: 1.5rem;
      animation: fadeSlide 1s ease forwards;
    }
    .resume-button {
      background-color: #7b2cbf;
      color: #fff;
      padding: 10px 20px;
      text-decoration: none;
      border-radius: 5px;
      display: inline-block;
      margin-top: 1rem;
    }
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 1rem;
    }
    .skill-category h3 {
      color: #4c1d95;
      margin-bottom: 0.5rem;
    }
    .tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.5rem;
    }
    .tag {
      background-color: #d0bdf4;
      padding: 0.4rem 0.8rem;
      border-radius: 20px;
      font-size: 0.85rem;
      color: #3c096c;
      cursor: pointer;
      transition: transform 0.2s;
    }
    .tag:hover {
      transform: scale(1.05);
      background-color: #c19bf5;
    }
    .contact a {
      color: #930101;
      display: block;
      margin: 0.3rem 0;
    }
    .skill-bar {
      background-color: #e0d4f7;
      border-radius: 10px;
      overflow: hidden;
      margin-top: 0.5rem;
    }
    .skill-bar-fill {
      height: 10px;
      border-radius: 10px;
      background: linear-gradient(90deg, #9d4edd, #c77dff);
      width: 0;
      animation: fillBar 2s ease-in-out forwards;
    }
    @keyframes fillBar {
      0% { width: 0; }
      100% { width: var(--fill-width); }
    }
    @keyframes fadeSlide {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }
    footer {
      text-align: center;
      padding: 2rem;
      font-size: 0.9rem;
      background-color: #3e1f6d;
      color: #fff;
    }
    footer a {
      color: #cba7ff;
      text-decoration: none;
    }
    footer .credits {
      margin-top: 1rem;
      font-size: 0.8rem;
    }
  </style>
</head>
<body>
  <button class="toggle-button" onclick="toggleMode()">Toggle Theme</button>

  <nav class="taskbar">
    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#skills">Skills</a>
    <a href="#projects">Projects</a>
    <a href="#contact">Contact</a>
  </nav>

  <header class="header-profile" id="home">
    <img src="disha.jpg" alt="Disha Sahoo">
    <h1>DISHA SAHOO</h1>
    <p><br>I'm a BCA (Bachelor of Computer Applications) student with a passion for technology, problem-solving, and modern computing systems. I enjoy exploring how today's applications are built, deployed, and optimized using emerging technologies. Whether it's web development, software design, or digital transformation, I'm always eager to learn, create, and grow.</p>
  </header>

  <section class="about-animate" id="about">
    <h2>About Me</h2>
    <p><p>Hi, I'm Disha Sahoo, a curious and motivated BCA (Bachelor of Computer Applications) student with a keen interest in modern computing systems and digital transformation. I enjoy learning how today’s applications are built, deployed, and scaled using emerging technologies.</p>
    <p>Lately, I've been exploring the world of cloud platforms like AWS, Azure, and Google Cloud, where I’m learning how businesses build reliable, secure, and scalable solutions. My academic journey has also given me a strong base in programming (Python, Java, C), web development (HTML, CSS, JavaScript), and database management.</p>
    <p>I’m passionate about applying these skills to solve real-world problems—whether that’s automating tasks, deploying web apps, or managing virtual resources efficiently. I also value clean code, teamwork, and continuous learning.</p>
    <p>Currently, I’m looking for opportunities to grow through internships and project work, especially in areas like cloud infrastructure, DevOps, or software development. My goal is to keep building, keep learning, and contribute to impactful digital solutions.</p></section>

  <section id="skills">
    <h2>My Skills</h2>
    <p>I'm passionate about technology and continuously expanding my skill set. From programming languages to design tools, enjoy learning new technologies and applying them to create innovative solutions.I Here's a overview of my technical abilities and the tools I work with to bring ideas to life.</p>
    <div class="skills-grid">
      <div class="skill-category">
        <h3>Programming Languages</h3>
        <P>Core programming languages I use for software development, web applications, and problem-solving. These form the foundation of my technical skills.</P>
        <div class="tags">
          <span class="tag">C++</span>
          <span class="tag">Python</span>
          <span class="tag">Java</span>
          <span class="tag">JavaScript</span>
          <span class="tag">HTML</span>
          <span class="tag">CSS</span>
        </div>
        <div class="skill-bar"><div class="skill-bar-fill" style="--fill-width: 85%;"></div></div>
      </div>
      <div class="skill-category">
        <h3>UI/UX Development</h3>
        <P>Design skills focused on creating intuitive user experiences and visually appealing interfaces that engage users and solve real problems.</P>
        <div class="tags">
          <span class="tag">User Interface Design</span>
          <span class="tag">Responsive Design</span>
          <span class="tag">Wireframing</span>
          <span class="tag">Prototyping</span>
          <span class="tag">User Experience</span>
        </div>
        <div class="skill-bar"><div class="skill-bar-fill" style="--fill-width: 75%;"></div></div>
      </div>
      <div class="skill-category">
        <h3>Frontend Technologies</h3>
        <P>Modern web development technologies I use to build responsive, interactive, and user-friendly web applications.</P>
        <div class="tags">
          <span class="tag">React</span>
          <span class="tag">HTML5</span>
          <span class="tag">CSS3</span>
          <span class="tag">JavaScript ES6+</span>
          <span class="tag">Tailwind CSS</span>
          <span class="tag">Bootstrap</span>
        </div>
        <div class="skill-bar"><div class="skill-bar-fill" style="--fill-width: 80%;"></div></div>
      </div>
      <div class="skill-category">
        <h3>Tools & Others</h3>
        <P>Essential development tools and soft skills that enhance my productivity and enable effective collaboration in development projects.</P>
        <div class="tags">
          <span class="tag">Git</span>
          <span class="tag">GitHub</span>
          <span class="tag">Figma</span>
          <span class="tag">Adobe XD</span>
          <span class="tag">VS Code</span>
          <span class="tag">Problem Solving</span>
        </div>
        <div class="skill-bar"><div class="skill-bar-fill" style="--fill-width: 70%;"></div></div>
      </div>
    </div>
  </section>
  </section>

  <section id="projects">
    <h2>Projects</h2>
    <P>Here are some of the projects I've worked on that showcase my programming skills and problem-solving abilities. Each project represents a learning journey and demonstrates different aspects of software development, from system design to user interface creation.</P>
   <div class="project">
      <h3>STUDENT MANAGEMENT SYSTEM</h3>
      <p>I have made a project on Student management system using OOP's concept in C++ which involves functionalities like user admission process and student details.</p>
      <H4>Key Features:</H4>
<UL>
  <LI>User registration and login</LI>
  <LI>Student data management</LI>
  <LI>Grade tracking</LI>
  <LI>Report generation</LI>
  </UL>
    </div>
    <div class="project">
      <h3>LIBRARY MANAGEMENT SYSTEM (C++ & Java AWT)</h3>
      <p>This system manages everyday operations of a library. By automating functions, it improves efficiency, reduces errors, and offers a more streamlined experience. Built with Java Swing and C++.</p>
      <H4>Key Features:</H4>
<UL>
    <LI>Book inventory management</LI>
    <LI>Member registration</LI>
    <LI>Borrowing/return system</LI>
    <LI>Fine calculation</LI>
    <LI>Search functionality</LI>
  </UL>
    </div>
    <div class="project">
      <h3>THE WORLD'S BIGGEST UNIVERSITY</h3>
      <p>An informational project exploring large-scale universities like IGNOU that enable global education through flexibility, technology, and outreach.</p>
      <H4>Key Features:</H4>
<UL>
    <LI>Responsive web design</LI>
    <LI>Interactive course catalog</LI>
    <LI>Student portal mockup</LI>
    <LI>Modern UI/UX design</LI>
    </UL>    
</div>
  </section>

   <section class="contact" id="contact">
  <h2>Contact</h2>
  <p>Phone: 8018986248</p>
  <a href="mailto:dishasahoo2323@gmail.com">Email: dishasahoo2323@gmail.com</a>
  <a href="https://www.linkedin.com/in/disha-sahoo-52039b306">LinkedIn: Disha Sahoo</a>
  <a href="https://github.com/disha2323sahoo">GitHub: disha2323sahoo</a>
  <a class="resume-button" href="resume.pdf" download>Download Resume</a>

  <h3 style="margin-top:2rem;">Contact Me</h3>
  <form style="display: flex; flex-direction: column; gap: 1rem; max-width: 500px; margin-top: 1rem;">
    <input type="text" placeholder="Your Name" required style="padding: 10px; border-radius: 5px; border: 1px solid #ccc;">
    <input type="email" placeholder="Your Email" required style="padding: 10px; border-radius: 5px; border: 1px solid #ccc;">
    <input type="text" placeholder="Subject" required style="padding: 10px; border-radius: 5px; border: 1px solid #ccc;">
    <textarea placeholder="Your Message" rows="5" required style="padding: 10px; border-radius: 5px; border: 1px solid #ccc;"></textarea>
    <button type="submit" style="padding: 10px 20px; background-color: #7b2cbf; color: white; border: none; border-radius: 5px; cursor: pointer;">Submit</button>
  </form>
</section>
   <footer>
    <p>Quick Links</p>
    <a href="#">Home</a> | <a href="#about">About</a> | <a href="#skills">Skills</a> | <a href="#projects">Projects</a> | <a href="#contact">Contact</a>
    <p class="credits">Connect: <a href="mailto:dishasahoo@example.com">dishasahoo@example.com</a> | +91 8018986248<br>
    Made with ❤️ by Disha Sahoo<br>
    © 2025 All rights reserved.<br>
    <a href="#top">Back to Top ↑</a></p>
  </footer>
  <script>
    function toggleMode() {
      document.body.classList.toggle('dark-mode');
    }
  </script>
</body>
</html>
