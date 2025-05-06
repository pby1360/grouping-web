<!-- The exported code uses Tailwind CSS. Install Tailwind CSS in your dev environment to ensure all styles work. -->
<template>
  <div class="min-h-screen bg-gray-50">
    <!-- 상단 네비게이션 -->
    <HeaderLayout />

    <!-- 메인 컨텐츠 -->
    <main class="container mx-auto px-4 py-8">
      <RouterView />
    </main>

    <!-- 푸터 -->
    <FooterLayout />
  </div>
</template>

<script lang="ts" setup>
import { ref, computed } from 'vue'
import HeaderLayout from '@/components/layout/HeaderLayout.vue'
import FooterLayout from '@/components/layout/FooterLayout.vue'
import { RouterView } from 'vue-router'
</script>

<style scoped></style>
