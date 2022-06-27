<template>
    <div class="card text-center">

        <img :src="info.poster" :alt="`cover of ${info.title}`" class="card-img-top img-poster " />
        <div class="card-body">
            <h5 class="card-title text-white">{{ info.title }}</h5>
            <div class="text-muted">
                <h6>{{ info.author }}</h6>
            </div>
            <div class="text-muted"><span class="fs-6"> {{ info.year }}</span></div>

        </div>

    </div>
</template>

<script>
export default {
    name: 'TheCard',
    props: {
        info: {
            type: Object,
            required: true,
        },

    },
    components: {
    }
}
</script>

<style lang="scss" scoped>
@import "./src/assets/scss/main.scss";

.card {
    border-radius: 0;
    background-color: $grey_color;
    height: 100%;
    margin-bottom: 1rem;
}

.img-poster {
    border-radius: 0;
    width: auto;
    margin-top: 10px;
    margin-left: 10px;
    margin-right: 10px;
}
</style>