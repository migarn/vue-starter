<template>
    <div>
        <h1>System do zapisów na zajęcia</h1>

        <div v-if="authenticatedUsername">
			<logged :username="authenticatedUsername" @logout="logMeOut()"></logged>
        </div>

        <div v-else>
            <login-form @login="logMeIn($event)"></login-form>
			</div>

    </div>
</template>

<script>
    import "milligram";
    import LoginForm from "./LoginForm";
	import Logged from "./Logged";

    export default {
        components: {LoginForm, Logged},
        data() {
            return {
                authenticatedUsername: '',
            }
        },
        methods: {
            logMeIn(username) {
                this.authenticatedUsername = username;
            },
            logMeOut() {
                this.authenticatedUsername = '';
            }
        }
    }
</script>
