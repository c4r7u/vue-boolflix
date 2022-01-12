<template>
    <div class="series">
        <ul>
            <li>
                <img :src="(`https://image.tmdb.org/t/p/w185/` + `${details.poster_path}`)" alt="">
            </li>
            <li>Titolo: {{ details.name }}</li>
            <li>Titolo originale: {{ details.original_name }}</li>
            <li>
                <div>Lingua:<img :src="require(`../assets/${details.original_language}.png`)" alt=""></div>
            </li>
            <!-- <li> {{ details.original_language }}</li> -->
            <li>Voto {{ details.vote_average }}</li>
        </ul>
    </div>
</template>


<script>
export default {
    name: "SeriesCard",
    props: {
        details: Object,
    },
};
</script>

<style scoped lang="scss" >
.series {
    margin: 15px;
    border: 1px solid black;
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