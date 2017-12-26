<template>
  <div class="wrapper-parent">
      <div id="parent">
        <h1 class="title">I'm a User component (Parent Component)</h1>
        <p>I want to communicate with other child component</p>
        <p style="font-weight:bold;">My name is : {{name}}</p>
        <p>Change my first child name</p> <button class="button" @click="changeName()">Change name</button>
        <hr>
        <div class="col-md-2">
          <user :parentname="name" @nameWasReset="name = $event"></user>
        </div>
        <div class="col-md-2">
          <edit-user></edit-user>
        </div>
      </div>
  </div>
</template>

<script>
import firstChildComponent from "./firstChildComponent"
import secondChildComponent from "./secondChildComponent"
export default {
  data () {
    return {
      name: 'Jhon Doe'
    }
  },
  components:{
    'user' : firstChildComponent,
    'edit-user':secondChildComponent
  },
  methods:{
    changeName(){
      this.name = "Neil amstrong"
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 
.title{
  margin-bottom: 10px;
}
#parent p{
  margin-bottom: 10px;
}
.button{
  border: none;
  width: 120px;
  height: 34px;
  background: #73c000;
  border-radius: 10px;
  font-size: 14px;
  color: white;
  margin-bottom: 10px;
  cursor: pointer;
}
.wrapper-parent{
  padding: 0px 80px;
  height: auto;
}
#parent{
  width: 800px;
  height: 400px;
  background-color: #e3f2fd;
  border: 1px solid;
  border-radius: 10px;
  padding: 47px;
}
.col-md-2{
  width: 47.8%;
  height: auto;
  margin-right: 30px;
  margin-top: 20px; 
  display: inline-block;
  vertical-align: top;
}
.col-md-2:nth-last-child(1) {
  margin-right: 0px;
}
</style>
