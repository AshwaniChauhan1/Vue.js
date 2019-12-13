<template>
    <div>
        <formComponent :propName="name" @edit-item="edit" @submit_item="submit" :editIndex="editIndex"/>
        <ul>
            <li v-for="(item, index) in items" v-bind:key="index">
                <span>{{item}}</span>
                <a v-on:click="$delete(items, index)">Delete</a>
                <a v-on:click.prevent="editItem(index)">Edit</a>
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
          name:"",
          indexval: null
      }
  },
   methods:{
       submit(text) {
            this.items.push(text);

       },
       editItem(index) {
            this.editIndex = true;
            this.indexval =index;
            this.name=this.items[this.indexval];
        },

        edit: function(text) {
            this.items[this.indexval] = text;
            this.items.splice(this.indexval,1,this.items[this.indexval]),
            this.editIndex = false;
            this.indexval = null
            }
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