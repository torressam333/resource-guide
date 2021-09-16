<template>
  <base-card>
    <base-button
        @click="setSelectedTab('stored-resources')"
        :mode="isStoredSelected"
    >Stored Resources</base-button>
    <base-button
        @click="setSelectedTab('add-resource')"
        :mode="isAddSelected"
    >Resource Form</base-button>
  </base-card>
  <!--keep alive caches our tabbed components
    See: https://vuejs.org/v2/guide/components-dynamic-async.html
    -->
  <keep-alive>
    <component :is="selectedTab"></component>
  </keep-alive>
</template>

<script>
import AddResource from './AddResource';
import BaseCard from "../UI/BaseCard";
import BaseButton from "../UI/BaseButton";
import StoredResources from "./StoredResources";

export default {
  components: {AddResource, BaseButton, BaseCard, StoredResources},
  data () {
    return {
      selectedTab: 'stored-resources',
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
  },
  provide () {
    return {
      resources: this.storedResources
    }
  },
  methods: {
    setSelectedTab (tab) {
      this.selectedTab = tab;
    }
  },
  computed: {
    isStoredSelected () {
      return this.selectedTab === 'stored-resources' ? 'active' : 'flat';
    },
    isAddSelected () {
      return this.selectedTab === 'add-resource' ? 'active' : 'flat';
    }
  }
}
</script>