<script>
export default {
    name: 'HomeView'
}  
</script>

<template>
    <div class="home_page">
        <div class="home">
            <div class="black text-white d-flex align-items-end justify-content-center flex-column">
                <h1>He</h1>
                <h1>llo</h1>
            </div>
            <div class="white">
                <h3>I'm Giulia Grifo,</h3>
                <h3>a Web Developer</h3>
                <button class="cta">
                    <span class="hover-underline-animation"><a href="#menu">Click to enter</a> </span>
                    <svg viewBox="0 0 46 16" height="10" width="30" xmlns="http://www.w3.org/2000/svg"
                        id="arrow-horizontal">
                        <path transform="translate(30)"
                            d="M8,0,6.545,1.455l5.506,5.506H-30V9.039H12.052L6.545,14.545,8,16l8-8Z" data-name="Path 10"
                            id="Path_10">
                        </path>
                    </svg>
                </button>
            </div>
        </div>
        <div id="menu" class="container d-flex flex-column justify-content-center">
            <div class="pages d-flex justify-content-center align-items-center">
                <ul class="list-unstyled text-center">
                    <li><a class="link about" href="/about">About</a></li>
                    <li><a class="link projects" href="/projects">Progetti</a></li>
                    <li><a class="link contacts" href="/contacts">Contatti</a></li>
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
    display: flex;
    align-items: center;


    .black {
        background-color: black;
        width: 40%;
        height: 80%;
        margin-left: 4rem;

        h1 {
            font-size: 200px;
            margin-right: 1rem;
        }
    }

    .white {
        margin-left: 2rem;

        h3 {
            font-size: 80px;
            color: rgba(255, 117, 98, 255);
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
