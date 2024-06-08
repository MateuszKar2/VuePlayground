
<template>
    <section>
        <h1>Ships List</h1>
        <StarShipItem v-for="(ship, index) in ships" :key="index" :ship="ship"/>
    </section>

</template>

<script>
import StarShipItem from './StarShipItem'
import ref from 'vue'

    export default {
        name: "StarShipList",
        components: {
            StarShipItem
        },

        async setup() {
            const ships = ref(null)
            const response = await fetch('https://swapi.dev/api/starships/') //będziemy asynchronicznie łądować dane
            const parsedResponse = await response.json() // sparsować dane

            ships.value = [...parsedResponse.results]

        return { ships}
        }
    };
</script>

<style lang="scss" scoped>

</style>