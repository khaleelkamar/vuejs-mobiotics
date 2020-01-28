<template>
  <div>
    <h1>{{name}}</h1>Even numbers
    <span v-for="(data,index) in arr" v-bind:key="index">
      <span v-if="data % 2 ==0">{{data}}</span>
    </span>

    <br />
    <h3>text box</h3>
    <input v-model="message" placeholder="Enter" />

    <p>Message is: {{ message }}</p>

    <h3>Radio button</h3>
    <input type="radio" id="male" value="Male" v-model="gender" />
    <label for="male">Male</label>
    <br />
    <input type="radio" id="female" value="Female" v-model="gender" />
    <label for="female">Female</label>
    <br />
    <span>Gender: {{ gender }}</span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "Vue test",
      arr: [],
      message: "",
      gender: ""
    };
  },
  beforeCreate() {
    //console.log('beforeCreate')
  },
  created() {
    //console.log('created')
  },
  beforeMount() {
    ///console.log(`beforeMount`)
  },
  mounted() {
    this.arr = [1, 2, 3, 4, 5, 6];

    //console.log("mounted")
  },
  beforeUpdate() {
    //console.log("beforeUpdate")
  }
};
</script>

<style scoped>
span {
  padding-right: 6px;
}
input {
  margin-top: 10px;
}
</style>