<template>
	<div style="float:right;">
		<button class="button button-outline" @click="signUp()">Zapisz się</button>
		<button style="margin-left:5px;">Usuń puste spotkanie</button>
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
                this.meeting.participants.push(this.username);
				//participants.push(this.username);
				//meeting.participants = participants;
				this.$emit('signUp');
            }
        },
		props: ['username', 'meeting']
    }
</script>