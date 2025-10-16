<template>
  <TheResource :resources="resources" />
</template>

<script>
import TheResource from './components/TheResource.vue'

export default {
  components: {
    TheResource,
  },
  data() {
    return {
      resources: [
        {
          id: 0,
          title: 'Study Vue',
          description: 'You may study a lot',
          link: 'http://vuejs.org',
        },
        {
          id: 1,
          title: 'Learn Java',
          description: 'This is difficult!',
          link: 'http://google.com',
        },
      ],
    }
  },
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
