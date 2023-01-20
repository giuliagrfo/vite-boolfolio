<script>
import ProjectCard from './ProjectCard.vue';

export default {
    components: {
        ProjectCard
    }
}
</script>

<template>
    <section class="vue-home">
        <div class="container">
            <h1>Projects</h1>
            <ProjectCard />
        </div>
    </section>


</template>

<style lang="scss" scoped>
h1 {
    font-size: 1.4em;

    span.yellow {
        color: yellow;
        text-decoration: underline;
    }
}
</style>