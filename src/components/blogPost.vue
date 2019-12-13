<template>
    <div>
        <h3>{{post.title}}</h3> 
        <!-- {{title}} -->
        <button v-on:click="$emit('enlarge-txt')">
        Enlarge text
        </button>
         <div v-html="post.content"></div>
         
    </div>
</template>

<script>
export default {
    props:['post'],
    // [title]
    name:'blogPost'
}
</script>

<style scoped>

</style>