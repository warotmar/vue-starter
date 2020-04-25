<template>
    <div>
        <h1>Witaj w systemie zapisów na zajęcia</h1>
		<div v-if="authrnticatedUsername != ''">
		<h3>Jesteś zalogowany jako {{authrnticatedUsername}} </h3>
		<a@click="logMeOut()"> wyloguj </a>
		</div>

<div v-else>
        <login-form @login="logMeIn($event)"></login-form>
		</div>
    </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";

    export default {
	components: {LoginForm},
	
        data() {
            return {
                email: '',
				authrnticatedUsername: ''
            }
        },
		
		methods: {
			logMeIn(username) {
			this.authrnticatedUsername = username;
			this.email = '';
			},
			
			logMeOut() {
			this.authrnticatedUsername = '';
			}
		
		}
    }
</script>
