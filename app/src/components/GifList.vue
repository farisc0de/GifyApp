<template>
    <div id="giflist">
        <GifCard v-for="gif in gifs" :key="gif.id" :gif="gif" />
    </div>
</template>

<script>

import GifCard from "@/components/GifCard.vue";

export default {
    name: "GifList",
    components: {
        GifCard
    },
    props: {
        gifs: Array
    }
}
</script>

<style scoped>
#giflist {
    margin-top: 15px;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}
</style>