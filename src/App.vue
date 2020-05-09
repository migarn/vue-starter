<template>
    <div>
        <h1>System do zapisów na zajęcia</h1>

        <div v-if="authenticatedUsername">
			<logged-in-page :username="authenticatedUsername" :meetings="meetings" @logout="logMeOut($event)"></logged-in-page>
        </div>
        <div v-else>
            <login-form @login="logMeIn($event)"></login-form>
		</div>
    </div>
</template>
<script>
    import "milligram";
    import LoginForm from "./LoginForm";
	import LoggedInPage from "./LoggedInPage";
    export default {
        components: {LoginForm, LoggedInPage},
        data() {
            return {
                authenticatedUsername: '',
				meetings: [],
            }
        },
        methods: {
            logMeIn(username) {
                this.authenticatedUsername = username;
            },
            logMeOut(meetings) {
                this.authenticatedUsername = '';
				this.meetings = meetings;
            }
        }
    }
</script>
