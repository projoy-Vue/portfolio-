<template>
  <footer class="footer">
    <div class="footer-content">
      <div class="social-links">
        <!-- GitHub Icon -->
        <a href="https://github.com/yourusername" target="_blank" rel="noopener noreferrer">
          <i class="fab fa-github"></i> <!-- Using FontAwesome for GitHub icon -->
        </a>
        <!-- LinkedIn Icon -->
        <a href="https://www.linkedin.com/in/yourusername" target="_blank" rel="noopener noreferrer">
          <i class="fab fa-linkedin"></i> <!-- Using FontAwesome for LinkedIn icon -->
        </a>
        <!-- Twitter Icon -->
        <a href="https://twitter.com/yourusername" target="_blank" rel="noopener noreferrer">
          <i class="fab fa-twitter"></i> <!-- Using FontAwesome for Twitter icon -->
        </a>
      </div>
      <p class="footer-text">&copy; {{ currentYear }} Your Name. All Rights Reserved.</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer",
  data() {
    return {
      currentYear: new Date().getFullYear(), // Get the current year
    };
  },
};
</script>

<style scoped>
.footer {
  width: 100%;
  background-color: #333;
  color: white;
  text-align: center;
  padding: 1rem 0;
  /* position: relative; */
  transition: all 0.3s ease-out;
}
.footer:hover {
  background-color: #444; /* Slight change on hover for interactivity */
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.7);
}
.footer-content {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.social-links {
  margin-bottom: 1rem;
}

.social-links a {
  margin: 0 10px; /* Space between icons */
  font-size: 1.5rem; /* Icon size */
  color: white; /* Icon color */
  transition: transform 0.3s, color 0.3s; /* Animation for hover effect */
}

.social-links a:hover {
  transform: scale(1.1); /* Scale effect on hover */
  color: #ffcc00;; /* Change color on hover, you can modify it for each icon */
}

.footer-text {
  font-size: 0.9rem;
}

/* FontAwesome specific styles */
.fab {
  font-weight: bold;
}
</style>
