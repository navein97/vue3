<template>
  <div class="container mx-auto px-4">
    <h1>Example Ref</h1>
    <p>{{ count }}</p>
    <button @click="increaseCounter">Increase Counter</button>
    <p>Full Name: {{ fullName }}</p>
    <p>Full Name: {{ reversedMessage }}</p>
    <p>{{ oldNew }}</p>
  </div>
</template>

<script setup>
import { ref, computed, watch } from "vue";

const count = ref(0);
const firstName = ref("Jeff");
const lastName = ref("Bong");
const message = ref("Hello");

const increaseCounter = () => {
  //regular function
  count.value++; //the calculation you cant see, its behind the scene. what you only can see now is the action.
  //increase counter here to update value only, not display, so no need computed
  //(Like a magic window to show your display)
};

const fullName = computed(() => {
  //computed property
  return firstName.value + " " + lastName.value; //you can directly see the calculations happening, returning the value for to display.
});

const reversedMessage = computed(() => {
  return message.value.split("").reverse().join("");
});

const oldNew = ref("");
njjn;
watch(count, (newValue, oldValue) => {
  oldNew.value = `Count changed from ${oldValue} to ${newValue}`;
});

// isi form
// submit
//console.log
</script>
