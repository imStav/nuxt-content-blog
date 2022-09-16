<template>
  <div>
    <div class="flex justify-center border border-b">
      <ContentNavigation v-slot="{ navigation }">
        <ul>
          <li v-for="link of navigation" :key="link._path">
            <NuxtLink :to="link._path">{{ link.title }}</NuxtLink>
          </li>
        </ul>
      </ContentNavigation>
    </div>

    <NuxtPage />
  </div>
</template>