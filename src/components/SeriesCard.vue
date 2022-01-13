<template>
    <div class="series">
        <div class="face poster">
            <img v-if="details.poster_path" :src="(`https://image.tmdb.org/t/p/w342/` + `${details.poster_path}`)" alt="">
            <img v-else src="../assets/none_poster.png" alt="">
        </div>
        <div class="face infos">
            <ul>
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
    width: 380px;
    flex-shrink: 0;
    display: flex;
}

.face {
    position: relative;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}

.infos {
    display: none;

}

.series:hover .poster {
    display: none;
}

.series:hover .infos {
    display: inline-block;
    border: 1px solid black;
    margin: 10px;
    height: 450px;
}

.poster {
    margin-top: 10px;
    width: 100%;
    height: auto;
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