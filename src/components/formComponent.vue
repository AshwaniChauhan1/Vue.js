<template>
 <div>
    <h2>Fill Form and Press Enter</h2> 
        <br/>
        <form v-on:submit.prevent>
            <input v-on:keypress="submit" type="text" placeholder="Enter Something" v-model="msg" />
        </form>
</div>
</template>

<script>
export default {
  name: "formComponent",
  data: function() {
    return {
      msg: "",
      editIndex: false
    };
  },
  methods: {
    submit: function(e) {
      if (e.keyCode === 13) {
          this.$emit("submit-item", this.msg)
          this.msg = "";
      }
    }
  }
};
</script>