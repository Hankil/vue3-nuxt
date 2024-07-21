<template>
  <header>
    <h1>
      <NuxtLink to="/">
        <img src="~/assets/images/pinia.png" alt="logo" class="w-10" />
        <span class="text-foreground">BizOffice</span>
      </NuxtLink>
    </h1>
    <NavMenu />
    <Button size="lg">신청</Button>
  </header>
</template>

<script setup>
import { Button } from '@/components/ui/button';
import NavMenu from '@/components/NavMenu';
</script>

<style lang="scss" scoped></style>
