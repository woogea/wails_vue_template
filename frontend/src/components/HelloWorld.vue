<template>
  <div class="hello">
    <input type="text" v-model="yourname"/>
    <input type="button" value="run" @click="greeting()"/>
    <h1>{{msg}}</h1>
  </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  props: {
  },
  data:function(){
    return{
      yourname: "",
    }
  },
  methods:{
    greeting: async function(){
      await window.go.main.App.Greet(this.yourname).then((result)=>{
        console.log(result)
        this.msg = result;
      })
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
