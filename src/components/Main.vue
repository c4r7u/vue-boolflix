<template>
    <main>
        <h2>Film</h2>
        <MovieCard v-for="movie in moviesList" :key="movie.id" :details="movie" />

        <h2>Series</h2>
        <SeriesCard v-for="series in seriesList" :key="series.id" :details="series" />
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