<script setup lang="ts">
type Props = {
  spacing?: TSpacing
  background?: TBackground
  html: string
}
const { spacing = { vertical: "md" }, background = { color: "neutral", visible: true }, html } = defineProps<Props>()
</script>
<template>
  <DBackground v-bind="background">
    <DWrapper :spacing="spacing">
      <div v-html="html" class="prose"></div>
    </DWrapper>
  </DBackground>
</template>
