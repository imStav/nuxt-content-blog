<template>
  <main class="min-h-screen bg-slate-100 text-slate-700 dark:bg-black dark:text-slate-400">
    <div class="p-8 md:w-2/3 xl:w-1/3 mx-auto">

      <!-- 
        Generates a card for each article contained in the 'blog' subfolder 
        (./content/blog) and displays front-matter data (title, date...) 
      -->
      <ContentList path="/blog" v-slot="{ list }">
        <div v-for="article in list" :key="article._path" class="h-fit px-4 pt-4 pb-6 hover:bg-slate-200 hover:text-black dark:hover:bg-neutral-800 dark:hover:text-white duration-200 my-4 rounded-lg">
          <NuxtLink :to="article._path">
            <div class="sm:grid grid-cols-2">
              <div class="flex flex-col justify-center">
                <h2 class="text-2xl font-bold tracking-wide w-fit">{{ article.title }}</h2>
                <div class="flex flex-row mb-2">
                  <p>{{ article.author }}</p>
                  <p class="mx-4">{{ article.date }}</p>
                </div>
                <p>{{ article.description }}</p>
              </div>
              <img :src="article.img" alt="" class="my-4 sm:my-0 w-fit rounded-lg">
            </div>
          </NuxtLink>
        </div>
      </ContentList>

    </div>
  </main>
</template>