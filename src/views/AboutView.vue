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
            <div class="title text-center">
                <h1>About Me</h1>
            </div>
            <div class="name text-center">
                <p>
                    Sono un'appassionata di tecnologia e coding. <br>
                    Con l'accademia di Boolean ho avuto l'opportunità di mettermi in gioco,
                    iniziando a programmare non solo applicazioni, ma anche il mio futuro.
                </p>
            </div>
            <a href="#skills">
                <div class="scrolldown">
                    <div class="chevrons">
                        <div class="chevrondown"></div>
                        <div class="chevrondown"></div>
                    </div>
                </div>
            </a>

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
    font-size: 100px;
}


#banner {
    padding-bottom: 4rem;
    height: calc(100vh - 190px);
    display: flex;
    justify-content: center;
    flex-direction: column;
    position: relative;

    .title h1 {
        font-family: 'Montserrat', sans-serif;
        font-weight: 900;
        color: rgba(255, 117, 98, 255);
    }

    .name {
        display: flex;
        justify-content: center;
    }

    .name p {
        margin-top: 3rem;
        color: black;
        width: 50%;
        text-align: center;
    }

    a {
        text-decoration: none;
        color: black;
    }

    .scrolldown {
        --color: black;
        --sizeX: 30px;
        --sizeY: 50px;
        width: var(--sizeX);
        height: var(--sizeY);
        border: 1px solid;
        border-radius: 50px;
        box-sizing: border-box;
        margin-bottom: 16px;
        cursor: pointer;
        position: absolute;
        top: 80%;
        right: 50%;
    }

    .scrolldown::before {
        content: "";
        position: absolute;
        bottom: 30px;
        left: 50%;
        width: 6px;
        height: 6px;
        margin-left: -3px;
        background-color: var(--color);
        border-radius: 100%;
        animation: scrolldown-anim 2s infinite;
        box-sizing: border-box;
        box-shadow: 0px -5px 3px 1px #2a547066;
    }

    @keyframes scrolldown-anim {
        0% {
            opacity: 0;
            height: 6px;
        }

        40% {
            opacity: 1;
            height: 10px;
        }

        80% {
            transform: translate(0, 20px);
            height: 10px;
            opacity: 0;
        }

        100% {
            height: 3px;
            opacity: 0;
        }
    }

    .chevrons {
        padding: 6px 0 0 0;
        margin-left: -3px;
        margin-top: 48px;
        width: 30px;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .chevrondown {
        margin-top: -6px;
        position: relative;
        left: 8%;
        border: solid var(--color);
        border-width: 0 3px 3px 0;
        display: inline-block;
        width: 10px;
        height: 10px;
        transform: rotate(45deg);
    }

    .chevrondown:nth-child(odd) {
        animation: pulse54012 500ms ease infinite alternate;
    }

    .chevrondown:nth-child(even) {
        animation: pulse54012 500ms ease infinite alternate 250ms;
    }

    @keyframes pulse54012 {
        from {
            opacity: 0;
        }

        to {
            opacity: 0.5;
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

        p {
            text-align: justify;
            padding: 0 4rem;
        }

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