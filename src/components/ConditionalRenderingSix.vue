
<!-- conditional rendering -->
<!-- dytektywa v-if / v-if-else / v-else , Vue.js daje możliwość skorzystania z zamiennika w postaci v-show-->
<!--różnica między tymi dwoma sposobami jest taka żę (1)element nie będzie renderowany w konsoli dopóki nie zostanie spełniony, w (2)
wszystko bedzie renderowane w konsoli ale niespełniające warunki otrzymają klasę display: none-->

<template>
    <div>
        <p>Masks: {{ masks }}</p>
        <p v-show =  "masks > 3"> You can buy a mask! </p>
        <p v-show = "masks > 0 && masks <= 3"> You can't buy a mask, but hurry up!</p>
        <p v-show = "masks <= 0"> You can't buy a mask, it's out of stock!</p>
        <button v-show = "masks" @click="buyMasks">Buy a mask</button> 
    </div>
</template>

<script>
    import {ref} from 'vue';

    export default {
        name: "ConditionalRenderingSix",
        setup() {
            const masks = ref(5);

                function buyMasks() {
                    masks.value--;
                }

              return { masks, buyMasks} 
        }
    }
</script>















<!-- <template>
    <div>
        
    </div>
</template>

<script>
    import {} from 'vue';

    export default {
        name: "ConditionalRendering",
        setup() {

        }
    }
</script> -->