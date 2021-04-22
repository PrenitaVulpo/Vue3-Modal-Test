<template>
  <img alt="Vue logo" src="./assets/logo.png">
	<h1>{{ tittle }}</h1>
	<p>Welcome...</p>
	<div v-if="showModal">
		<Modal :header="header" :text="text" theme="sale" @close="toggleModal">
			  <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Ninja Givaway!</h1>
      <p>Grab your ninja swag for half price!</p>
    </Modal>
	</div>
	<button @click="toggleModal">Open modal</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "Vue app",
      header: "sign up for the giveaway!",
      text: "Grab what you get!",
      showModal: false,
    };
  },
	methods: {
		toggleModal() {
			this.showModal = !this.showModal
		}
	}
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
	width: 100%;
	height: 100%;
}
</style>
