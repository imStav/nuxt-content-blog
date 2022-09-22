<template>
  <main class="min-h-screen bg-slate-200 text-slate-700 dark:bg-neutral-900 dark:text-slate-400">
    <div class="grid gap-10 place-content-center p-16 md:grid-cols-2 xl:grid-cols-3 xl:px-96">
      <ContentList path="/blog" v-slot="{ list }">
        <div v-for="article in list" :key="article._path" class="bg-slate-100 dark:bg-neutral-800 h-fit px-4 pt-4 pb-6 rounded-lg border border-transparent hover:border-blue-500 duration-200">
          <h2 class="text-2xl font-bold tracking-wide">{{ article.title }}</h2>
          <p class="mt-4 mb-8">{{ article.description }}</p>
          <NuxtLink :to="article._path" class="bg-slate-200 dark:bg-neutral-900 hover:bg-blue-500 hover:text-white duration-200 px-5 py-2 rounded-full">Read more</NuxtLink>
        </div>
      </ContentList>
    </div>
  </main>
</template>