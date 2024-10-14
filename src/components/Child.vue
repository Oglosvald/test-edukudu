<script setup>
const title = defineModel('title')
const bool = defineModel('bool')
</script>

<template>
  <p>Child title: {{ title }}</p>
  <p>Child bool: {{ bool }}</p>
  <input type="text" v-model="title" />
  <p><button @click="bool = !bool">change bool</button></p>
  
</template>