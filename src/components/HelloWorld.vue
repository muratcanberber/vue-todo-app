<script setup>
import { ref } from "vue";
import { v4 as uuidv4 } from "uuid";
const items = ref([
  {
    id: uuidv4(),
    name: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Dolorum dolore accusamus dignissimos soluta veniam voluptatum perferendis velit quos, autem ipsam.a",
  },
]);

let newTodo = ref("");

function addNewTodo() {
  items.value.push({
    id: uuidv4(),
    name: newTodo.value,
  });
}

function removeTodo(id) {
  items.value = items.value.filter((item) => item.id !== id);
}
</script>

<template>
  <div class="container">
    <div class="box mt-5 columns">
      <input
        class="input is-large"
        type="text"
        placeholder="Type a new TODO"
        v-model="newTodo"
      />
      <button class="button is-primary is-large ml-4" @click="addNewTodo">
        ADD
      </button>
    </div>
  </div>
  <section class="container">
    <div class="box mt-5 columns" v-for="(item, key) in items" :key="key + 1">
      <div class="column is-italic is-bold">#{{ key + 1 }}</div>
      <div class="column is-two-thirds">{{ item.name }}</div>
      <div class="column has-text-right">
        <button class="button is-danger" @click="removeTodo(item.id)">X</button>
      </div>
    </div>
  </section>
</template>

<style></style>
