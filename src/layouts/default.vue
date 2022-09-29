<template>
  <main class="px-4 py-8 text-gray-700 dark:text-gray-200 flex flex-col items-center">
    <RouterView v-slot="{ Component, route }">
      <component :is="Component" :key="route" />
    </RouterView>
    <Footer />
  </main>
</template>
