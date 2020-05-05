<template>
    <div>
		<h2>Witaj {{ username }}!<button @click="$emit('logout')">Wyloguj</button></h2>
        
    </div>
</template>

<script>
    export default {
		props: ['buttonLabel', 'username']
    }
</script>
