<template>
  <UModal>
    <div class="p-2">
      <div class="flex justify-between items-center p-4">
        <h1 class="text-3xl font-semibold">{{ project.title }}</h1>
        <div class="space-x-2">
          <UTooltip text="Open site in new window" v-if="project.link">
            <ULink :to="project.link" external target="_blank">
              <UIcon class="h-7 w-7" name="heroicons-outline:arrow-top-right-on-square" />
            </ULink>
          </UTooltip>
          <UTooltip text="Open repo in new window" v-if="project.github_repo">
            <ULink :to="`https://github.com/curdledSoy/${project.github_repo}`" external target="_blank">
              <UIcon class="h-7 w-7" name="i-simple-icons:github" />
            </ULink>
          </UTooltip>
        </div>

      </div>

      <ContentRenderer :value="project" class="text-wrap h-[2/3] overflow-scroll p-4 w-full prose dark:prose-invert" />
    </div>
  </UModal>
</template>

<script lang="ts" setup>
import type { ParsedContent } from '@nuxt/content';
defineProps<{ project: ParsedContent }>(
)

</script>