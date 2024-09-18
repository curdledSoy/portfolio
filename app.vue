<template>
  <div>
    <div>
    <Header />
    <main class="min-h-[calc(100vh-var(--header-height))]">
      <NuxtPage />
    </main>
    <footer class="py-6 bg-gray-50 dark:bg-gray-950 text-center text-sm text-gray-500 dark:text-gray-400 ">
      &copy; 2024 Tom Brittenden. All rights reserved.
    </footer>
    </div>
    <UModals />
  </div>
</template>

<style lang="css">
:root {
  --header-height: 4rem;

}

html {
  scroll-behavior: smooth;
}

section {
  min-height: 100vh
}


</style>
