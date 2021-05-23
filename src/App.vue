<template>
  <h1>{{title}}</h1>
  <teleport to=".modals" v-if="showModal">
    <Modal  theme="sale" @close="toggleModal" >
      <template v-slot:links>
        <a href="#">Sign up</a>
        <a href="#">More info</a>
      </template>
      <h1>Ninja Giveaway</h1>
      <p>Get it now</p>

    </Modal>
  </teleport>
  <teleport to=".modals" v-if="showLoginModal">
    <Modal @close="toggleLoginModal">
      <template v-slot:links>
        <a href="#">Log in</a>
        <a href="#">Forgot Password</a>
      </template>
      <h1>Log in</h1>
      <br>
      <label for="email">User name</label>
      <input type="email" name="email" id="email">
      <br>
      <label for="password">Password</label>
      <input type="password" name="password" id="pw">
    </Modal>
  </teleport>
  <p>Welcome</p>
  <br>
  <button @click="toggleModal">Open Modal</button>
  <button @click="toggleLoginModal">Open Login Modal</button>
  <!-- <input type="text" ref="name">
  <button @click="handleClick">Click me</button> -->
</template>

<script>
import Modal from './components/Modal.vue'
export default {
  name: 'App',
  data() {
    return {
       title: 'My First Vue App!',
       header: 'Sign up for the Giveaway!',
       text: "Get it for half price",
       showModal: false,
       showLoginModal: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleLoginModal() {
      this.showLoginModal = !this.showLoginModal
    }
  },
  components: {Modal}
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
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
