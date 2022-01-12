<template>
    <div class="movie">
        <ul>
            <li>Titolo: {{ details.title }}</li>
            <li>Titolo originale: {{ details.original_title }}</li>
            <li>Lingua: {{ details.original_language }}</li>
            <li>Voto {{ details.vote_average }}</li>
        </ul>
    </div>
</template>

<script>
export default {
    name: "MovieCard",
    props: {
        details: Object,
    },
};
</script>


<style scoped lang="scss">
.movie {
    margin: 15px;
    border: 1px solid black;
}

.movie li {
    list-style: none;
}
</style>