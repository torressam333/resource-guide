<template>
  <base-header title="Software Dev Resources"></base-header>
  <root-resource></root-resource>
</template>

<script>
import BaseHeader from "./components/layouts/BaseHeader";
import RootResource from "./components/resources/RootResource";

export default {
  components: {
    BaseHeader,
    RootResource,
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

*, *:before, *:after {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>
