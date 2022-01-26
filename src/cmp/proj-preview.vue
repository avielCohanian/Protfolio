<template>
  <article v-show="idx === page" class="proj-preview">
    <slot></slot>
  </article>
</template>

<script>
  export default {
    name: 'proj-preview',
    props: ['idx', 'page'],
  };
</script>

<style></style>
