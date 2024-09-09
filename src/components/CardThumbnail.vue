<script setup lang="ts">
const props = defineProps({
  title: String,
  image: String,
});
</script>

<template>
  <div class="card">
    <img :src="image" :alt="title" class="card__thumbnail" />
    <p class="card__title">{{ title }}</p>
  </div>
</template>

<style scoped lang="scss">
.card {
  background-color: white;
  border-radius: 4px;
  overflow: hidden;
  padding: 0 0 15px 0;
  box-shadow:
  0px 0px 2.7px rgba(0, 0, 0, 0.022),
  0px 0px 6.9px rgba(0, 0, 0, 0.031),
  0px 0px 14.2px rgba(0, 0, 0, 0.039),
  0px 0px 29.2px rgba(0, 0, 0, 0.048),
  0px 0px 80px rgba(0, 0, 0, 0.07);
  border: 1px solid #eee;
  &__thumbnail {
    width: 100%;
    max-height: 250px;
    height: 250px;
    object-fit: cover;
  }
  &__title {
    margin: 10px 0 0;
    padding: 0 10px;
    display: -webkit-box;
    -webkit-line-clamp: 1;
    -webkit-box-orient: vertical;  
    overflow: hidden;
    font-weight: 600;
    font-size: 14px;
  }
  @media (min-width: 500px) {
    &__thumbnail {
      max-height: 210px;
      height: 210px;
    }
  }
  @media (min-width: 768px) {
    &__thumbnail {
      max-height: 200px;
      height: 200px;
    }
  }
  @media (min-width: 992px) {
    &__thumbnail {
      max-height: 180px;
      height: 180px;
    }
  }
}
</style>
