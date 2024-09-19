<template>
  <div class="home vw-100">
      <div class="container">
          <div class="greeting">Hi there👋,</div>
          <h1 class="name animated-greeting">My name is <span class="highlight">Lamlankosi Nomnganga</span></h1>
          <p class="title">I am a <span v-if="title">{{ title }}</span> and a passionate Gamer</p>
          <a href="#about" class="btn btn-success">Get to know me</a>
          <div class="social-media">
              <i class="bi bi-linkedin"></i>
              <i class="bi bi-github"></i>
          </div>
      </div>
  </div>
</template>

<script>
import { computed, onMounted } from 'vue'
import { useStore } from 'vuex'
export default {
  setup() {
      const store = useStore()
      const jobTitle = computed(() => store.state.jobTitle)

      function repeat() {
          if (!jobTitle.value) return;
          let cnt = 0;
          setInterval(() => {
              cnt = (cnt + 1) % jobTitle.value.length;
              title.value = jobTitle.value[cnt].title;
          }, 2000);
      }

      onMounted(async () => {
          await store.dispatch('fetchJobTitle');
          repeat();
      });

      const title = computed(() => jobTitle.value ? jobTitle.value[0].title : '');

      return { title };
  }
}
</script>

<style scoped>
.home {
height: 100vh; 
display: flex;
align-items: center;
justify-content: center;
/* background-color: #5c5c5c; */
color: white;
}

.container {
text-align: left;
max-width: 960px;
width: 100%;
padding: 0 20px;
}

.greeting {
font-size: 1.2rem;
margin-bottom: 0.5rem;
text-align: left;
}

.animated-greeting {
animation: slideIn 1.5s ease-out;
}

@keyframes slideIn {
from {
  transform: translateX(-100%);
  opacity: 0;
}
to {
  transform: translateX(0);
  opacity: 1;
}
}

.highlight {
font-size: 2.5rem;
margin-bottom: 0.5rem;
color: #37ff00;
}

.title {
font-size: 1.2rem;
margin-bottom: 0.5rem;
}

.btn {
  background-color: black;
  color: white;
  padding: 10px 20px;
  text-decoration: none;
  border: none;
  border-radius: 5px;
  transition: background-color 0.3s;
}

.btn:hover {
background-color: #f4a261;
}

.social-media i {
font-size: 1.5rem;
margin: 0 10px; 
}
</style>
