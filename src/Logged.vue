<template>
    <div>
		<h2>Witaj {{ username }}!<button @click="$emit('logout')" style="float:right;">Wyloguj</button></h2>
        
    </div>
</template>

<script>
    export default {
		props: ['buttonLabel', 'username']
    }
</script>
