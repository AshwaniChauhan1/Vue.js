<template>
 <div>
    <h2>Fill Form and Press Enter</h2> 
        <br/>
        <form v-on:submit.prevent>
          <input v-on:keypress="submit" type="text" placeholder="Enter Something" v-model="text" />
        </form>
</div>
</template>

<script>
export default {
  name: "formComponent",
  data: function() {
    return {
      text: ''
    };
  },
  watch: {
  propName: function(newValue) {
    this.text = newValue;
    }
  },
  props:{
     propName: {
      type: String,
      require: true
    },
    editIndex: {
      type: Boolean,
      require: true
    },
    indexval:{
      type: Number,
      require: true
    }
  },
  methods: {
    submit: function(e) {
       if (e.keyCode === 13) {  
         if (this.editIndex ==true) {
            this.$emit("edit-item", this.text);
          } else{
            this.$emit("submit_item", this.text);
          }
          this.text="";
        }
      
    }
  }
  
  
}
</script>