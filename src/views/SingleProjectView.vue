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
                <div class="col-4">
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
    </div>
</template>


<style lang="scss" scoped>
.single-project {
    margin-top: 6rem;

    .project_image {
        height: 500px;
        overflow-y: scroll;
    }
}
</style>