<template>
  <div class="h-full grid grid-cols-4 justify-stretch">
    <nuxt-link
      v-for="item in lists"
      :key="item.name"
      :to="item.url"
      target="_blank"
      class="flex justify-center"
    >
      <div class="flex items-center">
        <i><img :src="item.url" :alt="item.name" /></i>
        <span>{{ item.name }}</span>
      </div>
    </nuxt-link>
  </div>
</template>

<script setup lang="ts">
const lists = ref([
  {
    name: 'Item1',
    logo: 'logo1',
    url: '/',
  },
  {
    name: 'Item2',
    logo: 'logo2',
    url: '/',
  },
  {
    name: 'Item3',
    logo: 'logo3',
    url: '/',
  },
  {
    name: 'Item4',
    logo: 'logo4',
    url: '/',
  },
]);
</script>

<style scoped></style>
