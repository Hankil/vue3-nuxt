<template>
  <header>
    <h1>
      <NuxtLink to="/">
        <img src="~/assets/images/logo.png" alt="logo" class="w-10" />
        <span class="text-foreground">TITLE</span>
      </NuxtLink>
    </h1>
    <Button size="lg">버튼</Button>
  </header>
</template>

<script setup>
import { Button } from '@/components/ui/button';
</script>

<style lang="scss" scoped></style>
