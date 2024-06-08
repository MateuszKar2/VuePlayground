Suspense
<template>
    <div class="container">
    <Suspense>
        <template #default>
            <StarShipList></StarShipList>
        </template>
    </Suspense>
    </div>
<script>
import StarShipList from './AuxiliaryComponents/StarShipList.vue';


    export default {
        name: "SuspenseTwelve",
        components: {StarShipList, AppLoader}
    };
</script>

<style lang="scss">
.container {
    width: 100vw;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #000;
    color: #fcd711
}
</style>