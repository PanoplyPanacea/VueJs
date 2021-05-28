<template>
<div class="listcontainer">
     <ul id="list-1">
        <li :key= "index" 
            v-for="(name, index) in listDisplay"
            @click="$emit('itemselect', index)" >
             {{name}}
        </li>     
    </ul>
</div>
   
</template>
<script>
export default {
    name: "List",
    props:{
        listDisplay: Array,
        listValue: Array
    }

}
</script>
<style scope>
.listcontainer{
    display: table;
    top: 0px;
    left: 0px;    
    width: 100%;
    text-align: left;
}
ul {
  list-style: none;
  font-size: 9pt;
  margin: 0px !important;
  box-sizing: border-box;
  padding: 0px !important;
  border: 1px solid #d7d7d7;
  box-shadow: 2px 2px 3px #a3a3a3;
  -moz-box-shadow: 2px 2px 3px 0 #a3a3a3;
  -webkit-box-shadow: 2px 2px 3px 0 #a3a3a3;
  width: 100%;
  max-height: 300px;
  overflow-y: auto;
  overflow: auto;
  border-top: 0;
}
 li {
  padding-left: 5px;
  padding-right: 5px !important;
  line-height: 24px !important;
  margin-bottom: 2px;
}
li:hover{
    background-color: aquamarine;
}
</style>
