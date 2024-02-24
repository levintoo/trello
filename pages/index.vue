<script setup>
const darkMode = ref(false)
</script>

<template>
  <main :class="{ 'dark' : darkMode }">
    <div class="min-h-full bg-white dark:bg-dim-900">
      <div class="grid grid-cols-12 sm:px-6 lg:max-w-7xl lg:px-8 lg:gap-4">

        <!-- left sidebar -->
        <div class="hidden md:block xs-col-span-1 xl:colspan-2">
          <div class="sticky top-0">
            <SidebarLeft />
          </div>
        </div>
        <!-- main content -->
        <div class="bg-cyan-100">s</div>
        <!-- right sidebar -->
        <div class="bg-purple-100">d</div>

      </div>
    </div>
  </main>
</template>