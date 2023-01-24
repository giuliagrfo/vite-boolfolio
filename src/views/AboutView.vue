<script>

export default {
    name: 'AboutView'
}  
</script>

<template>
    <div class="banner">
        <h2 class="sign p-5">GG</h2>
        <div class="name text-center">
            <h2>I'm Giulia Grifo</h2>
        </div>
        <div class="title text-center">
            <h1>About Me</h1>
        </div>
    </div>

    <div class="row skills g-0">
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
            <h4 class="pt-5 mt-5">Knowledge Is Everything</h4>
            <h1>My Skills</h1>
            <div class="description">
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Mollitia, deserunt facilis adipisci
                    repellat
                    tempora perspiciatis obcaecati inventore nisi possimus nesciunt cum voluptate asperiores provident
                    corrupti debitis distinctio libero explicabo saepe praesentium maiores porro exercitationem
                    accusantium
                    tenetur! Rem placeat facilis, quaerat consequuntur accusantium, explicabo, reiciendis aut quibusdam
                    quia
                    in provident natus reprehenderit blanditiis necessitatibus! Ratione officiis facilis quo, dolorem
                    quaerat sed voluptates omnis ipsa vero magni doloremque nostrum itaque dolore aperiam molestiae sunt
                    esse eveniet iusto quos ullam nisi. Reprehenderit beatae sapiente fugiat ipsa ducimus iure
                    provident,
                    magni obcaecati illum, dolorem doloremque ut facere quas assumenda quos saepe accusamus dicta
                    eveniet.
                </p>
            </div>

        </div>
    </div>
</template>

<style lang="scss" scoped>
h1 {
    font-family: 'Montserrat', sans-serif;
    font-weight: 900;
    font-size: 80px;
}

.banner {
    background-color: rgba(111, 119, 244, 255);
    padding-bottom: 4rem;
    height: 450px;

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

.left {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
}

.description {
    margin: 5.3rem 10rem;
}
</style>