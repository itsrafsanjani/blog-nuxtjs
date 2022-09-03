<template>
  <div class="container p-3">
    <h3 class="text-center">Posts</h3>
    <ul class="mt-3">
      <li
        v-for="(post, index) in 10"
        :key="index"
        class="mb-3 p-3 rounded text-white bg-indigo-400"
      >
        <NuxtLink :to="{ name: 'posts-slug', params: { slug: index } }">
          <h1 class="text-xl mb-2">Lorem ipsum dolor sit amet.</h1>
          <p class="truncate">
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ea, nobis
            voluptatibus? Illum, suscipit. Rerum aspernatur soluta
            necessitatibus voluptate quasi error similique nihil voluptatem
            provident minima, inventore molestiae ipsam eum illum.
          </p>
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "PostIndex",
});
</script>
