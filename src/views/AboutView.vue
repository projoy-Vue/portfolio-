<template>
  <section class="about" id="about">
    <div class="container">
      <!-- Section Title -->
      <h2 class="section-title">About Me</h2>
      <p class="section-subtitle">
        Discover who I am, my passion for development, and how I can help bring your ideas to life.
      </p>

      <div class="about-content">
        <!-- Personal Details -->
        <div class="about-text">
          <h3>Hi, I'm [Your Name]</h3>
          <p>
            I'm a passionate front-end developer with a keen eye for detail and a love for creating stunning, user-friendly web applications. 
            With [X years] of experience in the industry, I've worked on various projects, helping businesses and individuals build their online presence.
          </p>
          <p>
            My expertise includes HTML, CSS, JavaScript, React, Vue.js, and responsive web design. I thrive on challenges, continuously learning new technologies to stay ahead in this ever-evolving field.
          </p>
          <a href="#contact" class="cta-button">Let’s Collaborate</a>
        </div>

        <!-- Image/Illustration -->
        <div class="about-image">
          <img :src="url" alt="Your Name" />
        </div>
      </div>

      <!-- Skills/Highlights Section -->
      <div class="skills-highlights">
        <h3>What I Bring to the Table</h3>
        <ul class="skills-list">
          <li><strong>Clean Code:</strong> Writing maintainable and efficient code.</li>
          <li><strong>Responsive Design:</strong> Crafting layouts that shine on all devices.</li>
          <li><strong>Framework Expertise:</strong> Vue.js, React, and more.</li>
          <li><strong>Team Collaboration:</strong> Working seamlessly with teams or independently.</li>
        </ul>
      </div>

      <!-- Fun Facts/Stats -->
      <div class="fun-facts">
        <h3>Did You Know?</h3>
        <div class="facts-grid">
          <div class="fact-item">
            <h4>50+</h4>
            <p>Projects Completed</p>
          </div>
          <div class="fact-item">
            <h4>10K+</h4>
            <p>Lines of Code Written</p>
          </div>
          <div class="fact-item">
            <h4>5+</h4>
            <p>Years of Experience</p>
          </div>
          <div class="fact-item">
            <h4>20+</h4>
            <p>Happy Clients Worldwide</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { gsap } from "gsap";

export default {
  name: "About",
  data(){
    return {
      url: ("https://demo.sparklewpthemes.com/buzzstorepro/eshopjet/wp-content/uploads/sites/8/2021/01/image-11.png") //require
    }
  },
  mounted() {
    // GSAP Animations
    gsap.from(".about", { opacity: 0, y: 50, duration: 1 });
    gsap.from(".about-image img", { opacity: 0, scale: 0.8, duration: 1.2, delay: 0.5 });
  },
};
</script>

<style scoped>
/* General Styles */
.about {
  padding: 4rem 1rem;
  text-align: center;
  background-color: var(--bg-color);
  color: var(--text-color);
}

.container {
  max-width: 1000px;
  margin: 0 auto;
}

.section-title {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.section-subtitle {
  font-size: 1.2rem;
  margin-bottom: 2rem;
  color: var(--secondary-text-color);
}

/* About Content Styles */
.about-content {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 2rem;
}

.about-text {
  flex: 1;
  text-align: left;
}

.about-text h3 {
  font-size: 1.8rem;
  margin-bottom: 1rem;
}

.about-text p {
  font-size: 1rem;
  line-height: 1.6;
  margin-bottom: 1rem;
}

.cta-button {
  display: inline-block;
  margin-top: 1rem;
  padding: 0.75rem 1.5rem;
  background-color: var(--primary-color);
  color: #fff;
  border-radius: 5px;
  text-decoration: none;
  transition: background-color 0.3s ease;
}

.cta-button:hover {
  background-color: var(--primary-color-hover);
}

/* Image Styles */
.about-image {
  flex: 1;
}

.about-image img {
  width: 100%;
  border-radius: 10px;
  box-shadow: var(--box-shadow);
}

/* Skills/Highlights Styles */
.skills-highlights {
  margin-top: 3rem;
}

.skills-list {
  list-style: none;
  padding: 0;
  margin: 0;
  text-align: left;
}

.skills-list li {
  font-size: 1rem;
  line-height: 1.8;
  margin-bottom: 0.5rem;
}

/* Fun Facts Styles */
.fun-facts {
  margin-top: 3rem;
}

.facts-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 2rem;
  text-align: center;
}

.fact-item h4 {
  font-size: 2rem;
  color: var(--primary-color);
  margin-bottom: 0.5rem;
}

.fact-item p {
  font-size: 1rem;
  color: var(--secondary-text-color);
}
@media  (max-width: 768px) {
  /*  */
  
}
</style>
