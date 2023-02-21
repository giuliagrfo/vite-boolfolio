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
        },

    }
}
</script>

<template>
    <div class="col-4 project">
        <div class="image">
            <img class="img-fluid" v-if="project.cover_image" :src="getImage(project.cover_image)" alt="">
            <img class="img-fluid" v-else src="/img/placeholder-1.png" alt="">
            <div class="card-body">
                <div class="title text-center">
                    <h4 class="">{{ project.title }}</h4>
                    <div class="single-project mt-3">
                        <router-link :to="{ name: 'single-project', params: { slug: project.slug } }"
                            class="text-decoration-none link">Read
                            More</router-link>

                    </div>
                </div>
            </div>
        </div>


    </div>
</template>

<style lang="scss">
.project {
    height: auto;

    .image {
        position: relative;

        img {
            max-width: 100%;
            width: 800px;
            height: 300px;
            object-fit: cover;
            object-position: top;
        }

        .card-body {
            display: none;
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
        }

        &:hover .card-body {
            display: block;
            background-color: rgb(0 0 0 / 88%);
            cursor: pointer;
        }

    }


    .title {
        max-width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;

        h4 {
            font-family: 'Montserrat', sans-serif;
            font-weight: 900;
            font-size: 40px;
            color: white;
        }

        .link {
            font-family: 'Montserrat', sans-serif;
            font-weight: 900;
            font-size: 20px;
            color: rgba(255, 117, 98, 255);
        }
    }
}
</style>

