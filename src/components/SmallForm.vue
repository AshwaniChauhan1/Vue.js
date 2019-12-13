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
         submit: function(e,index) {
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