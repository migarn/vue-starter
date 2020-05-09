<template>
	<div>
		<div v-if="!addMeetingClicked">
			<button @click="clickAddNew()">Dodaj nowe spotkanie</button>
		</div>
		<div v-else>
			<new-meeting-form @added="addNewMeeting($event)"></new-meeting-form>
		</div>
		<meetings-list :meetings="meetings" :username="username"></meetings-list>
	</div>
</template>
<script>
	import NewMeetingForm from "./NewMeetingForm";
	import MeetingsList from "./MeetingsList";
	export default {
		components: {NewMeetingForm, MeetingsList},
		props: ['username', 'meetings'],
		data() {
			return {
				addMeetingClicked: false
			};
		},
		methods: {
			clickAddNew() {
				this.addMeetingClicked = true;
			},
			addNewMeeting(meeting) {
				this.meetings.push(meeting);
				this.addMeetingClicked = false;
				this.$emit('meetings', this.meetings);
			}
		}
	}
</script>