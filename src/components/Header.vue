<template>
  <header class="header">
    <div class="logo">Your Name or Logo</div>
    <nav class="navbar">
      <ul :class="['nav-links', { 'active': isMenuOpen }]">
        <li><a href="/" @click="closeMenu">Home</a></li>
        <li><a href="/projects" @click="closeMenu">Projects</a></li>
        <li><a href="/skills" @click="closeMenu">Skills</a></li>
        <li><a href="/About"  @click="closeMenu">About</a></li>
        <li><a href="/contact" @click="closeMenu">Contact</a></li>
      </ul>
      <div class="hamburger" @click="toggleMenu">
        <span class="line"></span>
        <span class="line"></span>
        <span class="line"></span>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  data() {
    return {
      isMenuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen;
    },
    closeMenu() {
      this.isMenuOpen = false;
    },
  },
};
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  background-color: #333;
  color: white;
  position: relative;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.5);
  transition: background-color 0.3s, box-shadow 0.3s;
}

.header:hover {
  background-color: #444; /* Slight change on hover for interactivity */
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.7);
}

.logo {
  font-size: 1.8rem;
  font-weight: bold;
  transition: transform 0.3s;
}

.logo:hover {
  transform: scale(1.05); /* Scale effect on hover */
}

.navbar {
  display: flex;
  align-items: center;
}

.nav-links {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav-links li {
  margin: 0 2rem;
}

.nav-links a {
  text-decoration: none;
  color: white;
  position: relative;
  overflow: hidden;
  transition: color 0.3s;
}

.nav-links a:hover {
  color: #ffcc00; /* Highlight color on hover */
}

.nav-links a::after {
  content: '';
  position: absolute;
  width: 100%;
  height: 2px;
  background: #ffcc00; /* Underline color */
  bottom: 0;
  left: -100%;
  transition: all 0.3s ease;
}

.nav-links a:hover::after {
  left: 0; /* Animate underline on hover */
}

.hamburger {
  display: none; /* Hidden by default */
  flex-direction: column;
  cursor: pointer;
}

.hamburger .line {
  height: 3px;
  width: 25px;
  background-color: white;
  margin: 4px 0;
  transition: all 0.3s ease;
}

.hamburger.active .line:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px); /* Animation for X shape */

}

.hamburger.active .line:nth-child(2) {
  opacity: 0; /* Hide middle line */
}

.hamburger.active .line:nth-child(3) {
  transform: rotate(-45deg) translate(5px, -5px); /* Animation for X shape */
}

@media (max-width: 768px) {
  .nav-links {
    display: none; /* Hide links on mobile */
    flex-direction: column;
    position: absolute;
    top: 70px; /* Adjust based on header height */
    left: 0;
    width: 100%;
    background-color: #333;
    padding: 1rem 0;
    z-index: 10;
    transition: max-height 0.3s ease; /* Add transition */
  }

  .nav-links.active {
    display: flex; /* Show links when menu is open */
  }

  .hamburger {
    display: flex; /* Show hamburger on mobile */
  }
}
</style>

