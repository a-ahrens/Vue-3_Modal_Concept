<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Ninja Giveaway!</h1>
      <p>Grab your swag for half price!</p>
    </Modal>
  </teleport>
  
  <button @click="toggleModal">open modal</button>
  
  <div v-if="showModal2">
    <Modal theme="clearance" @close="toggleModal2">
      <h1>Clearance SALE!</h1>
    </Modal>
  </div>
  <button @click="toggleModal2">open modal 2</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My First Vue App :)",
      showModal: false,
      showModal2: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModal2() {
      this.showModal2 = !this.showModal2;
    },
  },
};
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

h1 {
  border-bottom: qpx solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}

.modal h1 {
  color: #03cfb4;
  border: none;
  padding: 0;
}
</style>
