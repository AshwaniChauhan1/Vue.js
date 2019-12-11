<template>
    <div>
        <h2>Fill Form and Press Enter</h2>
        <form v-on:submit.prevent>
        <input type="text" placeholder="Enter Something" v-on:keypress="submit" v-model="msg"/>
        </form>
        <ul>
             <li v-for="(item, index) in items" v-bind:key="index"><span>{{item}}</span><a v-on:click="$delete(items, index)">Delete</a><a v-on:click.prevent="editItem(index)">Edit</a></li>
        </ul>
    </div>
    
</template>

<script>

export default {
    name:'SmallForm',
    data: () =>{
        return{
            msg:"",
            items:[],
            editIndex: false
        }
    },
    methods:{
         submit: function(e) {
         if (e.keyCode === 13) {
              if (this.editIndex > 0) {
               this.msg = "";
              this.editIndex = -1;

        } 
        else {
          this.items.push(this.msg);
          this.msg = "";
          //eslint-disable-next-line
     
        }
      }
         },
         editItem: function(index) {
         this.editIndex = index;
        this.msg = this.items[index];
        //eslint-disable-next-line
         
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