<template>
  <ul>
    <resource-item
        v-for="resource in resources"
        :key="resource.id"
        :res-id="resource.id"
        :description="resource.description"
        :link="resource.link"
        :title="resource.title"
    >
    </resource-item>
  </ul>
</template>

<script>
import ResourceItem from "./ResourceItem";

export default {
  name: ['stored-resources'],
  components: {
    ResourceItem
  },
  inject: ['resources']
}
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0 auto;
  max-width: 40rem;
  padding: 0;
}
</style>
