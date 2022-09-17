<template>
  <div>
    <nav class="flex justify-center border border-b">
      <ContentNavigation v-slot="{ navigation }">
        <ul class="flex flex-row">
          <li 
            v-for="link of navigation" :key="link._path" class="text-xl mx-2 my-4">
            <NuxtLink :to="link._path">{{ link.title }}</NuxtLink>
          </li>
        </ul>
      </ContentNavigation>
    </nav>

    <NuxtPage />
  </div>
</template>