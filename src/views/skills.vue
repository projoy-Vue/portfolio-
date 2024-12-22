<template>
    <section class="skills" id="skills">
      <h2 class="skills-title">My Skills</h2>
      <p class="skills-subtitle">
        Here are some of the technologies and tools I use to create amazing web experiences.
      </p>
      <div class="skills-container">
        <div
          v-for="skill in skills"
          :key="skill.id"
          class="skill-card"
          ref="skillCards"
        >
          <img :src="skill.icon" :alt="skill.name" class="skill-icon" />
          <h3 class="skill-name">{{ skill.name }}</h3>
          <div class="progress-bar">
            <div
              class="progress-fill"
              :style="{ width: skill.proficiency + '%' }"
            ></div>
          </div>
          <p class="skill-level">{{ skill.level }}</p>
        </div>
      </div>
      <button @click="toggleDarkMode" class="toggle-dark-mode">
        {{ isDarkMode ? "Light Mode" : "Dark Mode" }}
      </button>
    </section>
  </template>
<script>
import { gsap } from "gsap";

export default {
  name: "Skills",
  data() {
    return {
      skills: [
        { id: 1, name: "HTML", icon: "icons/html.svg", level: "Expert", proficiency: 95 },
        { id: 2, name: "CSS", icon: "icons/css.svg", level: "Advanced", proficiency: 90 },
        { id: 3, name: "JavaScript", icon: "icons/javascript.svg", level: "Expert", proficiency: 85 },
        { id: 4, name: "Vue.js", icon: "icons/vue.svg", level: "Advanced", proficiency: 80 },
        { id: 5, name: "React", icon: "icons/react.svg", level: "Intermediate", proficiency: 70 },
        { id: 6, name: "Git", icon: "icons/git.svg", level: "Advanced", proficiency: 85 },
        { id: 7, name: "SASS", icon: "icons/sass.svg", level: "Advanced", proficiency: 90 },
        { id: 8, name: "Tailwind CSS", icon: "icons/tailwind.svg", level: "Advanced", proficiency: 80 },
      ],
      isDarkMode: false,
    };
  },
  methods: {
    toggleDarkMode() {
      this.isDarkMode = !this.isDarkMode;
      document.documentElement.classList.toggle("dark-mode", this.isDarkMode);
    },
  },
  mounted() {
    gsap.from(this.$refs.skillCards, {
      opacity: 0,
      y: 50,
      duration: 1,
      stagger: 0.2,
    });
  },
};
</script>
<style scoped>
/* General Styles */
.skills {
  padding: 2rem 1rem;
  text-align: center;
  background-color: var(--bg-color);
  color: var(--text-color);
  transition: background-color 0.3s, color 0.3s;
}

.skills-title {
  font-size: 2.5rem;
  font-weight: bold;
  margin-bottom: 1rem;
}

.skills-subtitle {
  font-size: 1.2rem;
  margin-bottom: 2rem;
}

.skills-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 1.5rem;
}

.skill-card {
  background: var(--card-bg);
  border-radius: 10px;
  padding: 1.5rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  text-align: center;
  transition: transform 0.3s, box-shadow 0.3s;
}

.skill-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
}

.skill-icon {
  width: 60px;
  height: 60px;
  margin-bottom: 1rem;
}

.skill-name {
  font-size: 1.5rem;
  font-weight: bold;
  margin-bottom: 0.5rem;
}

.progress-bar {
  background: #e0e0e0;
  border-radius: 5px;
  overflow: hidden;
  margin: 1rem 0;
  height: 8px;
}

.progress-fill {
  height: 100%;
  background: var(--primary-color);
  transition: width 0.5s ease-in-out;
}

.skill-level {
  font-size: 1rem;
}

/* Dark Mode Styles */
:root {
  --bg-color: #f8f9fa;
  --text-color: #343a40;
  --card-bg: #fff;
  --primary-color: #007bff;
}

:root.dark-mode {
  --bg-color: #343a40;
  --text-color: #f8f9fa;
  --card-bg: #495057;
  --primary-color: #17a2b8;
}

/* Toggle Button */
.toggle-dark-mode {
  margin-top: 2rem;
  padding: 0.5rem 1rem;
  font-size: 1rem;
  background: var(--primary-color);
  color: rgb(255, 255, 255);
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background 0.3s;
}

.toggle-dark-mode:hover {
  background: var(--primary-color-dark);
}
</style>
 