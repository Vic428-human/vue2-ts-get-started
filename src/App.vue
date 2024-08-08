<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <PersonComponent :whatToSay="`準備開始模擬table filter 的功能`"></PersonComponent>
    <!-- <DataTable msg="準備開始模擬table filter 的功能"/> -->
  </div>
</template>

<script lang="ts">
// import DataTable from "./components/DataTable.vue";
import PersonComponent from "./components/PersonComponent.vue";

export default {
  components: {
    PersonComponent
  }
}
</script>

<style>
</style>
