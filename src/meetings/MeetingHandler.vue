<template>
	<div style="float:right;">
		<button class="button button-outline" @click="signUp()">Zapisz się</button>
		<button style="margin-left:5px;">Usuń puste spotkanie</button>
	</div>
</template>

<script>
    export default {
        methods: {
            signUp() {
                this.meeting.participants=this.username;
				this.$emit('signUp');
            }
        },
		props: ['username', 'meeting']
    }
</script>