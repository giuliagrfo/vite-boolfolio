<script>
import NavItem from '../components/NavItem.vue';

export default {
    name: 'AboutView',
    components: {
        NavItem
    }
}  
</script>

<template>
    <NavItem></NavItem>
    <section id="about" class="">
        <div id="banner">
            <div class="name text-center">
                <h2>I'm Giulia Grifo</h2>
            </div>
            <div class="title text-center">
                <h1>About Me</h1>
            </div>
            <div class="scroll d-flex justify-content-end align-items-end">
                <a href="#skills"><img src="/img/scroll-down.gif" alt=""></a>

            </div>
        </div>

        <div id="skills">
            <div class="row g-0">
                <div class="col-4 left d-flex">
                    <div class="box html">
                        <img src="img/html.svg" alt="">
                    </div>
                    <div class="box css">
                        <img src="img/css.svg" alt="">
                    </div>
                    <div class="box js">
                        <img src="img/js.svg" alt="">
                    </div>
                    <div class="box php">
                        <img src="img/php.svg" alt="">
                    </div>
                </div>
                <div class="col-8 right text-center">
                    <div class="description d-flex flex-column align-items-center justify-content-center">
                        <h1>My Skills</h1>

                        <p class="mt-5">
                            Ho frequentato il corso intensivo di 6 mesi proposto da Boolean Careers per diventare Web
                            Developer
                            e grazie a questa formazione ho acquisito competenze in linguaggi di programmazione
                            Front-end e Back-end, utilizzati per la realizzazione di vari progetti che potete trovare
                            <button class="cta">
                                <span class="hover-underline-animation"><a href="/projects">qui</a> </span>
                                <svg viewBox="0 0 46 16" height="10" width="30" xmlns="http://www.w3.org/2000/svg"
                                    id="arrow-horizontal">
                                    <path transform="translate(30)"
                                        d="M8,0,6.545,1.455l5.506,5.506H-30V9.039H12.052L6.545,14.545,8,16l8-8Z"
                                        data-name="Path 10" id="Path_10">
                                    </path>
                                </svg>
                            </button>
                        </p>

                    </div>

                </div>
            </div>
            <div id="logo" class="d-flex flex-row justify-content-between align-items-center">
                <img src="/img/laravel.svg" alt="">
                <img src="/img/bootstrap.png" alt="">
                <img src="/img/figma.png" alt="">
                <img src="/img/nodejs.png" alt="">
                <img src="/img/mysql.png" alt="">
                <img src="/img/vuejs.png" alt="">
            </div>
        </div>



    </section>
</template>

<style lang="scss" scoped>
#about {
    margin: 8rem 4rem;
    margin-bottom: 0;
}

h1 {
    font-family: 'Montserrat', sans-serif;
    font-weight: 900;
    font-size: 80px;
}


#banner {
    background-color: rgba(111, 119, 244, 255);
    padding-bottom: 4rem;
    height: calc(100vh - 190px);
    display: flex;
    justify-content: center;
    flex-direction: column;
    position: relative;

    .title h1 {
        font-family: 'Montserrat', sans-serif;
        font-weight: 900;
    }

    .title h1 {
        color: white;
    }

    .name h2 {
        font-family: 'Playfair Display', serif;
        font-weight: 800;
        margin-top: 8rem;
    }

    .scroll {
        position: absolute;
        top: 80%;
        right: 70px;

        img {
            width: 60px;
            filter: invert(1);
        }
    }
}

// .bio {
//     background-color: ;
// }

// SKILLS
#skills,
#bio {
    padding-top: 6rem;
}

.left {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    height: fit-content;

}

.right {
    max-height: 100%;

    .description {
        height: 100%;

        .col h6 {
            font-size: 20px;
            font-weight: 900;
            color: rgba(111, 119, 244, 255);
        }

        .languages p {
            text-align: left;
        }

    }
}

.box {
    flex-basis: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    aspect-ratio: 1/1;
    transition: 1s ease-in-out;

    img {
        width: 100px;
    }
}

.html {
    background-color: rgba(255, 117, 98, 255);
}

.css {
    background-color: rgba(140, 200, 237, 255);
}

.js {
    background-color: rgba(245, 207, 120, 255);
}

.php {
    background-color: rgba(177, 149, 222, 255);
}



#logo {
    padding: 3rem 0;


    img {
        width: 100px;
        height: fit-content;
        margin-right: 3rem;
    }
}
</style>