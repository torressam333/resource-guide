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
      type: {
        String
      }
    }
  }
}
</script>

<style scoped>
button {
  background-color: transparent;
  border: none;
  color: indianred;
  cursor: pointer;
  font-family: inherit;
  font-weight: 700;
  padding: 0.75rem 1.5rem;
}

button:hover,
button:active {
  background-color: #f6f5f5;
  border: 1px solid indianred;
  border-radius: 20px;
  color: indianred;
  padding: 0.25rem 1rem;
}

.flat {
  background-color: transparent;
  color: #39737e;
  border: none;
}

.flat:hover,
.flat:active {
  background-color: #edd2ff;
}
</style>
