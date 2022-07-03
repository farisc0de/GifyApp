<template>
    <div class="gif" :style="`background-image: url(${gif.images.original.url});`">
        <input ref="url" readonly type="text" :value="gif.images.original.url" style="flex: 1;" />
        <button @click="copyUrl">Copy</button>
    </div>
</template>

<script>
export default {
    name: "GifCard",
    props: {
        gif: Object
    },
    methods: {
        copyUrl() {
            this.$refs.url.select();
            document.execCommand('copy');
            this.$refs.url.value = "Copied (:";
        }
    }
}
</script>

<style scoped>
.gif {
    margin-bottom: 15px;
    width: 240px;
    height: 240px;
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
}
</style>