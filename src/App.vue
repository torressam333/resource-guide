<template>
  <stored-resources
      :resources="storedResources"
  ></stored-resources>
</template>

<script>
import StoredResources from "./components/resources/StoredResources";

export default {
  components: {
    StoredResources,
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

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>
