<template>
  <section class="projects">
    <h2 class="projects-title">My Projects</h2>
    <div class="projects-container">
      <div v-for="project in projects" :key="project.id" class="project-card">
        <img :src="project.image" :alt="project.title" class="project-image" />
        <h3 class="project-title">{{ project.title }}</h3>
        <p class="project-description">{{ project.description }}</p>
        <a :href="project.link" class="view-button" target="_blank" rel="noopener noreferrer">View Project</a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Projects",
  data() {
    return {
      projects: [
        {
          id: 1,
          title: "Project One",
          description: "A brief description of Project One.",
          image: "@/assets/project1-image.jpg", // Replace with your project image path
          link: "https://example.com/project-one", // Replace with your project URL
        },
        {
          id: 2,
          title: "Project Two",
          description: "A brief description of Project Two.",
          image: "@/assets/project2-image.jpg", // Replace with your project image path
          link: "https://example.com/project-two", // Replace with your project URL
        },
        {
          id: 3,
          title: "Project Two",
          description: "A brief description of Project Two.",
          image: "@/assets/project2-image.jpg", // Replace with your project image path
          link: "https://example.com/project-two", // Replace with your project URL
        },
        {
          id: 4,
          title: "Project Two",
          description: "A brief description of Project Two.",
          image: "@/assets/project2-image.jpg", // Replace with your project image path
          link: "https://example.com/project-two", // Replace with your project URL
        },
        {
          id: 5,
          title: "Project Two",
          description: "A brief description of Project Two.",
          image: "@/assets/project2-image.jpg", // Replace with your project image path
          link: "https://example.com/project-two", // Replace with your project URL
        },
        {
          id: 6,
          title: "Project Two",
          description: "A brief description of Project Two.",
          image: "@/assets/project2-image.jpg", // Replace with your project image path
          link: "https://example.com/project-two", // Replace with your project URL
        },
        {
          id: 7,
          title: "Project Two",
          description: "A brief description of Project Two.",
          image: "@/assets/project2-image.jpg", // Replace with your project image path
          link: "https://example.com/project-two", // Replace with your project URL
        },
        {
          id: 8,
          title: "Project Two",
          description: "A brief description of Project Two.",
          image: "@/assets/project2-image.jpg", // Replace with your project image path
          link: "https://example.com/project-two", // Replace with your project URL
        },
        {
          id: 9,
          title: "Project Two",
          description: "A brief description of Project Two.",
          image: "@/assets/project2-image.jpg", // Replace with your project image path
          link: "https://example.com/project-two", // Replace with your project URL
        },
        {
          id: 10,
          title: "Project Two",
          description: "A brief description of Project Two.",
          image: "@/assets/project2-image.jpg", // Replace with your project image path
          link: "https://example.com/project-two", // Replace with your project URL
        },
        // Add more projects as needed
      ],
    };
  },
};
</script>

<style scoped>
.projects {
  padding: 2rem;
  text-align: center;

}

.projects-title {
  font-size: 2.5rem;
  margin-bottom: 2rem;
}

.projects-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); /* Responsive grid */
  gap: 1.5rem;
}

.project-card {
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  padding: 1.5rem;
  transition: transform 0.3s;
}

.project-card:hover {
  transform: translateY(-5px); /* Elevate on hover */
}

.project-image {
  width: 100%;
  border-radius: 8px;
  margin-bottom: 1rem;
}

.project-title {
  font-size: 1.5rem;
  margin: 0.5rem 0;
}

.project-description {
  font-size: 1rem;
  margin-bottom: 1rem;
}

.view-button {
  padding: 0.5rem 1rem;
  background-color: #007bff; /* Button color */
  color: white;
  text-decoration: none;
  border-radius: 5px;
  transition: background-color 0.3s;
}

.view-button:hover {
  background-color: #0056b3; /* Button hover color */
}
</style>
  