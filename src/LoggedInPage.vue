<template>
    <div>
		<h2>Witaj {{ username }}!<button @click="$emit('logout')"
			style="float:right;" class="button button-outline">Wyloguj</button></h2>
				
		<div v-if="!addMeetingClicked">
			<button @click=addNewMeeting()>Dodaj nowe spotkanie</button>
		</div>
		
		<div>
			<meeting-page :added="addMeetingClicked"></meeting-page>
		</div>
		
    </div>
</template>

<script>
	import MeetingPage from "./meetings/MeetingPage";
    export default {
		components: {MeetingPage},
		data() {
            return {
                addMeetingClicked: "",
            }
        },
		methods: {
            addNewMeeting() {
                this.addMeetingClicked = true;
            }
        },
		props: ['username']
    }
</script>
