<template>
  <base-card>
    <base-button @click="changeAba('the-resource')" :mode="styleTheResource">Resources</base-button>
    <base-button @click="changeAba('the-form')" :mode="styleTheForm">Form</base-button>
  </base-card>
  <keep-alive>
    <component :is="stateBackground"></component>
  </keep-alive>
</template>

<script>
import TheResource from '../TheResource.vue'
import TheForm from './TheForm.vue'

export default {
  components: {
    TheResource,
    TheForm,
  },
  data() {
    return {
      stateBackground: 'the-resource',
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
  methods: {
    addResource(title, description, link) {
      this.resources.unshift({
        id: new Date().toISOString(),
        title: title,
        description: description,
        link: link,
      })
      this.stateBackground = 'the-resource'
    },
    changeAba(aba) {
      this.stateBackground = aba
    },
  },
  computed: {
    styleTheResource() {
      return this.stateBackground === 'the-resource' ? null : 'flat'
    },
    styleTheForm() {
      return this.stateBackground === 'the-form' ? null : 'flat'
    },
  },
  provide() {
    return {
      resources: this.resources,
      addResource: this.addResource,
    }
  },
}
</script>
