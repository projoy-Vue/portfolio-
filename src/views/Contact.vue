<template>
    <section class="contact" id="contact">
      <div class="container">
        <h2 class="section-title">Get in Touch</h2>
        <p class="section-subtitle">
          I’d love to hear from you! Fill out the form below or connect via social media.
        </p>
  
        <!-- Contact Form -->
        <form class="contact-form">
          <div class="form-group">
            <input type="text" placeholder="Your Name" v-model="form.name" required />
          </div>
          <div class="form-group">
            <input type="email" placeholder="Your Email" v-model="form.email" required />
          </div>
          <div class="form-group">
            <textarea placeholder="Your Message" v-model="form.message" rows="5" required></textarea>
          </div>
          <button type="submit" @click.prevent="submitForm" class="submit-button">Send Message</button>
        </form>
  
        <!-- Social Media Links -->
        <div class="social-links">
          <h3>Connect with me:</h3>
          <ul>
            <li><a href="https://linkedin.com" target="_blank" rel="noopener noreferrer"><i class="fab fa-linkedin"></i> LinkedIn</a></li>
            <li><a href="https://github.com" target="_blank" rel="noopener noreferrer"><i class="fab fa-github"></i> GitHub</a></li>
            <li><a href="https://twitter.com" target="_blank" rel="noopener noreferrer"><i class="fab fa-twitter"></i> Twitter</a></li>
          </ul>
        </div>
  
        <!-- FAQ Accordion -->
        <div class="faq">
          <h3>Frequently Asked Questions</h3>
          <div class="faq-item" v-for="(item, index) in faqs" :key="index">
            <div class="faq-question" @click="toggleFAQ(index)">
              {{ item.question }}
              <span class="toggle-icon">{{ item.open ? '-' : '+' }}</span>
            </div>
            <div class="faq-answer" v-if="item.open">{{ item.answer }}</div>
          </div>
        </div>
  
        <!-- Fun Facts Section -->
        <div class="fun-facts">
          <h3>Did You Know?</h3>
          <ul>
            <li>I’ve completed over <strong>50+ projects</strong> for clients worldwide.</li>
            <li>My portfolio has been viewed <strong>10,000+ times</strong> in the past year.</li>
            <li>I’m skilled in over <strong>10 programming languages and frameworks</strong>.</li>
          </ul>
        </div>
      </div>
    </section>
  </template>
  
  <script>
  import { gsap } from "gsap";
  
  export default {
    name: "Contact",
    data() {
      return {
        form: {
          name: "",
          email: "",
          message: "",
        },
        faqs: [
          {
            question: "What services do you offer?",
            answer: "I specialize in front-end development, responsive design, and web optimization.",
            open: false,
          },
          {
            question: "How soon can I expect a response?",
            answer: "I usually respond within 24 hours on weekdays.",
            open: false,
          },
          {
            question: "Do you take freelance projects?",
            answer: "Yes, I’m open to freelance opportunities and collaborations.",
            open: false,
          },
        ],
      };
    },
    methods: {
      submitForm() {
        alert(`Thank you, ${this.form.name}. Your message has been sent!`);
        this.form.name = "";
        this.form.email = "";
        this.form.message = "";
      },
      toggleFAQ(index) {
        this.faqs[index].open = !this.faqs[index].open;
      },
    },
    mounted() {
      gsap.from(".contact", { opacity: 0, y: 50, duration: 1 });
    },
  };
  </script>
  
  <style scoped>
  /* General Styles */
  .contact {
    padding: 4rem 1rem;
    text-align: center;
    background-color: var(--bg-color);
    color: var(--text-color);
  }
  
  .container {
    max-width: 800px;
    margin: 0 auto;
  }
  
  .section-title {
    font-size: 2.5rem;
    margin-bottom: 1rem;
  }
  
  .section-subtitle {
    font-size: 1.2rem;
    margin-bottom: 2rem;
  }
  
  /* Contact Form Styles */
  .contact-form {
    display: grid;
    gap: 1rem;
    margin-bottom: 3rem;
  }
  
  .form-group input,
  .form-group textarea {
    width: 100%;
    padding: 0.75rem;
    font-size: 1rem;
    border: 1px solid var(--border-color);
    border-radius: 5px;
  }
  
  .submit-button {
    padding: 0.75rem 2rem;
    font-size: 1rem;
    background-color: var(--primary-color);
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  
  .submit-button:hover {
    background-color: var(--primary-color-hover);
  }
  
  /* Social Links Styles */
  .social-links ul {
    list-style: none;
    padding: 0;
    display: flex;
    justify-content: center;
    gap: 1.5rem;
  }
  
  .social-links a {
    color: var(--primary-color);
    font-size: 1.2rem;
    text-decoration: none;
  }
  
  .social-links a:hover {
    color: var(--primary-color-hover);
  }
  
  /* FAQ Styles */
  .faq {
    margin-top: 2rem;
  }
  
  .faq-item {
    margin-bottom: 1rem;
  }
  
  .faq-question {
    font-size: 1.2rem;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    background-color: var(--input-bg-color);
    padding: 1rem;
    border-radius: 5px;
  }
  
  .faq-answer {
    margin-top: 0.5rem;
    font-size: 1rem;
    padding: 0.5rem;
    background-color: var(--input-bg-color);
    border-radius: 5px;
    text-align: left;
    margin-left: 5px;
  }
  
  /* Fun Facts Styles */
  .fun-facts ul {
    margin: 0;
    list-style: none;
    padding: 0;
    text-align: left;
    margin-top: 2rem;
  }
  
  .fun-facts li {
    font-size: 1rem;
    margin-bottom: 0.5rem;
  }
  </style>
  