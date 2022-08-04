<template>
  <p>Registration form here</p>
  <button @click="register">Register Me</button>
</template>

<script>
export default {
  props: ['id', 'event'],
  inject: ['GStore'], // <---- inject the global store
  methods: {
    register() {
      //assume success api call

      //set flash meessage
      // 'you success register for' + this.event.title

      this.GStore.flashMessage = 'you success register for' + this.event.title
      setTimeout(() => {
        this.GStore.flashMessage = ''
      }, 3000)

      this.$router.push({
        name: 'EventDetails',
        params: { id: this.event.id }
      })
    }
  }
}
</script>
