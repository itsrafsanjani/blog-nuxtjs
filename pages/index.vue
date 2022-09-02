<template>
  <div class="min-h-screen flex justify-center items-center">
    <div>
      <h1 class="text-5xl">Blog NuxtJS</h1>

      <div class="mt-8 flex justify-center items-center">
        <NuxtLink
          :to="{ name: 'posts' }"
          class="mx-2 underline hover:no-underline"
          >Posts</NuxtLink
        >
        <NuxtLink
          :to="{ name: 'register' }"
          class="mx-2 underline hover:no-underline"
          >Register</NuxtLink
        >
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "IndexPage",
});
</script>
