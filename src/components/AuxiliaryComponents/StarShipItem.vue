


<template>
    <section>
        <p class="ship">{{ ship.name }}</p>
    </section>

</template>

<script>
    export default {
        name: "StarShipItem",
        props: {
            ship: {
                type: Object,
                default: () => {}
            }
        }
    };
</script>

<style lang="scss" scoped>
    .ship {
        color: #fff,
    }
</style>
