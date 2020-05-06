<template>
    <div>
        <h1>System do zapisów na zajęcia</h1>

        <div v-if="authenticatedUsername">
			<logged-in :username="authenticatedUsername" @logout="logMeOut()"></logged-in>
        </div>

        <div v-else>
            <login-form @login="logMeIn($event)"></login-form>
			</div>

    </div>
</template>

<script>
    import "milligram";
    import LoginForm from "./LoginForm";
	import LoggedIn from "./LoggedIn";

    export default {
        components: {LoginForm, LoggedIn},
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
