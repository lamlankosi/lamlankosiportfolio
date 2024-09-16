<template>
  <div class="about">
    <h1>About</h1>
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
  </div>
</template>

<script>
export default {
    computed:{
        about() {
            return this.$store.state.about
        }
    },
    created(){
        this.$store.dispatch('fetchAbout')
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

@media (max-width: 768px) {
  .about {
    text-align: center;
  }
}
</style>
