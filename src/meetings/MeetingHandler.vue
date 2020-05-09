<template>
	<div v-if="this.meeting.participants.indexOf(this.username) === -1" style="float:right;">
		<button class="button button-outline" @click="signUp()">Zapisz się</button>
		<button v-if="this.meeting.participants.length === 0" style="margin-left:5px;" @click="deleteMeeting()">Usuń puste spotkanie</button>
	</div>
	<div v-else style="float:right;">
		<button class="button button-outline" @click="signOff()">Wypisz się</button>
	</div>
</template>
<script>
    export default {
		props: ['username', 'meeting'],
        methods: {
            signUp() {
				this.meeting.participants.push(this.username);
				this.$forceUpdate();
				this.$emit('signUp');
            },
			signOff() {
				this.meeting.participants.splice(this.meeting.participants.indexOf(this.username), 1);
				this.$forceUpdate();
				this.$emit('signOff');
            },
			deleteMeeting() {
				this.$emit('deleteMeeting', this.meeting);
			}
        }
		
    }
</script>