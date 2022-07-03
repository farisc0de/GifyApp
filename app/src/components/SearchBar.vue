<template>
    <input type="text" placeholder="Type something to search for gif" v-model="keyword" @input="onInput">
</template>

<script>
export default {
    name: "SearchBar",
    data() {
        return {
            keyword: '',
            timeout: null
        }
    },
    methods: {
        onInput() {
            clearTimeout(this.timeout);
            this.timeout = setTimeout(() => {
                this.search();
            }, 500)
        },
        search() {
            let apiKey = "API_KEY";
            fetch(`https://api.giphy.com/v1/gifs/search?api_key=${apiKey}&q=${this.keyword}&limit=10`).then(response => response.json()).then(result => {
                this.$emit("fetch-gifs", result.data);
            });
        }
    }
}
</script>

<style scoped>
input {
    padding: 10px 14px;
    border-radius: 4px;
    font-size: 18px;
    outline: 0;
    border: 2px solid #5f5f5f;
    width: 100%;
    display: block;
}

input:focus {
    border-color: #0078e0;
}
</style>