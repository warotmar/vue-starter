<template>
    <div>
        <h1>Witaj w systemie zapisów na zajęcia</h1>
		<div v-if="authrnticatedUsername != ''">
		<h3>Jesteś zalogowany jako {{authrnticatedUsername}} </h3>
		<a@click="logMeOut()"> wyloguj </a>
		</div>

<div v-else>
        <input type="email" v-model="email">
		<button@click="logMeIn()"> zaloguj </button>
		</div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                email: '',
				authrnticatedUsername: ''
            }
        },
		
		methods: {
			logMeIn() {
			this.authrnticatedUsername = this.email;
			this.email = '';
			},
			
			logMeOut() {
			this.authrnticatedUsername = '';
			}
		
		}
    }
</script>
