<script>
import ProjectCard from '../components/ProjectCard.vue'
export default {
    name: 'ProjectsView',
    components: {
        ProjectCard
    }
}  
</script>

<template>
    <div class="container">
        <div>
            <h1>My projects</h1>
        </div>

        <ProjectCard></ProjectCard>

    </div>
</template>

<style lang="scss" scoped>

</style>