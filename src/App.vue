<template>
  <div id="app">
    <MyAwsomeOne/>
    <RefTwo/>
    <ReactiveThree/>
    <ComputedPropertiesFour/>
    <WatchFive/>
    <ConditionalRenderingSix/>
    <BindSeven/>
    <RenderingListEight/>
    <LifecycleHooksTen/>
    <SlotyEleven/>
    <SuspenseTwelve/>
  </div>
</template>

<script>
// import MyAwsomeOne from './components/MyAwsomeOne.vue';
// import RefTwo from './components/RefTwo.vue';
// import ReactiveThree from './components/ReactiveThree';
// import ComputedPropertiesFour from './components/ComputedPropertiesFour';
// import WatchFive from './components/WatchFive.vue';
// import ConditionalRenderingSix from './components/ConditionalRenderingSix.vue';
// import BindSeven from './components/BindSeven.vue';
// import RenderingListEight from './components/RenderingListEight'
// import LifecycleHooksTen from './components/LifecycleHooksTen.vue';
// import SlotyEleven from './components/SlotyEleven.vue';
import { SuspenseTwelve } from './components/SuspenseTwelve.vue'

export default {
  name: 'App',

  components: {

    // MyAwsomeOne,
    // RefTwo,
    // ReactiveThree,
    // ComputedPropertiesFour,
    // WatchFive,
    // ConditionalRenderingSix,
    // BindSeven,
    // RenderingListEight,
    // LifecycleHooksTen,
    // SlotyEleven
    SuspenseTwelve

  }
}
</script>


