<template>
  <div class="about">
    <h1 class="display-2"> <strong>About</strong></h1>
    <div class="info">
      <div class="row align-items-center">
        <div class="col-lg-6 col-md-12 text-center">
          <img src="https://lamlankosi.github.io/project_images/Images/20240422_094754.jpg" alt="Profile" class="img-fluid w-50 profile-img">
        </div>
        <div class="col-lg-6 col-md-12 text-center text-lg-start">
          <p v-if="about" id="about">{{ about[0] }}</p>
        </div>
      </div>
    </div>
    <div class="row">
      <h2>Skills</h2>
      <div class="skills-wrapper">
        <div class="skills">
          <div class="skill" v-for="skill in skills" :key="skill.name">
            <img :src="skill.logo" :alt="skill.name" />
            <span>{{ skill.name }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    computed:{
    about() {
            return this.$store.state.about
    },
    skills(){
      return this.$store.state.skills
    }
    },
    created(){
        this.$store.dispatch('fetchAbout')
        this.$store.dispatch('fetchSkills')
    }
}
</script>

<style scoped>
.about {
  padding: 2rem;
  background-color: #666;
}

.img-fluid {
  object-fit: cover;
  border-radius: 1.2rem;
}

.profile-img {
  max-width: 100%;
  margin-bottom: 1.5rem;
}
.skills-wrapper {
  overflow: hidden;
  width: 100%;
  position: relative;
}

.skills {
  display: flex;
  animation: scroll 20s linear infinite;
}

.skill {
  display: flex;
  align-items: center;
  margin-right: 20px;
  flex-shrink: 0;
}

.skill img {
  width: 50px;
  height: 50px;
  margin-right: 10px;
} 

@keyframes scroll {
  0% {
    transform: translateX(100%);
  }
  100% {
    transform: translateX(-100%);
  }
}

@media (max-width: 768px) {
  .about {
    text-align: center;
  }
}
</style>
