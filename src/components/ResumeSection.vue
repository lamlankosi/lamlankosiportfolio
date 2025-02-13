<template>
  <div class="resume-container">
    <h2 class="title fade-in">Education & Experience</h2>

    <div class="tabs fade-in" style="animation-delay: 0.3s">
      <button
        v-for="tab in tabs"
        :key="tab"
        @click="selectedTab = tab"
        :class="{ active: selectedTab === tab }"
      >
        {{ tab }}
      </button>
    </div>

    <div v-if="selectedTab === 'Education'" class="grid fade-in" style="animation-delay: 0.6s">
      <div v-for="educ in education" :key="educ.school" class="card">
        <img :src="educ.schoolURL" :alt="educ.school" class="icon" />
        <h3>{{ educ.school }}</h3>
        <p class="year">{{ educ.year }}</p>
        <p class="description">{{ educ.occupation }}</p>
        <a v-if="educ.certificate && educ.certificate.trim() !== ''" :href="educ.certificate" target="_blank" class="btn btn-outline-dark">
          <i class="bi bi-eye"></i> View
        </a>
      </div>
    </div>

    <div v-if="selectedTab === 'Experience'" class="grid fade-in" style="animation-delay: 0.9s">
      <div v-for="exp in experience" :key="exp.companyName" class="card">
        <img :src="exp.schoolURL" :alt="exp.companyName" class="icon" />
        <h3>{{ exp.companyName }}</h3>
        <p class="year">{{ exp.year }}</p>
        <p class="description">{{ exp.occupation }}</p>
        <p class="description">{{ exp.responsibility }}</p>
      </div>
    </div>

    <div v-if="selectedTab === 'Badges'" class="grid fade-in" style="animation-delay: 1.2s">
      <div v-for="cert in filteredBadges" :key="cert.name" class="badge-card">
        <img :src="cert.badgeURL" :alt="cert.name" class="img" />
      </div>
    </div>

    <div v-if="selectedTab === 'Certificates'" class="certificates-grid fade-in" style="animation-delay: 1.5s">
      <div v-for="cert in filteredCertificates" :key="cert.name" class="certificate-card">
        <img :src="cert.certificateIMG" :alt="cert.name" class="certificate-image" />
        <h3 class="certificate-title">{{ cert.name }}</h3>
        <div class="button-group">
          <button class="download-btn"><i class="bi bi-box-arrow-down"> Download </i></button>
          <button class="view-btn"><i class="bi bi-eye"></i> View</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed, onMounted } from 'vue';
import { useStore } from 'vuex';

const store = useStore();
const selectedTab = ref('Education');
const tabs = ['Education', 'Experience', 'Badges', 'Certificates'];

const education = computed(() => store.state.education);
const experience = computed(() => store.state.experience);
const certificates = computed(() => store.state.certificates);

const filteredBadges = computed(() => {
  return certificates.value.filter(cert => cert.badgeURL && cert.badgeURL.trim() !== "");
});

const filteredCertificates = computed(() => {
  return certificates.value.filter(cert => cert.certificateIMG && cert.certificateIMG.trim() !== "");
});

onMounted(() => {
  store.dispatch('fetchEducation');
  store.dispatch('fetchExperience');
  store.dispatch('fetchCertificates');
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
.resume-container {
  margin: auto;
  text-align: center;
  color: #e0e0e0; /* Light grey text */
  padding: 2rem;

  background: #1a1a1a; /* Dark background */
}

.title {
  font-size: 2.5rem;
  font-weight: bold;
  color: #ffffff; /* White title */
  margin-bottom: 2rem;
}

.tabs {
  display: flex;
  justify-content: center;
  margin: 1.5rem 0;
}

.tabs button {
  background: none;
  border: none;
  padding: 10px 20px;
  color: #a0a0a0; /* Light grey */
  font-size: 1.2rem;
  cursor: pointer;
  transition: 0.3s ease;
}

.tabs button:hover {
  color: #ffffff; /* White on hover */
}

.tabs button.active {
  border-bottom: 3px solid #ffffff; /* White underline */
  color: #ffffff; /* White text */
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 20px;
  margin-top: 20px;
}

.card {
  background: #2c2c2c; /* Dark grey */
  padding: 20px;
  border-radius: 12px;
  box-shadow: 4px 4px 15px rgba(0, 0, 0, 0.5);
  transition: transform 0.3s ease;
}

.card:hover {
  transform: translateY(-5px);
}

.icon {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  margin-bottom: 10px;
}

h3 {
  color: #ffffff; /* White text */
  font-size: 1.4rem;
}

.year {
  font-size: 1rem;
  color: #a0a0a0; /* Light grey */
}

.description {
  font-size: 0.9rem;
  color: #c0c0c0; /* Light grey */
}

/* Certificates Grid */
.certificates-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
  margin-top: 20px;
  padding: 20px;
}

/* Certificate Card */
.certificate-card {
  background: #2c2c2c; /* Dark grey */
  padding: 20px;
  border-radius: 12px;
  box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.3);
  text-align: center;
  transition: transform 0.3s ease;
}

.certificate-card:hover {
  transform: translateY(-5px);
}

/* Certificate Image */
.certificate-image {
  width: 100%;
  height: auto;
  border-radius: 8px;
  border: 1px solid #3a3a3a; /* Medium grey border */
}

/* Certificate Title */
.certificate-title {
  color: #ffffff; /* White text */
  font-size: 1.4rem;
  margin-top: 10px;
}

/* Button Group */
.button-group {
  margin-top: 15px;
  display: flex;
  justify-content: center;
  gap: 10px;
}

/* Buttons */
.download-btn, .view-btn {
  background: #1e1e1e; /* Dark grey */
  color: #ffffff; /* White text */
  border: 1px solid #3a3a3a; /* Medium grey border */
  padding: 10px 20px;
  border-radius: 8px;
  font-size: 0.9rem;
  cursor: pointer;
  transition: background 0.3s ease, transform 0.2s ease;
  font-weight: 500;
  text-transform: uppercase;
}

/* Hover Effect */
.download-btn:hover, .view-btn:hover {
  background: #2a2a2a; /* Medium grey */
  transform: scale(1.05);
}

/* Click Effect */
.download-btn:active, .view-btn:active {
  transform: scale(0.98);
}

/* Badge Card */
.badge-card {
  display: flex;
  justify-content: center;
  align-items: center;
  background: #2c2c2c; /* Dark grey */
  border-radius: 12px;
  padding: 10px;
  transition: transform 0.2s ease-in-out;
}

.badge-card:hover {
  transform: scale(1.05);
}

.img {
  width: 110px;
  height: 110px;
  border-radius: 12px;
  border: 1px solid #3a3a3a; /* Medium grey border */
  padding: 8px;
  background-color: #1a1a1a; /* Dark grey */
  box-shadow: 2px 2px 6px rgba(0, 0, 0, 0.4);
}
.btn {
    padding: 8px 16px;
    border-radius: 6px;
    font-weight: 500;
    text-transform: uppercase;
    transition: all 0.2s ease-in-out;
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
  .card {
  background: #2c2c2c;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 4px 4px 15px rgba(0, 0, 0, 0.5);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  min-height: 250px;
  position: relative;
}

.content {
  flex-grow: 1;
}

.button-group, .btn-outline-dark {
  margin-top: auto;
  display: flex;
  justify-content: center;
  align-items: center;
}
@media (max-width: 768px) {
  .resume-container {
    padding: 1.5rem;
  }

  .tabs {
    flex-direction: column;
  }

  .tabs button {
    padding: 8px;
  }
}
</style>