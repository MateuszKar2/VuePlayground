<template>
  <div id="app">
    <MyAwsomeComponent/>
    <RefTwoComponent/>
    <ReactiveThreeComponent/>
    <ComputedPropertiesFour/>
    <WatchFive/>
    <ConditionalRendering/>
    <BindSeven/>
  </div>
</template>

<script>
// import MyAwsomeComponent from './components/MyAwsomeComponent.vue';
// import RefTwoComponent from './components/RefTwoComponent.vue';
// import ReactiveThreeComponent from './components/ReactiveThreeComponent';
// import ComputedPropertiesFour from './components/ComputedPropertiesFour';
// import WatchFive from './components/WatchFive.vue';
// import ConditionalRendering from './components/ConditionalRenderingSix.vue';
import BindSeven from './components/BindSeven.vue';
export default {
  name: 'App',

  components: {

    // MyAwsomeComponent,
    // RefTwoComponent,
    // ReactiveThreeComponent,
    // ComputedPropertiesFour,
    // WatchFive,
    // ConditionalRendering,
    BindSeven,
  }
}
</script>


