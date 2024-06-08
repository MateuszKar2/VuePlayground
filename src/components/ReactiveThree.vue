<!-- 3.Inny sposób tworzenia reaktywnych danych -->
<!-- Krótszy sposób niż w RefTwoComponent -->


<!-- <template>  
    <div>
      <h1>Price: {{ state.price }}$</h1>  (6)przed każdą z reaktywnych zmiennych wpisujemy state. 
      <button @click="makeOrder">Make next order</button>
      <p>Quantity : {{ state.quantity }}</p>
      <p>Order total price : {{ state.totalPrice }}</p>
      <p>Tax : {{ state.tax }}</p>
    </div>
  </template> -->

 <template>
    <div>
      <h1>Price: {{ price }}$</h1> 
      <button @click="makeOrder">Make next order</button>
      <p>Quantity : {{ quantity }}</p>
      <p>Order total price : {{ totalPrice }}</p>
      <p>Tax : {{ tax }}</p>
    </div>
  </template> 
  
  <script>
//   import { ref } from "vue";//(3)usówamy refa
  import { reactive, toRefs} from "vue"; //(1)importujemy reactive //(8)używająć spread tracimy reaktywnywość, dlatego korzystamy z dodatkowej funkcji - toRefs
  export default {
    name: "ReactiveThree",
    setup(){

    //   const quantity = ref(0);
    //   const price = ref(100)
    //   const totalPrice = ref(0)
    //  const tax = ref(0) //odnosi się to do jendej rzeczy, więc może chcielibyśmy trzymać to w jednym obiekcie 

const state = reactive({
    quantity: 0,
    price: 100,
    totalPrice: 0,
    tax: 0   //(2)tworzymy obiekyt
})

function makeOrder() {  //(4)przed każdą zmienną wpisuje state, ze względu na to że jest to obiekt, nie musimy korzystać już z value
        state.quantity++;
        state.totalPrice = state.quantity * state.price;
        state.tax = state.totalPrice * 0.23;
      }


      return {makeOrder, ...toRefs(state)} //(5)wpisuje state zamiast zmiennych   //(7)wyciągamy właściwości z obiektu za pomocą operatora spread(...)
    }
  }
  </script>