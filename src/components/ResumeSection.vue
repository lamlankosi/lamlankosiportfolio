<template>
  <div class="container">
      <div class="row">
          <h2 class="display-2">Products</h2>
      </div>
      <div class="row gap-2 justify-content-center my-2" v-if="education">
          <Card v-for="educ in education" :key="educ.school">
              <template #cardHeader>
                 <h5>{{ educ.school }}</h5> 
              </template>
              <template #cardBody>
                  <p class="lead">{{ educ.year }}</p>
              </template>
          </Card>
      </div>
      <div v-else>
          <Spinner />
      </div>

  </div>
</template>

<script setup>
import { useStore } from 'vuex'
import { computed, onMounted } from 'vue'
import Card from '@/components/Card.vue'
const store = useStore()
const education = computed(
  () => store.state.education
)
onMounted(() => {
  store.dispatch('fetchEducation')
}) 
</script>

<style scoped>

</style>