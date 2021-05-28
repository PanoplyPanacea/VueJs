<template>
    <div class="container">
        <div class="dropdown">
            <InputBox :showDropdownList="showDropdownList" :text='text' @openlist="$emit('openlist')"/>
         <i @click="$emit('toggle-list')" :class="showDropdownList ? 'fas fa-chevron-up' : 'fas fa-chevron-down'" />
        </div>        
        <list @itemselect="onitemselect" v-show="showDropdownList" :listDisplay="listDisplay" :listValue="listValue"/>
    </div>
</template>
<script>
import InputBox from './InputBox'
import List from './List'

export default{
    name: "DropDown",
    emits:['itemselect', 'openlist'],
    props:{
        showDropdownList: Boolean,
        text:String
        
    },
    data(){
        return{
            listValue:[],
            listDisplay: [],
        }
    },
    components:{
        InputBox,
        List
    },
    methods: {    
        onitemselect(index){
            console.log(index)
            const data = this.listDisplay[index]+" ("+this.listValue[index] +")"
            this.$emit('itemselect', data)
        },
         async fetchList(){
            const res = await fetch('api/list')
            const data = await res.json()
            return data;
        }
    },     
    async created(){
        console.log("hello")
        const list =await this.fetchList();
        console.log(list)
        this.listDisplay = list.display;
        this.listValue = list.value;
    }
    

}
</script>
<style scoped>
.container{
    width: 170px;  
    display: inline-block;
    height: 27px;
    white-space: nowrap;
}
.dropdown{
 width: 100%;
 display: inline-flex;
background-color: #fafafa;
position: relative;
left: 0px;
top: 0px;
z-index: 4;
cursor: default;
}
</style>