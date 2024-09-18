<template>
    <div class="projects">
        <div class="row">
            <h2 class="display-2"><strong>Projects</strong></h2>
        </div>
        <div class="row gap-2 justify-content-center my-2" v-if="projects">
            <Card v-for="project in projects" :key="project.school">
                <template #cardHeader>
                    <h5>{{ project.name }}</h5>
                    <img class="img-fluid" :src="project.background_img" :alt="project.name">
                </template>
                <template #cardBody>
                    <p class="lead">{{ project.description }}</p>
                    <p class="lead">{{ project.status }}</p>
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
const projects = computed(
    () => store.state.projects
)
onMounted(() => {
    store.dispatch('fetchProjects')
})
</script>

<style scoped>
.card {
    width: 24rem;
}

.projects {
    background-color: blue;
}
</style>