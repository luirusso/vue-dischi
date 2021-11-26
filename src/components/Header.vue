<template>
    <header>
        <a href="">
            <img src="../assets/logo.png" alt="" />
        </a>
        <div>
            <label for="genre">Filtra per genere</label>

            <select id="genre">
                <option value="volvo">Pop</option>
                <option value="saab">Rock</option>
                <option value="mercedes">Metal</option>
                <option value="audi">Jazz</option>
            </select>
        </div>
    </header>
</template>

<script>
export default {
    name: "Header",
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
      background-color: #1D2D3C;
      color: white;
    }
}
</style>
