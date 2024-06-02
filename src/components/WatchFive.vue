<!-- watch - służy do obserwowania naszych zmiennych, rzeczy które mogą się zmieniać -->

<template>
    <div>
        <p>You have 
            <strong>{{ shares }}</strong> shares and their value is 
            <strong>{{ shareValue }}</strong>, because shere price is 
            <strong>{{ sharePrice }}$</strong></p>
            <button @click="changeNumberOfShare(5)">Buy one share</button>
            <button @click="changeNumberOfShare(1)">Buy five shares</button>
            <button @click="changeNumberOfShare(-1)">Sell one share</button>
            <button @click="changeNumberOfShare(-5)">Sell five shares</button>
    </div>
</template>

<script>
import {computed, ref, watch} from 'vue';

export default {
    name: "WatchFive",
    setup() {
        const shares = ref(15);
        const sharePrice = ref(20);
        const shareValue = computed(() => shares.value * sharePrice.value);

        function changeNumberOfShare(number) {
            if (shares.value + number >= 0) {
            shares.value += number
            }
        }

        watch(shares, (shares, prevSheres) => { //jeżeli chcemy obserwowaćwię więcej niż jedną rzecz wtedy pakujemy to do tablicy ;)
            shares > prevSheres ? getPrice(1, 5) : getPrice(-5, -1)
        })

        function getPrice(min, max) {
            const priceDiff = Math.floor(Math.random() * (max - min) + min )
            if (sharePrice.value + priceDiff >= 0){
                sharePrice.value += priceDiff
            }
        }

        return{ shares, sharePrice, shareValue, changeNumberOfShare, getPrice};
    }
}


</script>