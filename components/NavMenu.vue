<template>
  <NavigationMenu>
    <NavigationMenuList>
      <NavigationMenuItem>
        <NavigationMenuLink href="/" class="flex items-center gap-1">
          <img src="@/assets/images/pinia.png" alt="logo" class="w-8" />
          <span class="text-xl font-medium">PrjName</span>
        </NavigationMenuLink>
      </NavigationMenuItem>
      <NavigationMenuItem>
        <NavigationMenuTrigger>소개</NavigationMenuTrigger>
        <NavigationMenuContent>
          <ul
            class="grid gap-3 p-6 md:w-[400px] lg:w-[500px] lg:grid-cols-[minmax(0,.75fr)_minmax(0,1fr)]"
          >
            <li class="row-span-3">
              <NavigationMenuLink as-child>
                <nuxt-link
                  class="flex h-full w-full select-none flex-col justify-end rounded-md bg-gradient-to-b from-muted/50 to-muted p-6 no-underline outline-none focus:shadow-md"
                  to="/"
                >
                  <img
                    src="https://www.radix-vue.com/logo.svg"
                    class="h-6 w-6"
                  />
                  <div class="mb-2 mt-4 text-lg font-medium">shadcn/ui</div>
                  <p class="text-sm leading-tight text-muted-foreground">
                    Beautifully designed components built with Radix UI and
                    Tailwind CSS.
                  </p>
                </nuxt-link>
              </NavigationMenuLink>
            </li>

            <li>
              <NavigationMenuLink as-child>
                <a
                  href="/docs"
                  class="block select-none space-y-1 rounded-md p-3 leading-none no-underline outline-none transition-colors hover:bg-accent hover:text-accent-foreground focus:bg-accent focus:text-accent-foreground"
                >
                  <div class="text-sm font-medium leading-none">
                    Introduction
                  </div>
                  <p
                    class="line-clamp-2 text-sm leading-snug text-muted-foreground"
                  >
                    Re-usable components built using Radix UI and Tailwind CSS.
                  </p>
                </a>
              </NavigationMenuLink>
            </li>
            <li>
              <NavigationMenuLink as-child>
                <a
                  href="/docs/installation"
                  class="block select-none space-y-1 rounded-md p-3 leading-none no-underline outline-none transition-colors hover:bg-accent hover:text-accent-foreground focus:bg-accent focus:text-accent-foreground"
                >
                  <div class="text-sm font-medium leading-none">
                    Installation
                  </div>
                  <p
                    class="line-clamp-2 text-sm leading-snug text-muted-foreground"
                  >
                    How to install dependencies and structure your app.
                  </p>
                </a>
              </NavigationMenuLink>
            </li>
            <li>
              <NavigationMenuLink as-child>
                <a
                  href="/docs/primitives/typography"
                  class="block select-none space-y-1 rounded-md p-3 leading-none no-underline outline-none transition-colors hover:bg-accent hover:text-accent-foreground focus:bg-accent focus:text-accent-foreground"
                >
                  <div class="text-sm font-medium leading-none">Typography</div>
                  <p
                    class="line-clamp-2 text-sm leading-snug text-muted-foreground"
                  >
                    Styles for headings, paragraphs, lists...etc
                  </p>
                </a>
              </NavigationMenuLink>
            </li>
          </ul>
        </NavigationMenuContent>
      </NavigationMenuItem>
      <NavigationMenuItem>
        <NavigationMenuTrigger>커뮤니티</NavigationMenuTrigger>
        <NavigationMenuContent>
          <ScrollArea class="h-80">
            <ul
              class="grid w-[400px] gap-3 p-4 md:w-[500px] md:grid-cols-2 lg:w-[600px]"
            >
              <li v-for="user in users" :key="user.id">
                <NavigationMenuLink as-child>
                  <a
                    :href="`https://jsonplaceholder.typicode.com/comments/${user.id}`"
                    class="block select-none space-y-1 rounded-md p-3 leading-none no-underline outline-none transition-colors hover:bg-accent hover:text-accent-foreground focus:bg-accent focus:text-accent-foreground"
                  >
                    <div class="text-sm font-medium leading-none">
                      {{ user.name }}
                    </div>
                    <p
                      class="line-clamp-2 text-sm leading-snug text-muted-foreground"
                    >
                      {{ user.email }}
                    </p>
                  </a>
                </NavigationMenuLink>
              </li>
            </ul>
          </ScrollArea>
        </NavigationMenuContent>
      </NavigationMenuItem>
      <NavigationMenuItem>
        <NavigationMenuTrigger>미디어</NavigationMenuTrigger>
        <NavigationMenuContent> 미디어content </NavigationMenuContent>
      </NavigationMenuItem>
    </NavigationMenuList>
  </NavigationMenu>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { ScrollArea } from '@/components/ui/scroll-area';
import {
  NavigationMenu,
  NavigationMenuContent,
  NavigationMenuItem,
  NavigationMenuLink,
  NavigationMenuList,
  NavigationMenuTrigger,
} from '@/components/ui/navigation-menu';

interface user {
  postId: number;
  id: number;
  name: string;
  email: string;
  body: string;
}
const users = ref<user[]>([]);
fetch('https://jsonplaceholder.typicode.com/comments')
  .then((response) => response.json())
  .then((json) => (users.value = json.slice(0, 25)));
</script>

<style scoped></style>
