<template>
    <section class="hero">
      <div class="hero-content">
        <h1 class="hero-title">Welcome to My Portfolio</h1>
        <p class="hero-description">I'm a passionate developer creating interactive web experiences.</p>
        <a href="/projects" class="cta-button">View My Work</a>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    name: "Hero",
  };
  </script>
  
  <style scoped>
  .hero {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh; /* Full viewport height */
    background: url('https://picsum.photos/536/354') no-repeat center center/cover; /* Background image */
    color: white;
    text-align: center;
    position: relative;
  }
  
  .hero::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.5); /* Dark overlay for readability */
    z-index: 1;
  }
  
  .hero-content {
    position: relative;
    z-index: 2; /* Bring content above overlay */
    padding: 0 20px; /* Add horizontal padding */
  }
  
  .hero-title {
    font-size: 3rem; /* Adjust font size for prominence */
    margin: 0;
    animation: fadeIn 1s ease-in; /* Animation for the title */
  }
  
  .hero-description {
    font-size: 1.5rem; /* Smaller font size for description */
    margin: 1rem 0;
    animation: fadeIn 1.2s ease-in; /* Animation for description */
  }
  
  .cta-button {
    display: inline-block;
    padding: 1rem 2rem;
    background-color: #ffcc00; /* Call-to-action button color */
    color: #333; /* Button text color */
    text-decoration: none;
    border-radius: 5px;
    font-weight: bold;
    transition: background-color 0.3s, transform 0.3s; /* Add transition effects */
  }
  
  .cta-button:hover {
    background-color: #ffd700; /* Button hover color */
    transform: scale(1.05); /* Slightly scale button on hover */
  }
  
  @keyframes fadeIn {
    from {
      opacity: 0;
      transform: translateY(20px); /* Slide in from below */
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  </style>
  