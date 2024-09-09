<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import CardThumbnail from './components/CardThumbnail.vue';
import Header from './components/layout/Header.vue'
import { ref, onMounted } from 'vue';
import image1 from './assets/images/2MM9Jqo.png';
import image2 from './assets/images/unmma82.jpeg';

const items = ref([])

const fakeItems = (count) => {
  const fakeData = [];
  for (let i = 0; i < count; i++) {
    const title = 'Product name is quite long in some cases'
    const image = Math.random() >= 0.5 ? image1 : image2
    fakeData.push({ title, image });
  }
  return fakeData;
}

onMounted(() => {
  items.value = fakeItems(20); 
})


</script>

<template>
  <Header />
  <div class="container">
    <h1>Photo Card</h1>
    <div class="list-product">
      <CardThumbnail v-for="(item, index) in items" :key="index" :title="item.title" :image="item.image" />
    </div>
  </div>
</template>

<style scoped lang="scss">
.container {
  width: 100%;
  max-width: 1230px;
  margin: auto;
  padding-left: 15px;
  padding-right: 15px;
  .list-product {
    display: grid;
    gap: 20px;
    grid-template-columns: repeat(2, 1fr);
  }
  @media (min-width: 500px) {
    .list-product {
      grid-template-columns: repeat(3, 1fr);
    }
  }
  @media (min-width: 768px) {
    .list-product {
      grid-template-columns: repeat(4, 1fr);
    }
  }
  @media (min-width: 992px) {
    .list-product {
      grid-template-columns: repeat(4, 1fr);
    }
  }
  @media (min-width: 1280px) {
    .list-product {
      grid-template-columns: repeat(6, 1fr);
    }
  }
}

</style>