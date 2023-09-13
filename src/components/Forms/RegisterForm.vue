<template>
    <div class="register-form">
        <h2>{{ formData.username }}</h2>

        <label for="username">Username:</label>
        <input type="text" id="username" name="username" v-model="formData.username" required><br><br>
        
        <label for="password">Password:</label>
        <input type="password" id="password" name="password" v-model="formData.password" required><br><br>
        
        <label for="confirm_password">Confirm Password:</label>
        <input type="password" id="confirm_password" name="confirm_password" v-model="formData.confirm_password" required><br><br>
        
        <input type="checkbox" id="confirm" name="confirm" v-model="confirm" required>
        <label for="confirm">Confirm registration</label><br><br>
        
        <button id="registerButton">Register</button>
    </div>
</template>
<script>
import axios from 'axios';

export default {

    name: 'RegisterForm',
    data() {
        return {
        formData: {
            username: '',
            password: '',
            confirm_password: '',
            confirm: false,
        },
        registrationResult: null,
        };
    },
    methods: {
        registerUser() {
        // Realizar validaciones aquí si es necesario

        // Hacer la solicitud POST a tu backend utilizando Axios
        axios.post('tu_api_url', this.formData)
            .then(response => {
            // Manejar la respuesta de la API aquí
                this.registrationResult = response.data;
            })
            .catch(error => {
            // Manejar errores de la API aquí
                this.registrationResult = error + 'Error en el registro.';
            });
        },
    }
}
</script>
<style>
    
</style>