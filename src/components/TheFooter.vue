<script>

export default {
    data() {
        return {
            icons: ["footer-facebook.png","footer-twitter.png",
        "footer-youtube.png","footer-pinterest.png","footer-periscope.png"],
        }
    },
    methods: {
        getImagePath(urlImg) {
            return new URL(`../assets/${urlImg}`, import.meta.url).href;
        }
    }
}

</script>

<template>
    <div class="wrapper">
        <section>
            <div class="container-menu-footer">
                <div class="container-ul">
                    <ul class="list-footer">
                        <li>Dc comics</li>
                        <li>Characters</li>
                        <li>Comics</li>
                        <li>Movies</li>
                        <li>TV</li>
                        <li>Games</li>
                        <li>Videos</li>
                        <li>News</li>
                    </ul>
                    <ul class="list-footer">
                        <li>Shop</li>
                        <li>Shop DC</li>
                        <li>Shop DC Collectibles</li>
                    </ul>
                </div>
                <ul class="list-footer">
                    <li>Dc</li>
                    <li>Terms Of Use</li>
                    <li>Privacy policy (New)</li>
                    <li>Ad Choices</li>
                    <li>Advertising</li>
                    <li>Jobs</li>
                    <li>Subscriptions</li>
                    <li>Talent Workshops</li>
                    <li>CPSC Certificates</li>
                    <li>Ratings</li>
                    <li>Shop Help</li>
                    <li>Contact Us</li>
                </ul>
                <ul class="list-footer">
                    <li>Sites</li>
                    <li>DC</li>
                    <li>MAD Magazine</li>
                    <li>DC Kids</li>
                    <li>DC Universe</li>
                    <li>DC Power Visa</li>
                </ul>
            </div>
        </section>
    </div>
    <div id="foot">
        <div class="foot-container">
            <span class="btn">sign-up now!</span>
            <div class="icons">
                <div id="follow">follow us</div>
                <ul class="list-icon">
                    <li v-for="icon in icons">
                        <img :src="getImagePath(icon)" alt="icon" class="img-icon">
                    </li>
                </ul>
            </div>
        </div>
    </div>
    <div id="dark-gray-bar"></div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables.scss" as *;
@use "../styles/partials/mixins.scss" as *;


.wrapper {
    background-image: url("../assets/footer-bg.jpg");
}

#foot {
    background-color: #303030;
    padding: 20px 0;
}
#dark-gray-bar {
    background-color: #202020;
    height: 100px;
}
section {
    padding-top: 30px;
    padding-bottom: 30px;
    @include space-position;
}

.foot-container {
    @include space-position;
    @include d-flex;
    justify-content: space-between;
}

.container-menu-footer {
    @include d-flex;
    gap: 20px;
}

.container-ul {
    @include d-flex-column;
}
.list-icon {
    @include my-ul-list;
    gap: 10px;

    li {
        width: 25px;
        cursor: pointer;
    }
}
.list-footer {
    list-style-type: none;
    padding: 0;
    margin: 18px 0;

    li {
        color: $color_secondary;
        font-size: small;
        padding: 3px;

        &:first-child {
            @include text-white;
            font-size: 18px;
            padding: 12px 3px;
        }
    }
}
.btn {
    @include pill;
    @include text-white;
    border: 2px solid $color_primary;
    padding: 10px;
}
.icons {
    @include d-flex;
    align-items: center;
    gap: 15px;
}
#follow {
    color: $color_primary;
    font-size: 16px;
    text-transform: uppercase;
    font-weight: 600;
}
.img-icon {
        width: 100%;
     }
</style>