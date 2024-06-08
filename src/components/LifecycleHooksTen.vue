


<template>
    <div>
        <p>Count: {{ count }}</p>
        <button @click="increment" >increment</button>
    </div>
</template>

<script>
import {ref, onBeforeMount, onMounted, onBeforeUpdate, onUpdated, onBeforeUnmount, onUnmounted, onRenderTracked, onRenderTriggered} from 'vue';

export default {
    name: "LifecycleHooksTen",
    setup() {   //wywoływane jest jeden raz przy tworzeniu instancji naszego komponentu

            const count = ref(0);
            function increment() {
                count.value++
            }

            console.log('setup')
            onBeforeMount(() => {
                console.log('onBeforeMount') //zanim zacznie montowanie się naszego komponentu
            });

            onMounted(() => {
                console.log('onMOunted') //wtedy gdy komponent jest zamontowany
            });

            onBeforeUpdate(() => {//jeśli nasze reaktywne dane są zmieniane(przed renderowaniem)
                console.log('onBeforeUpdate')
            });

            onUpdated(() => {  //jeśli nasze reaktywne dane są zmieniane(po renderowaniu)
                console.log('onUpdated')
            });

            onBeforeUnmount(() => {  //zanim instancja zostanie zniszczona, np. w dziecku komponentu
                console.log('onBeforeUnmount')
            });

            onUnmounted(() => {  //po tym jak instancja zostanie zniszczona, np. w dziecku komponentu
                console.log('onUnmonted')
            });
            //(Unmounted)usówać listenry, konczyć połączenie z bazą danych

            //są inne hooki, z których będziemy korzystać później:
            //onActivated - komponent aktywowany
            //onDeactivated - komponetn dezaaktywowany

            //onErrorCaptured - błąd w komponencie dziecka

            onRenderTracked((e) => {
                console.log('onRenderTracked', e)
            }); //dlaczego nasz komponent się zrenderował ponownie
            onRenderTriggered((e) => {
                console.log('onRenderTriggered', e)
            }); //dlaczego nasz komponent się zrenderował ponownie
        return {count, increment};
    }
}
</script>

<style lang="scss"></style>