<template>
  <div class="container p-3">
    <h3 class="text-center">Lorem ipsum dolor sit amet.</h3>
    <div class="mt-3 bg-gray-200">
      <p v-for="(paragraph, index) in 10" :key="index" class="bg-gray-100 mb-2 p-3">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Blanditiis
        doloribus temporibus culpa perspiciatis possimus aliquam itaque ea
        repudiandae maxime ex? Molestiae vero ipsam ad atque harum blanditiis
        eveniet est nobis.
      </p>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "PostShow",
});
</script>
