
<!-- 1.funkcje -->
 <template>
  <div>
    <button @click="sayHello">Say hello</button> <!-- v-on:click === @click -->
  </div>
</template>

<script>
export default {
  name: 'MyAwsomeOne',
  setup(){
    function sayHello() {
      const welcomeText = 'Siema, co tam?'
      console.log(addExclamationText(welcomeText));
    }
    function addExclamationText(text) {
        return `${text}!`
    }
    return {sayHello}
  }
}
</script>
<!-- cd vue-project
npm run serve -->




