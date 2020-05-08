<template>
	<form @submit.prevent="addNewMeeting()">
		<h3>Dodaj nowe spotkanie</h3>
		<label>Nazwa</label>
		<input type="text" v-model="newMeeting.name">
		<label>Opis</label>
		<textarea v-model="newMeeting.description"></textarea>
		<p style="color:red;"><button @click="addNewMeeting()">Dodaj</button> {{ this.warning }}</p>		
	</form>
</template>

<script>
	export default {
		data() {
			return {
				newMeeting: {},
				warning: ""
			};
		},
		methods: {
			addNewMeeting() {
				if (this.newMeeting.name) {
					this.newMeeting.participants = [];
					this.$emit('added', this.newMeeting);
					this.newMeeting = {};
				}
				else {
					this.warning = "Spotkanie musi mieć nazwę!";
				}
			}
		}
	}
</script>