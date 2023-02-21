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
        <div class="container">
            <div class="title">
                <h1 class="text-uppercase">Projects.</h1>
            </div>

            <div class="row g-5 mt-3" v-if="!loading">
                <ProjectCard :project="project" v-for="project in projects.data.results.data" />


                <!-- <nav class="d-flex justify-content-center pt-3" aria-label="Page navigation ">
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
                                                        </nav> -->
            </div>
            <div class="w-100 d-flex justify-content-center" v-else-if="loading">
                <div class="loader"></div>
            </div>
        </div>

    </section>
</template>

<style lang="scss" scoped>
#projects {
    padding-top: 5rem;
}

.loader {
    width: 50px;
    height: 50px;
    position: relative;
    z-index: 1;
    transform: translateX(-50%);
}

.loader::before,
.loader::after {
    content: '';
    position: absolute;
    width: inherit;
    height: inherit;
    border-radius: 50%;
    mix-blend-mode: multiply;
    animation: rotate92523 2s infinite cubic-bezier(0.77, 0, 0.175, 1);
}

.loader::before {
    background-color: rgb(23, 23, 23);
}

.loader::after {
    background-color: rgba(255, 117, 98, 255);
    animation-delay: 1s;
}

@keyframes rotate92523 {

    0%,
    100% {
        left: 35px;
    }

    25% {
        transform: scale(.3);
    }

    50% {
        left: 0%;
    }

    75% {
        transform: scale(1);
    }
}
</style>