<template>
    <main class="main">
        <div class="container">
            <Filter @onSearch="fetchCharacters" @onStatusChange="fetchCharacters" />
        </div>
        <div class="container">
            <ul class="characters">

                <Character v-for="(element, i) in store.characters" :key="i" :character="element" />

            </ul>
        </div>
    </main>
</template>
  
<script>
import axios from 'axios'
import store from '../store'
import Character from './Character.vue'
import Filter from './Filter.vue'
export default {
    components: {
        Character,
        Filter,
    },
    data() {
        return {
            store,
        }
    },
    computed: {
        characters() {
            return this.store.characters
        }
    },
    methods: {
        fetchCharacters() {
            const search = this.store.search
            axios
                .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=200&offset=0', {
                    params: {
                        fname: search,
                    }
                })
                .then((res) => {
                    this.store.characters = res.data.data
                })
        }
    },
    created() {
        this.fetchCharacters()
    },
}
</script>
  
<style lang="scss" scoped>
.characters {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
}
</style>