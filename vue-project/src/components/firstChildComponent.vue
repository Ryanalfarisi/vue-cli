<template>
  <div class="first-child">
    <h3>I'm first child components</h3>
    <p>this name given by parent</p>
    <p style="font-weight:bold;">First child name : {{parentname}}</p>
    <button class="button" @click="resetName()">Reset name</button>
  </div>
</template>

<script>
export default {
  props:['parentname'],
  methods:{
    resetName(){
      this.parentname = "Jhon Doe"
      this.$emit('nameWasReset',this.parentname);
    }
  }
 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.first-child{
    width: 100%;
    height: 150px;
    background-color: white;
    padding: 10px;
    border-radius: 20px;
    border: 3px solid #73c000;
}
.first-child p{
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
</style>
