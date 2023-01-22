<script setup>
import { onMounted, ref } from 'vue'

defineProps({
  msg: String,
})
const emit = defineEmits('updateMsg')

const count = ref(0)
const inputValue = ref('')



onMounted(()=>{
  emit('updateMsg', '123')
})

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
    <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>

  <input v-model="inputValue"/>
  <button @click="$emit('updateMsg', inputValue)">修改msg</button>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
