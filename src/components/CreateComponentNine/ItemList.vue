<!--Tworzenie komponentów-->

<template>
    <div  class="items-list">
        <SingleItem
            v-for="(item,index) in items" 
            :key="item.id"
            :index= "index"
            :item="item"
            />
    </div>
</template>

<!-- Są różne sposoby na zapisy propsów, najlepszy jest poniżej ponieważ możemy określić type propsa -->
<script>

import SingleItem from './item/SingleItem';


    export default {
        name: 'ItemList',
     
        
components: {
    SingleItem
},

        props: {
            items: {
                type: Array,
                default: () => [
                {
                    id: 1,
                    firstName: 'Zenek',
                    lastName: 'Janik',
                    age: 65,
                    party: 'Platforma',
                },
                {
                    id: 2,
                    firstName: 'Józef',
                    lastName: 'Kubik',
                    age: 77,
                    party: 'Narodowa',
                },
                ] //domyślna wartość
            }
        },
    };

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