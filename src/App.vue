<script>
import NavItem from './components/NavItem.vue'
export default {
    components: {
        NavItem
    }
}

</script>

<template>
    <NavItem />
    <router-view></router-view>
</template>

<style lang="scss">
@use './styles/general.scss';
</style>
