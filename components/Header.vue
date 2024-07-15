<template>
  <header>
    <h1>
      <NuxtLink to="/">
        <img src="~/assets/images/pinia.png" alt="logo" class="w-10" />
        <span class="text-foreground">TITLE</span>
      </NuxtLink>
    </h1>
    <Button size="lg">버튼</Button>
    <NavMenu />
  </header>
</template>

<script setup>
import { Button } from '@/components/ui/button';
import NavMenu from '@/components/NavMenu';
</script>

<style lang="scss" scoped></style>
