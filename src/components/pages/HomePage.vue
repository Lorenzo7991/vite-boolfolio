<script>
import axios from 'axios';
import ProjectCard from '../ProjectCard.vue';
const endpoint = 'http://127.0.0.1:8000/api/projects/';
export default {
    name: 'AppHome',
    components: { ProjectCard },
    data: () => ({
        projects: []

    }),
    methods: {
        fetchProjects() {
            axios.get(endpoint).then(res => {
                this.projects = res.data
            })
        }
    },
    created() {
        this.fetchProjects();
    }
}
</script>



<template>
    <div class="container">
        <ProjectCard v-for="project in projects" :project="project" />
    </div>
</template>



<style>
/* Style here */
</style>
