<template>
	<div v-if="this.meetings.length > 0">
		<h2>Zaplanowane zajęcia ({{ meetings.length }})</h2>
		<table>
        <thead>
			<tr>
				<th style="width:175px">Nazwa<br> spotkania</th>
                <th style="width:235px">Opis</th>
				<th>Uczestnicy</th>
				<th></th>
            </tr>
		</thead>
		<tbody>
            <tr v-for="meeting in this.meetings" :key="meeting.name">
                <td>{{ meeting.name }}</td>
                <td>{{ meeting.description }}</td>
				<td><p v-for="participant in meeting.participants" :key="participant">○ {{ participant }}</p></td>
				<td>
					<meeting-handler @signUp="signUp()" @signOff="signOff()" @deleteMeeting="deleteMeeting($event)" :meeting="meeting" :username="username"></meeting-handler>
				</td>
            </tr>
        </tbody>
	</table>
	</div>
	<div v-else>Brak zaplanowanych spotkań.</div>
</template>
<script>
	import MeetingHandler from "./MeetingHandler";
	export default {
		components: {MeetingHandler},
		props: ['username', 'meetings'],
		methods: {
            signUp() {
				this.$forceUpdate();
            },
			signOff() {
				this.$forceUpdate();
            },
			deleteMeeting(meeting) {
				this.meetings.splice(this.meetings.indexOf(meeting), 1);
			}
        }
	}
</script>