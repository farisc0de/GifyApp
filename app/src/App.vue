<template>
  <SearchBar @fetch-gifs="onFetch" />
  <GifList :gifs="gifs" />
</template>

<script>

import SearchBar from "@/components/SearchBar.vue";
import GifList from "@/components/GifList.vue";

export default {
  name: 'App',
  components: {
    SearchBar,
    GifList
  },

  data() {
    return {
      gifs: []
    }
  },

  methods: {
    onFetch(result) {
      this.gifs = result;
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  padding: 50px;
}
</style>
