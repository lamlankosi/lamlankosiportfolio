<template>

    <NavbarComponent/>
  
    <router-view/>
    <Footer/>


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
