<template>
  <main class="min-h-screen bg-slate-200 text-slate-700 dark:bg-neutral-900 dark:text-slate-400">
    <div class="p-16 md:w-2/3 xl:w-1/2 mx-auto">

      <!-- 
        Allows to access and render markdown files content  
        and their front-matter data (title, date...)
      -->
      <ContentDoc v-slot="{ doc }">
        <h1 class="text-4xl font-bold">{{ doc.title }}</h1>
        <div class="flex flex-row">
          <p>{{ doc.author }}</p>
          <p class="mx-4">{{ doc.date }}</p>
        </div>
        <p class="opacity-70 italic">{{ doc.description }}</p>
        <ContentRenderer :value="doc" class="my-8" />
      </ContentDoc>

    </div>
  </main>
</template>
