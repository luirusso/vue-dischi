<template>
    <main>
        <div class="container">
            <div class="row">
                <div
                    v-for="(album, index) in albums"
                    :key="`album-${index}`"
                    class="col card"
                >   
                    <Cardprop :image="album.poster" 
                    :title="album.title" 
                    :author="album.author" 
                    :year="album.year" 
                    :genre="album.genre"/>
                    
                </div>
            </div>
        </div>
    </main>
</template>

<script>
import Cardprop from '../components/Cardprop.vue';

    export default {
    name: "Main",
    components: {
        Cardprop,
    },
    props: {
        albums: Array,
    }
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
                // .card-content {
                //     display: flex;
                //     flex-direction: column;
                //     background-color: #2e3a46;
                //     padding: 1rem;
                //     height: 400px;
                // }
                // .card-text {
                //     align-self: center;
                //     justify-self: flex-end;
                // }
                // .title {
                //     color: white;
                //     text-transform: uppercase;
                //     padding: 1rem 0;
                //     font-weight: 200;
                // }
                // .author {
                //     color: #717075;
                //     padding: 5px 0;
                // }
                // .year {
                //     color: #717075;
                //     padding: 5px 0;
                // }
                // .genre {
                //     color: white;
                //     padding-top: 5px;
                // }
                // .cover-container {
                //     overflow: hidden;
                //     img {
                //         width: 100%;
                //     }
                // }
            }
        }
    }
}
</style>
