<template>
  <input type="text" class="input" :value="value" v-on="listeners" />
</template>

<script>
export default {
  props: {
    value: {
      type: String,
      default: ""
    }
  },
  computed: {
    listeners() {
      // console.log(this.$listeners);
      return {
        // Pass all component listeners directly to input 将所有组件侦听器直接传递到输入   使用父级监听器，然后重写了input事件，目的就是能够触发
        ...this.$listeners,
        // Override input listener to work with v-model 重写输入侦听器以使用v-model
        input: event => this.$emit("input", event.target.value)
        // input:function(event){
        //     this.$emit("input",event.target.value);
        // }
      };
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../variables.scss";

.input {
  width: 100%;
  padding: 8px 10px;
  border: 1px solid $vue-blue;
  border-radius: 5px;
  outline: none;
}
</style>
