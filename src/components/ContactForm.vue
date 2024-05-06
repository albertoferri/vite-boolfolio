<script>
import axios from 'axios'
export default {
    name: 'ContactForm',
    data() {
        return {
            formData: {
                name: '',
                email: '',
                content: '',
            },
        }
    },
    mounted() {
    },
    methods: {
        sendContactRequest() {

            axios.post('http://127.0.0.1:8000/api/new-contact', this.formData).then(res => {
                
            });
            this.$router.push({

                name: 'home'
            });
        }
    }
}
</script>

<template>

<form @submit.prevent="sendContactRequest()">

    <div class="mb-3">
        <label for="name" class="form-label">Nome</label>
        <input type="text" class="form-control" id="name" name="name" v-model="formData.name" required>
    </div>

    <div class="mb-3">
        <label for="email" class="form-label">Indirizzo email</label>
        <input type="email" class="form-control" id="email" name="email" aria-describedby="emailHelp" v-model="formData.email" required>
        <div id="emailHelp" class="form-text">Non condivideremo la tua mail con terzi.</div>
    </div>

    <div class="form-floating mb-3">
        <textarea class="form-control" placeholder="Inserisci il tuo messaggio" id="content" name="content" v-model="formData.content"></textarea>
        <label for="content">Messaggio</label>
    </div>

    
    <button type="submit" class="btn btn-primary">Invia!!</button>

</form>

</template>


<style lang="scss">
</style>