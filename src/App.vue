<script>
//import HelloWorld from './components/HelloWorld.vue'
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
                    console.log(response.data);
                    this.projects = response.data;
                })
                .catch(error => {
                    console.error(error.message);
                    this.error = error.message;
                })
        }
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
            <div class="row" v-if="!loading">
                <div class="col-3" v-for="project in projects.data">
                    <div class="card">
                        <div class="card-body">
                            <h4>{{ project.title }}</h4>
                        </div>
                    </div>

                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss">
@use './styles/general.scss';
</style>
