<template>
  <div style="display: flex; justify-content: space-between">
    <input type="text" v-model="task" />
    <button :disabled="!task" @click="list.push(task)">Add</button>
  </div>
  <p style="margin-top: 20px;">Total Tasks: {{ list.length }}</p>

  <div v-for="item in list" :key="item">
    <div style="display: flex; justify-content: space-between; align-items:center">
      <h4>{{ item }}</h4>
      <button @click="list.pop()">Delete</button>
    </div>
  </div>
</template>


<script lang="ts" setup>
import { ref } from "vue";

const task = ref("");
const list = ref([])


defineProps<{
  text: string;
}>();
</script>