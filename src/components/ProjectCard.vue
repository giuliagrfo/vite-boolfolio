<script>
import axios from 'axios';

export default {
    components: {
    },
    data() {
        return {
            projects: null,
            base_api_url: 'http://localhost:8000',
            loading: true
        }

    },
    methods: {
        getProjects(url) {
            // ajax call
            axios
                .get(url)
                .then(response => {
                    console.log(response.data.results);
                    this.projects = response;
                })
                .catch(error => {
                    console.error(error.message.data.results);
                    this.error = error.message;
                })
        },
        getImage(path) {
            console.log(path);
            if (path) {
                return this.base_api_url + path
            }
            return '/img/placeholder.jpg'
        },
    },
    mounted() {
        this.getProjects(this.base_api_url + '/api/projects');
    }
}
</script>

<template>
    <section class="vue-home">
        <div class="container">
            <h1>Projects</h1>
            <div class="row" v-if="projects">
                <div class="col-3 gy-4" v-for="project in projects.data.results">
                    <div class="card border-0">
                        <img class="card-image" :src="getImage(project.cover_image)" alt="">
                        <div class="card-body">
                            <h4>{{ project.title }}</h4>
                            <span><strong>Slug:</strong> {{ project.slug }}</span>
                            <p class="py-3"><strong>Description:</strong> {{ project.description }}</p>
                        </div>
                    </div>

                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss">

</style>

