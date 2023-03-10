<script>
import axios from 'axios';
import NavItem from '../components/NavItem.vue';
import { state } from '../state.js';

export default {
    name: 'ContactsView',
    components: {
        NavItem
    },
    data() {
        return {
            state,
            name: '',
            email: '',
            message: '',
            loading: false,
            success: false,
            errors: {}
        }
    },
    methods: {
        sendForm() {
            console.log('name', this.name);
            console.log('email', this.email);
            console.log('message', this.message);

            this.loading = true;

            this.errors = {};

            const data = {
                name: this.name,
                email: this.email,
                message: this.message
            }
            axios.post(`${this.state.base_api_url}/api/contacts`, data)
                .then((response) => {
                    this.success = response.data.success;

                    console.log(response);

                    if (this.success) {
                        this.name = '';
                        this.email = '';
                        this.message = '';
                    } else {
                        this.errors = response.data.errors;
                    }

                    this.loading = false
                });

        }
    }
}  
</script>

<template>
    <NavItem></NavItem>
    <section id="contacts" class="m-5">
        <div class="container">
            <h1 class="text-uppercase">Contacts.</h1>

            <div v-if="success" class="alert alert-success" role="alert">
                Messaggio inviato con successo!
            </div>
            <div class="login-box">
                <form @submit.prevent="sendForm()">
                    <div class="user-box">
                        <input required="name" name="name" type="text" v-model="name">
                        <label>Nome</label>
                        <p v-for="(error) in errors.name" class="alert alert-danger mt-2">
                            {{ error }}
                        </p>
                    </div>
                    <div class="user-box">
                        <input required="" name="email" type="email" v-model="email">
                        <label>Email</label>
                        <p v-for="(error) in errors.email" class="alert alert-danger mt-2">
                            {{ error }}
                        </p>
                    </div>
                    <div class="user-box">
                        <textarea name="message" id="message" v-model="message" cols="30" rows="10"
                            placeholder="Messaggio"></textarea>
                        <p v-for="(error) in errors.message" class="alert alert-danger mt-2">
                            {{ error }}
                        </p>
                    </div>
                    <button class="btn" type="submit" :disabled="loading">
                        <span></span>
                        <span></span>
                        <span></span>
                        <span></span>
                        {{ loading ? 'Sending..' : 'Invia' }}
                    </button>
                </form>

            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
#contacts {
    padding-top: 5rem;
}

.login-box {
    width: 900px;
    height: fit-content;
    padding: 40px;
    margin: 20px auto;
    background: rgba(0, 0, 0, .9);
    box-sizing: border-box;
    box-shadow: 0 15px 25px rgba(0, 0, 0, .6);
}

.login-box p:first-child {
    margin: 0 0 30px;
    padding: 0;
    color: #fff;
    text-align: center;
    font-size: 1.5rem;
    font-weight: bold;
    letter-spacing: 1px;
}

.login-box .user-box {
    position: relative;
}

.login-box .user-box input,
textarea {
    width: 100%;
    padding: 10px 0;
    font-size: 16px;
    color: #fff;
    margin-bottom: 30px;
    border: none;
    border-bottom: 1px solid #fff;
    outline: none;
    background: transparent;
}

.login-box .user-box label {
    position: absolute;
    top: 0;
    left: 0;
    padding: 10px 0;
    font-size: 16px;
    color: #fff;
    pointer-events: none;
    transition: .5s;
}

.login-box .user-box input:focus~label,
.login-box .user-box input:valid~label {
    top: -20px;
    left: 0;
    color: #fff;
    font-size: 12px;
}

.login-box form button {
    position: relative;
    display: inline-block;
    padding: 10px 20px;
    font-weight: bold;
    color: #fff;
    font-size: 16px;
    text-decoration: none;
    text-transform: uppercase;
    overflow: hidden;
    transition: .5s;
    margin-top: 40px;
    letter-spacing: 3px
}

.login-box button:hover {
    background: #fff;
    color: #272727;
    border-radius: 5px;
}

.login-box button span {
    position: absolute;
    display: block;
}

.login-box button span:nth-child(1) {
    top: 0;
    left: -100%;
    width: 100%;
    height: 2px;
    background: linear-gradient(90deg, transparent, #fff);
    animation: btn-anim1 1.5s linear infinite;
}

@keyframes btn-anim1 {
    0% {
        left: -100%;
    }

    50%,
    100% {
        left: 100%;
    }
}

.login-box button span:nth-child(2) {
    top: -100%;
    right: 0;
    width: 2px;
    height: 100%;
    background: linear-gradient(180deg, transparent, #fff);
    animation: btn-anim2 1.5s linear infinite;
    animation-delay: .375s
}

@keyframes btn-anim2 {
    0% {
        top: -100%;
    }

    50%,
    100% {
        top: 100%;
    }
}

.login-box button span:nth-child(3) {
    bottom: 0;
    right: -100%;
    width: 100%;
    height: 2px;
    background: linear-gradient(270deg, transparent, #fff);
    animation: btn-anim3 1.5s linear infinite;
    animation-delay: .75s
}

@keyframes btn-anim3 {
    0% {
        right: -100%;
    }

    50%,
    100% {
        right: 100%;
    }
}

.login-box button span:nth-child(4) {
    bottom: -100%;
    left: 0;
    width: 2px;
    height: 100%;
    background: linear-gradient(360deg, transparent, #fff);
    animation: btn-anim4 1.5s linear infinite;
    animation-delay: 1.125s
}

@keyframes btn-anim4 {
    0% {
        bottom: -100%;
    }

    50%,
    100% {
        bottom: 100%;
    }
}

.login-box p:last-child {
    color: #aaa;
    font-size: 14px;
}

.login-box button.a2 {
    color: #fff;
    text-decoration: none;
}

.login-box button.a2:hover {
    background: transparent;
    color: #aaa;
    border-radius: 5px;
}
</style>