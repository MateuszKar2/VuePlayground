




<template>
    <div  class="single-item"
            > <!--musi być unkalny klucz w postaci id-->
            <p>Candidate: {{ index + 1 }}</p>
            <p>Name: {{ item.firstName }} {{ item.lastName }}</p>
            <p>Age: {{ item.age }}</p>
            <p v-if="item.party">Party: {{ item.party }}</p>
            <div v-if="item.opinionPool"> 
                Opinion Pool:
                <progress max="100" :value="item.opinionPool"></progress> 
                {{ item.opinionPool}}%
            </div>
        </div>
</template>

<script>

    export default {
        name: "SingleItem",
        props: {
            item: {
                type: Object,
                default: () => ({}),
            }
            index: {
                type: Number,
                default: 0,
            }
        }
    }
</script>
<style lang="scss" scoped/>

        .single-item  {
        border: 1px solid black;
        padding: 10px;
    }
</style>