<template>
  <main class="min-h-screen bg-white text-slate-700 dark:bg-black dark:text-slate-400">
    <div class="p-8 sm:w-4/5 md:w-2/3 lg:w-2/4 xl:w-2/4 2xl:w-1/3 mx-auto">

      <!-- 
        Allows to access and render markdown files content  
        and their front-matter data (title, date...)
      -->
      <ContentDoc v-slot="{ doc }">
        <div>
          <h1 class="text-4xl font-bold">{{ doc.title }}</h1>
          <p v-if="doc.tags" class="text-sm border border-current w-fit my-2 px-2 rounded-full">#{{ doc.tags[0] }}</p>
        </div>
        
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
