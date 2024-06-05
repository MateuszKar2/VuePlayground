




<template>
    <div  class="single-item"
            > <!--musi być unkalny klucz w postaci id-->
            <p>Candidate: {{ index + 1 }}</p>
            <p>Name: {{ candidate.firstName }} {{ candidate.lastName }}</p>
            <p>Age: {{ candidate.age }}</p>
            <p v-if="candidate.party">Party: {{ candidate.party }}</p>
            <div v-if="candidate.opinionPool"> 
                Opinion Pool:
                <progress max="100" :value="candidate.opinionPool"></progress> 
                {{ candidate.opinionPool}}%
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
        }
    }
</script>
<style lang="scss" scoped>
        .items-list {
        font-family: Arial;
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        grid-gap: 25px;
        max-width: 1200px;
        margin: 0 auto;

    &__card {
        border: 1px solid black;
        padding: 10px;

    }
    }
</style>