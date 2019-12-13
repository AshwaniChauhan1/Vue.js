<template>
    <div >
        <h3>Here Is Counter</h3>
		<button @click="counter++">Clicked {{ counter }} times</button>
        <hr>
	</div>
</template>

<script>
export default {
    name:'counter',
    data: ()=>{
        return{
            counter:0
        }
    }
}
</script>

<style>
div{
    padding:8px;
}
</style>