<template>
  <ul>
    <BaseListItem v-for="resource in resources" :key="resource.id" :resources="resource" />
  </ul>
</template>
<script>
import BaseListItem from './BaseListItem.vue'
export default {
  components: {
    BaseListItem,
  },
  props: {
    resources: Array,
  },
}
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>
