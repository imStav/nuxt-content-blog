<template>
  <main class="min-h-screen bg-white text-slate-700 dark:bg-black dark:text-slate-400">
    <div class="p-8 sm:w-4/5 md:w-2/3 lg:w-2/4 xl:w-2/4 2xl:w-1/3 mx-auto">

      <!-- 
        Generates a card for each article contained in the 'blog' subfolder 
        (./content/blog) and displays front-matter data (title, date...) 
      -->
      <ContentList path="/blog" v-slot="{ list }">
        <div v-for="article in list" :key="article._path" class="h-fit hover:text-black hover:brightness-110 dark:hover:text-white duration-200 my-8">
          <NuxtLink :to="article._path">
            <div class="sm:grid grid-cols-2">
              <div class="flex flex-col justify-center">
                <h2 class="text-2xl font-bold tracking-wide w-fit">{{ article.title }}</h2>
                <p class="text-sm border border-current w-fit my-2 px-2 rounded-full">#{{ article.tags[0] }}</p>
                <div class="flex flex-row mb-2">
                  <p>{{ article.author }}</p>
                  <p class="mx-4">{{ article.date }}</p>
                </div>
                <p class="pr-4">{{ article.description }}</p>
              </div>
              <img :src="article.img" alt="" class="my-4 sm:my-0 w-fit rounded">
            </div>
          </NuxtLink>
        </div>
      </ContentList>

    </div>
  </main>
</template>