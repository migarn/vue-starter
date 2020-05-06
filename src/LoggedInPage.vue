<template>
    <div>
		<h2>Witaj {{ username }}!<button @click="$emit('logout')"
			style="float:right;" class="button button-outline">Wyloguj</button></h2>
				
		<div>
			<button>Dodaj nowe spotkanie</button>
		</div>
		
		<div>
			<meeting-page></meeting-page>
		</div>
		
    </div>
</template>

<script>
	import MeetingPage from "./meetings/MeetingPage";
    export default {
		components: {MeetingPage},
		props: ['buttonLabel', 'username']
    }
</script>
