<script>

import Card from "./Card.vue";
//il file json viene convertito in un array di oggetti memorizzato
//in dcComics
import dcComics from "../db/dc-comics.json";

export default {
    components: {
        Card,
    },
    data () {
        return {
            //copio l'array contenente i dati jason dentro i data del componente
            dcComicsCards: dcComics,
        }
    }
}

</script>

<template>
    <div class="card-wrapper">
        <Card v-for="comicCard in dcComicsCards"
        :path="comicCard.thumb" :priceItem="comicCard.price"
        :seriesItem="comicCard.series" :typeItem="comicCard.type"></Card>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables.scss" as *;
@use "../styles/partials/mixins.scss" as *;

.card-wrapper {
    @include space-position;
    @include d-flex;
    flex-wrap: wrap;
    row-gap: 30px;
}
</style>