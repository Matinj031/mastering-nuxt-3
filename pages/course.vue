<template>
  <div
    class="p-12 bg-gray-100 w-full min-h-screen flex flex-col items-center justify-end"
  >
    <div class="prose mb-12">
      <h1>
        <span class="font-medium">
          Course:
          <span class="font-bold">Mastering Nuxt</span>
        </span>
      </h1>
    </div>
    <div class="flex flex-row justify-center flex-grow">
      <div
        class="prose mr-4 p-4 bg-white rounded-md min-w-[20ch] flex flex-col"
      >
        <h3>Chapters</h3>
        <!-- All the lessons and chapters  listed here-->
        <div
          class="space-y-1 mb-4 flex flex-col"
          v-for="chapter in chapters"
          :key="chapter.slug"
        >
          <h4>
            {{ chapter.title }}
            <nuxtLink
              v-for="(lesson, index) in chapter.lessons"
              :key="lesson.slug"
              class="flex flex-row space-x-1 no-underline prose-sm font-normal py-1"
              :to="lesson.path"
            >
              <span class="text-gray-500" >{{ index + 1 }}</span>
              <span> {{ lesson.title }} </span>
            
            </nuxtLink>
          </h4>
        </div>
      </div>
      <div class="prose p-12 bg-white rounded-md w-[65ch]">
        <NuxtPage />
      </div>
    </div>
  </div>
</template>
<script setup>
const { chapters } = useCourse();
</script>
<style scoped>
.router-link-active{
  @apply text-blue-500
}
</style>