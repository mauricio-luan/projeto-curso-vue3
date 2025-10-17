<template>
  <base-card>
    <base-dialog v-if="isInputInvalid" title="Invalid input" @close="confirmError">
      <template #default>
        <p>Unfortunately, at leats one input value is invalid.</p>
        <p>Please check all input fields.</p>
      </template>
      <template #actions>
        <base-button @click="confirmError">Okay</base-button>
      </template>
    </base-dialog>

    <form @submit.prevent="resource">
      <div class="form-control">
        <label for="title">Title: </label>
        <input id="title" name="title" type="text" v-model="title" />
      </div>
      <div class="form-control">
        <label for="description">Description: </label>
        <textarea
          id="description"
          name="description"
          type="text"
          v-model="description"
          rows="3"
        ></textarea>
      </div>
      <div class="form-control">
        <label for="link">Link: </label>
        <input id="link" name="link" type="url" v-model="link" />
      </div>
      <base-button type="submit">Enviar</base-button>
    </form>
  </base-card>
</template>

<script>
export default {
  inject: ['addResource'],
  data() {
    return {
      title: '',
      description: '',
      link: '',
      isInputInvalid: false,
    }
  },
  emits: ['input-resource'],
  methods: {
    resource() {
      const title = this.title
      const description = this.description
      const link = this.link

      if (title.trim() === '' || description.trim() === '' || link.trim() === '') {
        this.isInputInvalid = true
        return
      }

      this.addResource(title, description, link)
    },
    confirmError() {
      this.isInputInvalid = false
    },
  },
}
</script>

<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}

.form-control {
  margin: 1rem 0;
}
</style>
