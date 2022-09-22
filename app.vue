<template>
  <div>
    <nav class="flex justify-center bg-slate-200 dark:bg-black dark:text-slate-400 sticky top-0">
      <ContentNavigation v-slot="{ navigation }">
        <ul class="flex flex-row">
          <li 
            v-for="link of navigation" :key="link._path" class="text-xl mx-2 my-4 dark:hover:text-white">
            <NuxtLink :to="link._path">{{ link.title }}</NuxtLink>
          </li>
        </ul>
      </ContentNavigation>
    </nav>

    <NuxtPage />
  </div>
</template>