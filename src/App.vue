<template>
    <div>
        <h1>Witaj w systemie zapisów na zajęcia</h1>
		<div v-if="authrnticatedUsername != ''">
		<button@click="logMeOut()"> wyloguj </button>
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
			},
			
			logMeOut() {
			this.authrnticatedUsername = '';
			}
		
		}
    }
</script>
