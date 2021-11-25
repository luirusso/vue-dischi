<template>
    <main>
        <div class="container">
            <div class="row">
                <div
                    v-for="(album, index) in albumList"
                    :key="`album-${index}`"
                    class="col card"
                >
                    <div class="card-content">
                        <div class="cover-container">
                            <img :src="album.poster" :alt="album.title" />
                        </div>
                        <div class="card-text">
                            <h3 class="title">
                            {{ album.title }}
                            </h3>
                            <div class="author">
                                {{ album.author }}
                            </div>
                            <div class="year">
                                {{ album.year }}
                            </div>
                            <div class="genre">
                                {{ album.genre }}
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>

<script>
import axios from "axios";

export default {
    name: "Main",
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
            .card {
                display: flex;
                flex-direction: column;
                text-align: center;
                width: calc(100% / 8);
                padding: 1rem;
                .card-content {
                    display: flex;
                    flex-direction: column;
                    background-color: #2e3a46;
                    padding: 1rem;
                    height: 100%;
                }
                .card-text {
                    align-self: center;
                    justify-self: flex-end;
                }
                .title {
                    color: white;
                    text-transform: uppercase;
                    padding: 1rem 0;
                    font-weight: 200;
                }
                .author {
                    color: #717075;
                    padding: 5px 0;
                }
                .year {
                    color: #717075;
                    padding: 5px 0;
                }
                .genre {
                    color: white;
                    padding-top: 5px;
                }
                .cover-container {
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
