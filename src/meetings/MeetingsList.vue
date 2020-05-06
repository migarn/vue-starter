<template>
    <table v-if="meetings.length > 0">
	<h2>Zaplanowane zajęcia</h2>
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
	<div v-else>Brak zaplanowanych spotkań</div>
</template>

<script>
export default {
    props: ['meetings']
}
</script>