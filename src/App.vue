<script setup>
// ref is used here to make an element reactive 
import { ref } from 'vue';
// Your JS logic goes here
// Using Composition API 

    // Reactive state of the variable location
    const location = ref("London");
    // Creating a counter for cart 
    const counter = ref(0);
    // Function to change location with the button click
    const changeLocation = () =>{
      if(location.value === "London")
    {
        location.value = 'New York';
    }
    else{
        location.value = 'London';
    }
    }

    const addToCart = () =>{
      if(counter.value < 10)
      counter.value++;
    }

    const removeFromCart = () =>{
      if(counter.value > 0)
      counter.value--;
    }
    const isOpen = ref(false);
</script>

<template>
<!-- Write your HTML here -->
  <h1>Daily Grind Cafe</h1> <br>
  <h2>Delicious Hot Coffee </h2> <br>
  <!-- Using v-if and v-else for conditional rendering -->
  <p v-if="isOpen">We're Open</p>
  <p v-else> We're closed </p>
  <!-- Text Interpolation -->
  <p>Located at {{ location }}</p> <br>
  <!-- Directives : v-on, v-bind, v-if, v-else -->
  <button v-on:click="changeLocation">Change Location</button> <br>
  <!-- Instead of v-on:click you can use @click -->
  <button @click="addToCart" v-bind:disabled="counter === 10" > Add to Cart </button> <br>
  <!-- : disable is shorthand-->
  <button @click="removeFromCart" :disabled="counter === 0 ">Remove From Cart</button> <br>
  <p> Cart: {{ counter }} </p>
</template>
<style scoped>
/* CSS Styles here */
h2{
  color: brown;
}
</style>