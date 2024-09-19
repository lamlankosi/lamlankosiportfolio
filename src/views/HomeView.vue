<template>
    <!-- <div class="container">
      <section class="row vh-100 vw-100" id="landing">
        <landingSection/>
      </section>
      <section class="row vh-100 vw-100" id="about">
        <AboutSection/>
      </section>
      <section class="row vh-100 vw-100" id="resume">
        <ResumeSection/>
      </section>
      <section class="row vh-100 vw-100" id="projects">
        <ProjectsSection/>
      </section>
      <section class="row vh-100 vw-100" id="contact">
        <ContactSection/>
      </section>
    </div> -->

    <!-- <div class="row full-height" id="home"> -->
      <LandingSection id="home"/>
      <AboutSection id="about" />
      <ResumeSection id="resume"/>
      <ProjectsSection id="projects"/>
      <ContactSection id="contact"/>
    <!-- <div class="row" id="about">
      <AboutSection/>
    </div>
    <div class="row" id="education-experience"></div>
    <div class="row" id="projects"></div>
    <div class="row" id="contact-me"></div> -->

</template>

<script>
import LandingSection from '@/components/LandingSection.vue'
import AboutSection from '@/components/AboutSection.vue'
import ResumeSection from '@/components/ResumeSection.vue'
import ProjectsSection from '@/components/ProjectsSection.vue';
import ContactSection from '@/components/ContactSection.vue';
export default {
  name: 'HomeView',
  components: {
    LandingSection,
    AboutSection,
    ResumeSection,
    ProjectsSection,
    ContactSection
  }
}
</script>

<style scoped>

</style>
