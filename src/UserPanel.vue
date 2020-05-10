<template>
    <div>
        <h2>Witaj {{ username }}</h2>
        <button @click="enter()" style="float: right;">{{ buttonLabelToDisplay }}</button> &nbsp;
    </div>
</template>

<script>
    export default {
        props: ['username', 'buttonLabel'],
		
        methods: {
            enter() {
                this.$emit('logout');
            }
        },

	computed: {
            buttonLabelToDisplay() {
                return this.buttonLabel || 'Wyloguj się';
            }
        }		
    }
</script>
