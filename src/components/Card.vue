<template>
  <div>
      <div class="row">
          <div 
            v-for="album in albumList"
            :key="`album-${album.title}`"
            class="col-6"
            >
            <img :src="album.poster" :alt="album.title">
            <h2>
                {{ album.title }}
            </h2>
            <div>
                {{ album.author }}
            </div>
            <div>
                {{ album.year }}
            </div>
            <div>
                {{ album.genre }}
            </div>
          </div>
      </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
    name: 'Card',
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
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(result => {
                console.log(result.data);
                this.albumList = result.data;
            })
            .catch(err => console.log(err));
        }
    },
};
</script>

<style scoped lang="scss">

</style>