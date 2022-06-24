<template>
    <div class="card text-center">

        <img :src="info.poster" :alt="`cover of ${info.title}`" class="card-img-top img-poster" />
        <div class="card-body">
            <h6 class="card-title">{{ info.title }}</h6>
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
        info: Object
    },
    components: {
    }
}
</script>

<style lang="scss" scoped>
</style>