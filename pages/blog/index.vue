<template>
  <main class="page">
    <div class="page-breakpoints-layout">

      <!-- 
        Generates a card for each article contained in the 'blog' subfolder 
        (./content/blog) and displays front-matter data (title, date...) 
      -->
      <ContentList path="/blog" v-slot="{ list }">
        <div v-for="article in list" :key="article._path" class="article-preview-effetcs my-8">
          <NuxtLink :to="article._path">
            <div class="sm:grid grid-cols-2">
              <div class="flex flex-col justify-center">
                <h2 class="heading text-3xl w-fit">{{ article.title }}</h2>
                <p class="badge">#{{ article.tags[0] }}</p>

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