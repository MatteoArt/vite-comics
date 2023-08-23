<script>

export default {
    data() {
        return {
            iconsImg: [
                {
                    name: "digital comics",
                    imgName: "buy-comics-digital-comics.png"
                },
                {
                    name: "dc merchandise",
                    imgName: "buy-comics-merchandise.png"
                },
                {
                    name: "subscription",
                    imgName: "buy-comics-subscriptions.png"
                },
                {
                    name: "comic shop locator",
                    imgName: "buy-comics-shop-locator.png"
                },
                {
                    name: "dc power visa",
                    imgName: "buy-dc-power-visa.svg"
                }
            ]
        }
    },
    methods: {
        getImage(imgUrl) {
            return new URL(`../assets/${imgUrl}`, import.meta.url).href;
        }
    }
}

</script>

<template>
    <section>
            <div class="icons-item" v-for="icon in iconsImg">
                <div class="icon-container">
                    <img :src="getImage(icon.imgName)" :alt="`${icon.name} image`">
                </div>
                <div class="desc"> {{ icon.name }} </div>
            </div>
    </section>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables.scss" as *;
@use "../styles/partials/mixins.scss" as *;

section {
    @include d-flex;
    justify-content: center;
    background-color: $color_primary;
    padding: 40px 0;
    gap: 35px;

    .icons-item {
        @include d-flex;
        align-items: center;
        gap: 8px;
    }

    .desc {
        @include text-white;
        font-size: 14px;
    }

    .icon-container {
        width: 35px;

        img {
            width: 100%;
        }
    }
}
</style>