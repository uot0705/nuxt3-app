<script setup lang="ts">
const pages = ["2024-03-23", "2024-03-30"];
</script>
<template>
  <div>
    <h1>ページ一覧</h1>
    <ul>
      <!-- ページリンクを動的に表示 -->
      <li v-for="page in pages" :key="page">
        <nuxt-link :to="`/study-notes/${page}`">{{ page }}</nuxt-link>
      </li>
    </ul>
  </div>
</template>
