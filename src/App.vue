<template>
  <div id="app">
    <div style="display:flex;padding:0px;">
      <div style="width:30%;background-color:whitesmoke;height:600px;">
        <h1 @click="changes" style="cursor:pointer;" >ASSIGNMENTS</h1>
        <h2 @click="changes1">Assignment 1</h2>
        <h2 @click="changes2">Assignment 2</h2>
        <h2 @click="changes3">Assignment 3</h2>
        <h2 @click="changes4">Assignment 4</h2>
      </div>
      <div style="width:70%;">
        <div v-if="!show1 && !show2 && !show3">
            <img alt="Vue logo" src="./assets/logo.png" height="300px">
            <h1>VUE.JS</h1>
        </div>
        <NewComponent v-if="show1 && !show2 && !show3" />
        <Dropdown v-if="show1 && show2 && !show3" />
        <SmallForm v-if="show1 && show2 && show3"/>
        <div v-if="!show1 && show2 && show3">
          <h1>Form By using Components</h1>
          <listComponent/>
        </div>
        <!-- <div v-if="!show1 && !show2 && show3">
          <h2>Practice</h2>
          <counter/>
          <addition/>
          <blogPost v-for="post in posts"
              v-bind:key="post.id"
              v-bind:post="post"
              :style="{ fontSize: postFontSize + 'em' }"
              v-on:enlarge-txt="postFontSize += 0.1">
              v-bind:title="post.title"
        />  
         <child-component :message="message" @update="updateMessage"></child-component>
        </div> -->
      </div>
    </div>
  </div>
</template>

<script>

import NewComponent from './components/NewComponent.vue'
import Dropdown from './components/Dropdown.vue'
import SmallForm from './components/SmallForm.vue'
import listComponent from './components/listComponent.vue'
// import ChildComponent from './components/ChildComponent'
// import counter from './components/counter.vue'
// import addition from './components/addition.vue'
// import blogPost from './components/blogPost.vue'


export default {
  name: 'app',
  components: {
    NewComponent,
    Dropdown,SmallForm,listComponent
    // ,ChildComponent,counter,addition,blogPost
  },
  data: ()=> {
    return{
      posts: [
      { id: 1, title: 'This is Props Example',content:'this content is latest edit property'},
      { id: 2, title: 'Emit function is used in Button',content:'we can perform event in parent from children' },
      { id: 3, title: 'FontSize increased by 0.1em ' }
    ],
    postFontSize: 1,
    message: 'Hello World!',
    assignments:[
      "assignment 1",
      "assignment 2",
      "assignment 3",
      "assignment 4",
      "PRACTICE"
      ],
      show1:false,
      show2:false,
      show3:false
    }
    
  },
  methods: {
    updateMessage (message) {
      this.message = message;
      //eslint-disable-next-line
      console.log(this.message);
    },
    changes(){
      this.show1=false;
      this.show2=false;
      this.show3=false;
    },
    changes1(){
      this.show1=true;
      this.show2=false;
      this.show3=false;
    },
    changes2(){
      this.show1=true;
      this.show2=true;
      this.show3=false;

    },
    changes3(){
      this.show1=true;
      this.show2=true;
      this.show3=true;
    },
    changes4(){
      this.show1=false;
      this.show2=true;
      this.show3=true;
    },
    changes5(){
      this.show1=false;
      this.show2=false;
      this.show3=true;
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
h2{
  cursor:pointer;
}
</style>
