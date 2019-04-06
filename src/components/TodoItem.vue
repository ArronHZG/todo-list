<template>
  <li class="item" @click="handleDelete">{{ value }}</li>
</template>

<script>
export default {
  props: ["value", "index"],
  // name: 'TodoItem',
  methods: {
    handleDelete() {
      this.$emit("delete", this.index);
    }
  }
};
</script>
<style scoped>
.item {
  color: cornflowerblue;
}
</style>
