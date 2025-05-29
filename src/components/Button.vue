<script setup>
defineProps({
  name: {
    type: String,
    required: true,
  },

  btn_type: {
    type: String,
    required: true,
  },

  url: {
    type: String,
    required: true,
  },

  download: {
    type: Boolean,
    default: false,
  },

  filename: {
    type: String,
  },
});
</script>

<template>
  <a
    v-if="btn_type === 'primary'"
    class="text-md font-body py-2 px-5 bg-(--color-secondary) text-(--color-dominant)"
    v-bind:href="url"
    :download="download === true ? filename : undefined"
    >{{ name }}</a
  >
  <a
    v-else-if="btn_type === 'ghost'"
    class="btn-ghost text-md font-body py-2 px-5 outline-2 outline-(--color-secondary) text-(--text-body-primary)"
    v-bind:href="url"
    :download="download === true ? filename : undefined"
    >{{ name }}</a
  >
</template>

<style scoped>
.btn-ghost {
  outline-offset: -2px;
}
</style>
