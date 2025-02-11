<template>
    <div class="projects">
      <div class="row text-center">
        <h2 class="title fade-in">Projects</h2>
      </div>
      <div class="row gap-3 justify-content-center my-4" v-if="projects">
        <Card v-for="project in projects" :key="project.name" class="project-card fade-in">
          <template #cardHeader>
            <h5 class="card-title">{{ project.name }}</h5>
            <img class="img-fluid project-image" :src="project.background_img" :alt="project.name">
          </template>
          <template #cardBody>
            <p class="lead text-secondary">{{ project.description }}</p>
            <div class="button-group">
              <a :href="project.vercel" target="_blank" v-if="project.vercel" class="btn btn-dark"><i class="bi bi-box-arrow-up-right"></i> Live Demo</a>
              <a :href="project.github" target="_blank" v-if="project.github" class="btn btn-outline-dark"><i class="bi bi-github"></i> Github</a>
            </div>
          </template>
        </Card>
      </div>
      <div v-else class="text-center">
        <Spinner />
      </div>
    </div>
  </template>
  
  <script setup>
  import { useStore } from 'vuex';
  import { computed, onMounted } from 'vue';
  import Card from '@/components/Card.vue';
  
  const store = useStore();
  const projects = computed(() => store.state.projects);
  
  onMounted(() => {
    store.dispatch('fetchProjects');
  });
  </script>
  
  <style scoped>
  /* Fade-in animation */
  @keyframes fadeInUp {
    from {
      opacity: 0;
      transform: translateY(30px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  
  /* Apply the fade-in animation */
  .fade-in {
    opacity: 0; /* Start hidden */
    animation: fadeInUp 0.8s ease-out forwards;
  }
  
  /* General styling */
  .projects {
    min-height: 100vh;
    padding: 3rem 0;
    background: #1a1a1a; /* Dark background */
    color: #e0e0e0; /* Light grey text */
  }
  
  /* Title */
  .title {
    font-size: 2.5rem;
    font-weight: bold;
    color: #ffffff; /* White title */
    margin-bottom: 2rem;
  }
  
  /* Project Card */
  .project-card {
    width: 22rem;
    background: #2c2c2c; /* Dark grey */
    backdrop-filter: blur(10px);
    color: #e0e0e0; /* Light grey text */
    border-radius: 12px;
    padding: 1.5rem;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    text-align: center;
    transition: transform 0.2s ease-in-out;
  }
  
  .project-card:hover {
    transform: translateY(-5px);
  }
  
  /* Project Title */
  .card-title {
    font-size: 1.5rem;
    font-weight: bold;
    color: #ffffff; /* White text */
    margin-bottom: 0.5rem;
  }
  
  /* Project Image */
  .project-image {
    width: 100%;
    border-radius: 8px;
    margin-bottom: 1rem;
  }
  
  /* Button Group */
  .button-group {
    display: flex;
    justify-content: center;
    gap: 10px;
    margin-top: 10px;
  }
  
  /* Buttons */
  .btn {
    padding: 8px 16px;
    border-radius: 6px;
    font-weight: 500;
    text-transform: uppercase;
    transition: all 0.2s ease-in-out;
  }
  
  .btn-dark {
    background: #1e1e1e; /* Dark grey */
    color: #ffffff; /* White text */
    border: 1px solid #3a3a3a; /* Medium grey border */
  }
  
  .btn-dark:hover {
    background: #2a2a2a; /* Medium grey */
    transform: scale(1.05);
  }
  
  .btn-outline-dark {
    border: 2px solid #3a3a3a; /* Medium grey border */
    color: #e0e0e0; /* Light grey text */
  }
  
  .btn-outline-dark:hover {
    background: #3a3a3a; /* Medium grey */
    color: #ffffff; /* White text */
    transform: scale(1.05);
  }
  .project-image {
  width: 100%;
  height: 180px; /* Fixed height for uniformity */
  object-fit: cover; /* Ensures images maintain aspect ratio */
  border-radius: 8px;
  margin-bottom: 1rem;
}
.project-card .card-body {
  flex-grow: 1; /* Makes content evenly distributed */
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.project-card {
  display: flex;
  flex-direction: column;
  width: 22rem; /* Ensures consistent width */
  min-height: 100%; /* Ensures all cards stretch equally */
  background: #2c2c2c;
  color: #e0e0e0;
  border-radius: 12px;
  padding: 1.5rem;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
  transition: transform 0.2s ease-in-out;
}


  /* Responsive Design */
  @media screen and (max-width: 800px) {
    .project-card {
      width: 18rem;
    }
  }
  </style>