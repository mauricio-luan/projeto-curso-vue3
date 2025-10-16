<template>
  <the-header title="RemeberMe" />
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
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Poppins', sans-serif;
}

body {
  margin: 0;
}
</style>
