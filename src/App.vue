<template>
  <div id="app">
    <Header />

    <Main :albums="albumList" />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data() {
        return {
            albumList: [],
        };
    },
    created() {
        this.getAlbums();
    },
    methods: {
        getAlbums() {
            /**
             * Get album list from api
             */
            axios
                .get("https://flynn.boolean.careers/exercises/api/array/music")
                .then((result) => {
                    console.log(result.data);
                    this.albumList = result.data.response;
                })
                .catch((err) => console.log(err));
        },
    },
}
</script>

<style lang="scss">
@import './styles/globals';

#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}
</style>
