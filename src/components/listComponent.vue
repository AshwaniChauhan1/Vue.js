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
          items:[]
      }
  },
   methods:{
       submit: function(msg) {
        this.items.push(msg);
    },
    edit: function() {

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