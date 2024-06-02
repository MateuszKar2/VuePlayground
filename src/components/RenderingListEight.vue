<!-- v-for- renderowanie listy -->

<template>
    <div  class="candidates">
        <div v-for="(candidate,index) in candidates" :key="candidate.id" class="candidates__card"><!--musi być unkalny klucz w postaci id-->
            <p>Candidate: {{ index + 1 }}</p>
            <p>Name: {{ candidate.firstName }} {{ candidate.lastName }}</p>
            <p>Age: {{ candidates.age }}</p>
            <p>Party: {{ candidate.party }}</p>
            <div>
                Opinion Pool:
                
            </div>
        </div>
    </div>
</template>

<script>
    import {ref} from 'vue';

    export default {
        name: "RenderingListEight",
        setup() {
            const candidates = ([
                {
                    id: 1,
                    firstName: 'Zuzanna',
                    lastName: 'Janiszewska',
                    age: 25,
                    party: 'Lewica',
                    opinionPool: 203,
                }
                {
                    id: 2,
                    firstName: 'Agnieszka',
                    lastName: 'Kubik',
                    age: 27,
                    party: 'PIS',
                    opinionPool: 149,
                }
                {
                    id: 1,
                    firstName: 'Natalia',
                    lastName: 'Laskowska',
                    age: 43,
                    party: 'PO',
                    opinionPool: 271,
                }
                {
                    id: 1,
                    firstName: 'Michał',
                    lastName: 'Kubik',
                    age: 21,
                    party: 'Konfederacja',
                    opinionPool: 42,
                }
                {
                    id: 1,
                    firstName: 'Adam',
                    lastName: 'Borkowski',
                    age: 26,
                    party: 'Lewica',
                    opinionPool: 203,
                }
            ])
                    return {candidates}
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