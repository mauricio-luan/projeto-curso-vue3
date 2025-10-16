<template>
  <li>
    <header>
      <h3>{{ resources.title }}</h3>
    </header>
    <div>
      <p>{{ resources.description }}</p>
      <a :href="resources.link">{{ resources.link }}</a>
    </div>
    <button>Delete</button>
  </li>
</template>

<script>
export default {
  props: {
    resources: Object,
  },
}
</script>

<style scoped>
li {
  margin: auto;
  max-width: 40rem;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

h3 {
  font-size: 1.25rem;
  margin: 0.5rem 0;
}

p {
  margin: 0.5rem 0;
}

a {
  text-decoration: none;
  color: #ce5c00;
}

a:hover,
a:active {
  color: #c89300;
}
</style>
