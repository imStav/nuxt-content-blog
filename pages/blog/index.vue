<template>
  <main class="min-h-screen bg-slate-200 text-slate-700 dark:bg-black dark:text-slate-400">
    <div class="p-8 md:w-2/3 xl:w-1/3 mx-auto">

      <!-- 
        Generates a card for each article contained in the 'blog' subfolder 
        (./content/blog) and displays front-matter data (title, date...) 
      -->
      <ContentList path="/blog" v-slot="{ list }">
        <div v-for="article in list" :key="article._path" class="h-fit px-4 pt-4 pb-6 border-l border-slate-700 dark:border-slate-400 hover:border-blue-500 hover:bg-blue-500/10 dark:hover:bg-blue-900/50 duration-200 my-4">
          <h2 class="text-2xl font-bold tracking-wide w-fit">{{ article.title }}</h2>
          <div class="flex flex-row items-center">
            <p>{{ article.author }}</p>
            <p class="mx-4">{{ article.date }}</p>
          </div>
          <p class="mt-4 mb-8">{{ article.description }}</p>
          <NuxtLink :to="article._path" class="border border-slate-700 dark:border-slate-400 hover:border-blue-500 hover:bg-blue-500 hover:text-white duration-200 px-5 py-2 rounded-full">Read more</NuxtLink>
        </div>
      </ContentList>

    </div>
  </main>
</template>