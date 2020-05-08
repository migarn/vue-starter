<template>
	<div v-if="this.meeting.participants.indexOf(this.username) === -1" style="float:right;">
		<button class="button button-outline" @click="signUp()">Zapisz się</button>
		<button style="margin-left:5px;">Usuń puste spotkanie</button>
	</div>
	<div v-else style="float:right;">
		<button class="button button-outline" @click="signOff()">Wypisz się</button>
	</div>
</template>

<script>
    export default {
		data() {
            return {
                participants: {}
            };
        },
        methods: {
            signUp() {
				if (this.meeting.participants.indexOf(this.username) === -1) {
					this.meeting.participants.push(this.username);
					this.$forceUpdate();
					this.$emit('signUp');
				}
            },
			signOff() {
				this.meeting.participants.splice(this.meeting.participants.indexOf(this.username), 1);
				this.$forceUpdate();
				this.$emit('signOff');
            }
        },
		props: ['username', 'meeting']
    }
</script>