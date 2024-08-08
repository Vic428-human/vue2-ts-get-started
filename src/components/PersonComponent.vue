<template>
  <div class="form">
    <div class="input-field">
        <label for="firstName" class="label font-weight-bold m-b-5">First Name</label>
        <input type="text" id="firstName" class="input input-border" placeholder="First Name" oninput="updateFullName()">
    </div>

    <div class="input-field">
        <label for="fullName" class="label font-weight-bold m-b-5">Full Name</label>
        <span id="fullName"></span>
    </div>

    <button onclick="speak()">SPEAK</button>
  </div>
</template>


<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class PersonComponent extends Vue {
  @Prop() private msg!: string;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.form {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 20px;
    font-family: Arial, sans-serif;
}

.input-field {
    margin-bottom: 20px;
    width: 100%;
}

.label {
    font-weight: bold;
    margin-bottom: 5px;
}

.input {
    /* width: 100%; */
    padding: 8px;
    box-sizing: border-box;
}

.input-border {
    border: 1px solid #ccc;
    border-radius: 4px;
}

.m-b-5 {
    margin-bottom: 5px;
}

button {
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
    background-color: #007BFF;
    color: white;
    border: none;
    border-radius: 4px;
}

button:hover {
    background-color: #0056b3;
}
</style>
