<template>
  <div class="form">
    <div class="input-field">
        <label for="firstName" class="label font-weight-bold m-b-5">First Name: </label>
        <input v-model="firstName" type="text" id="firstName" class="input input-border" placeholder="First Name">
    </div>

    <div class="input-field">
        <label for="fullName" class="label font-weight-bold m-b-5">Full Name: </label>
        <label >{{ fullName }}</label>
    </div>
    <button v-on:click="speak()">SPEAK</button>
  </div>
</template>
<script lang="tsx">
import { Vue, Component, Prop, Watch } from 'vue-property-decorator'

@Component
export default class PersonClassComponent extends Vue {
  // @Prop() whatToSay: string;
  // @Prop({ default: 'Default saying' }) readonly whatToSay!: string
  @Prop() whatToSay: string | undefined;

  // 初始化
  initialLastName="Smith";
  counter=1;
  firstName="Bob";
  lastName=this.initialLastName;

  // standard component 
  // watch: {
  //     firstName: {
  //         handler() {
  //             // handler code here
  //             this.lastName = this.initialLastName + this.counter ++;
  //             console.log('first name changed')
  //         }
  //     }
  // }
  @Watch('firstName') // watch 的是 <input v-model="firstName" 裡面輸入的值
  public onFirstNameChanged() {
    this.lastName = this.initialLastName + this.counter++;
    console.log('onFirstNameChanged===>',this.lastName)
  }
}
</script>
<!-- 
private renderdDashboardSheet() {
  return (
    <div class="dashboard-sheet">
      <div class="title">實驗</div>
    </div>
   
  )
}

render() {
return (
  <div>{this.renderdDashboardSheet()}</div>
);
} -->

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

