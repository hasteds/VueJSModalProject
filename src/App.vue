<template>
  <h1>{{  title }}</h1>>
  <p>Welcome, click bellow to open modal</p>

  <div v-if="showModal">
    <Modal theme="sale" @close="openModal">
      <template v-slot:links>
        <a href="https:/www.bug.hr">Bug.hr</a>
        <a href="https:/www.facebook.com">Facebook.com</a>
      </template>
      <h1>Modal 01</h1>
      <p>This is modal text area</p>
    </Modal>
  </div>

  <div v-if="showModal2">
    <Modal theme="normal" @close="openModal2">
      <template v-slot:sometext>
        <h5>Modal 2 </h5>
        <p>This is text are of second modal</p>
      </template>
    </Modal>
  </div>

  <br>
  <br>
  <button @click="openModal">Open Modal</button>
  <button @click="openModal2">Open alternative modal</button>
  
</template>

<script>
import Modal from './components/Modal.vue'; 

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: 'My first Vue application',
      header: 'Sign up for the giveaway',
      text: 'Oh my gawd what is this long ass text doing here',
      showModal: false,
      showModal2: false
    }
  },
  methods: {
    openModal() {
      this.showModal = !this.showModal
    },
    openModal2() {
      this.showModal2 = !this.showModal2
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
