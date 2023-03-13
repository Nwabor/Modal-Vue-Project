<template>
  <h1>{{ title }}</h1>
  <p>Welcome....</p>
  <div v-if="showModal">
    <ModalPage theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign Up</a>
        <a href="#">Sign in</a>
      </template>
      <h1>Ninja Giveaway</h1>
      <p>Grap your ninja swag for half a price</p>
    </ModalPage>
    />
  </div>
  <hr />
  <button @click="toggleModal">Open Modal</button>

  <div v-if="showModal2">
    <ModalPage2 @closed="toggleModal2" theme2="sale2">
      <template v-slot:links2>
        <a href="#">Sign Up</a>
        <a href="#">Sign in</a>
      </template>
      <h1>Second Modal</h1>
      <p>Register here</p>
    </ModalPage2>
  </div>
  <button @click="toggleModal2">Open Modal2</button>
</template>

<script>
import ModalPage from "./components/ModalPage.vue";
import ModalPage2 from "./components/ModalPage2.vue";
export default {
  name: "App",
  components: { ModalPage, ModalPage2 },
  data() {
    return {
      title: "Home is sweet",
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

p {
  font-size: 20px;
}
</style>
