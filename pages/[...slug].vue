<template>
  <main class="page">
    <div class="page-breakpoints-layout">

      <!-- 
        Allows to access and render markdown files content  
        and their front-matter data (title, date...)
      -->
      <ContentDoc v-slot="{ doc }">
        <div>
          <h1 class="heading text-4xl">{{ doc.title }}</h1>
          <p v-if="doc.tags" class="badge">#{{ doc.tags[0] }}</p>
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
