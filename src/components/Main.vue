<template>
  <main>
    <div class="container">
        <div class="row">
            <div 
                v-for="(album, index) in albumList"
                :key="`album-${index}`"
                class="col card"
            >
                <div class="cover-container">
                    <img :src="album.poster" :alt="album.title">
                </div>
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
  </main>
</template>

<script>
import axios from 'axios';

export default {
    name: 'Main',
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
                this.albumList = result.data.response;
            })
            .catch(err => console.log(err));
        }
    },
};
</script>

<style scoped lang="scss">
main {
    background-color: rgb(29, 45, 60);
    flex-grow: 1;

    .container {
        width: 95%;
        margin: 0 auto;
        .row {
            padding: 7rem 0;
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            align-items: center;
            align-content: center;
            .card {
                    display: flex;
                    flex-direction: column;
                    /* height: 300px; */
                    /* width: 200px; */
                    align-content: center;
                    justify-content: center;
                    align-items: center;
                    text-align: center;
                    background-color: #2E3A46;
                    margin: 1rem 1rem;
                    width: calc(100% / 8 - 2rem);
                    padding: 1rem;
                    height: 100%;
                .cover-container {
                    height: 162px;
                    width: 150px;
                    overflow: hidden;
                    img {
                        width: 100%;
                    }
                }
            }       
        }
    }
}
</style>