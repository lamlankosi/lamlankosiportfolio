<template>
  <div class="about">
    <h1>about</h1>
    <div class="info">
        <div class="row">
            <div class="col-lg-6">
                <img src="https://lamlankosi.github.io/project_images/Images/20240422_094754.jpg" alt="Profile" class="img-fluid w-50">
            </div>
            <div class="col-lg-6">
                <p v-if="about" id="about"> {{ about[0] }}</p>
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


.img-fluid {
  object-fit: cover;
  border-radius: 1.2rem;
}

.text {
  padding: 20px;
}
</style>