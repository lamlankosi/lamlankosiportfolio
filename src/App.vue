<template>
  <div class="wrapper">
    <NavbarComponent/>
    <main class="container-fluid">
      <router-view/>
    </main>
    <Footer/>
  </div>


</template>

<script>
import NavbarComponent from './components/NavbarComponent.vue';
import Footer from './components/Footer.vue';
export default{
  components: { 
  NavbarComponent,
  Footer
}
}
</script>

<style src="@/assets/css/style.css">

</style>
