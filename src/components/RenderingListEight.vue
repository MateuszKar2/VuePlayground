<!-- v-for- renderowanie listy -->
<!--nie powiniśmy mieszać warunkowania z v-if-->

<template>
    <div  class="candidates">
        <div v-for="(candidate,index) in candidateWithParty" 
            :key="candidate.id"
            class="candidates__card"
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
    </div>
</template>

<script>
    import {ref, computed} from 'vue';

    export default {
        name: "RenderingListEight",
        setup() {
            const candidateWithParty = computed(() => candidates.value.filter(({party}) => party))
            const candidates = ref([
                {
                    id: 1,
                    firstName: 'Zuzanna',
                    lastName: 'Janik',
                    age: 25,
                    party: 'Lewica',
                    opinionPool: 20.3,
                },
                {
                    id: 2,
                    firstName: 'Agnieszka',
                    lastName: 'Kubik',
                    age: 27,
                    party: '',
                    opinionPool: 14.9,
                },
                {
                    id: 3,
                    firstName: 'Natalia',
                    lastName: 'Laskowska',
                    age: 43,
                    party: 'PO',
                    opinionPool: 27.1,
                },
                {
                    id: 4,
                    firstName: 'Michał',
                    lastName: 'Kubik',
                    age: 21,
                    party: 'Konfederacja',
                    opinionPool: 4.2,
                },
                {
                    id: 5,
                    firstName: 'Adam',
                    lastName: 'Borkowski',
                    age: 26,
                    party: 'Lewica',
                    opinionPool: 11.9,
                },
                {
                    id: 6,
                    firstName: 'Paweył',
                    lastName: 'Dobosz',
                    age: 47,
                    party: 'PIS',
                    opinionPool: 35.9,
                }
            ])
                    return {candidates, candidateWithParty}
        }
    }
</script>
<style lang="scss">
    .candidates {
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