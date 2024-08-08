<template>
  <div id="app">
    <label class="h2">Standard Component</label>
    <PersonComponent :whatToSay="`我是 Standard Component`"></PersonComponent>
    <img alt="Vue logo" src="./assets/logo.png">
    <label class="h2">Class Component</label>
    <PersonClassComponent :whatToSay="`我是 Class Component`"></PersonClassComponent>
  </div>
</template>

<script lang="ts">
import PersonComponent from "./components/PersonComponent.vue";
import PersonClassComponent from "./components/PersonClassComponent.vue";

export default {
  components: {
    PersonComponent,
    PersonClassComponent,
  }
}
</script>

<style>
</style>
