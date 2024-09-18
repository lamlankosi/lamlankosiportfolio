<template>
  <div class="resume">
    <div class="row">
      <h2 class="display-2"><strong>Resume</strong></h2>
    <!-- <div class="row gap-3 justify-content-center my-2" v-if="education">
      <Card v-for="educ in education" :key="educ.school">
        <template #cardHeader>
          <div class="card-header">
            <h5 class="card-title"><strong>{{ educ.school }}</strong></h5>
          </div>
        </template>
        <template #cardBody>
          <div class="card-body d-flex align-items-start">
            <img :src="educ.schoolURL" :alt="educ.school" class="img-fluid card-image" />
            <div class="card-content ms-3">
              <p>{{ educ.occupation }}</p>
              <p class="lead">{{ educ.year }}</p>
            </div>
          </div>
        </template>
      </Card>
    </div>
    <div v-else>
      <Spinner />
    </div> -->
    <div class="education justify-content-center my-2">
      <div v-for="educ in education" :key="educ.school" class="education-class">
        <img :src="educ.schoolURL" :alt="educ.schoool" class="profilePic">
        <div class="education-content">
          <h3>{{ educ.school }}</h3>
          <h4>{{ educ.occupation }}</h4>
          <p>{{ educ.year }}</p>
        </div>
      </div>
    </div>
  </div>
  </div>
</template>

<script setup>
import { useStore } from 'vuex'
import { computed, onMounted } from 'vue'
// import Card from '@/components/Card.vue'

const store = useStore()
const education = computed(() => store.state.education)


onMounted(() => {
  store.dispatch('fetchEducation')

})
</script>

<style scoped>
/* .card {
  width: 20rem;
  background-color: #404040;
  box-shadow: 5px 5px #888888;
  color: white;
  padding: 1rem;
}

.card-body {
  display: flex;
  align-items: flex-start;
}

.card-image {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  object-fit: cover;
}

.card-content {
  flex-grow: 1;
}
*/
.resume {
  background-color: black;
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

#CV {
  background-color: black;
  color: white;
}

.education{
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2rem;
    margin: 7rem;
    width: 90%;
}
  
.education-class {
    gap: 1rem;
    padding: 1rem;
    background-color:#404040;
    box-shadow:  5px 5px #888888;

    
}
.education-content{
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}
.profilePic {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    object-fit: cover;
}

.education-content {
    display: flex;
    flex-direction: column;
}
.education-content h3, .education-content h4 {
    margin: 0;}
.education-content p {
    margin-top: 0.5rem;
}
img{
  display: block;
  max-width: 100%;
}
@media (max-width: 768px) {
  .education{
    grid-template-columns: 1fr;
    margin:1rem;
    justify-content: center;
  }
}
</style>