<template>
    <div class="series">
        <ul>
            <li>
                <img :src="(`https://image.tmdb.org/t/p/w342/` + `${details.poster_path}`)" alt="">
            </li>
            <li>Titolo: {{ details.name }}</li>
            <li>Titolo originale: {{ details.original_name }}</li>
            <li>Prima stagione uscita: {{ details.first_air_date }}</li>
            <li>
                <div>Lingua:<img :src="require(`../assets/${details.original_language}.png`)" alt=""></div>
            </li>
            <!-- <li> {{ details.original_language }}</li> -->
            <li>
                <i v-for="(star, i) in voteStar" :key="i" class="fas fa-star"></i>
                <i v-for="(star, j) in (5 - voteStar)" :key="j" class="far fa-star"></i>
            </li>
        </ul>
    </div>
</template>


<script>
export default {
    name: "SeriesCard",
    props: {
        details: Object,
    },
    data: function() {
        return {
            voteStar: Math.round(this.details.vote_average / 2)
        }
    }   
};
</script>

<style scoped lang="scss" >
.series {
    margin: 15px;
    border: 1px solid black;
    width: 420px;
    flex-shrink: 0;
}

li {
    list-style: none;
}
li div img {
    margin-left: 5px;
    width: 18px;
    height: auto;
    background-color: rgb(6, 11, 43);
}
</style>