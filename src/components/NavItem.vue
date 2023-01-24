<script>
export default {
    name: 'NavItem'
}
</script>

<template>
    <nav class="navbar navbar-expand-sm navbar-dark bg-dark">
        <div class="container">
            <a class="navbar-brand text-uppercase" href="/">Portfolio</a>
            <button class="navbar-toggler d-lg-none" type="button" data-bs-toggle="collapse" data-bs-target="#mainNav"
                aria-controls="mainNav" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="mainNav">
                <ul class="navbar-nav ms-auto mt-2 mt-lg-0">
                    <li class="nav-item">
                        <router-link class="nav-link text-uppercase" :to="{ name: 'home' }" aria-current="page">Home
                            <span class="visually-hidden">(current)</span></router-link>
                    </li>
                    <li class="nav-item">
                        <router-link class="nav-link text-uppercase" :to="{ name: 'about' }">About Me</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link class="nav-link text-uppercase" :to="{ name: 'projects' }">Projects</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link class="nav-link text-uppercase" :to="{ name: 'contacts' }">Contacts</router-link>
                    </li>
                </ul>

            </div>
        </div>
    </nav>

</template>

<style lang="scss" scoped>

</style>