<script setup lang="ts"></script>

<template>
  <header class="bg-white shadow-sm sticky top-0 z-50">
    <div class="container mx-auto px-4 py-3 flex items-center justify-between">
      <div class="flex items-center">
        <di class="text-2xl font-bold text-blue-600"><a href="/">Grouping</a></di>
      </div>
      <nav class="hidden md:flex items-center space-x-6">
        <a href="/about" class="text-gray-700 hover:text-blue-600 font-medium">서비스 소개</a>
        <a href="/guide" class="text-gray-700 hover:text-blue-600 font-medium">이용 가이드</a>
        <button
          class="bg-blue-600 text-white px-6 py-2 rounded-lg hover:bg-blue-700 transition !rounded-button whitespace-nowrap cursor-pointer"
          @click="$router.push('/sign-in')"
        >
          로그인
        </button>
      </nav>
      <button class="md:hidden text-gray-700">
        <i class="fas fa-bars text-2xl"></i>
      </button>
    </div>
  </header>
</template>
