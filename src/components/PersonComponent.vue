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

    <button onclick="speak()">SPEAK</button>
  </div>
</template>


<script lang="ts">
/*
  vue-class-component 作法
  https://github.com/kaorun343/vue-property-decorator

  export default class YourComponent extends Vue {
    @Prop(Number) readonly propA: number | undefined
    @Prop({ default: 'default value' }) readonly propB!: string
    @Prop([String, Boolean]) readonly propC: string | boolean | undefined
  }

  props: {
    propA: {
      type: Number,
    },
    propB: {
      default: 'default value',
    },
    propC: {
      type: [String, Boolean],
    },
  },
*/
export default {
  props: {
    whatToSay: {
        type: String,
        default: "Default saying"
    }
  },
  data() {
      return {
          initialLastName: "Smith",
          counter: 1,
          firstName: "Bob",
          lastName: "Smith"
      };
  },
  computed: {
      fullName() {
          return `${this.firstName} ${this.lastName}`;
      }
  },
  methods: {
      speak() {
          alert("This is " + this.fullName + " speaking. " + this.whatToSay);
      }
  },
  watch: {
      firstName: {
          handler() {
              // handler code here
              this.lastName = this.initialLastName + this.counter ++;
              console.log('first name changed')
          }
      }
  }

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
