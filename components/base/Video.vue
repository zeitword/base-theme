<script setup lang="ts">
type Props = {
  src: string;
  loop?: boolean;
  autoplay?: boolean;
  muted?: boolean;
  width?: number;
  height?: number;
};

const {
  src,
  loop = true,
  autoplay = true,
  muted = true,
  width = 1920,
  height = 1080,
} = defineProps<Props>();

const computedSrc = computed(() => {
  return `${src}#t=0001?w=${width}&h=${height}`;
});
</script>

<template>
  <video
    :src="`${computedSrc}`"
    class="top-0 left-0 size-full w-full object-cover"
    :loop
    :autoplay
    playsinline
    :muted
  ></video>
</template>
