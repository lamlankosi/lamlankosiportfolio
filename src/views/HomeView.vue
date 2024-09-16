<template>
 
    <!-- <div class="row full-height" id="home"> -->
      <LandingSection id="home"/>
      <AboutSection id="about" />
    <!-- <div class="row" id="about">
      <AboutSection/>
    </div>
    <div class="row" id="education-experience"></div>
    <div class="row" id="projects"></div>
    <div class="row" id="contact-me"></div> -->

</template>

<script>
import LandingSection from '@/components/LandingSection.vue';
import AboutSection from '@/components/AboutSection.vue';
export default {
  name: 'HomeView',
  components: {
    LandingSection,
    AboutSection
  }
}
</script>
