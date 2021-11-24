<script lang="ts">
import { ref } from 'vue';

export default {
  setup() {
    const name = ref('zhang san');
    const age = ref(18);

    return {
      name,
      age,
    };
  }
};
</script>
<template>
  <div>{{ name }}</div>
  <div>{{ age }}</div>
</template>