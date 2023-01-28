<script>
export default {
    name: 'HomeView'
}  
</script>

<template>
    <div class="home">
        <div class="enter_button d-flex flex-column">
            <a href="#menu"><img src="/img/enter.png" alt=""></a>
            <span class="text-center">enter</span>
        </div>

    </div>
    <div class="container d-flex flex-column justify-content-center" id="menu">
        <div class="pages d-flex justify-content-center align-items-center">
            <ul class="list-unstyled">
                <li><a href="">About Me</a></li>
                <li><a href="">Projects</a></li>
                <li><a href="">Contacts</a></li>
                <li><a href="">GitHub</a></li>
            </ul>
        </div>

        <ul id="social-media" class="list-unstyled d-flex justify-content-center">
            <li>
                <a href="https://dribbble.com/erinesullivan">
                    <i class="fab fa-dribbble"></i>
                    <span class="screen-reader-text"></span>
                </a>
            </li>
            <li>
                <a href="http://codepen.io/erinesullivan/">
                    <i class="fab fa-codepen"></i>
                    <span class="screen-reader-text"></span>
                </a>
            </li>
            <li>
                <a href="https://twitter.com/erin_e_sullivan">
                    <i class="fab fa-twitter"></i>
                    <span class="screen-reader-text"></span>
                </a>
            </li>
            <li>
                <a href="https://www.linkedin.com/in/erinesullivan1">
                    <i class="fab fa-linkedin"></i>
                    <span class="screen-reader-text"></span>
                </a>
            </li>
            <li>
                <a href="https://www.instagram.com/erin_e_sullivan/">
                    <i class="fab fa-instagram"></i>
                    <span class="screen-reader-text"></span>
                </a>
            </li>
        </ul>
    </div>

</template>

<style lang="scss" scoped>
@import url(https://use.fontawesome.com/releases/v5.0.6/css/all.css);

.home {
    height: calc(100vh - 74px);
    background: linear-gradient(0deg, rgba(0, 0, 0, 0.984), rgba(0, 0, 0, 0.843)), url('img/code.gif');
    background-color: rgba(10, 24, 23, 255);
    background-position: center;
    background-repeat: no-repeat;

    .enter_button {
        position: absolute;
        left: 50%;
        top: 60%;

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
}
</style>