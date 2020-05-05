<template>
    <div>
		<h2>Witaj {{ username }}!<button @click="$emit('logout')"
			style="float:right;" class="button button-outline">Wyloguj</button></h2>
		<button>Dodaj nowe spotkanie</button>
        
    </div>
</template>

<script>
    export default {
		props: ['buttonLabel', 'username']
    }
</script>
