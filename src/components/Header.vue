<template>
    <header>
        <div class="nav">
            <input v-model="userText" type="text" placeholder="Cerca">

            <button @click="$emit('searchDone', userText)">Cerca</button>
        </div>
    </header>
</template>

<script>
export default {
    name: 'Header',
    data: function() {
        return {
            userText: '',
        }
    }
}
</script>


<style lang="scss">
.nav {
    display: flex;
}
</style>