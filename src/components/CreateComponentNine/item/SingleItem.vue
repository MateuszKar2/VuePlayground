




<template>
    <div  class="single-item"> 
        <!--musi być unkalny klucz w postaci id-->
            <p>Candidate: {{ index + 1 }}</p>
            <p>Name: {{ firstName }} {{ lastName }}</p>
            <p>Age: {{ ageWithYear }}</p>
            <p v-if="item.party">Party: {{ item.party }}</p>
            <div v-if="item.opinionPool"> 
                Opinion Pool:
                <progress max="100" :value="item.opinionPool"></progress> 
                {{ item.opinionPool}}%
            </div>
        </div>
</template>

<script>
import { computed } from 'vue';

    export default {
        name: "SingleItem",
        props: {
            item: {
                type: Object,
                default: () => ({}),
            },
            index: {
                type: Number,
                default: 0,
            },
            firstName: {
                type: String,
                default: '',
            },
            lastName: {
                type: String,
                default: '',
                //required: true,//pole jest wymagane
            },
            age: {
                type: Number,
                default: 0,
            },
        },
        setup(props) {
            const ageWithYear = computed(() => `${props.age} years`)

            return { ageWithYear }
        }
    }
</script>
<style lang="scss" scoped>//scoped - indywidualny identyfikator, style nie będą się powtarzać/klasa dotyczy tylko tego komponentu

         .single-item {
            border: 1px solid black;
            padding: 10px;
         }

</style>