<template>
  <button
      :type="type"
      :class="mode"
  >
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: {
    type: {
      required: false
    },
    mode: {
      type: String
    }
  }
}
</script>

<style scoped>
.active {
  background-color: #3071a4;
  border-radius: 20px;
  color: #fff;
  border: none;
}

button {
  background-color: transparent;
  border: none;
  color: indianred;
  cursor: pointer;
  font-family: inherit;
  font-weight: 700;
  padding: 0.75rem 1.5rem;
}

.flat {
  background-color: transparent;
  color: #3071a4;
  border: none;
}

</style>
