<template>
  <div id="container-editor" ref="editor">
    <MonacoEditor :value="code" />
  </div>
</template>

<script setup lang="ts">
import MonacoEditor from './components/monaco-editor.vue'

let code = $ref(`function add() {
    return 1 + 1
  }`)
setInterval(() => {
  code += '\n'
  code += 'console.log("hello")'
}, 2000)
</script>

<style>
html,
body,
#app {
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
}

#container-editor {
  width: 100%;
  height: 100%;
}
</style>
s >
