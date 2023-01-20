<script>
import axios from 'axios'

export default {
    name: 'SingleProjectView',

    data() {
        return {
            project: null,
            base_api_url: 'http://localhost:8000',
            loading: true

        }
    },
    mounted() {
        const url = this.base_api_url + '/api/projects/' + this.params.slug
        console.log(url);
        axios.get(url)
            .then(response => {
                if (response.data.success) {
                    this.post = response.data.results
                    this.loading = false
                }
            })
            .catch(error => {
                console.log(error)
            })
    }
}
</script>

<template>

    <div class="single-project">
        {{ $route.params.slug }}

        <div class="single-project" v-if="project">
            <img class="img-fluid w-100" :src="api_base_url + '/storage/' + project.cover_image" :alt="project.title">
            <div class="container">
                <h2>
                    {{ project.title }}
                </h2>
                <div class="content">
                    {{ project.body }}
                </div>
            </div>
        </div>
    </div>
</template>


<style lang="scss" scoped>

</style>