<template>
	<div v-if="meetings.length > 0">
		<h2>Zaplanowane zajęcia ({{ meetings.length }})</h2>
		<table>
        <thead>
			<tr>
				<th>Nazwa spotkania</th>
                <th>Opis</th>
            </tr>
		</thead>
		<tbody>
            <tr v-for="meeting in meetings" :key="meeting.name">
                <td>{{ meeting.name }}</td>
                <td>{{ meeting.description }}</td>
            </tr>
        </tbody>
	</table>
	</div>

	<div v-else>Brak zaplanowanych spotkań</div>
</template>

<script>
	export default {
		props: ['meetings']
	}
</script>