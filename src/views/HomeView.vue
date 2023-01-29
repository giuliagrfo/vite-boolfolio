<script>
export default {
    name: 'HomeView'
}  
</script>

<template>
    <div class="home_page">
        <div class="home">
            <div class="enter_button d-flex flex-column">
                <a href="#menu"><img src="/img/enter.png" alt=""></a>
                <span class="text-center">enter</span>
            </div>

        </div>
        <div class="container d-flex flex-column justify-content-center" id="menu">
            <div class="pages d-flex justify-content-center align-items-center">
                <ul class="list-unstyled text-center">
                    <li><a class="link about" href="/about">About Me</a></li>
                    <li><a class="link projects" href="/projects">Projects</a></li>
                    <li><a class="link contacts" href="/contacts">Contacts</a></li>
                    <li><a class="link git" href="https://github.com/giuliagrfo">GitHub</a></li>
                </ul>
            </div>

            <ul id="social-media" class="list-unstyled d-flex justify-content-center">
                <li class="me-3">
                    <a href="https://github.com/giuliagrfo">
                        <i class="fab fa-github"></i>
                        <span class="screen-reader-text"></span>
                    </a>
                </li>
                <li>
                    <a href="https://www.linkedin.com/in/giulia-grifo-362907262/">
                        <i class="fab fa-linkedin"></i>
                        <span class="screen-reader-text"></span>
                    </a>
                </li>
            </ul>
        </div>
    </div>


</template>

<style lang="scss" scoped>
@import url(https://use.fontawesome.com/releases/v5.0.6/css/all.css);

.home {
    height: calc(100vh);
    background: linear-gradient(0deg, rgba(0, 0, 0, 0.984), rgba(0, 0, 0, 0.677)), url('img/code.gif');
    background-color: rgba(10, 24, 23, 255);
    background-position: center;
    background-repeat: no-repeat;

    .enter_button {
        position: absolute;
        left: 50%;
        top: 55%;

        img {
            width: 50px;
        }

        span {
            color: rgba(245, 1, 87, 255);
        }
    }
}

#menu {
    height: 100vh;

    li {
        text-decoration: none;
        font-family: 'Montserrat', sans-serif;
        font-weight: 900;
        font-size: 80px;
        transition: 0.5s ease-in-out;


        &:hover {
            transform: scale(1.2);
        }

        a {
            text-decoration: none;
        }
    }

    .about {
        color: rgba(111, 119, 244, 255);
    }

    .projects {
        color: rgba(245, 207, 120, 255);
    }

    .contacts {
        color: rgba(255, 117, 98, 255);
    }

    .git {
        color: rgba(140, 200, 237, 255);
    }

    i {
        margin-top: 4rem;
        font-size: 35px;
        color: rgba(111, 119, 244, 255);
    }
}
</style>
