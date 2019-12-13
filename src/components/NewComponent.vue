<template>
<div>
<h1 :class="{red:isRed}">Hello {{title}}</h1>
<input checked=isRed v-model="isRed" type="checkbox">
<input type="text" v-model="title">
<button v-on:click="clear">Clear</button>
<button v-on:click="caps">Caps</button>
<br>
<br>
<ul style="text-align:left">
  <li>Checkbox for Red</li>
  <li>Click Clear button for  clear Heading</li>
  <li>Click Caps button  for Capital Heading</li>
</ul>
</div>
</template>

<script>
export default {
  name: 'NewComponent',
  data: () =>{
      return{ 
          title:"New Component",
          isRed:false,
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