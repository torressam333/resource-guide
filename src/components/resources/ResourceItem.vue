<template>
  <li>
    <div>
      <header>
        <h3>
          {{ title }}
        </h3>
        <button>Delete</button>
      </header>
    </div>
    <p>{{ description }}</p>
    <nav>
      <a :href="link" target="_blank">Go To Resource</a>
    </nav>
  </li>
</template>

<script>
export default {
  name: ['resource-item'],
  props: {
    description: {
      type: String,
      required: true
    },
    link: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    }
  }
}
</script>