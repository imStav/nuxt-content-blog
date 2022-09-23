<template>
  <main class="min-h-screen bg-slate-200 text-slate-700 dark:bg-neutral-900 dark:text-slate-400">
    <div class="p-16 md:w-2/3 xl:w-1/2 mx-auto">
      <ContentDoc v-slot="{ doc }">
        <h1 class="bg-slate-100 dark:bg-neutral-800 w-fit rounded-full px-4 py-1">{{ doc.title }}</h1>
        <ContentRenderer :value="doc" class="my-8" />
      </ContentDoc>
    </div>
  </main>
</template>
