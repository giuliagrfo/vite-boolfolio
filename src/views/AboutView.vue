<script>

export default {
    name: 'AboutView'
}  
</script>

<template>
    <section id="about">
        <div id="banner">
            <h2 class="sign p-5">GG</h2>
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
                    <div class="description">
                        <h4>Knowledge Is Everything</h4>
                        <h1>My Skills</h1>
                        <p class="lead">
                            Sono un'appassionata di tecnologia e coding.
                            Dopo un periodo trascorso nella ristorazione, finalmente ho avuto l'opportunità di
                            mettermi
                            in gioco, iniziando a programmare non solo applicazioni, ma anche il mio futuro.

                        </p>
                        <p class="mt-5">
                            Ho frequentato il corso intensivo di 6 mesi proposto da Boolean per diventare Web
                            Developer
                            e grazie a questa formazione ho acquisito competenze in linguaggi di programmazione
                            Front-end e Back-end come:
                        </p>
                        <div class="row languages">
                            <div class="col">
                                <h6 class="text-uppercase">Html</h6>
                                <p>Linguaggio di Markup</p>
                                <p class="mt-3">Impaginazione e formattazione di pagine Web</p>
                            </div>
                            <div class="col">
                                <h6 class="text-uppercase">Css</h6>
                                <p>Cascading Style Sheets</p>
                                <p class="mt-3">Gestione del design delle pagine Web in combinazione con HTML</p>
                            </div>
                            <div class="col">
                                <h6 class="text-uppercase">Javascript</h6>
                                <p>
                                    Linguaggio di programmazione per realizzare pagine Web interattive,
                                    con relativa conoscenza del suo framework Vue.js
                                </p>
                            </div>
                            <div class="col">
                                <h6 class="text-uppercase">PHP</h6>
                                <p>
                                    Linguaggio di scripting (server side) per la gestione dei dati, con utilizzo del
                                    suo
                                    framework LARAVEL
                                </p>

                            </div>
                        </div>
                    </div>

                </div>
            </div>
            <div id="logo" class="d-flex flex-row justify-content-evenly align-items-center">
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
    margin: 3rem;
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
    height: 100vh;

    .sign,
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
        position: relative;
        top: 130px;
        right: 70px;

        img {
            width: 60px;
            filter: invert(1);
        }
    }
}

// SKILLS
#skills {
    height: 100vh;
    padding-top: 4rem;
}

.left {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    height: fit-content;

}

.right {
    height: fit-content;
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

.description {
    margin: 3.3rem 10rem;
    margin-bottom: 0;

    .col h6 {
        font-size: 20px;
        font-weight: 900;
        color: rgba(111, 119, 244, 255);


    }

    .languages p {
        text-align: left;

    }


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