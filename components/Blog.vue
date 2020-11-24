<template>
  <div class="pt-10 pb-20">
    <div class="container mx-auto space-y-10">
      <div class="flex justify-between">
        <span>Blog</span>
        <nuxt-link class="flex items-center space-x-2" to="/projects"><span>Todos</span><img class="w-5" src="~assets/icons/arrow-right.svg" alt="todos" /></nuxt-link>
      </div>
      <div class="grid grid-cols-3 gap-10">
          <div class="space-y-3">
            <div class="h-64 bg-gray-300 animate-pulse"></div>
            <p>Hoje, às 15:08</p>
            <p class="text-2xl">Lorem ipsum dolor sit</p>
            <p>Consectetur adipiscing elit maecenas vulputate, magna ac molestie placerat.</p>
          </div>
          <div class="space-y-3">
            <div class="h-64 bg-gray-300 animate-pulse"></div>
            <p>Hoje, às 15:08</p>
            <p class="text-2xl">Lorem ipsum dolor sit</p>
            <p>Consectetur adipiscing elit maecenas vulputate, magna ac molestie placerat.</p>
          </div>
          <div class="space-y-3">
            <div class="h-64 bg-gray-300 animate-pulse"></div>
            <p>Hoje, às 15:08</p>
            <p class="text-2xl">Lorem ipsum dolor sit</p>
            <p>Consectetur adipiscing elit maecenas vulputate, magna ac molestie placerat.</p>
          </div>
      </div>
    </div>
  </div>
</template>