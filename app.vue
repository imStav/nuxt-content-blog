<template>
  <div>
    <nav class="flex justify-center bg-slate-100 text-slate-700 dark:bg-black dark:text-slate-400 sticky top-0 z-10">

      <!-- Enables and displays dynamics navigation links -->
      <ContentNavigation v-slot="{ navigation }">
        <ul class="flex flex-row">
          <li v-for="link of navigation" :key="link._path" class="text-xl mx-2 my-4 hover:text-black dark:hover:text-slate-200 duration-200">
            <NuxtLink :to="link._path">{{ link.title }}</NuxtLink>
          </li>
        </ul>
      </ContentNavigation>

    </nav>

    <NuxtPage />
  </div>
</template>