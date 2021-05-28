<template>
<DropDown @toggle-list="toggleList" @itemselect="itemSelect" @openlist='openList' :text='text' :showDropdownList='showDropdownList' />
</template>

<script>
import DropDown from './components/Dropdown'
export default {
  name: 'App',
  components: {
    DropDown
  },   
  data(){
    return{
        showDropdownList : false,
        text: ''
    }
    },
  methods:{
        toggleList(){
            this.showDropdownList = !this.showDropdownList
            console.log(this.showDropdownList)
        },
        itemSelect(name){
          console.log(name)
          this.text=name
          this.showDropdownList = !this.showDropdownList
        },
        openList(){
          this.showDropdownList =  true;
        }

  }

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
</style>
