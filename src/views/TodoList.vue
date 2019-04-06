<template>
  <div>
    <h1>TodoList</h1>
    <input v-model="inputValue" />
    <!--<H2>{{ inputValue }}</H2>-->
    <button v-on:click="handleSubmit">提交</button>
    <ul>
      <todo-item
        v-for="(item, index) of list"
        :key="index"
        :value="item"
        :index="item.index"
        @delete="handleDelete"
      ></todo-item>

      <!--<li class='item' v-for="item in list" v-bind:key="item.index">{{item}}</li>-->
    </ul>
  </div>
</template>

<script>
import TodoItem from "@/components/TodoItem";
void function add() {};

export default {
  components: {
    "todo-item": TodoItem
  },
  data() {
    return {
      inputValue: "",
      list: []
    };
  },
  methods: {
    handleSubmit() {
      this.list.push(this.inputValue);
      this.inputValue = "";
    },
    handleDelete(index) {
      this.list.splice(index, 2);
    }
  }
};
</script>
<style></style>
