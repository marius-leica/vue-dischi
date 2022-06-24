<template>
    <div>
        <nav class="navbar navbar-expand-lg p-0">
            <div class="d-flex justify-space-betwen">
                <a class="navbar-brand py-2" href="#">
                    <img src="/img/spotify_logo.jpg" alt="" width="70" height="70" />
                </a>
                <div class="collapse navbar-collapse" id="navbarSupportedContent">
                    <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
                        <!-- <li class="nav-item" v-for="link in navLinks" :key="link">
                            <a class="nav-link active" aria-current="page" href="#">{{
                                    link
                            }}</a>
                        </li> -->
                    </ul>
                </div>
            </div>
        </nav>
    </div>
</template>

<script>
export default {
    name: 'TheHeader',
    components: {
    }
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/main.scss";

.navbar {
    background-color: $grey_color;
}
</style>