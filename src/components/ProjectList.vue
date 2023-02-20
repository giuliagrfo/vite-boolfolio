<script>
import ProjectCard from './ProjectCard.vue';
import { state } from '../state.js';
import axios from 'axios';
export default {
    components: {
        ProjectCard,
    },
    data() {
        return {
            state,
            projects: null,
            loading: true,
            error: null
        }
    },
    methods: {
        getProjects(url) {
            // ajax call
            axios
                .get(url)
                .then(response => {
                    console.log(response);
                    this.projects = response;
                    this.loading = false;
                })
                .catch(error => {
                    console.error(error.message);
                    this.error = error.message;
                    this.loading = false;
                })
        },
        prevPage(url) {
            this.getProjects(url)
        },
        nextPage(url) {
            this.getProjects(url)
        }
    },
    mounted() {
        this.getProjects(this.state.base_api_url + '/api/projects');
    }
}
</script>

<template>
    <section id="projects" class=" m-5">
        <div class="container d-flex m-5">
            <div class="title">
                <h1 class="text-uppercase">Projects.</h1>
            </div>

        </div>
        <div class="row g-3" v-if="!loading">
            <ProjectCard :project="project" v-for="project in projects.data.results.data" />
            <nav class="d-flex justify-content-center pt-3" aria-label="Page navigation ">
                <ul class="pagination">
                    <li class="page-item" v-if="projects.data.results.prev_page_url"
                        @click="prevPage(projects.data.results.prev_page_url)">
                        <a class="page-link" aria-label="Previous">
                            <span aria-hidden="true">&laquo;</span>
                        </a>
                    </li>
                    <li class="page-item active" aria-current="page">
                        <a class="page-link" href="#">{{ projects.data.results.current_page }}</a>
                    </li>
                    <li class="page-item" v-if="projects.data.results.next_page_url"
                        @click="nextPage(projects.data.results.next_page_url)">
                        <a class="page-link" aria-label="Next">
                            <span aria-hidden="true">&raquo;</span>
                        </a>
                    </li>
                </ul>
            </nav>
        </div>
        <div class=" text-center" v-else-if="loading">
            <div class="spinner-border m-5" role="status"></div>
            <h6>Loading...</h6>
        </div>

    </section>
</template>

<style lang="scss" scoped>
#projects {
    padding-top: 5rem;
}
</style>