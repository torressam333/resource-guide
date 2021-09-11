<template>
  <ul>
    <resource-item
        v-for="resource in storedResources"
        :key="resource.id"
        :description="resource.description"
        :link="resource.link"
        :title="resource.title"
    >
    </resource-item>
  </ul>
</template>

<script>
import ResourceItem from './components/resources/ResourceItem';

export default {
  components: {
    ResourceItem
  },
  data () {
    return {
      storedResources: [
        {
          id: 'vue-style-guide',
          title: 'Vue Style Guide',
          description: 'The official vue.js style guide',
          link: 'https://vuejs.org/v2/style-guide/'
        },
        {
          id: 'laravel-documentation',
          title: 'Laravel Documentation',
          description: 'The official Laravel Documentation',
          link: 'https://laravel.com/docs/8.x'
        }
      ]
    }
  }
}
</script>
