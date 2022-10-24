<template>
  <div>
    <nav class="navbar">

      <!-- Enables and displays dynamics navigation links -->
      <ContentNavigation v-slot="{ navigation }">
        <ul class="flex flex-row">
          <li v-for="link of navigation" :key="link._path" class="nav-links-effects text-xl mx-2 my-4">
            <NuxtLink :to="link._path">{{ link.title }}</NuxtLink>
          </li>
        </ul>
      </ContentNavigation>

    </nav>

    <NuxtPage />
  </div>
</template>