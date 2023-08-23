<script>

export default {
    props: {
        path: String,
        priceItem: String,
        seriesItem: String,
        typeItem: String
    },
}

</script>

<template>
    <div class="card">
        <div class="img-container">
            <div class="overlay">
                <span> {{ priceItem }} </span>
                <span> {{ typeItem }} </span>
            </div>
            <img :src="path" :alt="`${seriesItem} image`">
        </div>
        <div class="desc"> {{ seriesItem }} </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables.scss" as *;
@use "../styles/partials/mixins.scss" as *;

$a: 100%;
$b: 10px;
.card {
    flex-basis: calc((#{$a} / 6) - (#{$b}) * 2);
    margin: 0 10px;
    max-width: 146.667px;

    .desc {
        @include text-white;
        overflow-wrap: break-word;
        font-size: 14px;
        font-weight: 600;
        margin-top: 15px;
    }

    .img-container {
        height: 200px;
        position: relative;

        .overlay {
            display: none;
            position: absolute;
            top: 0;
            bottom: 0;
            right: 0;
            left: 0;
        }

        &:hover {

            .overlay {
                display: flex;
                flex-direction: column;
                align-items: center;
                justify-content: center;
                cursor: pointer;
                background-color: rgba(0, 0, 0, 0.5);
                @include text-white;
                font-weight: 600;

                span {

                    &:first-child {
                        font-size: 14px;
                        margin-bottom: 6px;
                    }

                    &:last-child {
                        font-size: 12px;
                    }
                }
            }
        }


        img {
            width: 100%;
            height: 100%;
        }
    }
}

</style>