<template>
<div>
    <h2 v-bind:style="{color:color_value.color}">Change to {{color_value.color}} By DropDownn</h2>
    <select v-model="color_value">
        <option v-bind:value="{ color: 'red' }">red</option>
        <option v-bind:value="{ color: 'blue' }">blue</option>
        <option v-bind:value="{ color: 'green' }">green</option>
        <option v-bind:value="{ color: 'black' }">black</option>
    </select>
    <h4>Below DropDown created by Array</h4>
    <select v-model="color_value">
        <option v-for="(col,index) in colors" v-bind:key="index" v-bind:value="{ color: col }">{{col}}</option>
    </select>
</div>
</template>

<script>
export default {
    name: "Dropdown",
    data: () =>{
      return{ 
          color_value: {color: "black" },
          colors:["red","blue","green","black"]
          }

    }
}
</script>

<style scoped>
    
</style>