<script>
import axios from 'axios'
import { state } from '../state.js'
import NavItem from '../components/NavItem.vue';

export default {
    name: 'SingleProjectView',
    components: {
        NavItem
    },
    data() {
        return {
            project: null,
            state,
            loading: true

        }
    }, methods: {

        getImage(path) {
            console.log(path);
            if (path) {
                return this.state.base_api_url + '/storage/' + path
            }
            return '/img/placeholder-1.jpg';
        }
    },
    mounted() {
        const url = this.state.base_api_url + '/api/projects/' + this.$route.params.slug
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
    <NavItem></NavItem>

    <div class="single-project" v-if="project">
        <div class="container">
            <h1 class="mb-5">
                {{ project.title }}
            </h1>
            <div class="row">
                <div class="col-8">
                    <div class="project_image">
                        <img class="img-fluid" v-if="project.cover_image" :src="getImage(project.cover_image)" alt="">
                        <img class="img-fluid" v-else src="/img/placeholder-1.png" alt="">
                    </div>
                </div>
                <div class="col-4 d-flex justify-content-center flex-column">
                    <div class="content">
                        <h2>{{ project.description }}</h2>
                    </div>
                    <!--<div class="type">
                                                                                            <strong>Tipologia: </strong>
                                                                                            <span v-if="project.type">
                                                                                                {{ project.type.name }}
                                                                                            </span>
                                                                                            <span v-else>No type assigned</span>
                                                                                        </div>

                                                                                        <div class="technologies">
                                                                                            <strong>Tecnologie: </strong>
                                                                                            <template v-if="project.technologies.length > 0">
                                                                                                <span v-for="technology in project.technologies">
                                                                                                    #{{ technology.name }}
                                                                                                </span>
                                                                                            </template>
                                                                                            <template v-else>No technologies assigned</template>
                                                                                        </div> -->

                </div>
            </div>



        </div>
    </div>
</template>


<style lang="scss" scoped>
.single-project {
    margin-top: 6rem;
    padding-bottom: 4rem;

    .row {
        padding: 4rem 0;
    }

    .project_image {
        height: 500px;
        overflow-y: auto;
        overflow: overlay;

        &::-webkit-scrollbar {
            background: transparent;
            width: 5px;
        }

        &::-webkit-scrollbar-thumb {
            background: rgba(255, 117, 98, 255);
            border-radius: 20px;
        }
    }

    .content {
        h2 {
            color: rgba(255, 117, 98, 255);
        }
    }
}
</style>