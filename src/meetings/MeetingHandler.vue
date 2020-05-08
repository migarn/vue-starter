<template>
	<div v-if="this.meeting.participants.length > 0" style="float:right;">
		<button class="button button-outline">Wypisz się</button>
	</div>
	<div v-else style="float:right;">
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