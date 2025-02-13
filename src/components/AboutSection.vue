<template>
  <div class="about">
    <h1 class="title fade-in">About Me</h1>

    <div class="info">
      <div class="row align-items-center">
        <div class="col-lg-6 col-md-12 text-lg-start text-center">
          <h2 class="intro fade-in" style="animation-delay: 0.3s">
            Hello, I'm <span class="name">Lamlankosi Nomnganga</span>
          </h2>
          <p v-if="about" id="about" class="fade-in" style="animation-delay: 0.6s">
            {{ about[0] }}
          </p>
          <div class="buttons fade-in" style="animation-delay: 0.9s">
            <a href="https://drive.google.com/file/d/1S4CyDVEmJR66DsLNury0ZgTfO6AqmWm-/view?usp=sharing" target="_blank" class="btn download">Download CV</a>
            <a href="#projects" class="btn projects">View Projects</a>
          </div>
        </div>
        <div class="col-lg-6 col-md-12 text-center">
          <img
            src="https://lamlankosi.github.io/project_images/Images/20240422_094754.jpg"
            alt="Profile"
            class="img-fluid profile-img fade-in"
            style="animation-delay: 1.2s"
            loading="lazy"
          />
        </div>
      </div>
    </div>

    <div class="stats fade-in" style="animation-delay: 1.5s">
      <div class="stat-box fade-in" style="animation-delay: 1.8s">
        <h3>{{ projects }}</h3>
        <p>Total Projects</p>
      </div>
      <div class="stat-box fade-in" style="animation-delay: 2.1s">
        <h3>{{ skills.length }}</h3>
        <p>Total Skills</p>
      </div>
      <div class="stat-box fade-in" style="animation-delay: 2.4s">
        <h3>{{ certificates }}</h3>
        <p>Total Certificates</p>
      </div>
    </div>

    <h2 class="title fade-in" style="animation-delay: 2.7s">Skills</h2>
    <div class="skills-grid">
      <div
        class="skill fade-in"
        v-for="(skill, index) in skills"
        :key="skill.name"
        :style="{ animationDelay: `${3.0 + index * 0.2}s` }"
      >
        <img :src="skill.logo" :alt="skill.name" />
        <span>{{ skill.name }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: 6,
      certificates: 8,
    };
  },
  computed: {
    about() {
      return this.$store.state.about || [];
    },
    skills() {
      return this.$store.state.skills || [];
    },
  },
  created() {
    this.$store.dispatch("fetchAbout");
    this.$store.dispatch("fetchSkills");
  },
};
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
.about {
  padding: 3rem;
  color: #e0e0e0; /* Light grey text */
  background: #1a1a1a; /* Dark background */
  text-align: center;
}

.title {
  font-size: 3rem;
  font-weight: bold;
  margin-bottom: 2rem;
  color: #ffffff; /* White title */
}

.intro {
  font-size: 1.8rem;
  color: #e0e0e0; /* Light grey */
}

.name {
  color: #ffffff; /* White name */
  font-weight: bold;
}

.profile-img {
  box-shadow: 0 0 10px rgba(255, 255, 255, 0.1);
  /* border-radius: 50%; */
  max-width: 100%;
  height: auto;
}

.buttons {
  margin-top: 1rem;
}

.btn {
  padding: 10px 20px;
  border: none;
  cursor: pointer;
  border-radius: 8px;
  font-weight: bold;
  margin: 5px;
  transition: background-color 0.3s, transform 0.3s;
}

.download {
  background: #2c2c2c; /* Dark grey */
  color: #e0e0e0; /* Light grey text */
}

.projects {
  background: #4a4a4a; /* Medium grey */
  color: #ffffff; /* White text */
}

.btn:hover {
  transform: scale(1.05);
  background-color: #7a7a7a; /* Medium grey on hover */
}

.stats {
  display: flex;
  justify-content: center;
  gap: 2rem;
  margin-top: 2rem;
}

.stat-box {
  background: #2c2c2c; /* Dark grey */
  padding: 1rem;
  border-radius: 10px;
  text-align: center;
  width: 50%;
  transition: transform 0.3s;
}

.stat-box h3 {
  font-size: 2rem;
  color: #ffffff; /* White */
}

.stat-box p {
  font-size: 1rem;
  color: #b0b0b0; /* Light grey */
}

.stat-box:hover {
  transform: scale(1.05);
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
  gap: 20px;
  justify-content: center;
  margin-top: 1rem;
  padding: 0 20px;
}

.skill {
  background: #2c2c2c; /* Dark grey */
  padding: 15px;
  border-radius: 8px;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  transition: transform 0.3s;
}

.skill img {
  width: auto;
  height: 50px;
  max-width: 100%;
  margin-bottom: 10px;
}

.skill:hover {
  transform: scale(1.1);
}

@media (max-width: 768px) {
  .about {
    text-align: center;
  }

  .stats {
    flex-direction: column;
    align-items: center;
  }

  .stat-box {
    width: 80%;
  }

  .skills-grid {
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
    gap: 10px;
  }
  .row{
    flex-direction: column-reverse;
  }
}
</style>