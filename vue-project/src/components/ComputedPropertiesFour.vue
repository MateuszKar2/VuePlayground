


<!-- 4.Computed properties -->
<!-- do uproszczenia zapisu (makeorder),  -->
<template>
    <div><h2>Computed properties</h2>
      <h1>Price: {{ price }}$</h1> 
      <button @click="makeOrder">Make next order</button>
      <p>Quantity : {{ quantity }}</p>
      <p>Order total price : {{ totalPrice }}</p>
      <p>Tax : {{ tax }}</p>
    </div>
  </template> 
  
  <script>

  import { ref, computed} from "vue"; 
  export default {
    name: "ComputedPropertiesFour",
    setup(){

    const quantity = ref(0);
    const price = ref(100);
    const totalPrice = computed(() => price.value * quantity.value); //computed będzie obserwowało nasze właśćiwości i jeżeli któraś z nich się zmieni bedzie obliczana na nowo
    const tax = computed(() => totalPrice.value * 0.23) ; 


function makeOrder() {  
        quantity.value++;
        // state.totalPrice = state.quantity * state.price;
        // state.tax = state.totalPrice * 0.23;
      }


      return {makeOrder, quantity, price, totalPrice, tax} 
    }
}
  </script>