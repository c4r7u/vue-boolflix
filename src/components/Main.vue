<template>
    <main>
        <!-- <h2>Film</h2> -->
        <div class="movies-container">
            <MovieCard v-for="movie in moviesList" :key="movie.id" :details="movie" />
        </div>
        <!-- <h2>Series</h2> -->
        <div class="series-container">
            <SeriesCard v-for="series in seriesList" :key="series.id" :details="series" />
        </div>
    </main>
</template>


<script>
import MovieCard from "./MovieCard.vue";
import SeriesCard from "./SeriesCard.vue";

export default {
    name: "Main", 
    components: {
        MovieCard,
        SeriesCard
    },
    props: {
        moviesList: Array,
        seriesList: Array
    }
}
</script>


<style lang="scss" scoped>

main {
    background-color: #434343;
    color: black
}


.movies-container {
    display: flex;
    overflow-x: auto;
}

.series-container {
    display: flex;
    overflow-x: auto;
}
</style>