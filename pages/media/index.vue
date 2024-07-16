<template>
  <div>
    <div class="grid grid-cols-4 gap-4 p-4">
      <div v-for="(item, index) in playLists" :key="index">
        <div
          class="cursor-pointer"
          @click="playVideo(item.videoId, item.title, item.artist)"
        >
          <div>
            <img
              :src="`https://img.youtube.com/vi/${item.videoId}/0.jpg`"
              :alt="item.title"
              class="filter grayscale hover:filter-none transition-all duration-200"
            />
          </div>
          <p class="mt-2 text-lg font-medium">{{ item.title }}</p>
          <p>{{ item.artist }}</p>
        </div>
      </div>
    </div>

    <Dialog v-model:open="playerModal">
      <DialogContent class="max-w-[85%]">
        <DialogHeader class="flex flex-row gap-3">
          <DialogTitle>{{ playVideoTitle }}</DialogTitle>
          <DialogDescription>
            {{ playVideoArtist }}
          </DialogDescription>
        </DialogHeader>
        <div class="relative h-0 pb-[56.25%]">
          <iframe
            class="absolute top-0 left-0 w-full h-full"
            :src="`https://www.youtube.com/embed/${playVideoId}`"
            :title="playVideoTitle"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
            referrerpolicy="strict-origin-when-cross-origin"
            allowfullscreen
          ></iframe>
        </div>
      </DialogContent>
    </Dialog>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import {
  Dialog,
  DialogHeader,
  DialogDescription,
  DialogTitle,
  DialogContent,
} from '@/components/ui/dialog';

interface playList {
  videoId: string;
  title: string;
  artist: string;
}
const playLists = ref<playList[]>([
  {
    videoId: '5KWtCfKSZWk',
    title: '사랑은 언제나 목마르다',
    artist: '유미',
  },
  {
    videoId: 'J6BSDlALQ70',
    title: '어제처럼',
    artist: 'J',
  },
  {
    videoId: 'MweOpoiuJDg',
    title: '그댄 행복에 살텐데',
    artist: '리즈',
  },
  {
    videoId: 'uYp15-zFr4M',
    title: '사랑의 인사',
    artist: '씨야(See Ya)',
  },
  {
    videoId: 'JDLDTwcG4f8',
    title: '습관',
    artist: '우수 ( WOO SOO)',
  },
  {
    videoId: '8lyrYU5wplE',
    title: '마지막 사랑',
    artist: '박기영',
  },
  {
    videoId: '4aHWbbB3V2o',
    title: '해줄 수 없는 일',
    artist: '박효신',
  },
  {
    videoId: 'i2aRMXZR1k0',
    title: '너의 모든 순간',
    artist: '성시경',
  },
]);

const playerModal = ref(false);
const playVideoId = ref('');
const playVideoTitle = ref('');
const playVideoArtist = ref('');
const playVideo = (videoId: string, title: string, artist: string) => {
  playerModal.value = true;
  console.log(videoId, title, artist);
  playVideoId.value = videoId;
  playVideoTitle.value = title;
  playVideoArtist.value = artist;
};
</script>

<style scoped></style>
