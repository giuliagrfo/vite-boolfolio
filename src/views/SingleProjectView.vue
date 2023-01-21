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
        const url = this.base_api_url + '/api/projects/' + this.$route.params.slug
        console.log(url);
        axios.get(url)
            .then(response => {
                if (response.data.success) {
                    this.project = response.data.results
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

    <div class="single-project mt-5">

        <div class="single-project" v-if="project">
            <div class="container">
                <img v-if="project.cover_image" class="img-fluid w-50" :src="base_api_url + project.cover_image"
                    :alt="project.title">
                <img v-else class="img-fluid w-25" src="/public/img/placeholder-1.png" alt="">
                <h2>
                    {{ project.title }}
                </h2>
                <div class="content">
                    {{ project.description }}
                </div>
                <div class="type">
                    <strong>Type: </strong>
                    <span v-if="project.type">
                        {{ project.type.name }}
                    </span>
                    <span v-else>No type assigned</span>
                </div>

                <div class="technologies">
                    <strong>Technologies: </strong>
                    <template v-if="project.technologies.length > 0">
                        <span v-for="technology in project.technologies">
                            #{{ technology.name }}
                        </span>
                    </template>
                    <template v-else>No technologies assigned</template>
                </div>
            </div>
        </div>
    </div>
</template>


<style lang="scss" scoped>

</style>