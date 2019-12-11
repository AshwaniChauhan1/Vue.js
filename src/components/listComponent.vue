<template>
    <div>
        <formComponent v-on:submit-item="submit" />
        <ul>
            <li v-for="(item, index) in items" v-bind:key="index">
                <span>{{item}}</span>
                <a v-on:click="$delete(items, index)">Delete</a>
                <a v-on:click.prevent="editItem(index)" >Edit</a>
            </li>
        </ul>
    </div> 
</template>

<script>
import formComponent from "./formComponent.vue";
export default {
    name: "listComponent",
    components: {
    formComponent
  },
  data:()=>{
      return{
          items:[],
          editIndex: false,
          msg:""
      }
  },
   methods:{
       submit: function(msg) {
        if (e.keyCode === 13) {
                if (this.editIndex ==true) {
                this.items[index] = this.msg;
                this.items.splice(this.indexval,1,this.items[index]),
                //eslint-disable-next-line
                console.log(this.items);
               this.msg = "";
              this.editIndex = false;
              }
              else{
                this.items.push(this.msg);
                this.msg = "";
              } 
            }
    },
   
     editItem: function(index) {
     this.editIndex = true;
     this.indexval =index;
    this.msg = this.items[index];
    },
   }
}
</script>

<style scoped>
 li{
    border: 1px solid;
    padding: 4px;
}
a{
    color:blue;
    float:right;
    padding:4px 8px;
    text-decoration:underline;
}
</style>