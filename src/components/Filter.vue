<template>
    <div class="container">
        <input @keyup.enter="$emit('onSearch')" class="search" type="text" v-model="store.search"
            placeholder="Filtra la carta per nome">
    </div>
</template>

<script>
import store from '../store'
export default {
    data() {
        return {
            store,
        }
    },
}
</script>

<style lang="scss" scoped>
.container {
    display: flex;
    justify-content: center;
}

.search {
    width: 300px;
    height: 40px;
    background-color: rgb(84, 12, 12);
    border: 1px solid rgb(255, 255, 255);
    margin-bottom: 20px;
}

.search::placeholder {
    color: rgb(255, 255, 255);
    font-size: 20px;
}
</style>