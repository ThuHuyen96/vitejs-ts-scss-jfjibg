<script setup lang="ts">
import { ref } from 'vue';
const msg = ref('Product name is quite long in some cases');
</script>

<template>
  <div>
    <img src="https://imgur.com/2MM9Jqo" />
    <p>{{ msg }}</p>
  </div>
</template>

<style scoped lang="scss"></style>
