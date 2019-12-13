<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    
    <NewComponent />
    <SmallForm/>
    <div>
      <h1>Form By using Component</h1>
      <listComponent/>
    </div>
    
    
    
    <div style="background-color:whitesmoke;">
      <h2>Practice</h2>
      <counter/>
      <addition/>
      <blogPost v-for="post in posts"
              v-bind:key="post.id"
              v-bind:post="post"
              :style="{ fontSize: postFontSize + 'em' }"
              v-on:enlarge-txt="postFontSize += 0.1">
              <!-- v-bind:title="post.title" -->
      </blogPost>  
      <child-component :message="message" @update="updateMessage"></child-component>
    </div>

    
    
  </div>
</template>

<script>

import NewComponent from './components/NewComponent.vue'
import counter from './components/counter.vue'
import addition from './components/addition.vue'
import SmallForm from './components/SmallForm.vue'
import blogPost from './components/blogPost.vue'
import listComponent from './components/listComponent.vue'
import ChildComponent from './components/ChildComponent'


export default {
  name: 'app',
  components: {
    NewComponent,
    counter,addition,SmallForm,blogPost,listComponent,ChildComponent
  },
  data: ()=> {
    return{
      posts: [
      { id: 1, title: 'This is Props Example',content:'this content is latest edit property'},
      { id: 2, title: 'Emit function is used in Button',content:'we can perform event in parent from children' },
      { id: 3, title: 'FontSize increased by 0.1em ' }
    ],
    postFontSize: 1,
    message: 'Hello World!'
    }
    
  },
  methods: {
    updateMessage (message) {
      this.message = message;
      //eslint-disable-next-line
      console.log(this.message);
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
  margin-top: 60px;
}
</style>
