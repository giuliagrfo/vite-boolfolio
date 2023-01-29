<script>
import ProjectList from '../components/ProjectList.vue'
import NavItem from '../components/NavItem.vue';
export default {
    name: 'ProjectsView',
    components: {
        ProjectList,
        NavItem
    }
}  
</script>

<template>
    <NavItem></NavItem>
    <ProjectList></ProjectList>

</template>

<style lang="scss" scoped>

</style>