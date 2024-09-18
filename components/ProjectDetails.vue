<template>
  <UModal >
    <div class="h-[2/3] flex overflow-scroll p-4 w-full prose dark:prose-invert" >
    <ContentRenderer :value="project"  />
    </div>
    
  </UModal>
</template>

<script lang="ts" setup>
import type { ParsedContent } from '@nuxt/content';
defineProps<{ project: ParsedContent }>(
)

</script>