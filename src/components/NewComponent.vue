<template>
<div>
<h1 :class="{red:isRed}">Hello {{title}}</h1>
<br>
<input checked=isRed v-model="isRed" type="checkbox">
<input type="text" v-model="title">
<button v-on:click="clear">Clear</button>
<button v-on:click="caps">Caps</button>
<h2 v-bind:style="{color:color_value.color}">Change to {{color_value.color}} By DropDownn</h2>
<select v-model="color_value">
  <option v-bind:value="{ color: 'red' }">red</option>
  <option v-bind:value="{ color: 'blue' }">blue</option>
  <option v-bind:value="{ color: 'green' }">green</option>
  <option v-bind:value="{ color: 'black' }">black</option>
</select>
<p>DropDown created by array</p>
<select v-model="color_value">
  <option v-for="(col,index) in colors" v-bind:key="index" v-bind:value="{ color: col }">{{col}}</option>
</select>
</div>
</template>

<script>
export default {
  name: 'NewComponent',
  data: () =>{
      return{ 
          title:"New Component",
          isRed:false,
          color_value: {color: "black" },
          colors:["red","blue","green","black"]
          }

    },
    created: function() {
    //eslint-disable-next-line
    console.log("created");
    this.date = new Date();
  },
  mounted: function() {
    //eslint-disable-next-line
    console.log("mounted");
    this.date = new Date();
  },
  updated: function() {
    //eslint-disable-next-line
    console.log("updated");
    // this.message = new Date();
  },
  destroyed: function() {
    //eslint-disable-next-line
    console.log("destroyed");
    this.message = new Date();
  },
methods:{
        clear: function(){
            this.title=''
        },
        caps(){
            this.title= this.title.toUpperCase()
        },
    }
    //  computed: {
    //     date: {
    //         set: function(newvalue) {
    //             //eslint-disable-next-line
    //             console.log(newvalue);
    //             this.date = new Date(newvalue).getTime();
    //         }
    //     }
    // }



}

</script>

<style>
.red{
    color:red;
}
</style>