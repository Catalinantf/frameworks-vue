<template>
  <v-img :src="character.image" class="mx-auto" max-width="500"></v-img>
</template>

<script>
export default {
  props: {
    character: { type: Object },
  },
  data() {
    return { show: false };
  },
};
</script>
