<script>
import axios from 'axios';

export default {
    name: 'ProjectCard',
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
                    console.log(response);
                    this.projects = response;
                })
                .catch(error => {
                    console.error(error.message);
                    this.error = error.message;
                })
        },
        getImage(path) {
            console.log(path);
            if (path) {
                return this.base_api_url + '/storage/' + path
            }
            return '/img/placeholder.jpg';
        },
        trimDescription(text) {
            if (text.length > 100) {
                return text.slice(0, 100) + '...'
            }
            return text
        },
        prevPage(url) {
            this.getProjects(url)
        },
        nextPage(url) {
            this.getProjects(url)
        }
    },
    mounted() {
        this.getProjects(this.base_api_url + '/api/projects');
    }
}
</script>

<template>
    <div class="row" v-if="projects">
        <div class="col-3 gy-4" v-for="project in projects.data.results">
            <div class="card border-0">
                <img v-if="project.cover_image" class="card-image" :src="getImage(project.cover_image)" alt="">
                <img v-else src="/public/img/placeholder-1.png" alt="">
                <div class="card-body">
                    <h4>{{ project.title }}</h4>
                    <p class="py-3"><strong>Description:</strong>{{ trimDescription(project.description ) }}</p>
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
                    <div class="single-project mt-3">
                        <router-link :to="{ name: 'single-project', params: { slug: project.slug } }"
                            class="text-decoration-none">Read
                            More</router-link>

                    </div>
                </div>
            </div>


            <!-- <nav class="d-flex justify-content-center pt-3" aria-label="Page navigation ">
                </div>
   
                <ul class="pagination">
                    <li class="page-item" v-if="projects.prev_page_url" @click="prevPage(projects.prev_page_url)">
                        <a class="page-link" aria-label="Previous">
                            <span aria-hidden="true">&laquo;</span>
                        </a>
                    </li>
                    <li class="page-item active" aria-current="page"><a class="page-link" href="#">{{
                        projects.current_page
                    }}</a></li>
                    <li class="page-item" v-if="projects.next_page_url" @click="nextPage(projects.next_page_url)">
                        <a class="page-link" aria-label="Next">
                            <span aria-hidden="true">&raquo;</span>
                        </a>
                    </li>
                </ul>
            </nav> -->
        </div>
    </div>

</template>

<style lang="scss">

</style>

