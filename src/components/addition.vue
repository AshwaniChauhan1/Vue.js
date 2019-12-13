<template>
    <div>
        <h3>Addition Function</h3>
        <button v-on:click="a++">AddToA</button>
        <button v-on:click='b++'>AddToB</button>
        <p>Age = {{age}}</p>
        <p>a = {{a}}</p>
        <p>b = {{b}}</p>
        <p>Age + a = {{addToA()}}</p>
        <p>Age + b = {{addToB()}}</p>
        <hr>
    </div>
</template>

<script>
export default {
    name:'addition',
    data(){
        return{
            age:20,
            a:0,
            b:0
        }
        
    },
    methods:{
        addToA: function(){
            return this.a + this.age;
            //eslint-disable-next-line
            console.log("addToA")
        },

        addToB: function(){
            return this.b + this.age
        }
    }
}
</script>