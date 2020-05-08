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
				if (this.meeting.participants.indexOf(this.username) === -1) {
					this.meeting.participants.push(this.username);
				}
				this.$emit('signUp');
            }
        },
		props: ['username', 'meeting']
    }
</script>