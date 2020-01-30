<template>
  <div>
    <div class="centre">
    <h1>{{name}}</h1>
    Even numbers
    <span v-for="(data,index) in arr" v-bind:key="index">
      <span v-if="data % 2 ==0">{{data}}</span>
    </span>

    <br />
    <h3>text box</h3>
    <input v-model="message" placeholder="Enter" />

    <p>Message is: {{ message }}</p>
    </div>
    <div class="centreRadio">
      <h3>Radio button</h3>
      <input type="radio" id="male" value="Male" v-model="gender" />
      <label for="male">Male</label>
    <br />
    
    <input type="radio" id="female" value="Female" v-model="gender" />
      <label for="female">Female</label>
      <br />
      <span>Gender: {{ gender }}</span>
    </div>
    <div class="centre">
      <h3>lower to UPPER</h3>
      <button @click="dosomething()">{{btName}}</button>
      <label>{{CheckUpperCase}}</label>
    </div>
    <div class="centre">
      <h3>Take Full Name</h3>
      First name<input type="text" v-model="firstname">
      Last Name<input type="text" v-model="lastname">
    <button @click="computename()">{{Take_full_name}}</button>
    </div>
    <div class="centrelastname">
    Full name
    <label>{{Fullname}}</label>
    </div>

      
 
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "Vue test",
      arr: [],
      message: "",
      gender: "",
      cols: "",
      btName:"",
      uppercase:"",
      CheckUpperCase:"",
      Take_full_name:"",
      firstname:"",
      lastname:"",
      Fullname:""
     
    };
  },
   methods:{
         dosomething() {
         this.CheckUpperCase="UPPERCASE";
         this.CheckUpperCase=this.CheckUpperCase.toUpperCase();
        },
        computename() {
         this.Fullname=this.firstname+'   '+this.lastname;
        }
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
    this.btName="Click";
    this.CheckUpperCase="lowercase";
    this.Take_full_name="Take full name"


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
.centre{
  padding-left:40%;
}
button{
  margin-right: 10px;
  font-size: 14px;
  color: white;
  background-color:green;
  border-color:white;
  cursor:pointer;
}
.centrelastname{
  padding-left:40%;
  margin-top:10px;
  font-size:18px
}
.centrelastname label{
  color:red;
}
.centreRadio{
  padding-left:40%;
  margin-bottom:20px;
  font-size:18px
}
</style>