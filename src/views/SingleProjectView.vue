<script>
import axios from 'axios'
import { state } from '../state.js'

export default {
    name: 'SingleProjectView',

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

    <div class="single-project mt-5" v-if="project">
        <div class="container">
            <img class="w-50" v-if="project.cover_image" :src="getImage(project.cover_image)" alt="">
            <img class="w-50" v-else src="/img/placeholder-1.png" alt="">
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

</template>


<style lang="scss" scoped>

</style>