<template>
    <header>
        <nav class="navbar navbar-expand-lg navbar-light bg-black">
            <div class="container-fluid">
                <a class="navbar-brand text-danger my-style" href="#">BOOLFLIX</a>
                <div class="d-flex">
                    <input v-model="userText" class="form-control me-2" type="text" placeholder="Cerca" aria-label="Search">

                    <button @click="$emit('searchDone', userText)" class="btn btn-outline-success my-type" type="submit">Cerca</button>
                </div>
            </div>
        </nav>
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

.my-style {
    font-family: Bebas Neue, sans-serif;
    font-size: 30px;
}

.my-type {
    color: #dc3545;
    background-color: black;
    border-color: #dc3545;
}

.my-type:hover {
    background-color: rgb(150, 141, 141);
    border-color: #dc3545;
    color: #dc3545;
}
</style>