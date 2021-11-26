<template>
    <header>
        <a href="">
            <img src="../assets/logo.png" alt="" />
        </a>
        <div>
            <label for="genre">Filtra per genere</label>
            <select 
            v-model="filterGenre"
            @click="$emit('performFilter', filterGenre)"
            id="genre">
                <option value="pop">Pop</option>
                <option value="rock">Rock</option>
                <option value="metal">Metal</option>
                <option value="jazz">Jazz</option>
            </select>
        </div>
    </header>
</template>

<script>
export default {
    name: "Header",
    data() {
      return {
        filterGenre: '',
      }
    }
};
</script>

<style scoped lang="scss">
header {
    padding: 1rem 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 65px;
    color: white;
    background-color: #2e3a46;
    img {
        max-width: 48px;
    }
    label {
        padding-right: 20px;
    }
    select {
        padding: 0.5rem 5rem;
        border-radius: 10px;
        background-color: #1d2d3c;
        color: white;
        cursor: pointer;
    }
}
</style>
