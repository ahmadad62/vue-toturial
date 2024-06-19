<template>
  <h1>{{ title }}</h1>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @close="changeModal">
      <h1>OpenCode give away!</h1>
      <p>Grab a course for free!</p>
      <template v-slot:links>
        <a href="#">Sign up</a>
        <a href="#">More Info</a>
      </template>
    </Modal>
  </teleport>
  <teleport to=".modals" v-if="showModalTwo">
    <Modal theme="" @close="changeModalTwo">
      <h1>Sign for news!</h1>
      <p>don't lose any!</p>
    </Modal>
  </teleport>
  <p>Welcome to our website</p>
  <button @click.alt="changeModal">Show Modal(alt)</button>
  <button @click="changeModalTwo">Show Modal</button>

</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: "this is a test app",
      showModal: false,
      showModalTwo: false,
    }
  },
  methods: {
    changeModal() {
      this.showModal = !this.showModal
    },
    changeModalTwo() {
      this.showModalTwo = !this.showModalTwo
    }
  },
}
</script>

<style>
#app, .modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  color: red
}
</style>
