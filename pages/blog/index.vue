<template>
    <main class="min-h-screen grid gap-10 place-content-center p-16 md:grid-cols-2 xl:grid-cols-3 xl:px-96 bg-slate-200 dark:bg-black dark:text-slate-400">
      <ContentList path="/blog" v-slot="{ list }">
        <div v-for="article in list" :key="article._path" class="border border-slate-500 h-fit p-4">
          <h2 class="text-2xl font-bold tracking-wide">{{ article.title }}</h2>
          <p class="leading-tight">{{ article.description }}</p>
        </div>
      </ContentList>
    </main>
  </template>