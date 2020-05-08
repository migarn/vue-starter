<template>
    <div>
		<h2>Witaj {{ username }}!<button @click="logMeOut()"
			style="float:right;" class="button button-outline">Wyloguj</button></h2>

		<div>
			<meeting-page :meetings="meetings" :username="username" @meetings=meetings></meeting-page>
		</div>
		
    </div>
</template>

<script>
	import MeetingPage from "./meetings/MeetingPage";
    export default {
		components: {MeetingPage},
		methods: {
			logMeOut() {
				this.$emit('logout', this.meetings);
			}
		},
		props: ['username', 'meetings']
    }
</script>
