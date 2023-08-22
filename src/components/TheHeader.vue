<script>

export default {
    data() {
        return {
            navLinks: [
                { nameLink: "characters", path: "/" },
                { nameLink: "comics", path: "/comics" },
                { nameLink: "movies", path: "/movies" },
                { nameLink: "tv", path: "/tv" },
                { nameLink: "games", path: "/games" },
                { nameLink: "collectibles", path: "/collect" },
                { nameLink: "videos", path: "/videos" },
                { nameLink: "fans", path: "/fans" },
                { nameLink: "news", path: "/news" },
                { nameLink: "shop", path: "/shop" },
            ],
        }
    },
    methods: {
        isActive(link) {
            if (link === "comics") {
                return "active-link";
            } else {
                return "";
            }
        }
    }
}

</script>

<template>
    <header>
        <div class="logo-container">
            <img class="img-logo" src="../assets/dc-logo.png" alt="dc logo">
        </div>
        <ul class="nav-link">
            <li class="link-list-item" v-for="link in navLinks" :class="isActive(link.nameLink)">
                <a class="link" href="#"> {{ link.nameLink }} </a>
            </li>
        </ul>
    </header>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables.scss" as *;
@use "../styles/partials/mixins.scss" as *;

header {
    @include d-flex;
    @include space-position;
    justify-content: space-between;
}

.nav-link {
    @include my-ul-list;
    gap: 20px;

    li {
        border-top: 4px solid transparent;
        border-bottom: 4px solid transparent;
    }

    .active-link {
        border-bottom: 4px solid $color_primary;
        color: $color_primary;

        .link {
            color: $color_primary;
        }
    }

}

.link-list-item {
    display: flex;
    align-items: center;
}

.link {
    text-decoration: $my_link;
    text-transform: uppercase;
    font-size: 14px;
    color: black;
    font-weight: 600;

    &:visited {
        color: black;
    }
}

.img-logo {
    width: 100%;
}

.logo-container {
    width: 80px;
    padding: 10px 0;
}
</style>