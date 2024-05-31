<!-- v-bind(:) -dyrektywa pozwalająca dynamicznie dodawać elementy i atrybuty -->

<template>
    <div>
    <div>
        <p>Masks: {{ masks }}</p>
        <p v-if =  "masks > 3"> You can buy a mask! </p>
        <p v-else-if = "masks > 0 && masks <= 3"> You can't buy a mask, but hurry up!</p>
        <p v-else > You can't buy a mask, it's out of stock!</p>
        <button class="btn" 
        @click="buyMasks" 
        :disabled="!masks" 
        :style="{ 'btn__warning': masks > 0 && masks <= 3 }">Buy a mask
        </button>
        <!-- (3) -->
        <!-- :style="{backgroundColor: '#077bff', color: 'black'}">Buy a mask</button>  -->
        <!-- (2)stylee wbudowane  -->
    </div>
    <div>
        <img 
        :src="images[currentIamge]" 
        :alt="`Image ${currentIamge} + 1`" 
        class="image" />
        <button class="btn" @click="ChangeImage" :disabled="currentIamge >= images.length - 1"> Change Image</button>
    </div>
    </div>
</template>

<script>
    import {ref, toRef, reactive} from 'vue';

    export default {
        name: "BindSeven",
        setup() {
            const masks = ref(5);
            
            const styles = reactive({
                btn: {
                    backgroundColor: '#17a2b8',
                    color: '#fff',
                }
            })

                function buyMasks() {
                    masks.value--;
                }

                const images = ref([
                    'https://cdn.pixabay.com/photo/2023/06/25/11/12/orange-flowers-8087066_1280.jpg',
                    'https://cdn.pixabay.com/photo/2023/01/05/13/34/rose-7698947_960_720.jpg',
                ])

                const currentIamge = ref(0);

                function ChangeImage() {
                    currentIamge.value++
                }

              return { masks, buyMasks , ...toRef(styles), images, currentIamge, ChangeImage} 
        }
    }
</script>

<style lang="scss">//(1)
.btn {
    color: white;
    background-color: green;
    border: none;
    padding: 5px, 10px;
    font-size: 16px;
    cursor: "pointer";
    transition: "background-color 0.1 easy-in";

&--warning {
    background-color: '#17a2b8';
    color: '#fff';
}
&:disabled {
    cursor: default;
    background-color: #bd213b;
}
}
.image {
    margin-top: 50px;
    width: 300px;
    display: block;
}
</style>