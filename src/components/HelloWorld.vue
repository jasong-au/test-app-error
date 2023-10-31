<script setup lang="ts">
import { ref } from 'vue'

defineProps<{ msg: string }>()

// this causes the parser error on 'npm run build', but works fine with 'npm run dev'
// console.log('import.meta.env.VITE_TEST', import.meta.env.VITE_TEST)

// this causes the same error
// console.log("import.meta.env.VITE_TEST", import.meta.env.VITE_TEST)

// this gives a different error and points out the line number
const text = 'import.meta.env.VITE_TEST'
console.log(text)

// this works with backticks
// console.log(`import.meta.env.VITE_TEST`, import.meta.env.VITE_TEST)

// this is fine with a space instead of a period so it isn't the full string
// console.log('import meta.env.VITE_TEST', import.meta.env.VITE_TEST)

// this is also fine as it doesn't exist
// console.log('import meta.env.VITE_DOES_NOT_EXIST', import.meta.env.VITE_DOES_NOT_EXIST)


const count = ref(0)
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Install
    <a href="https://github.com/vuejs/language-tools" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
