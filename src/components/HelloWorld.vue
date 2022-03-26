<script setup lang="ts">
const { msg } = defineProps<{ msg?: string }>()

let count = $ref(0)
const add = () => {
  count++
}

let count2 = $ref(0)
const add2 = () => {
  count2++
}
</script>

<template>
  <p>{{ msg }}</p>
  <div @click="add">{{ count }}</div>
  <div @click="add2">{{ count2 }}</div>
</template>

<style scoped>
a {
  color: #42b983;
}

label {
  margin: 0 0.5em;
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}
</style>
