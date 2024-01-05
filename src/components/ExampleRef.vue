<template>
  <div class="container mx-auto px-4">
    <h1>Example Ref</h1>
    <p>{{ count }}</p>
    <button @click="increaseCounter">Increase Counter</button>
    <form @submit.prevent="handleSubmit">
      <!-- prevent = not cause page to refresh -->
      <input type="text" v-model="firstName" placeholder="First Name" />
      <!-- v-model = input and property to sync -->
      <input type="text" v-model="lastName" placeholder="Last Name" />
    </form>
    <button @click="handleSubmit">Submit</button>
    <p>Full Name: {{ fullName }}</p>
    <!-- <p>Full Name: {{ fullName }}</p> -->
    <p>Reversed Name: {{ reversedMessage }}</p>
    <p>Count: {{ oldNew }}</p>
  </div>
</template>

<script setup>
import { ref, computed, watch } from "vue";

const count = ref(0);
const firstName = ref("");
const lastName = ref("");
const fullName = ref("");
// const message = ref("Hello");

const increaseCounter = () => {
  //regular function
  count.value++; //the calculation you cant see, its behind the scene. what you only can see now is the action.
  //increase counter here to update value only, not display, so no need computed
  //(Like a magic window to show your display)
};

// const fullName = computed(() => {
//   //computed property
//   return firstName.value + " " + lastName.value; //you can directly see the calculations happening, returning the value for to display.
// });

const reversedMessage = computed(() => {
  return fullName.value.split("").reverse().join("");
});

const oldNew = ref("");
watch(count, (newValue, oldValue) => {
  oldNew.value = `Changed from ${oldValue} to ${newValue}`;
});

const handleSubmit = () => {
  fullName.value = firstName.value + " " + lastName.value;
};
// fill form with firstName and lastName
// submit
//console.log the firstName + lastName
</script>
