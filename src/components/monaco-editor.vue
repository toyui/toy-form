<template>
  <div id="editor" ref="editorEl"></div>
</template>

<script setup lang="ts">
import { onMounted, onUnmounted, watchEffect } from 'vue'
import * as monaco from 'monaco-editor'

interface MonacoProps {
  value: string
  language: string
  options?: monaco.editor.IEditorConstructionOptions
}
const { value = 'hello monaco', language = 'javascript', options = {} } = defineProps<MonacoProps>()

const editorEl = $ref(null)

// TODO add editor type
let editor: monaco.editor.IStandaloneCodeEditor

watchEffect(() => {
  if (value && editor) {
    editor.setValue(value)
  }
})

onMounted(() => {
  editor = monaco.editor.create(editorEl!, {
    value,
    language,
    ...options,
  })
})

onUnmounted(() => {
  editor.dispose()
})
</script>

<style scope>
#editor {
  width: 100%;
  height: 100%;
}
</style>
