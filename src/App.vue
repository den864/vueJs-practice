<template>

  <h1>Get input field Value</h1>
  <input type="text" placeholder="enter text" v.model="text1"/>
  <br/><br/>
  <input type="text" placeholder="enter second text" v.model="text2"/>
  <button type="button" v-on:click="getData()">Get Data</button>

  <div>
    <p v-html="rawHtml"></p>   
  </div>

  <div>
    Hello {{fname}} {{lname}} 
    <p>City is {{address}}</p>
    <p>Contact Number is {{contactNo}}</p>
  </div>

  <!-- you cant pass inner text in div if youre using v-text. -->
  <div v-text="text"></div> 



  <div>
    <button v-on:click="updateText">Click Here to Change Name</button>

    <p>a is {{a}}</p>
    <p>b is {{b}}</p>
    <button v-on:click="calculateSum">click here to calculate Sum</button>
    <p>sum is {{a+b}}</p>

    <p>flag is {{flag?"yes":"no"}}</p>
    <button v-on:click="toggleSomething">Click to Change Flag</button>
  </div>



  <div>
    <button v-bind:disabled="flag">disabled button</button>
  </div>

  <div>
    <button v-on:click="func">Console Print</button>
  </div>

  <div>
    <button v-on:click="showAlert">Click to get alert</button>
  </div>

  <div>
    <button v-on:mouseover="showAlert">Mouse Over to get alert</button>
  </div>

</template>

<script>
export default {
  name: 'App',
  data(){
    return {
      fname:"Dhaval",
      lname:"Birade",
      address:"Navsari",
      contactNo:"000000000000",
      text:"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum",
      a:10,
      b:20,
      flag:false,
      rawHtml:"<h1>raw html</h1>",
      // disableBtn:false,
    }; 
  },

  methods:{
    updateText(){
      this.fname="abcd"
      this.lname="xyzw"
    },
    calculateSum(){
      this.a+=this.b
    },
    toggleSomething(){
      this.flag=!this.flag
    },
    func(){
      console.log("hello")
    },
    showAlert(){
      alert("hello! this is alert message.");
    },
    
  }

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

div{
  margin: 20px;
}

</style>