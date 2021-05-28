<template>
<div>
    <input  type="text" :value="text" placeholder="Select Value" @click="$emit('openlist')" /> 
    </div>
</template>
<script>
export default{
    name: "InputBox",
    props:{
        text:String,
    },
   }
</script>
<style scoped>

input {
  width: 170px;
  height: 25px;
  box-sizing: border-box;
  padding-left: 5px !important;
  padding-top: 0px !important;
  padding-bottom: 0px !important;
  background-color: #fff;
  font-size: 9.75pt !important;
  color: #4a4a4a;
  border:1px solid gray;
  margin-right: 3px;
}
</style>
