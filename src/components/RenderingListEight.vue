<!-- v-for- renderowanie listy -->
<!--nie powiniśmy mieszać warunkowania z v-if-->

<template>
    <ItemList :items="candidates"/>
</template>

<script>
    import {ref, computed} from 'vue';
    import ItemList from './item/ItemList'

    export default {
        name: "RenderingListEight",
        components: {
            ItemList,
        },
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
<style></style>


