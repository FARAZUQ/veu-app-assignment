<template>
  <div class="hello">
    <h1>{{ msg }}</h1>           
    <label for="#">Enter Number : </label>
    <input type="text" @keypress="restrictChars($event)" />
    <button>Submit</button>
    <!-- <h2> {{cubeofnumber}}</h2> -->
  </div>
</template>

<script>
export default {
  props: {
    msg: String
  },
  methods: {
      restrictChars: function($event) {
        var ch = String.fromCharCode($event.which);
        if (!(/[0-9]/.test(ch))) {
          $event.preventDefault();
        }
      console.log(ch);
    },
    // cube : function($event) {
    //   console.log($event);
    //   return this.cubeofnumber = this.restrictChars($event);
    // }
  }  
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
input {
    margin: 5px auto;
    border: 1px solid #888
}
h1 {
    color: rgba(44, 122, 238, 0.747);
    text-align: center;
}
div {
    text-align: center;
}
button {
    background-color: rgb(74, 174, 241);
    color: white;
    text-align: center;
    margin: 5px;
    border: 1px solid #888
}
</style>
