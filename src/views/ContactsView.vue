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
    <div class="container mt-5 pt-5">
        <h1 class="text-uppercase">Contacts</h1>

        <div v-if="success" class="alert alert-success" role="alert">
            Messaggio inviato con successo!
        </div>

        <form @submit.prevent="sendForm()">
            <div class="mb-3">
                <label for="name" class="form-label">Full Name</label>
                <input type="text" name="name" id="name" v-model="name" class="form-control" placeholder="full name"
                    aria-describedby="fullNameHelper">
                <p v-for="(error) in errors.name" class="alert alert-danger mt-2">
                    {{ error }}
                </p>
                <small id="fullNameHelper" class="text-muted">Add your full name</small>
            </div>
            <div class="mb-3">
                <label for="email" class="form-label">Email</label>
                <input type="email" name="email" id="email" v-model="email" class="form-control"
                    placeholder="name@example.com" aria-describedby="emailHelper">
                <p v-for="(error) in errors.email" class="alert alert-danger mt-2">
                    {{ error }}
                </p>
                <small id="emailHelper" class="text-muted">Add your email address</small>
            </div>

            <div class="mb-3">
                <label for="message" class="form-label">Message</label>
                <textarea class="form-control" name="message" id="message" v-model="message" rows="5"
                    placeholder="type here..."></textarea>
                <p v-for="(error) in errors.message" class="alert alert-danger mt-2">
                    {{ error }}
                </p>
            </div>

            <button type="submit" class="btn btn-primary" :disabled="loading">
                {{ loading? 'Sending..': 'Contact Me' }}
            </button>
        </form>
    </div>

</template>

<style lang="scss" scoped>

</style>