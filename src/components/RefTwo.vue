<!-- 2.Tworzenie reaktywnych danych które mogę pokazać w oknie przeglądarki -->

<template>
    <div>
        <button @click="incrementpension">Increment my pension</button>
        <p>Your pension will be: {{ pension }}</p>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue'; //(1)
  export default {
    name: 'RefTwo',
    setup(){
      const pension = ref(100);//(2)

      console.log(pension);
      function incrementpension() {
        pension.value++//(3)   //zmienna nie jest reaktywna, tzn. że zmiany które dokonujemy nie odzwierciedlają się w drzewie dom, dlatego korzystamy z ref
      }
      return { pension, incrementpension }
    }
  }
  </script>