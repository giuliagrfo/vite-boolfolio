<script>
import { state } from '../state.js'
export default {
    name: 'ProjectCard',
    props: {
        project: Object
    },
    data() {
        return {
            state
        }

    },
    methods: {

        getImage(path) {
            console.log(path);
            if (path) {
                return this.state.base_api_url + '/storage/' + path
            }
            return '/img/placeholder-1.jpg';
        },
        trimDescription(text) {
            if (text.length > 100) {
                return text.slice(0, 100) + '...'
            }
            return text
        }
    }
}
</script>

<template>
    <div class="col-3 gy-4">
        <div class="card border-0">
            <img v-if="project.cover_image" :src="getImage(project.cover_image)" alt="">
            <img v-else src="/img/placeholder-1.png" alt="">
            <div class="card-body">
                <h4>{{ project.title }}</h4>
                <div v-if="project.description != null">
                    <p class="py-3"><strong>Description:</strong>{{ trimDescription(project.description) }}</p>
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
                <div class="single-project mt-3">
                    <router-link :to="{ name: 'single-project', params: { slug: project.slug } }"
                        class="text-decoration-none">Read
                        More</router-link>

                </div>
            </div>
        </div>


    </div>

</template>

<style lang="scss">

</style>

