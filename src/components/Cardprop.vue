<template>
    <div class="card-content">
        <div class="cover-container">
            <img :src="image" :alt="title" />
        </div>
        <div class="card-text">
            <h3 class="title">
                {{ title }}
            </h3>
            <div class="author">
                {{ author }}
            </div>
            <div class="year">
                {{ year }}
            </div>
            <div class="genre">
                {{ genre }}
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Cardprop",
    props: {
        image: String,
        title: String,
        author: String,
        year: String,
        genre: String,
    },
};
</script>

<style scoped lang="scss">
.card-content {
    display: flex;
    flex-direction: column;
    background-color: #2e3a46;
    padding: 1rem;
    height: 400px;
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
</style>
